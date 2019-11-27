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
ms.openlocfilehash: ed45e06297b77ea60304cdcfe1b08e97f9e4c085
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446586"
---
# <a name="assemblyoptions-enumeration"></a>AssemblyOptions-Enumeration
Listet die Assemblyoptionen auf.  
  
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
  
|Field|Beschreibung|  
|-----------|-----------------|  
|optAssemTitle|String: stellt den Assemblytitel dar.|  
|optAssemDescription|String: enthält die Beschreibung der Assembly.|  
|optAssemConfig|String: enthält die Assemblykonfiguration.|  
|optAssemOS|Zeichenfolge codiert als: "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|String: enthält das assemblygebiets Schema.|  
|optAssemVersion|Zeichen folgen codiert als: "Major. Minor. Build. Revision".|  
|optAssemCompany|String: enthält das Unternehmen.|  
|optAssemProduct|String: enthält den Produktnamen.|  
|optAssemProductVersion|String (auch als InformationalVersion bezeichnet).|  
|optAssemCopyright|String: enthält Informationen zum Copyright.|  
|optAssemTrademark|String: enthält die Markeninformationen.|  
|optAssemKeyFile|Zeichenfolge (Dateiname).|  
|optAssemKeyName|Zeichenfolge (der Schlüssel Name).|  
|optAssemAlgID|ULONG|  
|optassemflags|ULONG|  
|optAssemHalfSign|Bool (auch als "Delta Sign" bezeichnet).|  
|optAssemFileVersion|Zeichen folgen codiert als "Major. Minor. Build. Revision"-identisch mit ProductVersion.|  
|optAssemSatelliteVer|Zeichen folgen codiert als "Major. Minor. Build. Revision".|  
|optLastAssemOption|Ein-Wert für die Anzahl der Elemente.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Alink. h  
  
 **Bibliothek**: Alink. dll  
  
## <a name="see-also"></a>Siehe auch

- [Al.exe (Assembly Linker-Tool)](../../tools/al-exe-assembly-linker.md)
