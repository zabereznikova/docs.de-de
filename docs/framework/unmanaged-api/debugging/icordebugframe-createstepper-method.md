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
ms.openlocfilehash: 5dfb64d0c440cbd2c8a8a65b2c18d78f02a7615e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679714"
---
# <a name="icordebugframecreatestepper-method"></a>ICorDebugFrame::CreateStepper-Methode

Ruft einen Stepper ab, der dem Debugger das Ausführen von schrittweise Vorgängen in Relation zu diesem ICorDebugFrame ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppStepper`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugStepper-Objekts, das es dem Debugger ermöglicht, schrittweise Vorgänge in Relation zum aktuellen Frame auszuführen.  
  
## <a name="remarks"></a>Hinweise  

 Wenn der Frame nicht aktiv ist, muss das Stepper-Objekt in der Regel zum Frame zurückkehren, bevor der Schritt abgeschlossen ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
