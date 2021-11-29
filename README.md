# C2FDAN 

We release a dataset to evaluate face identification performance of occluded faces based on [MegaFace](http://megaface.cs.washington.edu/). Our occlusion vary in form, color, size, and position:
- form: rectangle (aspect ratio 0.5 - 2) and text ([list](https://raw.githubusercontent.com/sindresorhus/
  mnemonic-words/master/words.json) )
- color: random in RGB color space
- size: rectangle and text
  - rectangle: area ratio (area of rectangle / area of image) in {0.05, 0.1, 0.15} 
  - text: height ratio (height of text / height of image) in {0.1, 0.3, 0.5} 
- position: (mouth, nose, eyes, outside)



Examples of occluded faces with different occlusions:

![dataset](https://github.com/stefhoer/C2FDAN/raw/main/ressources/dataset.png)

## Download

We provide masks and occluded images for all facescrub gallery images of the Megaface benchmark. The probe images remain untouched. Download the dataset from [http://megaface.cs.washington.edu/](http://megaface.cs.washington.edu/) or [https://github.com/deepinsight/insightface](https://github.com/deepinsight/insightface).

```shell
MegaFace-facescrub
└───default
│   └───Adam_Brody
│   │   │   Adam_Brody_241.png
│   │   ...
│   ...
│   └───Victoria_Justice
└───square
│   └───eyes
│   │   └───0.05
│   │   │   └───img
│   │   │   │   └───Adam_Brody
│   │   │   │   │   │   Adam_Brody_241.png
│   │   │   │   │   │   ...
│   │   │   │   │   ...
│   │   │   │   └───Victoria_Justice
│   │   │   └───mask
│   │   └───0.1
│   │   └───0.15
│   └───mouth
│   └───nose
│   └───outside
└───text
│   └───eyes
│   ...
│   └───outside
```

## Alignment

To align the faces we make use of 5 landmarks extracted by MTCNN [^1].  The alignment script is provided under  `align_dataset.py`, which is based on the code from  [^2].


## Cite

If you find PartialLFW useful in your research, please cite the following papers:

~~~tex
@INPROCEEDINGS{hoermann2021C2FDAN,
    author={Hörmann, Stefan and Zhibing, Xia and Knoche, Martin and Rigoll, Gerhard},
    booktitle={2021 16th IEEE International Conference on Automatic Face and Gesture Recognition (FG 2021)}, 
    title={{A Coarse-to-Fine Dual Attention Network for Blind Face Completion}}, 
    year={2021},
  }

@inproceedings{kemelmacher2016megaface,
  title={The megaface benchmark: 1 million faces for recognition at scale},
  author={Kemelmacher-Shlizerman, Ira and Seitz, Steven M and Miller, Daniel and Brossard, Evan},
  booktitle={Proceedings of the IEEE conference on computer vision and pattern recognition},
  pages={4873--4882},
  year={2016}
}
~~~

## References

[^1]: K. Zhang, Z. Zhang, Z. Li, and Y. Qiao, “Joint face detection and alignment using multitask cascaded convolutional networks,” IEEE Signal Processing Letters, vol. 23, no. 10, pp. 1499–1503, 2016

[^2]: [https://github.com/davidsandberg/facenet](https://github.com/davidsandberg/facenet) and [https://github.com/YYuanAnyVision/mxnet_mtcnn_face_detection](https://github.com/YYuanAnyVision/mxnet_mtcnn_face_detection)



## Contact

[Stefan Hörmann (s.hoermann@tum.de)](mailto:s.hoermann@tum.de)