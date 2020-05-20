---
title: EClrOperation-Enumeration
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
ms.openlocfilehash: e7cb1c2070e760258e548d2f45e3b6ed11e046c4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616319"
---
# <a name="eclroperation-enumeration"></a>EClrOperation-Enumeration
Beschreibt den Satz von Vorgängen, für die ein Host Richtlinien Aktionen anwenden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn eine <xref:System.AppDomain> nicht ordnungsgemäß (grob) entladen wird.|  
|`OPR_AppDomainUnload`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein <xref:System.AppDomain> entladen wird.|  
|`OPR_FinalizerRun`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn Finalizer ausgeführt werden.|  
|`OPR_ProcessExit`|Der Host kann Richtlinien Aktionen angeben, die durchgeführt werden sollen, wenn der Prozess beendet wird.|  
|`OPR_ThreadAbort`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein Thread abgebrochen wird.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein unhöflicher Thread Abbruch in einem kritischen Code Bereich auftritt.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein grober Thread Abbruch in einem nicht kritischen Code Bereich auftritt.|  
  
## <a name="remarks"></a>Hinweise  
 Die Common Language Runtime (CLR)-Zuverlässigkeits Infrastruktur unterscheidet zwischen Abbrüchen und Ressourcen Zuordnungs Fehlern, die in kritischen Codebereichen auftreten, sowie in nicht kritischen Codebereichen. Dieser Unterschied ist so konzipiert, dass Hosts verschiedene Richtlinien festlegen können, je nachdem, wo ein Fehler im Code auftritt.  
  
 Ein *kritischer Bereich von Code* ist ein beliebiger Speicherplatz, der von der CLR nicht garantiert werden kann, dass das Abbrechen einer Aufgabe oder das Fehlschlagen einer Anforderung für Ressourcen nur die aktuelle Aufgabe beeinträchtigt. Wenn eine Aufgabe z. b. eine Sperre aufrecht erhält und ein HRESULT empfängt, das einen Fehler beim Erstellen einer Speicher Belegungs Anforderung angibt, genügt es nicht, diese Aufgabe abzubrechen, um die Stabilität des zu gewährleisten <xref:System.AppDomain> , da das <xref:System.AppDomain> möglicherweise andere Tasks enthält, die auf die gleiche Sperre warten. Das Abbrechen der aktuellen Aufgabe kann dazu führen, dass diese anderen Tasks nicht mehr reagieren. In einem solchen Fall benötigt der Host die Möglichkeit, die gesamte zu entladen, <xref:System.AppDomain> anstatt potenzielle Instabilität zu gefährden.  
  
 Ein *nicht kritischer Code Bereich*ist andererseits eine Region, in der die CLR gewährleisten kann, dass ein Abbruch oder ein Fehler nur die Aufgabe beeinträchtigt, bei der der Fehler auftritt.  
  
 Die CLR unterscheidet auch zwischen ordnungsgemäßen und nicht ordnungsgemäßen (unhöflichen) Abbrüchen. Im Allgemeinen macht ein normaler oder ordnungsgemäßer Abbruch jeden Aufwand, um Routinen und Finalizer für die Ausnahmebehandlung auszuführen, bevor eine Aufgabe abgebrochen wird, während ein unhöflicher Abbruch keine Garantie dafür gibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](eclrfailure-enumeration.md)
- [EPolicyAction-Enumeration](epolicyaction-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](iclrpolicymanager-interface.md)
- [IHostPolicyManager-Schnittstelle](ihostpolicymanager-interface.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
