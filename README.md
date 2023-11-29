## Active Foundational Models for Fault Diagnosis of Electrical Motors
We have developed an Active foundational model for the first time in the field of electrical motor fault diagnosis.  The developed model can able to detect and diagnose faults within and across machines. The potential impact of this paper is to train the backbone model with fewer labeled samples, which are most informative. This work will be submitted to the journal, and the preprint is available in arXiv [[1]](https://arxiv.org/abs/2311.15516)

## Abstract
Fault detection and diagnosis of electrical motors are of utmost importance in
ensuring the safe and reliable operation of several industrial systems. Detection
and diagnosis of faults at the incipient stage allow corrective actions to be taken
in order to reduce the severity of faults. The existing data-driven deep learning
approaches for machine fault diagnosis rely extensively on huge amounts of labeled samples, where annotations are expensive and time-consuming. However,
a major portion of unlabeled condition monitoring data is not exploited in the
training process. To overcome this limitation, we propose a foundational model-based Active Learning framework that utilizes less amount of labeled samples,
which are most informative and harnesses a large amount of available unlabeled
data by effectively combining Active Learning and Contrastive Self-Supervised
Learning techniques. It consists of a transformer network-based backbone model
trained using an advanced nearest-neighbor contrastive self-supervised learning
method. This approach empowers the backbone to learn improved representations of samples derived from raw, unlabeled vibration data. Subsequently,
the backbone can undergo fine-tuning to address a range of downstream tasks,
both within the same machines and across different machines. The effectiveness
of the proposed methodology has been assessed through fine-tuning of the backbone for multiple target tasks using three distinct machine-bearing fault
datasets. The experimental evaluation demonstrates a superior performance as
compared to existing state-of-the-art fault diagnosis methods with less amount
of labeled data.

## Dataset
The data set used in this work to construct the backbone model is the [Korea Advanced Institute of Science and Technology (KAIST) dataset](https://www.sciencedirect.com/science/article/pii/S2352340923001671) . The data comprises measurements under three loading conditions: 0 Nm, 2 Nm and 4 Nm. The sampling frequency for vibration, temperature, and driving current data was set at 25.6 kHz. This dataset contains 120 seconds of vibration data in normal states and 60 seconds in faulty states. The second part of the dataset focuses on vibration and current data acquired from the bearing faults at different locations such as inner-race, outer-race, and ball. These data were collected under continuously varying speed conditions by modifying the motor speed between 680 and 2460 RPM. In this work, we specifically consider the vibration data for bearing faults, shaft misalignment faults, rotor unbalance faults at a constant speed, and bearing faults at varying speeds. The backbone model is trained by combining data from normal, inner race, outer race, shaft misalignment, rotor unbalance faults at constant speed, and normal, inner race, and outer race faults at variable speed conditions. 

## Flowchart for the proposed model
<p align="center">
<img src="https://i.imgur.com/X4hhwiI.png" width=40% height=40%>
</p>
Fig. Backbone Training in NNCLR Framework<p align="center">
<img src="https://i.imgur.com/H6ZaNzj.png" width=40% height=40%>
</p>
Fig. Feed Forward Network Training in NNCLR Framework

## Contributions
1. In this study, we have introduced a novel foundational model-based AL
framework for electrical motor fault diagnosis. This model consists of two
5
key components: the construction of the backbone model, followed by the
fine-tuning procedure for various target tasks using less amount of labeled
samples.
2. Instead of solely relying on data augmentation techniques, we have employed an advanced method called instance discrimination-based contrastive
Self-Supervised Learning (SSL) to train the transformer-based backbone
model. In contrastive self-supervised learning, we have harnessed the benefits of using the nearest neighbor as a positive sample. This approach
allows the transformer encoder to learn a more robust representation of
the vibration signal, resulting in a well-generalized backbone model.
3. We have implemented AL strategy based on entropy and Kullback-Leibler
(KL) divergence as combined heuristics for strategic sample selection. This
helps in identification of most informative samples for annotation within
the iterative training loop. The experimental results demonstrate that the
proposed model can learn effective decision boundaries even with a limited
number of labeled samples. This achievement overcomes the laborious and
costly task of manual labeling.
4. Our research amalgamates the strengths of Active Learning (AL) and the
nearest neighbor contrastive SSL method. We have proposed a framework
for constructing the backbone model, enabling it to learn more refined
representations of the data with minimum labeled samples. Consequently,
the proposed model is highly effective in various downstream tasks within
the same machine as well as across different machines. The proposed
approach has been thoroughly evaluated using three publicly available
bearing fault datasets.

## NNCLR Training 
<p align="center">
<img src="https://i.imgur.com/VS6BmbP.jpg" width=100% height=100%>
</p>

Fig. NNCLR training for developing active foundational models for fault diagnosis of
electrical motors


## Target Tasks  
<p align="center">
<img src="https://i.imgur.com/S76ef1H.png" width=100% height=100%>
</p>

## Results
<p align="center">
<img src="https://i.imgur.com/qrPIUNP.png" width=100% height=100%>
</p>

## Conclusions
 To overcome the limitations of obtaining meaningful labeled samples and harness the unlabeled samples in the learning process, and rely less on data augmentation technique, a new active foundational model for fault diagnosis of the electrical motor was proposed based on the AL and nearest neighbor contrastive SSL. The training set samples are increased by labeling the most informative samples from the unlabeled pools. The informative samples from unlabeled samples are measured using entropy and KL divergence metric. Unlabeled samples with large uncertainties were selected for expert annotations to increase the size of the training set. Then, the transformer-based backbone network is constructed and trained using the proposed nearest neighbor contrastive self-supervised learning for 1D vibration signal. The developed backbone model can be fine-tuned for several target tasks within and across machines. The proposed approach was evaluated on three different induction motor bearing fault experimental datasets and performs better than existing fault diagnosis approaches with significantly less labeled samples. Future work will extend the proposed approach to diagnose faults across different types of machines.


