project('Script Terminal',
	'cpp',
	version: '0.0.0',
	license: 'LGPL3',
	default_options: [
		'cpp_std=c++2a',
		'warning_level=3',
		'optimization=3',
		'werror=true'
	]
)

cppUtils_dep = dependency('CppUtils', fallback: ['CppUtils', 'cppUtils_dep'])

public_dependencies = []
private_dependencies = [
	cppUtils_dep
]

includeDir = include_directories(['include', '.'])

sources = files([

])

headers = files([
	'include/Print.hpp'
])

scriptTerminal_lib = library(
	'ScriptTerminal',
	sources + headers,
	include_directories: includeDir,
	dependencies: public_dependencies + private_dependencies
)

scriptTerminal_dep = declare_dependency(
	link_with: scriptTerminal_lib,
	include_directories: includeDir,
	dependencies: public_dependencies + private_dependencies
)

unitTests_exe = executable(
	'UnitTests',
	sources: files(['src/main.cpp']) + headers,
	dependencies: [scriptTerminal_dep]
)

test('Unit tests', unitTests_exe)
