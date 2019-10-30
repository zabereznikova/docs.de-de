---
title: ICorConfiguration::SetGCThreadControl-Methode
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: f43ee6d9a3832fca1766ec27c9f02d1aab2f5b8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127773"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a>ICorConfiguration::SetGCThreadControl-Methode
Legt die Rückruf Schnittstelle für das Planen von Threads für nicht-Lauf Zeit Aufgaben fest, die andernfalls für eine Garbage Collection blockiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pGCThreadControl`  
 in Ein Zeiger auf ein [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) -Objekt, das den Host über die Unterbrechung von Threads für nicht-Lauf Zeit Aufgaben benachrichtigt.  
  
## <a name="remarks"></a>Hinweise  
 Der Host kann im [IGCThreadControl:: ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) -Rückruf auswählen, ob ein Thread neu geplant werden soll.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorConfiguration-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
