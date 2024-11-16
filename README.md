# Executable generated from DCDatalog


The running commands look like the following:
```shell
./cc {arc.bin}
./sg {arc.bin}
./delivery {assbl.bin} {basic.bin}
./sssp {warc.bin} {start_vertex:int (opt)}
./pagerank {matrix.bin} {start_value:float (opt)}
```

Here the programs use 64 threads as default.

Here the input binary data format should satisfy the following requirements:

The first two uint32_t elements specify the number of vertex and edges; the following are just plain tuples with int32_t for nodes. In SSSP, we should use int32_t as weights, and in PageRank, we use float as weights.

For example, in arc.bin, it looks like
```
{#vert: uint32_t} {#edge: uint32_t}
{1_from: int32_t} {1_to: int32_t}
{2_from: int32_t} {2_to: int32_t}
{3_from: int32_t} {3_to: int32_t}
...
{n_from: int32_t} {n_to: int32_t}
```
where n = #edge.

And for warc.bin, the case is similar but with weights
```
{#vert: uint32_t} {#edge: uint32_t}
{1_from: int32_t} {1_to: int32_t} {1_weight: int32_t}
{2_from: int32_t} {2_to: int32_t} {2_weight: int32_t}
{3_from: int32_t} {3_to: int32_t} {3_weight: int32_t}
...
{n_from: int32_t} {n_to: int32_t} {n_weight: int32_t}
```

If have any questions, please contact <a href="mailto:wjcskqygj@gmail.com">me</a> through email.
