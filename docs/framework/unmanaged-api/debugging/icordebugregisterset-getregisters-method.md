---
title: ICorDebugRegisterSet::GetRegisters-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ddefb1ac5694bf1f213dd77e0ffc7f746b7e62cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters-Methode
Ruft den Wert jedes Register (auf dem Computer, der Code derzeit ausgeführt wird), die durch die Bitmaske angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `mask`  
 [in] Eine Bitmaske, die angibt, welche Register Werte abgerufen werden sollen. Jedes Bit entspricht einer registriert wird. Wenn ein bit auf 1 festgelegt ist, wird der Wert des Registers abgerufen; Andernfalls ist der Wert des Registers nicht abgerufen werden.  
  
 `regCount`  
 [in] Die Anzahl der Registerwerte abgerufen werden sollen.  
  
 `regBuffer`  
 [out] Ein Array von `CORDB_REGISTER` Objekte, von denen jede einen Wert eines Registers empfängt.  
  
## <a name="remarks"></a>Hinweise  
 Die Größe des Arrays muss gleich der Anzahl von Bits, die auf einen in der Bitmaske festgelegt sein. Die `regCount` Parameter gibt die Anzahl der Elemente im Puffer, die die Registerwerte erhält. Wenn die `regCount` Wert ist zu klein für die angegebene Anzahl von Registern durch die Maske, die höhere nummerierten Register aus dem Satz abgeschnitten. Wenn die `regCount` Wert ist zu groß ist, der nicht verwendeten `regBuffer` Elemente nicht geändert werden.  
  
 Wenn die Bitmaske ein Registers angibt, der nicht verfügbar ist, `GetRegisters` gibt einen unbestimmten Wert für, die sich registrieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugRegisterSet-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [ICorDebugRegisterSet2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
