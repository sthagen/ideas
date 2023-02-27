
# Results vs. 3.10.4

- fork: python
- ref: main
- machine: linux-x86_64
- commit hash: 3eb12df
- commit date: 2023-02-11
- overall geometric mean: 1.29x faster \*

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20220323-linux-x86_64-python-v3.10.4-3.10.4-9d38120 | bm-20230211-linux-x86_64-python-main-3.12.0a5+-3eb12df |
|----------------|:------------------------------------------------------:|:------------------------------------------------------:|
| 2to3           | 332 ms                                                 | 250 ms: 1.33x faster                                   |
| chameleon      | 8.86 ms                                                | 6.58 ms: 1.34x faster                                  |
| docutils       | 3.18 sec                                               | 2.52 sec: 1.26x faster                                 |
| html5lib       | 85.8 ms                                                | 61.1 ms: 1.40x faster                                  |
| tornado_http   | 128 ms                                                 | 94.5 ms: 1.36x faster                                  |
| Geometric mean | (ref)                                                  | 1.34x faster                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20220323-linux-x86_64-python-v3.10.4-3.10.4-9d38120 | bm-20230211-linux-x86_64-python-main-3.12.0a5+-3eb12df |
|----------------|:------------------------------------------------------:|:------------------------------------------------------:|
| float          | 108 ms                                                 | 72.1 ms: 1.49x faster                                  |
| nbody          | 136 ms                                                 | 94.8 ms: 1.44x faster                                  |
| pidigits       | 190 ms                                                 | 193 ms: 1.01x slower                                   |
| Geometric mean | (ref)                                                  | 1.28x faster                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20220323-linux-x86_64-python-v3.10.4-3.10.4-9d38120 | bm-20230211-linux-x86_64-python-main-3.12.0a5+-3eb12df |
|----------------|:------------------------------------------------------:|:------------------------------------------------------:|
| regex_compile  | 174 ms                                                 | 129 ms: 1.35x faster                                   |
| regex_v8       | 25.0 ms                                                | 21.2 ms: 1.18x faster                                  |
| regex_dna      | 214 ms                                                 | 199 ms: 1.07x faster                                   |
| regex_effbot   | 3.21 ms                                                | 3.56 ms: 1.11x slower                                  |
| Geometric mean | (ref)                                                  | 1.11x faster                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20220323-linux-x86_64-python-v3.10.4-3.10.4-9d38120 | bm-20230211-linux-x86_64-python-main-3.12.0a5+-3eb12df |
|----------------------|:------------------------------------------------------:|:------------------------------------------------------:|
| pickle_pure_python   | 453 us                                                 | 288 us: 1.57x faster                                   |
| unpickle_pure_python | 297 us                                                 | 196 us: 1.51x faster                                   |
| json_dumps           | 13.5 ms                                                | 9.51 ms: 1.42x faster                                  |
| xml_etree_process    | 74.5 ms                                                | 55.2 ms: 1.35x faster                                  |
| json_loads           | 28.9 us                                                | 24.0 us: 1.20x faster                                  |
| xml_etree_generate   | 93.3 ms                                                | 80.5 ms: 1.16x faster                                  |
| pickle_list          | 4.50 us                                                | 4.05 us: 1.11x faster                                  |
| xml_etree_parse      | 163 ms                                                 | 148 ms: 1.10x faster                                   |
| xml_etree_iterparse  | 110 ms                                                 | 102 ms: 1.08x faster                                   |
| unpickle             | 14.3 us                                                | 13.4 us: 1.07x faster                                  |
| unpickle_list        | 4.99 us                                                | 4.95 us: 1.01x faster                                  |
| pickle               | 10.1 us                                                | 10.1 us: 1.01x faster                                  |
| pickle_dict          | 28.3 us                                                | 30.8 us: 1.09x slower                                  |
| Geometric mean       | (ref)                                                  | 1.18x faster                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20220323-linux-x86_64-python-v3.10.4-3.10.4-9d38120 | bm-20230211-linux-x86_64-python-main-3.12.0a5+-3eb12df |
|------------------------|:------------------------------------------------------:|:------------------------------------------------------:|
| python_startup         | 13.9 ms                                                | 8.92 ms: 1.56x faster                                  |
| python_startup_no_site | 5.76 ms                                                | 6.47 ms: 1.12x slower                                  |
| Geometric mean         | (ref)                                                  | 1.18x faster                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20220323-linux-x86_64-python-v3.10.4-3.10.4-9d38120 | bm-20230211-linux-x86_64-python-main-3.12.0a5+-3eb12df |
|-----------------|:------------------------------------------------------:|:------------------------------------------------------:|
| genshi_text     | 30.6 ms                                                | 20.6 ms: 1.49x faster                                  |
| mako            | 14.3 ms                                                | 9.95 ms: 1.43x faster                                  |
| django_template | 46.3 ms                                                | 33.3 ms: 1.39x faster                                  |
| genshi_xml      | 63.6 ms                                                | 46.6 ms: 1.36x faster                                  |
| Geometric mean  | (ref)                                                  | 1.42x faster                                           |

