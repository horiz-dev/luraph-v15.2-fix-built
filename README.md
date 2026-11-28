# luraph-v15.2-deobf

A foundation for a Luraph v15.2 deobfuscator: code from `luraph-v15-deobf` with initial adjustments for v15.2.
Status and identified differences: [V15_2.md](V15_2.md). General project documentation: [CLAUDE.md](CLAUDE.md), [LURAPH.md](LURAPH.md).

## Running in GitHub Codespaces

```bash
./setup.sh                                 # builds deobf/bin/luau and deobf/bin/luau-ast (takes a few minutes)
python3 deobf/deob.py sample.luau --detect   # identify the obfuscator
python3 deobf/deob.py sample.luau --no-devirt --debug   # behavior trace + intermediate files in output/
```

`--debug` also saves `sample.chunk_<key>.luau` (the VM from `loadstring`), `sample.protos.json`, and `sample.deobf.luau` alongside the output.
The result is not yet readable source code: see “What doesn’t work” in V15_2.md.

## What’s needed for verification

A pair consisting of the original source and its obfuscated output (for example, `sample_src.luau` and `sample_fly_obf.luau`), so the output can be compared line by line.