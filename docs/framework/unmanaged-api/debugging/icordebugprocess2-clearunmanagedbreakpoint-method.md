---
title: ICorDebugProcess2::ClearUnmanagedBreakpoint-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
ms.openlocfilehash: 8377ead42c752d8ebe9813d9e00662b94339f8a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137245"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a>ICorDebugProcess2::ClearUnmanagedBreakpoint-Methode
Entfernt einen zuvor festgelegten Haltepunkt an der angegebenen Adresse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `address`  
 in Ein `CORDB_ADDRESS` Wert, der die Adresse angibt, an der der Breakpoint festgelegt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Der angegebene Haltepunkt hätte zuvor durch einen früheren [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)-Befehl festgelegt.  
  
 Die `ClearUnmanagedBreakpoint`-Methode kann aufgerufen werden, während der Prozess, der debuggt wird, ausgeführt wird.  
  
 Die `ClearUnmanagedBreakpoint`-Methode gibt einen Fehlercode zurück, wenn der Debugger im verwalteten Modus angefügt wird oder wenn an der angegebenen Adresse kein Haltepunkt vorhanden ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
