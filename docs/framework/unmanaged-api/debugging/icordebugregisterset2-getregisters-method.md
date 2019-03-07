---
title: ICorDebugRegisterSet2::GetRegisters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c74509a0435fe54f754c6e47603bd74b5b09fe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493595"
---
# <a name="icordebugregisterset2getregisters-method"></a>ICorDebugRegisterSet2::GetRegisters-Methode
Ruft den Wert jedes Registers (für die Plattform, auf der Code derzeit ausgeführt wird), die von der angegebenen Bitmaske angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `maskCount`  
 [in] Die Größe in Bytes, der die `mask` Array.  
  
 `mask`  
 [in] Ein Array von Bytes, von denen jedes Bit eines Registers entspricht. Wenn das Bit 1 ist, wird der entsprechende Wert des Registers abgerufen werden.  
  
 `regCount`  
 [in] Die Anzahl der Registerwerte abgerufen werden sollen.  
  
 `regBuffer`  
 [out] Ein Array von `CORDB_REGISTER` Objekte, von denen jede den Wert eines Registers empfängt.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetRegisters` Methode gibt ein Array von Werten zurück, über die Register, die von der Maske angegeben werden. Das Array enthält keine Werte der Register, dessen Maskenbit nicht festgelegt ist. Daher die Größe der `regBuffer` Arrays gleich der Anzahl von 1 in der Maske sein muss. Wenn der Wert des `regCount` ist zu klein für die Anzahl der von der Maske, die Werte der Register mit höheren Nummern angegebene Register aus dem Satz abgeschnitten wird. Wenn `regCount` ist zu groß, die nicht verwendeten `regBuffer` Elemente nicht geändert werden.  
  
 Wenn ein Register nicht verfügbar, die von der Maske angegeben ist, wird für dieses Register ein unbestimmter Wert zurückgegeben.  
  
 Die `ICorDebugRegisterSet2::GetRegisters` Methode ist erforderlich, für die Plattformen, für die mehr als 64 Registern. IA64 hat z. B. 128 Allzweckregister und 128 Gleitkomma-Registerkarten, daher Sie mehr als 64-Bit in der Bitmaske müssen.  
  
 Wenn Sie nicht mehr als 64 Registern verfügen wie der Fall auf Plattformen wie X86, ist die `GetRegisters` -Methode übersetzt die Bytes in den `mask` Bytearray, in eine `ULONG64` und ruft dann die [ICorDebugRegisterSet:: GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) Methode, die akzeptiert die `ULONG64` Maske.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugRegisterSet2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
