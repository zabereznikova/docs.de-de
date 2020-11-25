---
title: ICorDebugMDA::GetOSThreadId-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: 80248bba6d11b8af07aa0517cb41c8a4f783b5e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710895"
---
# <a name="icordebugmdagetosthreadid-method"></a>ICorDebugMDA::GetOSThreadId-Methode

Ruft den Thread Bezeichner des Betriebssystems ab, auf dem der von [ICorDebugMDA](icordebugmda-interface.md) dargestellte Assistent für verwaltetes Debuggen (MDA) ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pOsTid`  
 vorgenommen Ein Zeiger auf den Thread Bezeichner des Betriebssystems.  
  
## <a name="remarks"></a>Hinweise  

 Der Betriebssystem Thread wird anstelle eines ICorDebugThread verwendet, um Situationen zuzulassen, in denen ein MDA entweder in einem systemeigenen Thread oder in einem verwalteten Thread ausgelöst wird, der noch keinen verwalteten Code eingegeben hat.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugMDA-Schnittstelle](icordebugmda-interface.md)
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
