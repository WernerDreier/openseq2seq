[![License](https://img.shields.io/badge/License-Apache%202.0-brightgreen.svg)](https://opensource.org/licenses/Apache-2.0)
[![Documentation](https://img.shields.io/badge/documentation-github.io-blue.svg)](https://nvidia.github.io/OpenSeq2Seq/html/index.html)
<div align="center">
  <img src="./docs/logo-shadow.png" alt="OpenSeq2Seq" width="250px">
  <br>
</div>

# Forked OpenSeq2Seq

Adopting for usage of wav2vec features produced by fairseq-library

## Documentation and installation instructions 
https://nvidia.github.io/OpenSeq2Seq/

## Acknowledgments
[NVIDIA Openseq2seq](https://github.com/NVIDIA/OpenSeq2Seq)
[Pytorch Fairseq] (https://github.com/pytorch/fairseq/blob/master/examples/wav2vec/README.md)

## Usage
- Use Fairseq Library to train a wav2vec model
- Use wav2vec model to featurize audio-files
- put wav2vec-files (.h5context file extension) in a folder called 'wav2vec_files' next to a folder containing original audio-files called 'wav_files'
- adjust your openseq2seq-config-file according to next section:

```
train_params = {
    "data_layer": Speech2TextDataLayer,
    "data_layer_params": {
        "cache_features": True,
        "cache_regenerate": False,
        "cache_format": "wav2vec",
        "num_audio_features": 512, #irrelevant but corrected
        ...
    },
}
```
