# 🧠 Minecraft Redstone Neural Network (MNIST Digit Recognizer)

A fully functional Convolutional Neural Network built inside **Vanilla Minecraft** using Redstone. This machine recognizes handwritten digits (0-9) drawn on a 28x28 input board.

**No Mods. No Command Blocks. Pure Binary Arithmetic.**

## 🚀 Overview

This project bridges the gap between high-level Deep Learning concepts and low-level digital logic. The model was trained in Python (TensorFlow) and then physically constructed block-by-block in Minecraft to perform inference using binary adders and comparators.

### ⚙️ Technical Specifications
* **Input:** 28x28 Drawing Board (784 bits).
* **Architecture:** Dense Neural Network (Input $\to$ Hidden $\to$ Output).
* **Precision:** Hybrid Integer Quantization.
    * *Hidden Layer:* 4-bit Signed Weights ($\pm 7$) using Two's Complement.
    * *Output Layer:* 8-bit Signed Weights ($\pm 127$) using **16-bit Signed Adders**.
* **Activation Function:** ReLU (Rectified Linear Unit) implemented via signal cut-off.
* **Output Logic:** Custom **Argmax Sequence** (Sequential Comparator) & ID Register to decode binary probability into a decimal display.
* **Clock Speed:** Optimized repeater timings for sequential processing.

## 🛠️ How It Works

### 1. Training (Python)
The logic begins in `train.py`. Since Redstone cannot handle floating-point numbers, the model is trained with specific constraints:
* **Integer Quantization:** Weights are clamped to specific integer ranges.
* **Data Thresholding:** MNIST data is converted to binary (0/1) to match the ON/OFF nature of Minecraft lamps.

### 2. The Physical Build (Minecraft)
The machine uses **Vanilla Redstone Mechanics**.
* **Calculations:** Done using cascaded binary adders.
* **Negative Numbers:** Handled using Two's Complement logic (e.g., -1 is represented as `1111`).
* **Max Finding:** A sequential comparator loops through the 10 output neurons to find the highest score and locks the winner's ID into memory.

## 📂 Repository Structure

* `train.py` - The TensorFlow script for training and quantizing the model.
* `world_download/` - The Minecraft world save file.

## 🙌 Credits & Inspiration

This project stands on the shoulders of the technical Minecraft community:

* **Mattbatwings:** Heavily inspired by his video *"I Made an AI with just Redstone"*.
* **Aminotreal:** Design used for the compact Binary Adders.
* **Shosancold:** Design logic used for the Binary Comparators.
* **Tools:** Built using **WorldEdit** and **Litematica** for construction efficiency.

---
*Built by Aryathama*
