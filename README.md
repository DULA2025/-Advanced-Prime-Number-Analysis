# Advanced Prime Number Analysis

This Python script performs an in-depth analysis of prime numbers up to a specified limit (10^10 by default), focusing on twin primes, prime distribution modulo 6, and prime gaps. It's designed to be memory-efficient and resumable.

## Features

1. **Prime Generation**
   - Uses SymPy's `primerange` for efficient prime number generation
   - Processes numbers in chunks to manage memory usage
   - Saves progress to disk for resuming interrupted runs

2. **Analysis Categories**
   - Twin primes (pairs differing by 2)
   - Primes modulo 6 (class 1 and class 5)
   - Prime gaps of 8, 10, 12, and 14

3. **Statistical Analysis**
   - Compares empirical vs theoretical twin prime density
   - Performs chi-square test on prime distribution
   - Visualizes gap frequencies

## How It Works

### Main Functions

1. `generate_primes_in_chunk(start, end)`
   - Generates prime numbers in a specified range using a memory-efficient generator

2. `compute_primes_in_chunks(limit, chunk_size, sub_chunk_size)`
   - Breaks the computation into manageable chunks
   - Processes sub-chunks within each chunk
   - Saves progress to pickle files
   - Collects:
     - All primes
     - Twin primes
     - Primes ≡ 1 (mod 6)
     - Primes ≡ 5 (mod 6)
     - Prime pairs with gaps 8, 10, 12, 14

3. `advanced_prime_analysis(limit)`
   - Main function that:
     - Resumes from saved progress if available
     - Computes prime statistics
     - Generates analysis and visualization
     - Performs density calculations using Hardy-Littlewood constant

### Output

- **Density Analysis**
  - Empirical vs theoretical twin prime counts
  - Ratio comparison

- **Distribution Analysis**
  - Counts of primes in classes 1 and 5 (mod 6)
  - Chi-square test for equal distribution

- **Gap Analysis**
  - Counts of prime pairs for each gap size
  - Visualization plot

## Usage

```python
# Set your desired limit
limit = 10000000000  # 10^10

# Run the analysis
advanced_prime_analysis(limit)
