---
title: EClrFailure-Enumeration
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef4e12015adc3d6e67ad9c8ba8b152cd775b85e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431928"
---
# <a name="eclrfailure-enumeration"></a>EClrFailure-Enumeration
Beschreibt den Satz von Fehlern, die für die ein Host Richtlinienaktionen festlegen kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|Fehler beim belegen von einer Ressource (z. B. einen Thread, einen Speicherblock oder eine Sperre) in einem unkritische Codebereich.|  
|`FAIL_CriticalResource`|Fehler beim belegen von einer Ressource (z. B. einen Thread, einen Speicherblock oder eine Sperre) in einem kritischen Codebereich.|  
|`FAIL_FatalRuntime`|Die common Language Runtime (CLR) ist nicht mehr in der Lage, verwalteten Code im Prozess ausgeführt. Damit Aufrufe hosting-Funktionen die HRESULT-Wert HOST_E_CLRNOTAVAILABLE zurückgeben.|  
|`FAIL_OrphanedLock`|Fehler durch einen Thread hat auf eine Sperre bei der Rückkehr aus einer <xref:System.AppDomain> Objekt. Der Host kann dieses Fehlers darin, dass einen Thread zum Abbrechen nicht festgelegt.|  
|`FAIL_StackOverflow`|Ein Stapelüberlauf aufgetreten.|  
|`FAIL_AccessViolation`|Es wurde versucht, das Lesen und Schreiben von geschütztem Arbeitsspeicher. Nicht unterstützt, die der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].|  
|`FAIL_CodeContract`|Ein Code-Vertrags-Fehler aufgetreten. Finden Sie unter [Code Verträge](../../../../docs/framework/debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter der [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) Methode eine Liste der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, die der Host Sie die Richtlinienaktionen fehlerbedingungen angeben können. Weitere Informationen über kritische und nicht kritische Bereiche des Codes finden Sie unter [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [SetActionOnFailure-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
