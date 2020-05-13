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
ms.openlocfilehash: 39b4e7e5123447a36254b55b6168c80e48c8dcab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205449"
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
