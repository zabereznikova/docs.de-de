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
ms.openlocfilehash: 6becc44b061ff2baac63437b6a72375d1c3735b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131159"
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
|`OPR_AppDomainRudeUnload`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein <xref:System.AppDomain> in einer nicht ordnungsgemäßen (unhöflichen) Art entladen wird.|  
|`OPR_AppDomainUnload`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein <xref:System.AppDomain> entladen wird.|  
|`OPR_FinalizerRun`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn Finalizer ausgeführt werden.|  
|`OPR_ProcessExit`|Der Host kann Richtlinien Aktionen angeben, die durchgeführt werden sollen, wenn der Prozess beendet wird.|  
|`OPR_ThreadAbort`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein Thread abgebrochen wird.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein unhöflicher Thread Abbruch in einem kritischen Code Bereich auftritt.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein grober Thread Abbruch in einem nicht kritischen Code Bereich auftritt.|  
  
## <a name="remarks"></a>Hinweise  
 Die Common Language Runtime (CLR)-Zuverlässigkeits Infrastruktur unterscheidet zwischen Abbrüchen und Ressourcen Zuordnungs Fehlern, die in kritischen Codebereichen auftreten, sowie in nicht kritischen Codebereichen. Dieser Unterschied ist so konzipiert, dass Hosts verschiedene Richtlinien festlegen können, je nachdem, wo ein Fehler im Code auftritt.  
  
 Ein *kritischer Bereich von Code* ist ein beliebiger Speicherplatz, der von der CLR nicht garantiert werden kann, dass das Abbrechen einer Aufgabe oder das Fehlschlagen einer Anforderung für Ressourcen nur die aktuelle Aufgabe beeinträchtigt. Wenn eine Aufgabe z. b. eine Sperre aufrecht erhält und ein HRESULT empfängt, das auf einen Fehler beim Erstellen einer Speicher Belegungs Anforderung hinweist, genügt es nicht, diese Aufgabe abzubrechen, um die Stabilität des <xref:System.AppDomain>zu gewährleisten, da die <xref:System.AppDomain> möglicherweise andere Tasks enthält. Es wird auf die gleiche Sperre gewartet. Das Abbrechen der aktuellen Aufgabe kann dazu führen, dass diese anderen Tasks nicht mehr reagieren. In einem solchen Fall benötigt der Host die Möglichkeit, die gesamte <xref:System.AppDomain> zu entladen, anstatt potenzielle Instabilität zu gefährden.  
  
 Ein *nicht kritischer Code Bereich*ist andererseits eine Region, in der die CLR gewährleisten kann, dass ein Abbruch oder ein Fehler nur die Aufgabe beeinträchtigt, bei der der Fehler auftritt.  
  
 Die CLR unterscheidet auch zwischen ordnungsgemäßen und nicht ordnungsgemäßen (unhöflichen) Abbrüchen. Im Allgemeinen macht ein normaler oder ordnungsgemäßer Abbruch jeden Aufwand, um Routinen und Finalizer für die Ausnahmebehandlung auszuführen, bevor eine Aufgabe abgebrochen wird, während ein unhöflicher Abbruch keine Garantie dafür gibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EPolicyAction-Enumeration](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
