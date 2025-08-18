## Vibe Navigator (street parade navigator)
I made this small site to help with choosing what DJs to follow and where to find them for Street Parade '25 (the largest techno festival in the world).

## How it works
The "dots" in the chart represent "styles" of different DJs. 
DJs that are close have similar music styles.

The way that was computed, was by getting embeddings for 30s track segments (for 1 to 3 tracks - depending on what was publicly available) per-artist, and simply computing the average embedding. 

I used a contrastive pre-trained model from huggingface - namely the `laion/clap-htsat-unfused` model. A "style classification" model is also available in HF but it is trained in too few songs - therefore I opted for the contrastive one that was trained in more songs.

The clustering is performed using simple spectral clustering (after some trial-and-error adjustment), and the 2D representation is the tSNE of the embeddings. 


