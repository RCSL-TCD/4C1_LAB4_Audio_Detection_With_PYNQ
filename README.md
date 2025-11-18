# Lab4: Deep Learning on PYNQ
## Experimental preparation
- A PYNQ-Z2 board with a image SD card.
- A Ethernet cable.
- A power cable.
- Google colab.

## Scope
In the last lab, we have learned how to map a traditional audio processing algorithm on the FPGA.


For this lab, we will explore how to deploy a Quantised Neural Network(QNN) on our FPGAs to finish a keyword spotting (KWS).


We will finish this task with:
- Dataset: Google Speech V2 (preprocessed version, 12 classes, MFCC feature extracted)
- Model:   QMLP (3bits)
- Board:   PYNQ-Z2 


This Lab4 contains 3 parts:
- Lab4 A: Train a quantised model and find out the difference between the float NN and the QNN.
- Lab4 B (optional): Export the quantised model into a hardware design which could be excuted on our PYNQ board.
- Lab4 C: Excute the model in the jupyter notebook to benchmark its performance.

## How to run this
### Whole flow
- S1 Data preprocessing: run LabData.py, you will download google speech data and then use MFCC to extract the feature then split them to dataset saved to data/kws_12cls_mfcc_10x49_quant_flat.npz
- S2 Model Training: In google colab, Lab4A will download our preprocessed dataset and then do float and qat training.
- S3 FPGA flow: Lab4B will generate the hwh and bit file for deployment
- S4 On board verification: put deploy/Lab4C_onboard.zip on your pynq board and then run all (auto downloaded if you run Lab4A).
### Lab flow
Only do:
- S2 Model Training: In google colab, Lab4A will download our preprocessed dataset and then do float and qat training.
- S4 On board verification: put deploy/Lab4C_onboard.zip on your pynq board and then run all (auto downloaded if you run Lab4A).

## Note
We do encourage you to finish this lab in a FINN docker enviroment, but considering limited time, you could also try this in a normal conda/python/colab enviroment.


In Lab4B, to generate your own DNN IP, it must be done in the FINN docker. Alternatively, you can also use the generated files provided in the blackboard to continue Lab4 C, or ask TA for a online jupyter sever link with configured enviroment to execute your IP/overlay generation scripts.


For what is FINN and how to set up a FINN enviroment, here are some links might be helpful for you:
- Enviroment setup: https://github.com/CNStanLee/start_with_finn.git
- FINN official docs: https://finn.readthedocs.io/en/latest/
- FINN github repo: https://github.com/Xilinx/finn
- FINN examples repo: https://github.com/Xilinx/finn-examples

## Resource link
- preprocessed dataset: https://drive.google.com/file/d/1uOrunzljVL44wj0A_Lax4fGHBc_NYyeS/view?usp=sharing
- deploypack: https://drive.google.com/file/d/1M4WEsDQ_rBy1OeDD-SrlghNUmYZzBkCR/view?usp=sharing

## Reference
- https://github.com/Xilinx/finn-examples