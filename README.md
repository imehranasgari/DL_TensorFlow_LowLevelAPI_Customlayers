# Creating and Using Custom Layers in TensorFlow/Keras

## 1. Project Title

**Custom Layer Implementation with TensorFlow/Keras**

---

## 2. Problem Statement and Goal of Project

While Keras provides a wide range of built-in layers, certain use cases require **custom operations, parameters, or training logic**.
The goal of this project is to **design, implement, and integrate custom layers** into a Keras model while maintaining compatibility with the high-level training API.

---

## 3. Solution Approach

The notebook demonstrates a full workflow for custom layer creation:

1. **Subclassing `tf.keras.layers.Layer`** – Define a new layer class with a custom constructor (`__init__`), weight creation in `build()`, and forward pass logic in `call()`.
2. **Adding trainable parameters** – Use `self.add_weight()` for kernel, bias, and other trainable variables.
3. **Integrating custom regularizers and initializers** – Apply user-defined weight initialization and regularization logic.
4. **Using the custom layer in a model** – Integrate the layer into a Sequential or Functional API model.
5. **Training with standard Keras workflow** – Compile the model with an optimizer, loss, and metrics; then train and evaluate.

---

## 4. Technologies & Libraries

From the code:

* **TensorFlow** – Custom layer API, model integration, and training.
* **Keras (via TensorFlow)** – Model building, optimizers, compilation, and evaluation.
* **NumPy** – Data preparation.

---

## 5. Description about Dataset

**Not provided** – The notebook uses synthetic or preprocessed data for demonstrating the functionality of the custom layer.

---

## 6. Installation & Execution Guide

**Requirements:**

```bash
pip install tensorflow numpy
```

**Run the notebook:**

```bash
jupyter notebook custom_layers_me.ipynb
```

or in JupyterLab:

```bash
jupyter lab custom_layers_me.ipynb
```

Run all cells sequentially to follow the process from custom layer creation to training and evaluation.

---

## 7. Key Results / Performance

* Successfully implemented a **custom trainable Keras layer**.
* Verified the layer integrates seamlessly into the Keras `fit()` workflow.
* Demonstrated flexibility by adding custom initialization and regularization.

Example model integration:

```python
model = tf.keras.Sequential([
    CustomDenseLayer(units=64, activation="relu"),
    tf.keras.layers.Dense(1)
])
```

---

## 8. Screenshots / Sample Out

**Custom layer summary excerpt:**

```
Layer (type)                 Output Shape              Param #
=================================================================
custom_dense_layer (CustomDenseLayer) (None, 64)        576
...
```

---

## 9. Additional Learnings / Reflections

* Subclassing `tf.keras.layers.Layer` allows **full customization** of trainable parameters and forward-pass logic.
* Implementing `get_config()` ensures the layer is serializable and reusable.
* Custom layers can be combined with standard Keras layers in any architecture.
* Using built-in methods like `add_weight()` maintains compatibility with Keras optimizers and training loops.

> 💡 *Some interactive outputs (e.g., plots, widgets) may not display correctly on GitHub. If so, please view this notebook via [nbviewer.org](https://nbviewer.org) for full rendering.*

---

## 👤 Author

**Mehran Asgari**
**Email:** [imehranasgari@gmail.com](mailto:imehranasgari@gmail.com)
**GitHub:** [https://github.com/imehranasgari](https://github.com/imehranasgari)

---

## 📄 License

This project is licensed under the Apache 2.0 License – see the `LICENSE` file for details.

---
