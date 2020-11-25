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
ms.openlocfilehash: cde25a9507006c89ef6490c13ae82033f04c2931
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731032"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult-Enumeration

Gibt die Äquivalenz zweier Assemblyidentitäten an, die durch die [CompareAssemblyIdentity](compareassemblyidentity-function.md) -Funktion bestimmt werden.  
  
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
  
## <a name="members"></a>Member  
  
|Membername|BESCHREIBUNG|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Gibt an, dass alle Assemblyfelder im Vergleich stimmen.|  
|`ACR_EquivalentFXUnified`|Gibt an, dass Assemblys basierend auf der CLR-Vereinheitlichung (Common Language Runtime Version) der Assemblyversionsnummern in der .NET Framework Version 2,0 als äquivalent betrachtet werden|  
|`ACR_EquivalentPartialFXUnified`|Gibt eine Teil Übereinstimmung der Assemblys basierend auf der CLR-Vereinheitlichung der Assemblyversionsnummern im .NET Framework 2,0 an.|  
|`ACR_EquivalentPartialMatch`|Gibt eine Teil Übereinstimmung der Assemblys an.|  
|`ACR_EquivalentPartialUnified`|Gibt eine Teil Übereinstimmung der Assemblys basierend auf der Legacy-Vereinheitlichung von Versionsnummern an.|  
|`ACR_EquivalentPartialWeakNamed`|Gibt eine Teil Übereinstimmung von einfach benannten Assemblys an.|  
|`ACR_EquivalentUnified`|Gibt an, dass Assemblys basierend auf der CLR-Vereinheitlichung der Versionsnummern in älteren Versionen der .NET Framework als gleichwertig betrachtet werden.|  
|`ACR_EquivalentWeakNamed`|Gibt eine Entsprechung zwischen zwei einfach benannten Assemblys an, deren Versionsnummern ignoriert wurden.|  
|`ACR_NonEquivalent`|Gibt an, dass zwischen den beiden Assemblys keine Entsprechung vorliegt.|  
|`ACR_NonEquivalentPartialVersion`|Gibt an, dass die beiden Assemblys mit Ausnahme ihrer Versionsnummern stimmen, die nur teilweise abgeglichen werden.|  
|`ACR_NonEquivalentVersion`|Gibt an, dass die beiden Assemblys mit Ausnahme ihrer Versionsnummern stimmen, die nicht mit identisch sind.|  
|`ACR_Unknown`|Gibt an, dass der Grund für die nicht Äquivalenz nicht bekannt ist.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [CompareAssemblyIdentity-Funktion](compareassemblyidentity-function.md)
- [Fusionsenumerationen](fusion-enumerations.md)
