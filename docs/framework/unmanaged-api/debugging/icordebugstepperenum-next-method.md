---
title: ICorDebugStepperEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ac3165ab17eb1b4bc55a4bee4d2d2b467f8aefe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987401"
---
# <a name="icordebugstepperenumnext-method"></a>ICorDebugStepperEnum::Next-Methode
Ruft die angegebene Anzahl von ICorDebugStepper-Instanzen aus der Enumeration ab, an der aktuellen Position ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl der `ICorDebugStepper` Instanzen abgerufen werden sollen.  
  
 `steppers`  
 [out] Ein Array von Zeigern, die jeweils auf eine `ICorDebugStepper` Objekt.  
  
 `pceltFetched`  
 [out] Zeiger auf die Anzahl der `ICorDebugStepper` Instanzen, die tatsächlich zurückgegeben. Dieser Wert kann null sein, wenn `celt` ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
