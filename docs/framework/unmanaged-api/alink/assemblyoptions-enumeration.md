---
title: AssemblyOptions-Enumeration
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 324e30f6cbcaa1d1d81c7c03967dbb629d2cd6e9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742266"
---
# <a name="assemblyoptions-enumeration"></a>AssemblyOptions-Enumeration
Listet die Assemblyoptionen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>Felder  
  
|Feld|Beschreibung|  
|-----------|-----------------|  
|optAssemTitle|Zeichenfolge – den Assemblytitel darstellt.|  
|optAssemDescription|Zeichenfolge – die Beschreibung der Assembly enthält.|  
|optAssemConfig|Zeichenfolge – enthält die Assemblykonfiguration.|  
|optAssemOS|-Codierte Zeichenfolge: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Zeichenfolge – das Gebietsschema der Assembly enthält.|  
|optAssemVersion|Zeichenfolge – gibt an, codiert als: "Major.Minor.Build.Revision".|  
|optAssemCompany|Zeichenfolge – das Unternehmen enthält.|  
|optAssemProduct|Zeichenfolge – der Name des Produkts enthält.|  
|optAssemProductVersion|Zeichenfolge (auch bekannt als InformationalVersion bezeichnet).|  
|optAssemCopyright|Zeichenfolge – die copyright-Informationen enthält.|  
|optAssemTrademark|Zeichenfolge – die Markeninformationen enthält.|  
|optAssemKeyFile|Zeichenfolge (Dateiname).|  
|optAssemKeyName|Zeichenfolge (wichtigsten Name).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|"Bool" (auch als DelaySign bezeichnet).|  
|optAssemFileVersion|Zeichenfolge – als "Hauptversion.Nebenversion.Build.Revision"--identisch mit ProductVersion codiert.|  
|optAssemSatelliteVer|Zeichenfolge – als "Hauptversion.Nebenversion.Build.Revision" codiert.|  
|optLastAssemOption|Ein Zähler, der die Anzahl der Elemente.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** alink.h  
  
 **Bibliothek**: alink.dll  
  
## <a name="see-also"></a>Siehe auch

- [Al.exe (Assembly Linker-Tool)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
