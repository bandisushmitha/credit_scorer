# DeFi Credit Scoring System

A machine learning-based credit scoring system for DeFi wallets using Aave V2 transaction data. This system analyzes wallet behavior patterns to assign credit scores between 0-1000, identifying reliable users and flagging risky or exploitative behavior.

## 🚀 Features

- **ML-Based Scoring**: Advanced machine learning model that analyzes transaction patterns
- **Real-time Processing**: Instant credit score calculation from transaction data
- **Risk Assessment**: Identifies bot-like, exploitative, or risky wallet behavior
- **User-Friendly Interface**: Clean, responsive web interface with dark theme
- **Transparent Methodology**: Clear explanation of scoring logic and feature engineering

## 📋 Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Architecture](#architecture)
- [Features Engineering](#features-engineering)
- [Scoring Methodology](#scoring-methodology)
- [API Reference](#api-reference)
- [File Structure](#file-structure)
- [Contributing](#contributing)
- [License](#license)

## 🛠️ Installation

### Prerequisites

- Python 3.8+
- Node.js (for web interface)
- Required Python packages (see `requirements.txt`)

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/defi-credit-scoring.git
   cd defi-credit-scoring
   ```

2. **Install Python dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Setup the web interface**
   ```bash
   # No additional setup needed for HTML/CSS interface
   # Simply open index.html in a web browser
   ```

## 🔧 Usage

### Command Line Interface

Generate credit scores from transaction data:

```bash
python score_generator.py --input user-transactions.json --output wallet_scores.json
```

### Web Interface

1. Open `index.html` in your web browser
2. Upload your transaction file (JSON or ZIP format)
3. Click "Process File" to generate scores
4. View results and analysis

### Supported File Formats

- **JSON**: Raw transaction data
- **ZIP**: Compressed transaction files
- **Maximum file size**: 100MB

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Data Input    │───▶│  Feature Eng.   │───▶│  ML Scoring     │
│ (Transactions)  │    │   Pipeline      │    │    Model        │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                                                        │
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Web Interface │◀───│  Score Output   │◀───│  Post-Process   │
│   (Frontend)    │    │   (0-1000)      │    │   & Validate    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### Processing Flow

1. **Data Ingestion**: Parse JSON transaction files
2. **Feature Engineering**: Extract wallet behavior patterns
3. **ML Scoring**: Apply trained model to generate scores
4. **Post-Processing**: Validate and normalize scores
5. **Output Generation**: Return structured results

## 🔍 Features Engineering

### Transaction-Based Features

- **Volume Metrics**
  - Total transaction volume
  - Average transaction size
  - Transaction frequency
  - Volume consistency over time

- **Behavior Patterns**
  - Deposit/withdrawal ratios
  - Borrowing patterns
  - Repayment consistency
  - Liquidation history

- **Risk Indicators**
  - Bot-like behavior detection
  - Unusual transaction patterns
  - Rapid-fire transactions
  - Exploitation attempts

### Temporal Features

- **Time-Series Analysis**
  - Transaction timing patterns
  - Seasonal behavior
  - Activity consistency
  - Peak usage times

- **Lifecycle Metrics**
  - Wallet age
  - Activity duration
  - Dormancy periods
  - Reactivation patterns

## 📊 Scoring Methodology

### Score Ranges

| Score Range | Category | Description |
|-------------|----------|-------------|
| 800-1000    | Excellent | Highly reliable, consistent behavior |
| 600-799     | Good | Reliable with minor inconsistencies |
| 400-599     | Fair | Moderate risk, some concerning patterns |
| 200-399     | Poor | High risk, multiple red flags |
| 0-199       | Critical | Extremely risky, likely bot/exploit |

### Scoring Components

1. **Reliability Score (40%)**
   - Consistent transaction patterns
   - Regular repayments
   - Long-term activity

2. **Risk Assessment (30%)**
   - Unusual behavior detection
   - Liquidation frequency
   - Exploitation indicators

3. **Activity Quality (20%)**
   - Meaningful transaction sizes
   - Diverse protocol usage
   - Organic interaction patterns

4. **Longevity Factor (10%)**
   - Wallet age and maturity
   - Sustained activity
   - Network effects

## 📁 File Structure

```
defi-credit-scoring/
├── README.md
├── requirements.txt
├── score_generator.py          # Main scoring script
├── feature_engineering.py      # Feature extraction logic
├── model/
│   ├── trained_model.pkl       # Pre-trained ML model
│   ├── scaler.pkl             # Feature scaler
│   └── model_config.json      # Model configuration
├── web/
│   ├── index.html             # Web interface
│   ├── styles.css             # Styling
│   └── script.js              # Frontend logic
├── data/
│   ├── sample_transactions.json
│   └── test_data/
├── tests/
│   ├── test_scoring.py
│   └── test_features.py
└── docs/
    ├── analysis.md            # Detailed analysis
    └── methodology.md         # Scoring methodology
```

## 🧪 Testing

Run the test suite:

```bash
python -m pytest tests/
```

Test specific components:

```bash
# Test feature engineering
python -m pytest tests/test_features.py

# Test scoring logic
python -m pytest tests/test_scoring.py
```

## 📈 Analysis

For detailed analysis of wallet scores and behavior patterns, see [analysis.md](docs/analysis.md).

Key insights include:
- Score distribution across wallet populations
- Behavioral patterns in different score ranges
- Risk factor correlations
- Model performance metrics

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines

- Follow PEP 8 style guidelines
- Add tests for new features
- Update documentation as needed
- Ensure backward compatibility

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Aave Protocol for providing transaction data
- Open-source ML libraries used in this project
- DeFi community for valuable feedback

## 📞 Support

For questions or support:
- Create an issue on GitHub
- Email: support@defi-credit-scoring.com
- Documentation: [docs/](docs/)

## 🔗 Links

- [Live Demo](https://your-demo-link.com)
- [API Documentation](https://api-docs-link.com)
- [Research Paper](https://research-paper-link.com)

---

**Note**: This system is for educational and research purposes. Always conduct your own due diligence when making financial decisions in DeFi protocols.
