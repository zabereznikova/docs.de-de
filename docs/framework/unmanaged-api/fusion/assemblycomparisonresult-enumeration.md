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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82b81ec29dece182548ead046edc7cb754fbf00e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult-Enumeration
Gibt die Gleichwertigkeit von zwei Assemblyidentitäten an, durch die [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
## <a name="members"></a>Member  
  
|Membername|Beschreibung|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Gibt an, dass alle im Vergleich übereinstimmen Assemblyfelder.|  
|`ACR_EquivalentFXUnified`|Gibt an, dass Assemblys als gleichwertig basierend auf die common Language Runtime-Version (CLR) Vereinheitlichung von Assemblyversionsnummern in .NET Framework, Version 2.0 betrachtet werden.|  
|`ACR_EquivalentPartialFXUnified`|Gibt eine partielle Übereinstimmung der basierend auf die CLR-Vereinheitlichung der Assemblyversionsnummern in .NET Framework 2.0-Assemblys an.|  
|`ACR_EquivalentPartialMatch`|Gibt eine partielle Übereinstimmung der Assemblys an.|  
|`ACR_EquivalentPartialUnified`|Gibt eine partielle Übereinstimmung basierend auf älteren Vereinheitlichung der Versionsnummern Assemblys an.|  
|`ACR_EquivalentPartialWeakNamed`|Gibt eine partielle Übereinstimmung von Assemblys mit einfachen Namen an.|  
|`ACR_EquivalentUnified`|Gibt an, dass Assemblys als gleichwertig basierend auf die CLR-Vereinheitlichung der Versionsnummern in älteren Versionen von .NET Framework betrachtet werden.|  
|`ACR_EquivalentWeakNamed`|Gibt an, eine Übereinstimmung zwischen zwei Assemblys mit einfachen Namen, deren Versionsnummern ignoriert wurden.|  
|`ACR_NonEquivalent`|Gibt an, dass keine Übereinstimmung zwischen den beiden Assemblys aufgetreten ist.|  
|`ACR_NonEquivalentPartialVersion`|Gibt an, dass die zwei Assemblys mit Ausnahme von deren Versionsnummern übereinstimmen, die nur teilweise übereinstimmen.|  
|`ACR_NonEquivalentVersion`|Gibt an, dass die zwei Assemblys mit Ausnahme von deren Versionsnummern übereinstimmen, was die stimmen nicht überein.|  
|`ACR_Unknown`|Gibt an, dass die Ursache für nicht vorhandene Äquivalenz nicht bekannt ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [CompareAssemblyIdentity-Funktion](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 [Fusion-Enumerationen](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
