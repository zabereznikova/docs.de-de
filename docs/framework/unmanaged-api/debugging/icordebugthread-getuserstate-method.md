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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4deaa3ab4b14fbd32d45841966cfac9e33b9f31
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987071"
---
# <a name="icordebugthreadgetuserstate-method"></a>ICorDebugThread::GetUserState-Methode
Ruft den aktuellen Benutzerzustand dieses ICorDebugThread ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pState`  
 [out] Ein Zeiger auf eine bitweise Kombination von CorDebugUserState-Enumerationswerte, die den aktuellen Benutzerzustand dieses Threads beschreiben.  
  
## <a name="remarks"></a>Hinweise  
 Der Benutzerzustand des Threads ist der Zustand des Threads an, wenn er von der Anwendung überprüft wird, der debuggt wird. Ein Thread möglicherweise mehrere Statusbits festgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
