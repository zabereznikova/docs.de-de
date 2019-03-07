---
title: ICorConfiguration::SetDebuggerThreadControl-Methode
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cecbbd7509fcd4f79aeb6e2711e8b7604c2f3a9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489689"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a>ICorConfiguration::SetDebuggerThreadControl-Methode
Legt die Rückrufschnittstelle, die die Debuggen von Diensten für das Debuggen von aufrufen, wenn die common Language Runtime (CLR) Threads blockiert und freigegeben werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pDebuggerThreadControl`  
 [in] Ein Zeiger auf ein [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) -Objekt, das den Host zu blockieren und Entsperren von Threads von den Debugdiensten benachrichtigt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorConfiguration-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
