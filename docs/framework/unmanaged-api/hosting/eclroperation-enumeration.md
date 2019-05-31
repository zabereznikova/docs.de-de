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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9bbff8bb1f095502f27b649639434010453ffe1
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423853"
---
# <a name="eclroperation-enumeration"></a>EClrOperation-Enumeration
Beschreibt die Vorgänge, die für die ein Host Richtlinienaktionen anwenden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`OPR_AppDomainRudeUnload`|Der Host kann Aktionen durchgeführt werden sollen angeben einer <xref:System.AppDomain> Weise eine nicht ordnungsgemäß (grobe) entladen wird.|  
|`OPR_AppDomainUnload`|Der Host kann Aktionen durchgeführt werden sollen angeben einer <xref:System.AppDomain> entladen wird.|  
|`OPR_FinalizerRun`|Der Host kann die Richtlinienaktionen ausgeführt werden, wenn der Finalizer ausgeführt angeben.|  
|`OPR_ProcessExit`|Der Host kann angeben, Richtlinienaktionen ausgeführt werden, wenn der Prozess beendet wird.|  
|`OPR_ThreadAbort`|Der Host kann die Richtlinienaktionen ausgeführt werden, wenn ein Thread abgebrochen angeben.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|Der Host kann die Richtlinienaktionen ausgeführt werden, tritt ein grobe Threadabbruch in einem kritischen Bereich des Codes angeben.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|Der Host kann die Richtlinienaktionen durchgeführt werden, tritt ein grobe Threadabbruch in einen nicht-kritische Codebereich angeben.|  
  
## <a name="remarks"></a>Hinweise  
 Die common Language Runtime (CLR) zuverlässigkeitsinfrastruktur unterscheidet zwischen Abbrüche und Ressource Fehler bei der Zuordnung, die auftreten, die im kritischen Bereich des Codes und diejenigen, die in nicht-kritische Bereiche des Codes auftreten. Diese Unterscheidung soll es ermöglicht Hosts, die verschiedene Richtlinien, je nachdem, in denen eines im Code Fehlers festzulegen.  
  
 Ein *des kritischen Codebereichs* ist eine beliebige Stelle, in denen die CLR kann nicht garantieren, diese eine Aufgabe oder Fehler beim Abschluss einer Anforderung für Ressourcen nur den aktuellen Task auswirkt. Z. B. wenn ein Task eine Sperre wird und empfängt ein HRESULT, das Fehler beim Erstellen einer speicherbelegungsanforderung weist darauf hin, es ist nicht ausreichend, einfach, um diese Aufgabe aus, um sicherzustellen, dass die Stabilität der Abbruch der <xref:System.AppDomain>, da die <xref:System.AppDomain> enthält möglicherweise andere Aufgaben, die die gleiche Sperre warten. Zum Verwerfen der aktuellen dazu Aufgabe diese Aufgaben nicht mehr reagiert. In diesem Fall benötigt der Host die Möglichkeit, den gesamten entladen <xref:System.AppDomain> statt Risiko potenzieller Systeminstabilität zur Folge.  
  
 Ein *unkritische Codebereich*, auf der anderen Seite ist eine Region, in denen die CLR garantieren kann, dass ein Abbruch oder Fehler auf dem der Fehler tritt nur auf die Aufgabe beeinflussen.  
  
 Die CLR unterscheidet sich auch zwischen ordnungsgemäßen und nicht ordnungsgemäß (grobe) abgebrochen. Im Allgemeinen wird einem normalen oder ordnungsgemäßen Abbruch höchste anstrengungen, um die Behandlung von Ausnahmen und Finalizer ausgeführt, bevor eine Aufgabe, Ausnahmebehandlungsroutinen solche garantiert wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EPolicyAction-Enumeration](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
