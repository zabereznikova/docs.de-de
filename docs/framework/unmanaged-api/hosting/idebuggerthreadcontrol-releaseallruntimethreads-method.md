---
title: IDebuggerThreadControl::ReleaseAllRuntimeThreads-Methode
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5e2501a5ab62c6aaef2b3f754f9eed10e4e4b97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505021"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a>IDebuggerThreadControl::ReleaseAllRuntimeThreads-Methode
Benachrichtigt den Host, dass die Debuggen von Diensten sind im Begriff, die alle Threads freigegeben, die blockiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `ReleaseAllRuntimeThreads` Methode nie in einem Runtime-Thread aufgerufen. Wenn der Host einen Common Language Runtime-Thread blockiert ist, sollte er es jetzt freigeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IDebuggerThreadControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
