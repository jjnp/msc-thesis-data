# README
This contains the raw data of my master's thesis experiments.

It should be understood in conjunction with the code that was produced.
From a format perspective both .csv and .dump are used.
CSV should be self-explanatory, but the .dump needs some explaining.
It is a raw binary serialization of 'python data, and thus has to be read using python.
As it has been serialized with `pickle` that library should also be used to read the data.

e.g.

```python
import pickle
with open('./7_osmotic_base/raw_data/osmotic_basic_openfaas_scaling.dump', 'rb') as f:
    data = pickle.load(f)
```

While I wasn't sure if this makes sense, since it is a more proprietary format than CSV, I decided to use it for a number of reasons:
 - it groups information together semantically in a clearer way than a CSV does
 - because the data is represented by pandas dataframes it can be written to csv easily anyways if there is a need
 - it allows us to integrate metadata more clearly
 - it binds the data to the simulator, since it uses the same data types. This makes sense since without understanding of the simulator a full understanding is not possibile anyways

### Download
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.6509857.svg)](https://doi.org/10.5281/zenodo.6509857)
Files are available via zenodo, since GitHub does not allow for sufficiently large file uploads.
They are group per experiment so that you do not need to download them all if you only care about a single one.
Find it on Zenodo [https://zenodo.org/record/6509857](here).


## Experiments and data download link

#### 1: Initial Experiments
The initial evaluation with load balancers either as round-robin or our least-response-time. Distribution is either on all nodes or centralized on a single one

#### 2: Least Response Time Implementation Variants
Evaluation of different implementation variants of our least response time. Particularly focused on different implementations of underlying weighted round robin

#### 3: Load Balancer Parametrizatino
Test about the weight range, weight mapping, and update frequency parameters in a variety of simulated scenarios.

#### 4: Load Balancer Resource Usage
Experiments on a real test-bed, evaluating the resource consumption of our least response time evaluation based on an adapted version of traefik.

#### 5: Load Balancer Scaling
Tests about the effect load balancer scale has on system performance.

#### 6: Osmotic Base Evaluatino
Basic evaluation of our osmotic scaling and scheduling approach.

#### 7: Osmotic Optimization Aggressiveness
Tests about the effect of scaling aggressiveness on load balancer scale and thus system performance. Scaling is realized via different upscaling pressure thresholds.

#### 8: Osmotic Dynamic Adaptation
Test whether the osmotic scaling and scheduling approach can adapt to changing system conditions with moving request origins as designed.


