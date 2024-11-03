

---

## Model Deployment and Saving

### Saving the Model
The trained models (both classifier and regressor) are saved using the `joblib` library. This allows for easy loading and use in future predictions without retraining the models.

- **Classifier Model**: Saved as `trained_classifier.pkl`
- **Regressor Model**: Saved as `trained_regressor.pkl`

To save your trained model, you can use the following code:

```python
import joblib

# Save classifier
joblib.dump(classifier_model, 'trained_classifier.pkl')

# Save regressor
joblib.dump(regressor_model, 'trained_regressor.pkl')
```

### Deploying the Model
The models are deployed using a Flask API, which serves the prediction functionality. The API allows users to send input data and receive predictions from both models.

1. **API Setup**: The API is defined in `app.py`. When run, it listens for incoming requests on the specified endpoint.
2. **Making Predictions**: Users can send a POST request to the `/predict` endpoint with the input data and specify the model type (`classifier` or `regressor`).

### Example Request
To make a prediction, send a JSON request as follows:
```json
{
    "input": [your_input_values_here],
    "model_type": "classifier"  // or "regressor"
}
```

The API responds with the prediction result, which can be easily integrated into applications or systems.

---
