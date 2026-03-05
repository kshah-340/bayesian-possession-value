# Data

This project uses the [StatsBomb Open Data](https://github.com/statsbomb/open-data) repository, 
which is freely available for non-commercial use under the StatsBomb Open Data License.

## Setup Instructions

1. Clone the StatsBomb open data repository:
```bash
git clone https://github.com/statsbomb/open-data.git
```

2. Place the cloned folder in the root of this repository, or update the data path 
in the notebook to point to wherever you've stored it locally.

3. This project uses match event data from the following competitions:
   - [LIST THE COMPETITIONS/MATCHES YOU USED HERE]

## Alternative: statsbombpy

You can also access StatsBomb data directly via their Python package:
```bash
pip install statsbombpy
```

The notebook uses statsbombpy for data loading. See the 
[statsbombpy documentation](https://github.com/statsbomb/statsbombpy) for usage details.

## License

StatsBomb open data is provided under the 
[StatsBomb Open Data License](https://github.com/statsbomb/open-data/blob/master/LICENSE.pdf). 
Please review this license before using the data for any purpose.
