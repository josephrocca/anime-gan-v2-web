# AnimeGANv2 tfjs/tflite/onnx

A browser version of this: https://huggingface.co/spaces/akhaliq/AnimeGANv2 (which is the FacePortraitV2 model from [here](https://github.com/bryandlee/animegan2-pytorch))

* ONNX Web Runtime (**working**): https://josephrocca.github.io/anime-gan-v2-web/onnx.html
* tflite (**not** working - [issue](https://github.com/tensorflow/tfjs/issues/5832)): https://josephrocca.github.io/anime-gan-v2-web/tflite.html
* tfjs (**not** working - [issue](https://github.com/tensorflow/tfjs/issues/5832)): https://josephrocca.github.io/anime-gan-v2-web/tfjs.html

[Here's the Google Colab notebook](https://colab.research.google.com/github/josephrocca/anime-gan-v2-web/blob/main/Export_PyTorch_AnimeGANv2_%E2%86%92_ONNX_%E2%86%92_TensorFlow_SavedModel_%E2%86%92_TF_js_%2B_tflite.ipynb) that I used to convert the models from the original Pytorch format.

The ONNX WebGL runtime doesn't support int64 ([issue](https://github.com/microsoft/onnxruntime/issues/9724)), so I used [this script](https://github.com/aadhithya/onnx-typecast) to convert int64 values to int32. Then I ran into another problem with the WebGL runtime ([issue](https://github.com/microsoft/onnxruntime/issues/9757)), so currently only the ONNX **wasm** runtime works.
