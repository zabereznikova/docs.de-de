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
ms.openlocfilehash: bc34ab9c8dbfe10282f36a241a4e433debef7dd0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420494"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a>ICorDebugProcess2::ClearUnmanagedBreakpoint-Methode
Entfernt einen zuvor festgelegten Haltepunkt an der angegebenen Adresse.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `address`  
 [in] Ein `CORDB_ADDRESS` Wert, der die Adresse angibt, an dem der Haltepunkt festgelegt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die angegebene Breakpoint würde zuvor festgelegten durch einen früheren Aufruf [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Die `ClearUnmanagedBreakpoint` Methode kann aufgerufen werden, während der zu debuggende Prozess ausgeführt wird.  
  
 Die `ClearUnmanagedBreakpoint` Methode gibt einen Fehlercode zurück, wenn der Debugger im ausschließlich verwalteten Modus verbunden ist oder wenn kein Haltepunkt an der angegebenen Adresse vorhanden ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
