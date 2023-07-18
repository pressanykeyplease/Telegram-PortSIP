# load(
#     "@build_bazel_rules_apple//apple:apple.bzl", "apple_static_framework_import",
# )

# apple_static_framework_import(
#     name = "PortSIPVoIPSDK",
#     framework_imports = glob(
#         ["PortSIPVoIPSDK.framework/**"],
#     ),
#     visibility = ["//visibility:private"],
# )

load(
    "@build_bazel_rules_apple//apple:apple.bzl", "apple_dynamic_framework_import",
)

apple_dynamic_framework_import(
    name = "PortSIPVoIPSDK",
    # bundle_only = True,
    framework_imports = glob(
        ["PortSIP.framework/**"],
    ),
    visibility = ["//visibility:private"],
)

objc_library(
    # alwayslink = 0,
    name = "PortSIP",
    enable_modules = True,
    module_name = "PortSIP",
    deps = [
        ":PortSIPVoIPSDK",
    ],
    linkopts = [
        "-ObjC",
    ],
    sdk_dylibs = [
        "libresolv",
    ],
    sdk_frameworks = [
        "AudioToolbox",
        "AVFoundation",
        "CoreGraphics",
        "VideoToolbox",
        "UIKit",
        "CoreMedia",
        "CoreVideo",
        "OpenGLES",
        "CoreGraphics",
        "QuartzCore",
    ],
    weak_sdk_frameworks = [
        "Network",
        "Metal",
        "MetalKit",
        "GLKit",
    ],
    visibility = [
        "//visibility:public",
    ],
)