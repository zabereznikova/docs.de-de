---
title: ICorDebugExceptionObjectCallStackEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
ms.openlocfilehash: 38de810509f15cf93475eb000837892b99684fc9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782752"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a>ICorDebugExceptionObjectCallStackEnum::Next-Methode
Ruft die angegebene Anzahl von [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Instanzen ab, die Informationen aus der-Rückruf Stapel eines Ausnahme Objekts enthalten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `celt`  
 in Die Anzahl der abzurufenden [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Instanzen.  
  
 `values`  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Objekt verweist.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Instanzen, die tatsächlich zurückgegeben werden.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugExceptionObjectCallStackEnum-Schnittstelle](icordebugexceptionobjectcallstackenum-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
