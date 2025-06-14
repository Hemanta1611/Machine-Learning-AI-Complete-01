# ⚠️ Important Notice: TensorFlow 2.16+ and Keras 3 Compatibility Issues

If you're encountering any of the following issues:

- Errors with `tf.keras.layers.Layer`, `KerasLayer`, or `KerasTensor`
- Error: `'NoneType' object has no attribute 'items'`
- Loss and accuracy being 0 every second epoch
- `ValueError: Exception encountered when calling Sequential.call()`
- Other strange/unexpected behaviors in TensorFlow (TF)

And you're using **TensorFlow 2.16 or newer**, the reason is likely due to **Keras 3** being introduced in TF 2.16+, which breaks backward compatibility with older Keras APIs.

---

## ✅ Solutions

### Option 1: Use `tf_keras` (Best Option for Now)

TF 2.16+ supports a backwards-compatible version of Keras (Keras 2) under the module `tf_keras`. Here's how to use it:

1. **Install `tf_keras`** (if not already installed):
   ```bash
   pip install tf_keras
   ```

2. **Update your code:**
   - Replace all instances of:
     ```python
     import tensorflow.keras as keras
     ```
     with:
     ```python
     import tf_keras as keras
     ```

   - Replace **all** `tf.keras` references with just `keras`:
     ```python
     # Old:
     tf.keras.layers.Dense(...)
     # New:
     keras.layers.Dense(...)
     ```

   - Replace all imports that start with `tensorflow.keras` with `tf_keras`:
     ```python
     # Old:
     from tensorflow.keras.models import Sequential
     # New:
     from tf_keras.models import Sequential
     ```

   **Note:** Do **not** change anything else from `tf.` except `tf.keras`.

3. **If using helper scripts** (like `helper_functions.py`):
   - Make sure those files **also use `tf_keras`** instead of `tf.keras`.
   - Any helper (e.g., TensorBoard callback) using `tf.keras` will break your code if not updated.

---

### Option 2: Downgrade TensorFlow

If you don’t want to refactor code, another temporary fix is to downgrade TensorFlow to **2.15 or earlier**.

```bash
pip install tensorflow==2.15.0
```

---

## 🔗 Official Reference

More details here:  
👉 [Keras Backwards Compatibility (TF-Keras 2)](https://keras.io/getting_started/#tensorflow--keras-2-backwards-compatibility)

---

### Credit: moophers
