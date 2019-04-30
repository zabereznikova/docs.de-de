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
ms.openlocfilehash: 03b8ecc996e14263510e2d0a658cec020696c263
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914498"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult-Enumeration
Gibt die Gleichwertigkeit von zwei Assemblyidentitäten, bestimmt durch die [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) Funktion.  
  
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
|`ACR_EquivalentFXUnified`|Gibt an, dass Assemblys als gleichwertig basierend auf der common Language Runtime-Version (CLR) Vereinheitlichung von Assemblyversionsnummern in .NET Framework, Version 2.0 angesehen werden.|  
|`ACR_EquivalentPartialFXUnified`|Gibt eine teilweise Übereinstimmung der basierend auf der CLR-Vereinheitlichung der Assembly-Versionsnummern in .NET Framework 2.0-Assemblys an.|  
|`ACR_EquivalentPartialMatch`|Gibt eine teilweise Übereinstimmung der Assemblys an.|  
|`ACR_EquivalentPartialUnified`|Gibt eine teilweise Übereinstimmung der älteren aufgrund der Vereinheitlichung der Versionsnummern in Assemblys an.|  
|`ACR_EquivalentPartialWeakNamed`|Gibt eine teilweise Übereinstimmung von Assemblys mit einfachen Namen an.|  
|`ACR_EquivalentUnified`|Gibt an, dass Assemblys als gleichwertig basierend auf der CLR-Vereinheitlichung der Versionsnummern in älteren Versionen von .NET Framework angesehen werden.|  
|`ACR_EquivalentWeakNamed`|Gibt eine Übereinstimmung zwischen zwei Assemblys, die eine Verbindung, deren Versionsnummern ignoriert wurden, mit einfachen Namen an.|  
|`ACR_NonEquivalent`|Gibt an, dass keine Übereinstimmung zwischen den beiden Assemblys aufgetreten ist.|  
|`ACR_NonEquivalentPartialVersion`|Gibt an, dass die beiden Assemblys ihre Versionsnummern übereinstimmen, die nur teilweise übereinstimmen.|  
|`ACR_NonEquivalentVersion`|Gibt an, dass die beiden Assemblys ihre Versionsnummern übereinstimmen, die nicht übereinstimmen.|  
|`ACR_Unknown`|Gibt an, dass der Grund für nicht vorhandene Äquivalenz nicht bekannt ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CompareAssemblyIdentity-Funktion](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)
- [Fusion-Enumerationen](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
