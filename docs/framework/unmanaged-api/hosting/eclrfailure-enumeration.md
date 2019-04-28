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
ms.openlocfilehash: 19dacae05766566521f563d0d24980c01dfb7a0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796122"
---
# <a name="eclrfailure-enumeration"></a>EClrFailure-Enumeration
Beschreibt die Fehler, die für die ein Host Richtlinienaktionen festlegen kann.  
  
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
|`FAIL_NonCriticalResource`|Fehler beim Versuch, eine Ressource (z. B. ein Thread, einen Speicherblock oder eine Sperre) reservieren in einen nicht-kritische Codebereich.|  
|`FAIL_CriticalResource`|Fehler beim Versuch, reservieren eine Ressource (z. B. ein Thread, einen Speicherblock oder eine Sperre) in einem kritischen Bereich des Codes.|  
|`FAIL_FatalRuntime`|Die common Language Runtime (CLR) ist nicht mehr in der Lage, verwalteten Code im Prozess ausgeführt. Damit geben Aufrufe alle Hostingfunktionen HOST_E_CLRNOTAVAILABLE einen HRESULT-Wert zurück.|  
|`FAIL_OrphanedLock`|Hat Fehler durch einen Thread eine Sperre nach dem Beenden einer <xref:System.AppDomain> Objekt. Der Host kann nicht dazu, die dazu führen, dass einen Thread abgebrochen festlegen.|  
|`FAIL_StackOverflow`|Es ist ein Stapelüberlauf aufgetreten.|  
|`FAIL_AccessViolation`|Es wurde versucht, das Lesen und Schreiben von geschütztem Arbeitsspeicher. Nicht unterstützt, die der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].|  
|`FAIL_CodeContract`|Ein Code-Contract-Fehler aufgetreten. Finden Sie unter [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter den [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) -Methode für eine Liste der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, die der Host kann mit der Aktionen für fehlerbedingungen an. Weitere Informationen zu wichtigen und nicht kritische Bereiche des Codes, finden Sie unter [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [SetActionOnFailure-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
