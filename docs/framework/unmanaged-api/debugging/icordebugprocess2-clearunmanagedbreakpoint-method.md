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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fb566ff2e5e2b0bcb096cead243ed65a904a914
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736979"
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
 [in] Ein `CORDB_ADDRESS` Wert, der die Adresse angibt, an dem der Haltepunkt festgelegt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die angegebene Breakpoint würde zuvor festgelegt wurden durch einen früheren Aufruf von [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Die `ClearUnmanagedBreakpoint` Methode kann aufgerufen werden, während der gedebuggte Prozess ausgeführt wird.  
  
 Die `ClearUnmanagedBreakpoint` Methode einen Fehlercode zurückgibt, wenn der Debugger im Modus "nur verwaltet" verbunden ist oder wenn kein Haltepunkt an der angegebenen Adresse vorhanden ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
