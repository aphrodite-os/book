# Boot process

```dot process
digraph {
    rankdir = TB;
    nodesep = 0.1;
    size = "8,99";
    layout = dot;

    "Bootloader" -> "ArchBootEntry";

    "ArchBootEntry" -> "SyscallSetup" [ dir=both ];
    "ArchBootEntry" -> "IndepBootEntry";

    "IndepBootEntry" -> "MemMapGen" [ dir=both ];
    "IndepBootEntry" -> "MemMapAllocInit" [ dir=both ];

    "IndepBootEntry" -> "PreuserModLoad" [ dir=both ];

    "IndepBootEntry" -> "InitEnv";

    "InitEnv" -> "StorageFSMount" [ dir=both ];
    "InitEnv" -> "KernelFSMount" [ dir=both ];

    "InitEnv" -> "InitEnvMod" [ dir=both ];
    "InitEnvMod" -> "PreuserModLoad";

    "InitEnv" -> "RamLoader";

    node [ name="RamInit" shape=diamond ];

    "RamLoader" -> "RamInit";

    node [ name="UserInit" shape=oval ];

    "RamInit" -> "UserInit" [ dir=both ];
    "UserInit" -> "UserModLoad";
    "UserInit" -> "ProcessFSMount";

    node [ name="DiskInit" shape=diamond ];

    "RamInit" -> "DiskInit";

    "DiskInit" -> "SysInit";
}
```

The above diagram represents the boot process, where oval nodes represent kernel items, diamond nodes represent OS items, bidirectional arrows represent items that return to their caller, and directional arrows represent items that don't. 