```
# C2FDAN

We release a dataset to evaluate face identification performance of occluded faces based on [MegaFace](http://megaface.cs.washington.edu/). Our occlusion vary in form, color, size, and position:
- form: rectangle (aspect ratio 0.5 - 2) and text ([list](https://raw.githubusercontent.com/sindresorhus/
mnemonic-words/master/words.json))
- color: random in RGB color space
- size: rectangle and text
  - rectangle: area ratio (area of rectangle / area of image) in {0.05, 0.1, 0.15} 
  - text: height ratio (height of text / height of image) in {0.1, 0.3, 0.5} 
- position: (mouth, nose, eyes, outside)

![dataset](https://github.com/stefhoer/c2fdan/raw/main/resources/dataset.png)

## Download

We provide masks and occluded images for all facescrub gallery images of the Megaface benchmark. The probe images remain untouched. Download the dataset from [http://vis-www.cs.umass.edu/lfw/](http://vis-www.cs.umass.edu/lfw/).

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
@INPROCEEDINGS{hoermann2021attention,
    author={Hörmann, Stefan and Zhang, Zeyuan and Knoche, Martin and Teepe, Torben and Rigoll, Gerhard},
    booktitle={2021 IEEE International Conference on Image Processing (ICIP)}, 
    title={{Attention-Based Partial Face Recognition}}, 
    year={2021},
    pages={2978-2982},
    doi={10.1109/ICIP42928.2021.9506476}
  }

@TechReport{LFWTechUpdate,
    author={Huang, Gary B and Learned-Miller, Erik},
    title={Labeled Faces in the Wild: Updates and New Reporting Procedures},
    institution={University of Massachusetts, Amherst},
    year={2014},
    number={UM-CS-2014-003},
    month={May}
}
~~~

## References

[^1]: K. Zhang, Z. Zhang, Z. Li, and Y. Qiao, “Joint face detection and alignment using multitask cascaded convolutional networks,” IEEE Signal Processing Letters, vol. 23, no. 10, pp. 1499–1503, 2016

[^2]: [https://github.com/davidsandberg/facenet](https://github.com/davidsandberg/facenet) and [https://github.com/YYuanAnyVision/mxnet_mtcnn_face_detection](https://github.com/YYuanAnyVision/mxnet_mtcnn_face_detection)



## Contact

[Stefan Hörmann (s.hoermann@tum.de)](mailto:s.hoermann@tum.de)