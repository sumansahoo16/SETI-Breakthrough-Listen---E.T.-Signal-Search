# SETI-Breakthrough-Listen---E.T.-Signal-Search

## Problem Statement
In this competition we are looking for technosignature signals in cadence snippets taken from the Green Bank Telescope (ie. accurately classifing anomalous signals). 
There are 6 channels in the images of shape (6, 273, 256) where 273 is the time axis and 256 is the frequency axis, representing the 2D spectrogram.


![image](https://www.kaggleusercontent.com/kf/69474525/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..d-6ON6IS5sCKVkY-C1x8_w.QXuT7uBWR5mNSO2M1546-bV9ZkFH2XUr6GfdLIe_S7wk_sBo7wdG2oyb9BnG4OM2wKzFY5PTDMfZEFWqaSSzdv92yEmjyjl6Pcs-TnUWZ73k8J1jEt97s99pMJi_8fJUKX2BRBT16hUiyXRo-2-Ix-HANMlNsDjDrgBABKD-KIYVRnJxBF8cW17dDgAnTWeGMCGZXx9oZTV7tDhg_vjhN-0XlkBzGnzwj2Oy36lut27cBalwKlVoacrF356cPRp5UyqTkSgqy6F6PfQtEwbzyCMlhGyBca1ZpDC2IPT-dpNX3r95gcMsa51chPILf2j6eQsBJTmeLuYLoSLrr5SefNLDjFReKjpF8WFmThQZy_pVX_1AdeNAE7tngZCc_MKH-U0yLpX61gptrhXYR1_tspZFZaKGr0nLeFNQHewH9jjGB3PzU4yVG-3kvEgxvxhIG1HZ7cE8rx8_2PviccqfvSZq-39TRk6sA7XIM9EkboJ0AJTP0tObkeI4LKCTlBSrAmMVrFz2ukRJsJZRgXRH7i-YJ7uT2aEnRu3kNFrWkR2XrtXkXlJVLSeZe5W1urV6nav-JcvpadRNBDHmgeMVvS36G_ORlNDKbnY8m4Z1GFNzwx_j3Qoka7xkDw6znxoEHrmKHNAmYIVy_kP-vLtIIg.s21Wh-mniFoEEGFt7Wa9ug/__results___files/__results___22_0.png)

![image](https://www.kaggleusercontent.com/kf/69474525/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..d-6ON6IS5sCKVkY-C1x8_w.QXuT7uBWR5mNSO2M1546-bV9ZkFH2XUr6GfdLIe_S7wk_sBo7wdG2oyb9BnG4OM2wKzFY5PTDMfZEFWqaSSzdv92yEmjyjl6Pcs-TnUWZ73k8J1jEt97s99pMJi_8fJUKX2BRBT16hUiyXRo-2-Ix-HANMlNsDjDrgBABKD-KIYVRnJxBF8cW17dDgAnTWeGMCGZXx9oZTV7tDhg_vjhN-0XlkBzGnzwj2Oy36lut27cBalwKlVoacrF356cPRp5UyqTkSgqy6F6PfQtEwbzyCMlhGyBca1ZpDC2IPT-dpNX3r95gcMsa51chPILf2j6eQsBJTmeLuYLoSLrr5SefNLDjFReKjpF8WFmThQZy_pVX_1AdeNAE7tngZCc_MKH-U0yLpX61gptrhXYR1_tspZFZaKGr0nLeFNQHewH9jjGB3PzU4yVG-3kvEgxvxhIG1HZ7cE8rx8_2PviccqfvSZq-39TRk6sA7XIM9EkboJ0AJTP0tObkeI4LKCTlBSrAmMVrFz2ukRJsJZRgXRH7i-YJ7uT2aEnRu3kNFrWkR2XrtXkXlJVLSeZe5W1urV6nav-JcvpadRNBDHmgeMVvS36G_ORlNDKbnY8m4Z1GFNzwx_j3Qoka7xkDw6znxoEHrmKHNAmYIVy_kP-vLtIIg.s21Wh-mniFoEEGFt7Wa9ug/__results___files/__results___22_1.png)

## Solution

At the beggining of the competition tried different approaches (use all channels, only 0,2,4, with vstack and without it). So, the best option was to use only 0,2,4 channels with vstack.
Also had a lot of experiments with img size and found that bigger resolution can improve results (512x512 /  672x672 / 896x896).

Augmentation:
- HorizontalFlip, VerticalFlip
- ShiflScaleRotate
- RandomResizedCrop (scale 0.9)
- IAAAdditiveGaussianNoise (scale 0.15)
- MixUp
- Shuffle the [0,2,4] channel as augmentation


Models:
- efficientnet_b0
- efficientnet_b5
- efficientnetv2m 




