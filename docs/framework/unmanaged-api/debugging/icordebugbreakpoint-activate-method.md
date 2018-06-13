---
title: ICorDebugBreakpoint::Activate-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82dad6af545464baade2b82d65e7ad4dba19fe3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402339"
---
# <a name="icordebugbreakpointactivate-method"></a>ICorDebugBreakpoint::Activate-Methode
Legt den Zustand "aktiven" dieses `ICorDebugBreakpoint`.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `bActive`  
 [in] Legen Sie diesen Wert auf `true` an den Zustand als aktiv ist; andernfalls legen Sie diesen Wert auf `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
