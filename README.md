# 🧬 Pokémon Stat Generation with Type-Aware Variational Autoencoder (VAE)

This project, developed for the **COSC5437 Deep Learning course**, focuses on generating new Pokémon stat profiles using a **Variational Autoencoder (VAE)** while incorporating Pokémon typing (`Type 1` and `Type 2`). To assess the quality of the generated Pokémon, a simple **battle simulation** is used to compare them with real Pokémon from the dataset.

---

## 🎯 Objectives

- Train a VAE to learn latent representations of Pokémon stats and types.
- Generate realistic Pokémon stat profiles conditioned on type information.
- Simulate 1-on-1 battles between generated and real Pokémon using simplified battle rules.
- Evaluate generation quality using win/loss statistics and radar visualizations.

---

## 📊 Dataset

- **Source**: [Kaggle Pokémon Dataset](https://www.kaggle.com/abcsds/pokemon)
- **Features Used**:
  - Stats: `HP`, `Attack`, `Defense`, `Sp. Atk`, `Sp. Def`, `Speed`
  - Types: `Type 1`, `Type 2` (missing Type 2 values filled as `"None"`)

---

## 🧠 Model: Variational Autoencoder (VAE)

- **Input**: Concatenation of normalized stats + one-hot encoded types
- **Latent Space**: 2D latent vector learned through reparameterization
- **Loss Function**:
  - Mean Squared Error (MSE) for reconstruction
  - KL Divergence for regularization
- **Output**: Reconstructed features representing new Pokémon

---

## ⚔️ Battle Simulation

Each generated Pokémon is matched against a random real Pokémon. The outcome is determined by this rule:

score = (Attack × type_multiplier) − opponent's Defense


- A simplified type-effectiveness chart is used (e.g., Fire > Grass, Water > Fire).
- Each battle results in a **Win**, **Loss**, or **Draw** for the generated Pokémon.
- Simulation is repeated over 100 battles to assess generation quality.

---

## 📈 Results

- ✅ **Training loss** converges over epochs
- ✅ **Radar plots** visually confirm stat realism
- ✅ **Battle outcomes**:
  - Balanced win/loss rate for generated Pokémon indicates success
  - Outliers may point to overpowered or underpowered stat generations

---

## 🚀 How to Run (Google Colab Recommended)

1. Clone this repository:
   ```bash
   git clone [https://github.com/Annas-Furquan-Pasha/Pokemon-Stat-Generation-using-VAE.git](https://github.com/Annas-Furquan-Pasha/Pokemon-Stat-Generation-using-VAE)
   cd Pokemon-Stat-Generation-using-VAE
```
