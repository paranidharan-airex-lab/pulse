# PULSE: Python Unified Library for Sensor Emulation

Welcome to the documentation for PULSE, a comprehensive Python library for synthetic sensor data generation. This documentation will guide you through installation, usage, and development of the PULSE library.

## What is PULSE?

PULSE is a sophisticated Python library jointly developed by Zenteiq Aitech Innovations Private Limited and the AiREX Lab at Indian Institute of Science, Bangalore. It provides a unified interface for simulating realistic datasets from various sensors and radars across multiple domains.

### Core Capabilities

PULSE enables you to:

- Generate synthetic sensor data for testing and validation
- Simulate complex radar-sensor interactions
- Create realistic time-series data with configurable parameters
- Inject and model various types of errors and anomalies
- Integrate with existing data pipelines and ML workflows

### Key Features

#### Comprehensive Sensor Coverage
- Support for multiple sensor types across various domains
- Extensible architecture for adding new sensor types
- Domain-specific parameter configurations

#### Advanced Simulation Capabilities
- PDW (Pulse Descriptor Word) simulation
- Configurable noise levels and error models
- Time-series generation with adjustable parameters
- Synthetic anomaly injection
- High-performance computing optimization using JAX and NumPy

#### Flexible Integration
- Simple Python API
- Streamlit-based user interface
- Support for various data formats including HDF5
- Compatible with major data science tools and frameworks

## Project Structure

The PULSE library is organized into several key components:

```
pulse_pdw/
├── src/pulse/           # Core library code
├── tests/              # Test suite
├── apps/               # Web interface
├── docs/              # Documentation
└── examples/          # Usage examples
```

### Current Implementation

The current version focuses on the PDW (Pulse Descriptor Word) Simulator, which provides:

- Scenario Management
- Radar Properties Configuration
- Sensor Properties Modeling
- Geometric Calculations
- Error Modeling

## Getting Started

To get started with PULSE:

1. Check the [Installation Guide](installation_guide.md) for setup instructions
2. Review the [Testing Guide](testing.md) for validation procedures
3. Explore the examples directory for usage demonstrations

## Contributing

We welcome contributions from the community! Please see our Contributing Guidelines for details on:

- Development workflow
- Code standards
- Pull request process
- Testing requirements

## Support and Contact

For support:

- Create an issue on GitHub: [https://github.com/zenoxml/pulse/issues](https://github.com/zenoxml/pulse/issues)
- Email: contact@scirex.org

## License

PULSE is licensed under the Apache License 2.0. See the LICENSE file for details.

## Citation

If you use PULSE in your research, please cite:

```bibtex
@software{pulse2025,
  title = {PULSE: Python Unified Library for Sensor Emulation},
  author = {{Zenteiq Aitech Innovations} and {AiREX Lab}},
  year = {2025},
  url = {https://github.com/zenoxml/pulse}
}
```

## Acknowledgments

This project is developed in collaboration with:

- Zenteiq Aitech Innovations Private Limited
- AiREX Lab at Indian Institute of Science, Bangalore
- ARTPARK (AI & Robotics Technology Park) at IISc