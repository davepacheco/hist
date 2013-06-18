# hist: generate histograms

Generates DTrace-style power-of-two histograms from streams of numbers.  On
systems with jot(1) to generate random data, try:

    $ jot -r 10 | ~/Manta/MarlinTools/hist2/hist 
               value  ------------- Distribution ------------- count
                 0.5 |                                         0
                   1 |@@@@                                     1
                   2 |                                         0
                   4 |                                         0
                   8 |                                         0
                  16 |@@@@@@@@                                 2
                  32 |@@@@@@@@@@@@                             3
                  64 |@@@@@@@@@@@@@@@@                         4
                 128 |                                         0

Your example will differ because that "-r" generates random data.  For
deterministic, sequential data:

    $ seq 10 100 | ~/Manta/MarlinTools/hist2/hist 
               value  ------------- Distribution ------------- count
                   4 |                                         0
                   8 |@@@                                      6
                  16 |@@@@@@@                                  16
                  32 |@@@@@@@@@@@@@@                           32
                  64 |@@@@@@@@@@@@@@@@                         37
                 128 |                                         0
