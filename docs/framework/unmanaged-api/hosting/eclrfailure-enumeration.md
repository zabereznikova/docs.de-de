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
ms.openlocfilehash: 7d935bff023d806cf8cfb6d87bde0f82666b51b5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131127"
---
# <a name="eclrfailure-enumeration"></a>EClrFailure-Enumeration
Beschreibt den Satz von Fehlern, bei denen ein Host Richtlinien Aktionen festlegen kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`FAIL_NonCriticalResource`|Beim Versuch, eine Ressource (z. b. einen Thread, einen Speicherblock oder eine Sperre) in einem nicht kritischen Code Bereich zuzuordnen, ist ein Fehler aufgetreten.|  
|`FAIL_CriticalResource`|Beim Versuch, eine Ressource (z. b. einen Thread, einen Speicherblock oder eine Sperre) in einem kritischen Code Bereich zuzuordnen, ist ein Fehler aufgetreten.|  
|`FAIL_FatalRuntime`|Der Common Language Runtime (CLR) ist nicht mehr in der Lage, verwalteten Code im Prozess auszuführen. Bei Aufrufen von-Hostingfunktionen wird ein HRESULT-Wert von HOST_E_CLRNOTAVAILABLE zurückgegeben.|  
|`FAIL_OrphanedLock`|Ein Thread konnte eine Sperre nicht freigeben, wenn er von einem <xref:System.AppDomain> Objekt zurückgegeben wurde. Dieser Fehler kann vom Host nicht festgelegt werden, damit ein Thread abgebrochen wird.|  
|`FAIL_StackOverflow`|Ein Stapelüberlauf ist aufgetreten.|  
|`FAIL_AccessViolation`|Es wurde versucht, geschützten Speicher zu lesen oder zu schreiben. Wird in der .NET Framework 4 nicht unterstützt.|  
|`FAIL_CodeContract`|Ein Code Vertrags Fehler ist aufgetreten. Siehe [Code Verträge](../../../../docs/framework/debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Hinweise  
 In der [ICLRPolicyManager:: abtactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) -Methode finden Sie eine Liste der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) -Werte, mit denen der Host die Richtlinien Aktionen für Fehlerbedingungen angeben kann. Weitere Informationen zu kritischen und nicht kritischen Codebereichen finden Sie unter [eclroperations](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [SetActionOnFailure-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
