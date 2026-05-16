> Started : 2025

<div align="center">

# EDS Mineralogical Mapping

A Python tool to generate mineralogical maps from EDS (Energy Dispersive Spectroscopy) element data.

[View Demo](#) · [Report Bug](#) · [Request Feature](#)

![Contributors](https://img.shields.io/badge/contributors-1-blue)
![Forks](https://img.shields.io/badge/forks-0-blue)
![Stars](https://img.shields.io/badge/stars-0-yellow)
![Issues](https://img.shields.io/badge/issues-0_open-green)
![License](https://img.shields.io/badge/license-MIT-green)

</div>

---

## Table of Contents

1. [About the Project](#about-the-project)
   - [Built With](#built-with)
2. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
3. [Usage](#usage)
4. [Roadmap](#roadmap)
5. [Contributing](#contributing)
6. [License](#license)
7. [Contact](#contact)
8. [Acknowledgements](#acknowledgements)

---

## About the Project

This project takes 11 element maps acquired by EDS (Si, Ti, Al, Fe, Mn, Mg, Ca, Na, K, O, P) and produces a color-coded mineralogical map where each pixel is assigned to its dominant mineral phase.

The classification works by normalizing raw EDS counts into atomic proportions, then finding the closest match to known mineral compositions using euclidean distance.

**Minerals identified :**
- Glaucophane, Omphacite, Epidote, Garnet, Quartz, Muscovite, Rutile, Sphene, Hematite

### Built With

- [Python 3.8+](https://www.python.org/)
- [Jupyter Notebook](https://jupyter.org/)
- [NumPy](https://numpy.org/)
- [Matplotlib](https://matplotlib.org/)

---

## Getting Started

### Prerequisites

- Python 3.8 or higher
- pip

### Installation

1. Clone the repository
```sh
git clone https://github.com/username/eds-mineralogical-mapping.git
```

2. Install dependencies
```sh
pip install numpy matplotlib tqdm
```

3. Place your `.txt` element files in the project folder

4. Open the notebook
```sh
jupyter notebook Carte.ipynb
```

---

## Usage

```python
# Load all element maps
mm = MineralMap()
mm.load_element("Si", "CHA(1,8)_Si-K.txt")
# ... load all 11 elements

# Normalize and classify
mm.normalize()
mm.classify()

# Display the map
mapper = MineralMapper(mm)
mapper.plot()
```

Input files are semicolon-separated `.txt` files where each row is a pixel row and each value is the raw EDS count for that element.

---

## Roadmap

- [x] Load and parse element maps
- [x] Normalize EDS counts to atomic proportions
- [x] Classify pixels by euclidean distance
- [x] Generate color-coded mineralogical map
- [ ] Export map as high-resolution image
- [ ] Add interactive visualization
- [ ] Support custom mineral databases

---

## Contributing

Pull requests are welcome. For major changes, please open an issue first.

---

## License

Distributed under the MIT License.

---

## Contact

Maxgoat — [LinkedIn](#) — email@example.com

Project link : [https://github.com/username/eds-mineralogical-mapping](#)

---

## Acknowledgements

- Mineral compositions based on representative EDS analyses from thin section CHA(1,8)
- Course material from geosciences department
