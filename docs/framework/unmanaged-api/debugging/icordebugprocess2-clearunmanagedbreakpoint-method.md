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
ms.openlocfilehash: e2aaf902afd71a4a81f7d64ef3fec046aacc91fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792532"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a>ICorDebugProcess2::ClearUnmanagedBreakpoint-Methode
Entfernt einen zuvor festgelegten Haltepunkt an der angegebenen Adresse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `address`  
 in Ein `CORDB_ADDRESS` Wert, der die Adresse angibt, an der der Breakpoint festgelegt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Der angegebene Haltepunkt hätte zuvor durch einen früheren [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)-Befehl festgelegt.  
  
 Die `ClearUnmanagedBreakpoint`-Methode kann aufgerufen werden, während der Prozess, der debuggt wird, ausgeführt wird.  
  
 Die `ClearUnmanagedBreakpoint`-Methode gibt einen Fehlercode zurück, wenn der Debugger im verwalteten Modus angefügt wird oder wenn an der angegebenen Adresse kein Haltepunkt vorhanden ist.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
