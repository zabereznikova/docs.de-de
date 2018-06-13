---
title: ICorDebugFrame::CreateStepper-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3662ed8a3fda5881b0e0929a830d19b0d805299f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411030"
---
# <a name="icordebugframecreatestepper-method"></a>ICorDebugFrame::CreateStepper-Methode
Ruft eine zugeordnetem, die dem Debugger ermöglicht, die relativ zu diesem ICorDebugFrame schrittweisen Vorgänge ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppStepper`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugStepper-Objekts, das dem Debugger ermöglicht, relativ zum aktuellen Rahmen schrittweisen Vorgänge.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Frame nicht aktiv ist, müssen das zugeordnetem-Objekt in der Regel auf den Frame zurück, bevor der Schritt abgeschlossen ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
