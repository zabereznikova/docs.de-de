---
title: AssemblyComparisonResult-Enumeration
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
ms.openlocfilehash: e3cdb648397ca4f4aa2326e4f2349a5a14c3edcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178291"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult-Enumeration
Gibt die Äquivalenz zweier Assemblyidentitäten an, die durch die [CompareAssemblyIdentity-Funktion](compareassemblyidentity-function.md) bestimmt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a>Members  
  
|Membername|Beschreibung|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Gibt an, dass alle Baugruppenfelder in der Vergleichsübereinstimmung übereinstimmen.|  
|`ACR_EquivalentFXUnified`|Gibt an, dass Assemblys basierend auf der CLR-Vereinheitlichung (Common Language Runtime Version) von Assemblyversionsnummern in der .NET Framework Version 2.0 als gleichwertig betrachtet werden.|  
|`ACR_EquivalentPartialFXUnified`|Gibt eine partielle Übereinstimmung der Assemblys basierend auf der CLR-Vereinheitlichung von Assemblyversionsnummern in .NET Framework 2.0 an.|  
|`ACR_EquivalentPartialMatch`|Gibt eine teilgleiche Übereinstimmung der Assemblys an.|  
|`ACR_EquivalentPartialUnified`|Gibt eine teilweise Übereinstimmung der Assemblys basierend auf der älteren Vereinheitlichung von Versionsnummern an.|  
|`ACR_EquivalentPartialWeakNamed`|Gibt eine partielle Übereinstimmung von einfach benannten Assemblys an.|  
|`ACR_EquivalentUnified`|Gibt an, dass Assemblys basierend auf der CLR-Vereinheitlichung von Versionsnummern in älteren Versionen von .NET Framework als gleichwertig betrachtet werden.|  
|`ACR_EquivalentWeakNamed`|Gibt eine Übereinstimmung zwischen zwei einfach benannten Assemblys an, deren Versionsnummern ignoriert wurden.|  
|`ACR_NonEquivalent`|Gibt an, dass keine Übereinstimmung zwischen den beiden Assemblys aufgetreten ist.|  
|`ACR_NonEquivalentPartialVersion`|Gibt an, dass die beiden Assemblys mit Ausnahme ihrer Versionsnummern übereinstimmen, die nur teilweise übereinstimmen.|  
|`ACR_NonEquivalentVersion`|Gibt an, dass die beiden Assemblys mit Ausnahme ihrer Versionsnummern übereinstimmen, die nicht übereinstimmen.|  
|`ACR_Unknown`|Gibt an, dass der Grund für die Nichtäquivalenz nicht bekannt ist.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** Fusion.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [CompareAssemblyIdentity-Funktion](compareassemblyidentity-function.md)
- [Fusionsenumerationen](fusion-enumerations.md)
