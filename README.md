# Personality Analyzer

This project contains the code and models developed for analyzing and predicting personality traits from text. It is part of my diploma work and utilizes transformer-based models to predict the **Big Five personality traits** (OCEAN: Openness, Conscientiousness, Extraversion, Agreeableness, Neuroticism) from textual data.

## Usage

1. Run all cells until **Train** section.
2. Run code under **Save/load model** section.
3. Call `load_model_only(model, 'model/personality.pth')` function.
4. Call `predict` function with your text as an argument to predict personality traits.

### Training the Model

1. **Train**:
   You can train the model by running whole Jupyter notebook, including **Train** section.

2. **Saving the model**:
   Run cells under "Save/load model" header.

### Input Format

The model expects the following data format in a CSV file:

- **Text column**: The second column in the CSV file should contain the text input (e.g., conversation or message).
- **User ID column**: The third column should contain unique identifier of user.
- **Personality trait columns**: The next columns should contain the **OCEAN** traits scores for each text entry.

### Model Details

- **Model Type**: Custom model based on distilbert, use attention pooling and multi-layer perceptron.
- **Preprocessing**: Features extraction, z-score normalization for features.
- **Output**: The model outputs a set of **30 personality facets** (Each trait in OCEAN has 6 facets).

