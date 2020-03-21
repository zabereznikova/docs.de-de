---
title: ICorDebugRegisterSet::GetRegisters-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 32e899622b9c649a08e3bca1b6645f70dcbcbb19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178544"
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters-Methode
Ruft den Wert jedes Registers ab (auf dem Computer, der derzeit Code ausführt), der von der Bitmaske angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mask`  
 [in] Eine Bitmaske, die angibt, welche Registerwerte abgerufen werden sollen. Jedes Bit entspricht einem Register. Wenn ein Bit auf einbit festgelegt ist, wird der Wert des Registers abgerufen. Andernfalls wird der Wert des Registers nicht abgerufen.  
  
 `regCount`  
 [in] Die Anzahl der registerwerte, die abgerufen werden sollen.  
  
 `regBuffer`  
 [out] Ein Array `CORDB_REGISTER` von Objekten, von denen jedes den Wert eines Registers empfängt.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Größe des Arrays sollte gleich der Anzahl der Bits sein, die in der Bitmaske auf eins festgelegt sind. Der `regCount` Parameter gibt die Anzahl der Elemente im Puffer an, die die Registerwerte empfangen. Wenn `regCount` der Wert für die Anzahl der register, die durch die Maske angegeben werden, zu klein ist, werden die höheren nummerierten Register aus dem Satz abgeschnitten. Wenn `regCount` der Wert zu groß `regBuffer` ist, werden die nicht verwendeten Elemente nicht geändert.  
  
 Wenn die Bitmaske ein Register angibt, das nicht verfügbar ist, `GetRegisters` gibt ein unbestimmter Wert für dieses Register zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugRegisterSet-Schnittstelle](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)
