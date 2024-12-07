# RAG-Inspired WebToons Style Transfer Model

This is a PyTorch project to transfer the style of an input image to that of a given WebToons original series. The model utilizes a RAG-inspired architecture, querying a vector database with the inputs to attain an appropriate style image for style transfer. The style images populating the vector database are scraped from WebToons. 

<img width="757" alt="image" src="https://github.com/user-attachments/assets/172f5831-8fb6-4391-9a90-04ae3c81db77">

The approach and methodologies of these processes are detailed in the project report $\LaTeX$ file.

## Requirements

Please install requirements by `pip install -r requirements.txt`

- python 3.12.2
- aiofiles 24.1.0
- aiohttp 3.11.10
- beautifulsoup4 4.12.3
- pandas 2.2.3
- Pillow 11.0.0
- python-dotenv 1.0.1
- qdrant_client 1.12.1
- regex 2024.11.6
- Requests 2.32.3
- torch 2.5.1
- torchvision 0.20.1
- transformers 4.47.0

Please create a [Qdrant](https://qdrant.tech/) account and cluster. The cluster URL and API key are necessary to set up the vector database.

## Usage

### Data Scraping (Optional)

Within `Scraping.ipynb` lies an example of the data scraping process and the code to scrape any WebToons series. The only input to change is the number of episodes being scraped. This process is optional because within the `comic_series` directory there already exists ~1000 episodes worth of images.

### Style Transfer

Within `RAG-Model` lies the code to transfer any image with any scraped WebToons series. The inputs needed for populating the [Qdrant](https://qdrant.tech/) vector database are the cluster URL and API key for a cluster hosted on [Qdrant](https://qdrant.tech/). 
The inputs needed for the style transfer are...

- `series`: series name of any scraped WebToons series
- `content_idx`: index of the image to be styled within the `content_images` directory.
- `content_path` (optional): path to the image to be styled.
- `k_images`: the number of style images with which to style the input image.
- `image_size`: square image resolution.





