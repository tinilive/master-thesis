# Personality Analyzer

This project contains the code and models developed for analyzing and predicting personality traits from text. It is part of my diploma work and utilizes transformer-based models to predict the **Big Five personality traits** (OCEAN: Openness, Conscientiousness, Extraversion, Agreeableness, Neuroticism) from textual data.

## Usage

1. Run all cells until **Train** section.
2. Run code under **Save/load model** section.
3. Call `load_model_only(model, 'model/personality_5.pth')` function.
4. Call `calculate_traits_for_text` function with your text as an argument to predict personality traits.

### Training the Model

1. **Hyperparameters tuning**
   See second cell. It has following parameters:
   - `VOCAB_SIZE = 40000`: Number of unique tokens in the vocabulary.
   - `MAX_LEN = 512`: Maximum sequence length for input texts.
   - `BATCH_SIZE = 8`: Number of samples per training batch.
   - `EMBED_SIZE = 512`: Dimensionality of token and position embeddings.
   - `HIDDEN_SIZE = 512`: Size of the hidden layers in the transformer.
   - `NUM_HEADS = 16`: Number of attention heads in each encoder layer.
   - `NUM_LAYERS = 5`: Number of transformer encoder layers.
   - `DROPOUT = 0.1`: Dropout rate used for regularization.
   - `EPOCHS = 20`: Number of training epochs.
   - `OUTPUT_SIZE = 5`: Number of output values (one per personality trait).

2. **Train**:
   You can train the model by running whole Jupyter notebook, including **Train** section.

3. **Saving the model**:
   Run cells under "Save/load model" header.

### Input Format

The model expects the following data format in a CSV file:

- **Text column**: The second column in the CSV file should contain the text input (e.g., conversation or message).
- **Personality trait columns**: The next columns should contain the **OCEAN** traits scores for each text entry.

### Model Details

- **Model Type**: Transformer-based (Custom architecture with multiple layers, attention heads, etc.)
- **Preprocessing**: SentencePiece for tokenization, z-score normalization for personality trait scores.
- **Output**: The model outputs a set of **5 personality traits** (OCEAN).
