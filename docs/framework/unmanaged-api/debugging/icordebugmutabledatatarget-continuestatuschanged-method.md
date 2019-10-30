---
title: 'Icordebugmutabledatatarget:: continuestatuschangi-Methode'
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
ms.openlocfilehash: abaf2d0542e16f526ecbe369370c31c225808f1f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139352"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a>Icordebugmutabledatatarget:: continuestatuschangi-Methode
Ändert den Fortsetzungsstatus für das ausstehende Debugereignis für den angegebenen Thread.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwThreadId`  
 Der vom Betriebssystem definierte Threadbezeichner.  
  
 `continueStatus`  
 Ein [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)-Wert, der den neuen angeforderten Fortsetzungsstatus angibt.  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger ruft die `ContinueStatusChanged`-Methode auf, wenn er eine ICorDebug-Methode aufruft, die erfordert, dass das aktuelle Debugereignis auf eine Weise behandelt wird, die sich möglicherweise von der Weise unterscheidet, auf die es normalerweise behandelt würde. Gibt es beispielsweise eine ausstehende Ausnahme, und der Debugger fordert einen Vorgang an, der die Ausnahme abbrechen würde (z.B. [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) oder `FuncEval`), wird über diese API angefordert, dass die Ausnahme abgebrochen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugMutableDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
