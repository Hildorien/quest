IBM Quest Synthetic Data Generator
==================================

![build](https://github.com/halfvim/quest/workflows/build/badge.svg)

Modified from https://sourceforge.net/projects/ibmquestdatagen/.

## Build

Compile with
* *Microsoft Visual Studio* on Windows, or 
* *make* command on Linux/macOS.

## Usage

```
./gen seq|lit|tax [OPTIONS]
```

Options for subcommands are listed below.

```
./gen seq [OPTIONS]

Options:
  -ncust number_of_customers_in_000s (default: 100)
  -slen avg_trans_per_customer (default: 10)
  -tlen avg_items_per_transaction (default: 2.5)
  -nitems number_of_different_items_in_000s (default: 10)
  -rept repetition-level (default: 0)

  -seq.npats number_of_seq_patterns (default: 5000)
  -seq.patlen avg_length_of_maximal_pattern (default: 4)
  -seq.corr correlation_between_patterns (default: 0.25)
  -seq.conf avg_confidence_in_a_rule (default: 0.75)

  -lit.npats number_of_patterns (default: 25000)
  -lit.patlen avg_length_of_maximal_pattern (default: 1.25)
  -lit.corr correlation_between_patterns (default: 0.25)
  -lit.conf avg_confidence_in_a_rule (default: 0.75)

  -fname <filename> (write to filename.data and filename.pat)
  -ascii (Write data in ASCII format; default: False)
  -version (to print out version info)
```

```
./gen lit [OPTIONS]

Options:
  -ntrans number_of_transactions_in_000s (default: 1000)
  -tlen avg_items_per_transaction (default: 10)
  -nitems number_of_different_items_in_000s) (default: 100)

  -npats number_of_patterns (default: 10000)
  -patlen avg_length_of_maximal_pattern (default: 4)
  -corr correlation_between_patterns (default: 0.25)
  -conf avg_confidence_in_a_rule (default: 0.75)

  -fname <filename> (write to filename.data and filename.pat)
  -ascii (default: True)
  -randseed # (reset seed used generate to x-acts; must be negative)
  -version (to print out version info)
```

```
./gen tax [OPTIONS]

Options:
  -ntrans number_of_transactions_in_000s (default: 1000)
  -tlen avg_items_per_transaction (default: 10)
  -nitems number_of_different_items_in_000s (default: 100)
  -nroots number_of_roots (default: 250)
  -nlevels number_of_different_levels (default: 0)
  -fanout average_fanout (default: 5)
  -depth affects_average_depth_of_items_in_itemsets (default: 1)

  -npats number_of_patterns (default: 10000)
  -patlen avg_length_of_maximal_pattern (default: 4)
  -corr correlation_between_patterns (default: 0.25)
  -conf avg_confidence_in_a_rule (default: 0.75)

  -fname <filename> (write to filename.data and filename.pat)
  -ascii (Write data in ASCII format; default: True)
  -randseed # (reset seed used generate to x-acts; must be negative)
  -version (to print out version info)
```

## Usage Example

```
gen lit -ascii -ntrans 10 -tlen 3 -nitems 4 -fname output
```
10000 transactions will be produced involving an average of 3 items per transaction, drawn from 4000 total number of items. The output will be written to file output.data. 
