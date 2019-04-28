---
title: IDebuggerThreadControl::StartBlockingForDebugger-Methode
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfc94c2de1a14842cc017e5c4ef6023154c20f2a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699902"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a>IDebuggerThreadControl::StartBlockingForDebugger-Methode
Benachrichtigt den Host, dass die Debuggen von Diensten zu beginnen, alle Threads blockiert sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwUnused`  
 [in] Für die zukünftige Verwendung reserviert.  
  
## <a name="remarks"></a>Hinweise  
 Die `StartBlockingForDebugger` Methode kann in einem Runtime-Thread aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IDebuggerThreadControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
