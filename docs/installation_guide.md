# Installation Guide

This guide provides detailed instructions for installing and setting up the PULSE library. We'll cover both basic installation and development setup options.

## Prerequisites

Before installing PULSE, ensure you have:

- Python 3.12 or higher
- pip or conda package manager
- Git (for development installation)

## Installation Methods

### Method 1: Using Conda (Recommended for Development)

1. Create a new conda environment:
```bash
conda create -n pulse_env python=3.12
conda activate pulse_env
```

2. Install core dependencies:
```bash
conda install numpy scipy pandas streamlit pyyaml h5py plotly
conda install -c conda-forge pint
```

3. Install PULSE in development mode:
```bash
git clone https://github.com/zenoxml/pulse.git
cd pulse
pip install -e .
```

### Method 2: Using pip (For Users)

```bash
pip install pulse-pdw
```

## Verifying Installation

To verify your installation:

1. Start Python:
```bash
python
```

2. Try importing PULSE:
```python
import pulse
print(pulse.__version__)
```

## Configuration Setup

### Basic Configuration

1. Create a configuration directory:
```bash
mkdir ~/.pulse
```

2. Create a basic configuration file (`config.yaml`):
```yaml
scenario:
  start_time: 0
  end_time: 10
  time_step: 0.1

radars:
  - name: "Radar1"
    start_position: [0, 0]
    rotation_type: "constant"
    rotation_params:
      t0: 0
      alpha0: 0
      T_rot: 4
    pri_type: "fixed"
    pri_params:
      pri: 0.001

sensors:
  - name: "Sensor1"
    start_position: [1000, 1000]
    error_model: "gaussian"
    error_params:
      mean: 0
      std: 0.1
```

### Advanced Configuration

For advanced users, PULSE supports additional configuration options:

- Custom error models
- Specialized sensor configurations
- Performance optimization settings
- Output format specifications

Create these configurations in separate YAML files within your project directory.

## Running the Web Interface

To launch the Streamlit-based user interface:

```bash
streamlit run apps/app.py
```

## Troubleshooting

### Common Issues

1. **Dependency Conflicts**
   - Solution: Use a fresh conda environment
   - Alternative: Check `requirements.txt` for specific versions

2. **Import Errors**
   - Verify Python path settings
   - Check installation location
   - Confirm all dependencies are installed

3. **Configuration Issues**
   - Validate YAML syntax
   - Check file permissions
   - Verify file locations

### Getting Help

If you encounter problems:

1. Check the [GitHub Issues](https://github.com/zenoxml/pulse/issues)
2. Review error messages and logs
3. Contact support at contact@scirex.org

## Next Steps

After installation:

1. Review the [Testing Guide](testing.md)
2. Explore example scripts in the `examples/` directory
3. Read the API documentation

## System Requirements

### Minimum Requirements
- Python 3.12+
- 4GB RAM
- 1GB disk space