All benchmarks:
===============

| Benchmark               | bm-20220323-linux-x86_64-python-v3.10.4-3.10.4-9d38120 | bm-20230211-linux-x86_64-python-main-3.12.0a5+-3eb12df |
|-------------------------|:------------------------------------------------------:|:------------------------------------------------------:|
| deltablue               | 7.39 ms                                                | 3.11 ms: 2.38x faster                                  |
| logging_silent          | 173 ns                                                 | 91.0 ns: 1.90x faster                                  |
| scimark_sor             | 193 ms                                                 | 106 ms: 1.81x faster                                   |
| go                      | 226 ms                                                 | 133 ms: 1.70x faster                                   |
| pyflate                 | 675 ms                                                 | 398 ms: 1.70x faster                                   |
| richards                | 71.4 ms                                                | 42.3 ms: 1.69x faster                                  |
| raytrace                | 461 ms                                                 | 281 ms: 1.64x faster                                   |
| hexiom                  | 9.42 ms                                                | 5.91 ms: 1.59x faster                                  |
| scimark_monte_carlo     | 105 ms                                                 | 65.8 ms: 1.59x faster                                  |
| pickle_pure_python      | 453 us                                                 | 288 us: 1.57x faster                                   |
| chaos                   | 104 ms                                                 | 66.5 ms: 1.57x faster                                  |
| python_startup          | 13.9 ms                                                | 8.92 ms: 1.56x faster                                  |
| crypto_pyaes            | 118 ms                                                 | 75.6 ms: 1.56x faster                                  |
| unpickle_pure_python    | 297 us                                                 | 196 us: 1.51x faster                                   |
| spectral_norm           | 148 ms                                                 | 98.5 ms: 1.50x faster                                  |
| float                   | 108 ms                                                 | 72.1 ms: 1.49x faster                                  |
| genshi_text             | 30.6 ms                                                | 20.6 ms: 1.49x faster                                  |
| scimark_lu              | 158 ms                                                 | 108 ms: 1.46x faster                                   |
| deepcopy_memo           | 50.0 us                                                | 34.3 us: 1.46x faster                                  |
| nbody                   | 136 ms                                                 | 94.8 ms: 1.44x faster                                  |
| sqlglot_parse           | 2.04 ms                                                | 1.42 ms: 1.43x faster                                  |
| mako                    | 14.3 ms                                                | 9.95 ms: 1.43x faster                                  |
| json_dumps              | 13.5 ms                                                | 9.51 ms: 1.42x faster                                  |
| sqlglot_transpile       | 2.42 ms                                                | 1.71 ms: 1.41x faster                                  |
| pprint_pformat          | 1.97 sec                                               | 1.40 sec: 1.41x faster                                 |
| html5lib                | 85.8 ms                                                | 61.1 ms: 1.40x faster                                  |
| django_template         | 46.3 ms                                                | 33.3 ms: 1.39x faster                                  |
| logging_format          | 8.92 us                                                | 6.43 us: 1.39x faster                                  |
| pprint_safe_repr        | 943 ms                                                 | 684 ms: 1.38x faster                                   |
| pycparser               | 1.51 sec                                               | 1.10 sec: 1.38x faster                                 |
| async_tree_memoization  | 854 ms                                                 | 620 ms: 1.38x faster                                   |
| logging_simple          | 8.06 us                                                | 5.87 us: 1.37x faster                                  |
| async_tree_none         | 713 ms                                                 | 522 ms: 1.36x faster                                   |
| genshi_xml              | 63.6 ms                                                | 46.6 ms: 1.36x faster                                  |
| tornado_http            | 128 ms                                                 | 94.5 ms: 1.36x faster                                  |
| thrift                  | 1.03 ms                                                | 761 us: 1.36x faster                                   |
| unpack_sequence         | 59.5 ns                                                | 43.9 ns: 1.35x faster                                  |
| async_tree_io           | 1.78 sec                                               | 1.31 sec: 1.35x faster                                 |
| regex_compile           | 174 ms                                                 | 129 ms: 1.35x faster                                   |
| xml_etree_process       | 74.5 ms                                                | 55.2 ms: 1.35x faster                                  |
| chameleon               | 8.86 ms                                                | 6.58 ms: 1.34x faster                                  |
| aiohttp                 | 1.34 ms                                                | 1.01 ms: 1.33x faster                                  |
| 2to3                    | 332 ms                                                 | 250 ms: 1.33x faster                                   |
| scimark_fft             | 414 ms                                                 | 312 ms: 1.33x faster                                   |
| scimark_sparse_mat_mult | 5.48 ms                                                | 4.13 ms: 1.33x faster                                  |
| gunicorn                | 1.43 ms                                                | 1.09 ms: 1.32x faster                                  |
| fannkuch                | 477 ms                                                 | 363 ms: 1.32x faster                                   |
| deepcopy                | 429 us                                                 | 329 us: 1.30x faster                                   |
| sqlglot_normalize       | 135 ms                                                 | 104 ms: 1.29x faster                                   |
| sqlglot_optimize        | 65.3 ms                                                | 50.8 ms: 1.29x faster                                  |
| nqueens                 | 99.3 ms                                                | 77.6 ms: 1.28x faster                                  |
| docutils                | 3.18 sec                                               | 2.52 sec: 1.26x faster                                 |
| deepcopy_reduce         | 3.75 us                                                | 2.97 us: 1.26x faster                                  |
| async_tree_cpu_io_mixed | 949 ms                                                 | 755 ms: 1.26x faster                                   |
| coroutines              | 31.7 ms                                                | 25.2 ms: 1.25x faster                                  |
| sqlalchemy_declarative  | 165 ms                                                 | 137 ms: 1.21x faster                                   |
| sympy_integrate         | 23.9 ms                                                | 19.9 ms: 1.21x faster                                  |
| json_loads              | 28.9 us                                                | 24.0 us: 1.20x faster                                  |
| bench_thread_pool       | 943 us                                                 | 786 us: 1.20x faster                                   |
| dulwich_log             | 75.5 ms                                                | 63.1 ms: 1.20x faster                                  |
| sympy_str               | 324 ms                                                 | 273 ms: 1.19x faster                                   |
| regex_v8                | 25.0 ms                                                | 21.2 ms: 1.18x faster                                  |
| sympy_expand            | 537 ms                                                 | 459 ms: 1.17x faster                                   |
| sqlalchemy_imperative   | 21.0 ms                                                | 18.1 ms: 1.17x faster                                  |
| xml_etree_generate      | 93.3 ms                                                | 80.5 ms: 1.16x faster                                  |
| json                    | 5.35 ms                                                | 4.63 ms: 1.16x faster                                  |
| sympy_sum               | 183 ms                                                 | 159 ms: 1.15x faster                                   |
| mdp                     | 2.82 sec                                               | 2.47 sec: 1.14x faster                                 |
| pathlib                 | 20.0 ms                                                | 17.7 ms: 1.13x faster                                  |
| sqlite_synth            | 2.90 us                                                | 2.59 us: 1.12x faster                                  |
| pickle_list             | 4.50 us                                                | 4.05 us: 1.11x faster                                  |
| xml_etree_parse         | 163 ms                                                 | 148 ms: 1.10x faster                                   |
| meteor_contest          | 114 ms                                                 | 105 ms: 1.09x faster                                   |
| xml_etree_iterparse     | 110 ms                                                 | 102 ms: 1.08x faster                                   |
| regex_dna               | 214 ms                                                 | 199 ms: 1.07x faster                                   |
| unpickle                | 14.3 us                                                | 13.4 us: 1.07x faster                                  |
| telco                   | 6.68 ms                                                | 6.34 ms: 1.05x faster                                  |
| unpickle_list           | 4.99 us                                                | 4.95 us: 1.01x faster                                  |
| pickle                  | 10.1 us                                                | 10.1 us: 1.01x faster                                  |
| pidigits                | 190 ms                                                 | 193 ms: 1.01x slower                                   |
| generators              | 75.8 ms                                                | 77.5 ms: 1.02x slower                                  |
| pickle_dict             | 28.3 us                                                | 30.8 us: 1.09x slower                                  |
| regex_effbot            | 3.21 ms                                                | 3.56 ms: 1.11x slower                                  |
| python_startup_no_site  | 5.76 ms                                                | 6.47 ms: 1.12x slower                                  |
| coverage                | 75.3 ms                                                | 96.8 ms: 1.29x slower                                  |
| Geometric mean          | (ref)                                                  | 1.29x faster                                           |

Benchmark hidden because not significant (2): bench_mp_pool, async_generators
Ignored benchmarks (3) of public/results/bm-20220323-3.10.4-9d38120/bm-20220323-linux-x86_64-python-v3.10.4-3.10.4-9d38120.json: flaskblogging, mypy, pylint
Ignored benchmarks (5) of public/results/bm-20230211-3.12.0a5+-3eb12df/bm-20230211-linux-x86_64-python-main-3.12.0a5+-3eb12df.json: asyncio_tcp, create_gc_cycles, djangocms, gc_traversal, mypy2