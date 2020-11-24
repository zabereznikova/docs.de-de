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
ms.openlocfilehash: a713fd006f1e9ad8fe7109651c2cda5025da3566
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673942"
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
 in Ein- `CORDB_ADDRESS` Wert, der die Adresse angibt, an der der Breakpoint festgelegt wurde.  
  
## <a name="remarks"></a>Hinweise  

 Der angegebene Haltepunkt hätte zuvor durch einen früheren [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)-Befehl festgelegt.  
  
 Die- `ClearUnmanagedBreakpoint` Methode kann aufgerufen werden, während der Prozess, der debuggt wird, ausgeführt wird.  
  
 Die- `ClearUnmanagedBreakpoint` Methode gibt einen Fehlercode zurück, wenn der Debugger im reinen Modus angefügt wird oder wenn an der angegebenen Adresse kein Haltepunkt vorhanden ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
