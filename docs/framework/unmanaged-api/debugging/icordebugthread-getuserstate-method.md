---
title: ICorDebugThread::GetUserState-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
ms.openlocfilehash: f3511ff5ee9b9221037c64a5e17d61f6bf52e5f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133421"
---
# <a name="icordebugthreadgetuserstate-method"></a>ICorDebugThread::GetUserState-Methode
Ruft den aktuellen Benutzer Zustand dieses ICorDebugThread ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pState`  
 vorgenommen Ein Zeiger auf eine bitweise Kombination von CorDebugUserState-Enumerationswerten, die den aktuellen Benutzer Zustand dieses Threads beschreiben.  
  
## <a name="remarks"></a>Hinweise  
 Der Benutzer Zustand des Threads ist der Zustand des Threads, wenn er von dem Programm überprüft wird, das gerade deentschlgt wird. Für einen Thread sind möglicherweise mehrere State-Bits festgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
