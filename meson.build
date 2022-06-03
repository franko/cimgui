project('cimgui', 'c', 'cpp', version : '1.87')

cc = meson.get_compiler('cpp')
cimgui_supcpp_lib = cc.find_library('supc++')

cimgui_imgui_dep = dependency('imgui')
cimgui_imgui_demo_dep = dependency('imguidemo')

cimgui_lib = library('cimgui', 'cimgui.cpp',
    dependencies : [cimgui_imgui_dep, cimgui_imgui_demo_dep, cimgui_supcpp_lib],
    install : true,
)

install_headers('cimgui.h')

pkg = import('pkgconfig')

pkg.generate(cimgui_lib,
    filebase : 'cimgui',
    name : 'cimgui',
    libraries : cimgui_lib,
    version : meson.project_version(),
    description : 'Dear ImGui C API interface library',
    url : 'http://github.com/cimgui/cimgui',
)

