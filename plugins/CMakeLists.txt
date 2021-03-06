# Copyright (c) 2015-2018, EPFL/Blue Brain Project
# All rights reserved. Do not distribute without permission.
# Responsible Author: Cyrille Favreau <cyrille.favreau@epfl.ch>
#
# This file is part of Brayns <https://github.com/BlueBrain/Brayns>

option(BRAYNS_DEFLECT_ENABLED "Activate streaming to display wall" OFF)
if(BRAYNS_DEFLECT_ENABLED)
  add_subdirectory(Deflect)
endif()

if(BRAYNS_NETWORKING_ENABLED)
  add_subdirectory(Rockets)
endif()

option(BRAYNS_MULTIVIEW_ENABLED "Activate Multiview camera plugin" OFF)
if(BRAYNS_MULTIVIEW_ENABLED)
  add_subdirectory(Multiview)
endif()

option(BRAYNS_OPENDECK_ENABLED "Activate OpenDeck plugin" OFF)
if(BRAYNS_OPENDECK_ENABLED)
  add_subdirectory(OpenDeck)
endif()

option(BRAYNS_VRPN_ENABLED "Activate vrpn plugin" OFF)
if(BRAYNS_VRPN_ENABLED)
  add_subdirectory(VRPN)
endif()

option(BRAYNS_CIRCUITVIEWER_ENABLED "Activate CircuitViewer plugin" OFF)
if (BRAYNS_CIRCUITVIEWER_ENABLED)
  add_subdirectory(CircuitViewer)
endif()

option(BRAYNS_CIRCUITEXPLORER_ENABLED "Activate CircuitExplorer plugin" OFF)
if (BRAYNS_CIRCUITEXPLORER_ENABLED)
  add_subdirectory(CircuitExplorer)
endif()

option(BRAYNS_DTI_ENABLED "Activate DTI plugin" OFF)
if (BRAYNS_DTI_ENABLED)
  add_subdirectory(DTI)
endif()

option(BRAYNS_BBIC_ENABLED "Activate BBIC Volume plugin" OFF)
if(BRAYNS_BBIC_ENABLED)
  add_subdirectory(BBIC)
endif()

option(BRAYNS_CIRCUITINFO_ENABLED "Activate CircuitInfo plugin" OFF)
if(BRAYNS_CIRCUITINFO_ENABLED)
    add_subdirectory(CircuitInfo)
endif()

option(BRAYNS_CIRCUITRENDERER_ENABLED "Activate CircuitRenderer plugin" OFF)
if(BRAYNS_CIRCUITRENDERER_ENABLED)
    add_subdirectory(CircuitRenderer)
endif()

if(BRAYNS_PBRTV2_ENABLED)
    add_subdirectory(Fluorescence)
endif()

if(BRAYNS_PBRT_ENABLED OR BRAYNS_PBRTV2_ENABLED)
    add_subdirectory(PBRVolumes)
endif()

add_subdirectory(Example)
if (TARGET Brayns-all)
  add_dependencies(Brayns-all exampleBraynsPlugin)
endif()
