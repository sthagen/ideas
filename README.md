# Faster CPython Ideas

Discussion and work tracker for Faster CPython project.

New ideas should be created as new [issues](https://github.com/faster-cpython/ideas/issues/new/choose).  It is ok if the idea is not fully formed -- we treat them as discussions to arrive at something actionable.  (We had previously used discussions for this, but that is now deprecated).

The [CPython issue tracker](https://github.com/python/cpython/issues) should be used for actual work-in-progress. 

Some links to presentations and other preliminary documentation:

- [Guido's slides at the 2021 Python Language Summit](FasterCPythonDark.pdf)
- [Mark's slides explaining Tiers of Execution](https://docs.google.com/presentation/d/1_cvQUwO2WWsaySyCmIy9nj9by4JKnkbiPCqtluLP3Mg)
- [PEP 659](https://peps.python.org/pep-0659/)

## Published Results

<!-- START table -->
## linux x86_64 (linux)
| date | fork | ref | version | hash | vs. 3.10.4: | vs. 3.11.0: | vs. base: |
| --- | --- | --- | --- | --- | ---: | ---: | ---: |
| [2023-04-01](results/bm-20230401-3.12.0a6%2B-06249ec) | python | main | 3.12.0a6+ | 06249ec | [1.29x faster](results/bm-20230401-3.12.0a6%2B-06249ec/bm-20230401-linux-x86_64-python-main-3.12.0a6%2B-06249ec-vs-3.10.4.md) | [1.03x faster](results/bm-20230401-3.12.0a6%2B-06249ec/bm-20230401-linux-x86_64-python-main-3.12.0a6%2B-06249ec-vs-3.11.0.md) |  |
| [2023-03-26](results/bm-20230326-3.12.0a6%2B-2cdc518) | python | 2cdc5189a6 | 3.12.0a6+ | 2cdc518 | [1.30x faster](results/bm-20230326-3.12.0a6%2B-2cdc518/bm-20230326-linux-x86_64-python-2cdc5189a6bc3157fddd-3.12.0a6%2B-2cdc518-vs-3.10.4.md) | [1.03x faster](results/bm-20230326-3.12.0a6%2B-2cdc518/bm-20230326-linux-x86_64-python-2cdc5189a6bc3157fddd-3.12.0a6%2B-2cdc518-vs-3.11.0.md) |  |
| [2023-03-25](results/bm-20230325-3.12.0a6%2B-662c16c) | faster-cpython | pep_669 | 3.12.0a6+ | 662c16c | [1.32x faster](results/bm-20230325-3.12.0a6%2B-662c16c/bm-20230325-linux-x86_64-faster%252dcpython-pep_669-3.12.0a6%2B-662c16c-vs-3.10.4.md) | [1.05x faster](results/bm-20230325-3.12.0a6%2B-662c16c/bm-20230325-linux-x86_64-faster%252dcpython-pep_669-3.12.0a6%2B-662c16c-vs-3.11.0.md) | [1.02x faster](results/bm-20230325-3.12.0a6%2B-662c16c/bm-20230325-linux-x86_64-faster%252dcpython-pep_669-3.12.0a6%2B-662c16c-vs-base.md) |
| [2022-10-24](results/bm-20221024-3.11.0-deaf509) | python | deaf509e8f | 3.11.0 | deaf509 | [1.25x faster](results/bm-20221024-3.11.0-deaf509/bm-20221024-linux-x86_64-python-deaf509e8fc6e0363bd6-3.11.0-deaf509-vs-3.10.4.md) |  |  |
| [2022-03-23](results/bm-20220323-3.10.4-9d38120) | python | 9d38120e33 | 3.10.4 | 9d38120 |  | [1.27x slower](results/bm-20220323-3.10.4-9d38120/bm-20220323-linux-x86_64-python-9d38120e335357a3b294-3.10.4-9d38120-vs-3.11.0.md) |  |

## linux x86_64 (pythonperf2)
| date | fork | ref | version | hash | vs. 3.10.4: | vs. 3.11.0: | vs. base: |
| --- | --- | --- | --- | --- | ---: | ---: | ---: |
| [2023-04-01](results/bm-20230401-3.12.0a6%2B-06249ec) | python | main | 3.12.0a6+ | 06249ec |  | [1.02x faster](results/bm-20230401-3.12.0a6%2B-06249ec/bm-20230401-pythonperf2-x86_64-python-main-3.12.0a6%2B-06249ec-vs-3.11.0.md) |  |
| [2023-03-25](results/bm-20230325-3.12.0a6%2B-30a306c) | python | main | 3.12.0a6+ | 30a306c |  | [1.03x faster](results/bm-20230325-3.12.0a6%2B-30a306c/bm-20230325-pythonperf2-x86_64-python-main-3.12.0a6%2B-30a306c-vs-3.11.0.md) |  |
| [2023-03-06](results/bm-20230306-3.12.0a5%2B-f533f21) | python | f533f216e6 | 3.12.0a5+ | f533f21 |  | [1.03x faster](results/bm-20230306-3.12.0a5%2B-f533f21/bm-20230306-pythonperf2-x86_64-python-f533f216e6aaba3f3663-3.12.0a5%2B-f533f21-vs-3.11.0.md) |  |
| [2022-10-24](results/bm-20221024-3.11.0-deaf509) | python | deaf509e8f | 3.11.0 | deaf509 |  |  |  |

## windows amd64 (pythonperf1)
| date | fork | ref | version | hash | vs. 3.10.4: | vs. 3.11.0: | vs. base: |
| --- | --- | --- | --- | --- | ---: | ---: | ---: |
| [2023-04-01](results/bm-20230401-3.12.0a6%2B-06249ec) | python | main | 3.12.0a6+ | 06249ec | [1.19x faster](results/bm-20230401-3.12.0a6%2B-06249ec/bm-20230401-pythonperf1-amd64-python-main-3.12.0a6%2B-06249ec-vs-3.10.4.md) | [1.07x faster](results/bm-20230401-3.12.0a6%2B-06249ec/bm-20230401-pythonperf1-amd64-python-main-3.12.0a6%2B-06249ec-vs-3.11.0.md) |  |
| [2023-03-25](results/bm-20230325-3.12.0a6%2B-30a306c) | python | main | 3.12.0a6+ | 30a306c | [1.21x faster](results/bm-20230325-3.12.0a6%2B-30a306c/bm-20230325-pythonperf1-amd64-python-main-3.12.0a6%2B-30a306c-vs-3.10.4.md) | [1.09x faster](results/bm-20230325-3.12.0a6%2B-30a306c/bm-20230325-pythonperf1-amd64-python-main-3.12.0a6%2B-30a306c-vs-3.11.0.md) |  |
| [2022-11-12](results/bm-20221112-3.12.0a1%2B-99972dc) | python | 99972dc745 | 3.12.0a1+ | 99972dc | [1.16x faster](results/bm-20221112-3.12.0a1%2B-99972dc/bm-20221112-pythonperf1-amd64-python-99972dc7450f1266e392-3.12.0a1%2B-99972dc-vs-3.10.4.md) | [1.05x faster](results/bm-20221112-3.12.0a1%2B-99972dc/bm-20221112-pythonperf1-amd64-python-99972dc7450f1266e392-3.12.0a1%2B-99972dc-vs-3.11.0.md) |  |
| [2022-11-11](results/bm-20221111-3.12.0a1%2B-3dd6ee2) | python | 3dd6ee2c00 | 3.12.0a1+ | 3dd6ee2 | [1.16x faster](results/bm-20221111-3.12.0a1%2B-3dd6ee2/bm-20221111-pythonperf1-amd64-python-3dd6ee2c0022cb49e5cb-3.12.0a1%2B-3dd6ee2-vs-3.10.4.md) | [1.05x faster](results/bm-20221111-3.12.0a1%2B-3dd6ee2/bm-20221111-pythonperf1-amd64-python-3dd6ee2c0022cb49e5cb-3.12.0a1%2B-3dd6ee2-vs-3.11.0.md) |  |
| [2022-11-09](results/bm-20221109-3.12.0a1%2B-c03e05c) | python | c03e05c2e7 | 3.12.0a1+ | c03e05c | [1.09x faster](results/bm-20221109-3.12.0a1%2B-c03e05c/bm-20221109-pythonperf1-amd64-python-c03e05c2e72f3ea5e797-3.12.0a1%2B-c03e05c-vs-3.10.4.md) | [1.01x slower](results/bm-20221109-3.12.0a1%2B-c03e05c/bm-20221109-pythonperf1-amd64-python-c03e05c2e72f3ea5e797-3.12.0a1%2B-c03e05c-vs-3.11.0.md) |  |
| [2022-11-04](results/bm-20221104-3.12.0a1%2B-044bcc1) | python | 044bcc1771 | 3.12.0a1+ | 044bcc1 | [1.11x faster](results/bm-20221104-3.12.0a1%2B-044bcc1/bm-20221104-pythonperf1-amd64-python-044bcc1771fe7e2f8eba-3.12.0a1%2B-044bcc1-vs-3.10.4.md) | [1.00x slower](results/bm-20221104-3.12.0a1%2B-044bcc1/bm-20221104-pythonperf1-amd64-python-044bcc1771fe7e2f8eba-3.12.0a1%2B-044bcc1-vs-3.11.0.md) |  |
| [2022-10-24](results/bm-20221024-3.11.0-deaf509) | python | deaf509e8f | 3.11.0 | deaf509 | [1.11x faster](results/bm-20221024-3.11.0-deaf509/bm-20221024-pythonperf1-amd64-python-deaf509e8fc6e0363bd6-3.11.0-deaf509-vs-3.10.4.md) |  |  |
| [2022-03-23](results/bm-20220323-3.10.4-9d38120) | python | 9d38120e33 | 3.10.4 | 9d38120 |  | [1.11x slower](results/bm-20220323-3.10.4-9d38120/bm-20220323-pythonperf1-amd64-python-9d38120e335357a3b294-3.10.4-9d38120-vs-3.11.0.md) |  |

## darwin arm64 (darwin)
| date | fork | ref | version | hash | vs. 3.10.4: | vs. 3.11.0: | vs. base: |
| --- | --- | --- | --- | --- | ---: | ---: | ---: |
| [2023-04-01](results/bm-20230401-3.12.0a6%2B-06249ec) | python | main | 3.12.0a6+ | 06249ec | [1.19x faster \*](results/bm-20230401-3.12.0a6%2B-06249ec/bm-20230401-darwin-arm64-python-main-3.12.0a6%2B-06249ec-vs-3.10.4.md) | [1.01x slower](results/bm-20230401-3.12.0a6%2B-06249ec/bm-20230401-darwin-arm64-python-main-3.12.0a6%2B-06249ec-vs-3.11.0.md) |  |
| [2023-03-25](results/bm-20230325-3.12.0a6%2B-30a306c) | python | main | 3.12.0a6+ | 30a306c | [1.19x faster \*](results/bm-20230325-3.12.0a6%2B-30a306c/bm-20230325-darwin-arm64-python-main-3.12.0a6%2B-30a306c-vs-3.10.4.md) | [1.02x slower](results/bm-20230325-3.12.0a6%2B-30a306c/bm-20230325-darwin-arm64-python-main-3.12.0a6%2B-30a306c-vs-3.11.0.md) |  |
| [2023-03-18](results/bm-20230318-3.12.0a6%2B-3adb23a) | python | main | 3.12.0a6+ | 3adb23a | [1.20x faster \*](results/bm-20230318-3.12.0a6%2B-3adb23a/bm-20230318-darwin-arm64-python-main-3.12.0a6%2B-3adb23a-vs-3.10.4.md) | [1.02x slower](results/bm-20230318-3.12.0a6%2B-3adb23a/bm-20230318-darwin-arm64-python-main-3.12.0a6%2B-3adb23a-vs-3.11.0.md) |  |
| [2022-10-24](results/bm-20221024-3.11.0-deaf509) | python | deaf509e8f | 3.11.0 | deaf509 | [1.22x faster \*](results/bm-20221024-3.11.0-deaf509/bm-20221024-darwin-arm64-python-deaf509e8fc6e0363bd6-3.11.0-deaf509-vs-3.10.4.md) |  |  |
| [2022-03-23](results/bm-20220323-3.10.4-9d38120) | python | v3.10.4 | 3.10.4 | 9d38120 |  | [1.22x slower \*](results/bm-20220323-3.10.4-9d38120/bm-20220323-darwin-arm64-python-v3.10.4-3.10.4-9d38120-vs-3.11.0.md) |  |


<!-- END table -->

There is also a [complete list of published results](results/README.md) (and [legacy results](benchmark-results/README.md)).
