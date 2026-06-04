<div align="center">
<h2>BioSVD: a Rapid 3D Biomedical Optical Imaging Technique via Stable Video Diffusion</h2>

## Dataset
The data is released on Google Drive(https://drive.google.com/drive/folders/1WyKKeP8n4_DK6SsEitj_RfGv1XBP9tFI?usp=sharing).

## Getting Started
This repository is based on animate-anything(https://github.com/alibaba/animate-anything). You can find more details about Installation and Requirements.

### Create Conda Environment (Optional)
It is recommended to install Anaconda.

**Windows Installation:** https://docs.anaconda.com/anaconda/install/windows/

**Linux Installation:** https://docs.anaconda.com/anaconda/install/linux/

```bash
conda create -n animation python=3.10
conda activate animation
```

### Python Requirements
```bash
pip install -r requirements.txt
```

### Configuration

The configuration uses a YAML config borrowed from [Tune-A-Video](https://github.com/showlab/Tune-A-Video) repositories. 

All configuration details are placed in `example/train_mask_motion.yaml`. Each parameter has a definition for what it does.


### Finetuning anymate-anything
You can finetune anymate-anything with text, motion mask, motion strength guidance on your own dataset. The following config requires around 30G GPU RAM. You can reduce the train_batch_size, train_data.width, train_data.height, and n_sample_frames in the config to reduce GPU RAM:
```
python train.py --config example/train_mask_motion.yaml pretrained_model_path=<download_model>
```

## Shoutouts

- [Text-To-Video-Finetuning](https://github.com/ExponentialML/Text-To-Video-Finetuning.git)
- [Showlab](https://github.com/showlab/Tune-A-Video) and bryandlee[https://github.com/bryandlee/Tune-A-Video] for their Tune-A-Video contribution that made this much easier.
- [lucidrains](https://github.com/lucidrains) for their implementations around video diffusion.
- [cloneofsimo](https://github.com/cloneofsimo) for their diffusers implementation of LoRA.
- [kabachuha](https://github.com/kabachuha) for their conversion scripts, training ideas, and webui works.
- [JCBrouwer](https://github.com/JCBrouwer) Inference implementations.
- [sergiobr](https://github.com/sergiobr) Helpful ideas and bug fixes.
