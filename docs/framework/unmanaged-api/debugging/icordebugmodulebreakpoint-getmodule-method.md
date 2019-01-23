---
title: ICorDebugModuleBreakpoint::GetModule-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce53137021fe9ccaf170bed28918b8f5fe87715b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504990"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a>ICorDebugModuleBreakpoint::GetModule-Methode
Ruft einen Schnittstellenzeiger auf ein "ICorDebugModule", die das Modul verweist, in dem dieser Haltepunkt festgelegt ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppModule`  
 [out] Ein Zeiger auf die Adresse einer `ICorDebugModule` -Schnittstelle, die das Modul verweist, in dem der Haltepunkt festgelegt ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

