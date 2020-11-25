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
ms.openlocfilehash: 352e1acd1fdd8297754e18b2e8c6448ea723a557
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717030"
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
  
|Feld|BESCHREIBUNG|  
|-----------|-----------------|  
|optassemblytitle|String: stellt den Assemblytitel dar.|  
|optassemdescription|String: enthält die Beschreibung der Assembly.|  
|optassemconfig|String: enthält die Assemblykonfiguration.|  
|optassemos|Zeichenfolge codiert als: "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion".|  
|optassemprocessor|ULONG|  
|optassemlocale|String: enthält das assemblygebiets Schema.|  
|optassemversionsversion|Zeichen folgen codiert als: "Major. Minor. Build. Revision".|  
|optassemcompany|String: enthält das Unternehmen.|  
|optassemproduct|String: enthält den Produktnamen.|  
|optassemproductversion|String (auch als InformationalVersion bezeichnet).|  
|optassemcopyright|String: enthält Informationen zum Copyright.|  
|optassemtrademark|String: enthält die Markeninformationen.|  
|optassemkeyfile|Zeichenfolge (Dateiname).|  
|optassemkeyname|Zeichenfolge (der Schlüssel Name).|  
|optassemalgid|ULONG|  
|optassemflags|ULONG|  
|optassemhalfsign|Bool (auch als "Delta Sign" bezeichnet).|  
|optassemfileversion|Zeichen folgen codiert als "Major. Minor. Build. Revision"-identisch mit ProductVersion.|  
|optassemsatellitever|Zeichen folgen codiert als "Major. Minor. Build. Revision".|  
|optlastassemsoption|Ein-Wert für die Anzahl der Elemente.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Alink. h  
  
 **Bibliothek**: alink.dll  
  
## <a name="see-also"></a>Weitere Informationen

- [Al.exe (Assembly Linker-Tool)](../../tools/al-exe-assembly-linker.md)
