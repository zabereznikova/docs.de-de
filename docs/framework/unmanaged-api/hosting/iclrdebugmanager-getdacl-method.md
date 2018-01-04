---
title: ICLRDebugManager::GetDacl-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.GetDacl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::GetDacl
helpviewer_keywords:
- GetDacl method [.NET Framework hosting]
- ICLRDebugManager::GetDacl method [.NET Framework hosting]
ms.assetid: 7115e920-aaff-440a-824e-39497139c6f6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d21e95b24133cf0320c0e7bfb223d6bf1a7cf1b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagergetdacl-method"></a>ICLRDebugManager::GetDacl-Methode
Diese Methode ist nicht implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppacl`  
 [out] Ein Schnittstellenzeiger auf die Zugriffssteuerungsliste (ACL).  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|E_NOTIMPL|Die Methode ist nicht implementiert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRDebugManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [SetDacl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)  
 [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
