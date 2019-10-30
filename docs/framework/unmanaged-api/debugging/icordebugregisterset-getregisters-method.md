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
ms.openlocfilehash: 112d530c765fc74ab4ea767cb3168977d1b45f47
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138366"
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters-Methode
Ruft den Wert der einzelnen Register (auf dem momentan ausgeführten Code) ab, der durch die Bitmaske angegeben wird.  
  
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
 in Eine Bitmaske, die angibt, welche Registerwerte abgerufen werden sollen. Jedes Bit entspricht einem Register. Wenn ein Bit auf 1 festgelegt ist, wird der Wert des Registers abgerufen. Andernfalls wird der Wert des Registers nicht abgerufen.  
  
 `regCount`  
 in Die Anzahl der abzurufenden Registrierungs Werte.  
  
 `regBuffer`  
 vorgenommen Ein Array von `CORDB_REGISTER`-Objekten, von denen jede den Wert eines Register erhält.  
  
## <a name="remarks"></a>Hinweise  
 Die Größe des Arrays sollte gleich der Anzahl von Bits sein, die in der Bitmaske auf eins festgelegt ist. Der `regCount`-Parameter gibt die Anzahl der Elemente im Puffer an, die die Registerwerte erhalten. Wenn der `regCount` Wert für die Anzahl der von der Maske festgelegten Register zu klein ist, werden die höheren nummerierten Register von der Menge abgeschnitten. Wenn der `regCount` Wert zu groß ist, werden die nicht verwendeten `regBuffer` Elemente unverändert geändert.  
  
 Wenn die Bitmaske ein nicht verfügbares Register angibt, gibt `GetRegisters` einen unbestimmten Wert für dieses Register zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRegisterSet-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
