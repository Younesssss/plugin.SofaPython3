cmake_minimum_required(VERSION 3.1)
project(PythonModule_SofaGui)


####################################################################################################
### Module dependencies
####################################################################################################
find_package(SofaGui REQUIRED)

####################################################################################################
### Module files
####################################################################################################
set(SOURCE_FILES
    ${CMAKE_CURRENT_SOURCE_DIR}/src/SofaPython3/SofaGui/Module_SofaGui.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/src/SofaPython3/SofaGui/Binding_GUIManager.cpp
)

set(HEADER_FILES
    ${CMAKE_CURRENT_SOURCE_DIR}/src/SofaPython3/SofaGui/Binding_GUIManager.h
)

set(MODULE_NAME Gui)
set(PACKAGE_DIRECTORY  ${SP3_PYTHON_PACKAGES_DIRECTORY})

SP3_add_python_module(
    TARGET
        ${PROJECT_NAME}
    MODULE_NAME
        ${MODULE_NAME}
    SOURCES
        ${SOURCE_FILES}
        ${HEADER_FILES}
    DEPENDS
        SofaCore SofaGuiCommon SofaGuiMain
    DESTINATION
        ${PACKAGE_DIRECTORY}/Sofa
)