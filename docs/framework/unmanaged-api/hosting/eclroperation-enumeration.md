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
ms.openlocfilehash: 4b18c89cee0c3f5088a9978e448a0d61de1b9848
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434244"
---
# <a name="eclroperation-enumeration"></a>EClrOperation-Enumeration
Beschreibt den Satz von Vorgängen, die für die Richtlinienaktionen ein Host angewendet werden kann.  
  
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
|`OPR_AppDomainRudeUnload`|Der Host kann die Richtlinienaktionen durchgeführt werden sollen angeben einer <xref:System.AppDomain> nicht ordnungsgemäße (grobe) Weise entladen wird.|  
|`OPR_AppDomainUnload`|Der Host kann die Richtlinienaktionen durchgeführt werden sollen angeben einer <xref:System.AppDomain> wird entladen.|  
|`OPR_FinalizerRun`|Der Host kann die Richtlinienaktionen, die ausgeführt werden, wenn Finalizer angeben.|  
|`OPR_ProcessExit`|Der Host kann angeben, Richtlinienaktionen, die ausgeführt werden, wenn der Prozess beendet wird.|  
|`OPR_ThreadAbort`|Der Host kann die Richtlinienaktionen, die ausgeführt werden, nach dem Abbrechen eines Threads angeben.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|Der Host kann die Richtlinienaktionen, die ausgeführt werden, tritt eine grobe Threadabbruchs in einem kritischen Codebereich angeben.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|Der Host kann die Richtlinienaktionen durchgeführt werden, tritt eine grobe Threadabbruchs in einem unkritische Codebereich angeben.|  
  
## <a name="remarks"></a>Hinweise  
 Die common Language Runtime (CLR) Zuverlässigkeit Infrastruktur unterscheidet zwischen abgebrochen und Ressource belegungsfehler angezeigt, die in kritischen Bereiche des Codes und those, die occur an in unkritische Bereiche des Codes auftreten. Diese Unterscheidung dient zum Zulassen von Hosts, die verschiedene Richtlinien, je nachdem, wo eines im Code Fehlers festzulegen.  
  
 Ein *kritischen Codebereich* ist eine Stelle, wo die CLR kann nicht garantieren, eine Aufgabe oder ein auf eine Anforderung nicht abschließen für Ressourcen nur auf den aktuellen Task auswirkt. Beispielsweise, wenn eine Aufgabe ist eine Sperre aufrechterhält, und ein HRESULT, das erhält bei einer speicherbelegungsanforderung Fehler weist darauf hin, ist es nicht ausreichend, einfach, um diese Aufgabe aus, um sicherzustellen, dass die Stabilität der Abbruch der <xref:System.AppDomain>, da die <xref:System.AppDomain> enthält möglicherweise andere Aufgaben, die die gleiche Sperre warten. Für das Abbrechen des aktuellen Aufgabe kann dazu führen, dass die andere Tasks reagiert (oder bleibt hängen) unbegrenzt. In diesem Fall benötigt der Host die Möglichkeit, den gesamten entladen <xref:System.AppDomain> anstatt potenzielle Instabilität Risiko.  
  
 Ein *unkritische Codebereich*, eine Region, in denen die CLR garantieren kann, dass ein Abbruch oder Fehler nur auf den Task auswirkt auf dem der Fehler tritt auf, auf der anderen Seite ist.  
  
 Die CLR unterscheidet sich auch zwischen ordnungsgemäßes und nicht ordnungsgemäß (grobe) abgebrochen. Im Allgemeinen wird einem normalen oder ordnungsgemäßen Abbruch bemüht, Ausnahmebehandlung und Finalizer vor dem Abbrechen einer Aufgabe trotz aller bemühungen Ausnahmebehandlungsroutinen solche Garantien ausführen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [EClrFailure-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [EPolicyAction-Enumeration](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
