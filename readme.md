# Console Symbol Registry

This repository contains symbol mappings and NID references for PlayStation 4 (Gen4) and PlayStation 5 (Gen5), collected for research and documentation purposes.
Console entries are categorized by generation.

No proprietary SDK material, firmware content, or encryption keys are included.

## Format

`NID  Alias  ExportName  Generation`

- **NID**: String identifier used by the runtime loader
- **Alias**: Internal/implementation entrypoint name used for indexing
- **ExportName**: Conventional public-facing label (often `sce*`) when known
- **Generation**: `Gen4`, `Gen5`, or `Gen4, Gen5`

## Sample

```csharp
[Flags]
public enum Generation
{
    None = 0,
    Gen4 = 1,
    Gen5 = 2
}

[SysAbiExport(Nid = "Up36PTk687E", ExportName = "sceVideoOutOpen", Target = Generation.Gen4 | Generation.Gen5)]
public static int VideoOutOpen(CpuContext ctx) { ... }
```

### Credits

Portions of the data were derived from publicly available open-source emulator projects, including [Kyty](https://github.com/InoriRus/Kyty), and reorganized for clarity and indexing.