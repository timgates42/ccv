load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
	name = "bazel_skylib",
	remote = "https://github.com/bazelbuild/bazel-skylib.git",
	commit = "836f1b2f564e8952a9b1ae72f66fc9fad8c8e6f1",
	shallow_since = "1599514179 -0600"
)

git_repository(
	name = "build_bazel_rules_cuda",
	remote = "https://github.com/liuliu/rules_cuda.git",
	commit = "30a3c2f46168278803899487d7de200b714f5879",
	shallow_since = "1600578176 -0400"
)

load("@build_bazel_rules_cuda//gpus:cuda_configure.bzl", "cuda_configure")
load("@build_bazel_rules_cuda//nccl:nccl_configure.bzl", "nccl_configure")

cuda_configure(name = "local_config_cuda")
nccl_configure(name = "local_config_nccl")

load("//config:ccv.bzl", "ccv_setting")

ccv_setting(
	name = "local_config_ccv",
	have_cblas = True,
	have_libpng = True,
	have_libjpeg = True,
	have_fftw3 = True,
	have_pthread = True,
	have_liblinear = True,
	have_tesseract = True,
	have_gsl = True,
	have_cudnn = True,
	have_nccl = True,
	use_openmp = True,
	use_dispatch = True
)
