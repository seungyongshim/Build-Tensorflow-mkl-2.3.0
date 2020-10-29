# POC-Build-Tensorflow-mkl-2.3.0

- https://software.intel.com/content/www/us/en/develop/articles/intel-optimization-for-tensorflow-installation-guide.html#wind_B_S
- https://www.tensorflow.org/install/source_windows


## msys2 설치하기
- https://www.msys2.org/docs/ci/

## Github Action으로 빌드 불가
- 6시간 넘어가서 타임아웃됨

## 로컬 빌드 환경 구축
```
$env:PATH = "c:\python37;" + $env:PATH
python ./configure.py
./bazel.exe --output_base="$env:GITHUB_WORKSPACE/output" build --announce_rc --config=opt --experimental_shortened_obj_file_path=true --config=mkl --define=no_tensorflow_py_deps=true tensorflow/tools/pip_package:build_pip_package
```
