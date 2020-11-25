---
title: ICorDebugProcess::IsOSSuspended-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
ms.openlocfilehash: fffa61d8e406162251b0934a9846e5a813422798
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724584"
---
# <a name="icordebugprocessisossuspended-method"></a>ICorDebugProcess::IsOSSuspended-Methode

Ruft einen Wert ab, der angibt, ob der angegebene Thread angehalten wurde, weil der Debugger diesen Prozess beendet hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a>Parameter  

 `threadID`  
 in Die ID des fraglichen Threads.  
  
 `pbSuspended`  
 vorgenommen Ein Zeiger auf einen booleschen Wert, der ist, `true` Wenn der angegebene Thread angehalten wurde, andernfalls * `pbSuspended` ist `false` .  
  
## <a name="remarks"></a>Hinweise  

 Wenn der angegebene Thread durch den Debugger angehalten wurde, der diesen Prozess beendet, wird die Win32-anhalteanzahl des angegebenen Threads um 1 erhöht. Diese Informationen können von der Benutzeroberfläche des Debuggers berücksichtigt werden, wenn das Betriebssystem (OS) der Thread Anzahl für den Benutzer angezeigt wird.  
  
 Die- `IsOSSuspended` Methode ist nur im Kontext des nicht verwalteten Debuggens sinnvoll. Während des verwalteten Debuggens werden Threads gemeinsam angehalten und nicht als Betriebssystem angehalten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
