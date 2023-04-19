# Baselines for the UniMorph-SIGMORPHONS shared task 0 - 2023

### Non-neural

The non-neural baseline is based on the [non-neural baseline](https://github.com/sigmorphon2020/task0-baselines/tree/master/nonneural) designed for the 2020 shared task.

To run on the dev set
```bash
python nonneural.py
```

add flag `-t` to on the test set, and `-h` for help on other options.

### Neural

The neural baseline is an input-invariant transformer by [Wu and Cotterell (2019)](https://arxiv.org/abs/2005.10213). 
It can be found [here](https://github.com/omagolda/neural-transducer/tree/master/example/sigmorphon2023-shared-tasks).