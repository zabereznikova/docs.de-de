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
ms.openlocfilehash: 293787d7798768ff2b4e2fb8fec9ed201fdb85ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085414"
---
# <a name="assemblyoptions-enumeration"></a>AssemblyOptions-Enumeration
Listet die Assemblyoptionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
