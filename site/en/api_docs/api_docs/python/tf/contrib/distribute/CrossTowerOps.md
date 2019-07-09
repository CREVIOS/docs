

page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>


<!-- DO NOT EDIT! Automatically generated file. -->

# tf.contrib.distribute.CrossTowerOps

## Class `CrossTowerOps`





Defined in [`tensorflow/contrib/distribute/python/cross_tower_ops.py`](https://www.github.com/tensorflow/tensorflow/blob/r1.10/tensorflow/contrib/distribute/python/cross_tower_ops.py).

Base class for cross-tower reduction and broadcasting algorithms.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__()
```



<h3 id="batch_reduce"><code>batch_reduce</code></h3>

``` python
batch_reduce(
    aggregation,
    value_destination_pairs
)
```

Reduce PerDevice objects in a batch.

Reduce each first element in `value_destination_pairs` to each second
element which indicates the destinations.

#### Args:

* <b>`aggregation`</b>: Indicates how a variable will be aggregated. Accepted values
    are <a href="../../../tf/VariableAggregation#SUM"><code>tf.VariableAggregation.SUM</code></a>, <a href="../../../tf/VariableAggregation#MEAN"><code>tf.VariableAggregation.MEAN</code></a>.
* <b>`value_destination_pairs`</b>: a list or a tuple of tuples of PerDevice objects
    and destinations. If a destination is None, then the destinations
    are set to match the devices of the input PerDevice object.


#### Returns:

a list of Mirrored objects.


#### Raises:

* <b>`ValueError`</b>: if `value_destination_pairs` is not a list or a tuple of
    tuples of PerDevice objects and destinations

<h3 id="broadcast"><code>broadcast</code></h3>

``` python
broadcast(
    tensor,
    destinations
)
```

Broadcast the `tensor` to destinations.

#### Args:

* <b>`tensor`</b>: the tensor to broadcast.
* <b>`destinations`</b>: the broadcast destinations.


#### Returns:

a Mirrored object.

<h3 id="reduce"><code>reduce</code></h3>

``` python
reduce(
    aggregation,
    per_device_value,
    destinations=None
)
```

Reduce `per_device_value` to `destinations`.

It runs the reduction operation defined by `aggregation` and put the
result on `destinations`.

#### Args:

* <b>`aggregation`</b>: Indicates how a variable will be aggregated. Accepted values
    are <a href="../../../tf/VariableAggregation#SUM"><code>tf.VariableAggregation.SUM</code></a>, <a href="../../../tf/VariableAggregation#MEAN"><code>tf.VariableAggregation.MEAN</code></a>.
* <b>`per_device_value`</b>: a PerDevice object.
* <b>`destinations`</b>: the reduction destinations.


#### Returns:

a Mirrored object.


#### Raises:

* <b>`ValueError`</b>: if per_device_value is not a PerDevice object.


