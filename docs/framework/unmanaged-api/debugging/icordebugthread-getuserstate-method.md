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
ms.openlocfilehash: d1ff3427feb5dc8395bbb2fda78e3e93e1a1a8f0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378858"
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
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
