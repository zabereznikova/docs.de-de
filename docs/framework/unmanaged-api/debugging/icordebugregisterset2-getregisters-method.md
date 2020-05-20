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
ms.openlocfilehash: 71b9d59621efb547713cb4a6c9df7a7142f4a677
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615188"
---
# <a name="icordebugregisterset2getregisters-method"></a>ICorDebugRegisterSet2:: GetRegisters-Methode

Ruft den Wert der einzelnen Register (für die Plattform, auf der der Code gerade ausgeführt wird) ab, die von der angegebenen Bitmaske angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Parameter

 `maskCount`  
 in Die Größe des Arrays in Bytes `mask` .  
  
 `mask`  
 in Ein Bytearray, das jedem Bit entspricht, das einem Register entspricht. Wenn das Bit 1 ist, wird der zugehörige Registrierungs Wert abgerufen.  
  
 `regCount`  
 in Die Anzahl der abzurufenden Registrierungs Werte.  
  
 `regBuffer`  
 vorgenommen Ein Array von- `CORDB_REGISTER` Objekten, von denen jede den Wert eines Register empfängt.  
  
## <a name="remarks"></a>Hinweise

 Die- `GetRegisters` Methode gibt ein Array von Werten aus den Registern zurück, die von der Maske angegeben werden. Das Array enthält keine Werte von Registern, deren Masken Bit nicht festgelegt ist. Folglich muss die Größe des `regBuffer` Arrays mit der Anzahl von 1 in der Maske identisch sein. Wenn der Wert von `regCount` zu klein für die Anzahl der von der Maske festgelegten Register ist, werden die Werte der höher nummerierten Register von der Menge abgeschnitten. Wenn `regCount` zu groß ist, werden die `regBuffer` nicht verwendeten Elemente unverändert geändert.  
  
 Wenn ein nicht verfügbares Register durch die Maske angegeben wird, wird für dieses Register ein unbestimmter Wert zurückgegeben.  
  
 Die- `ICorDebugRegisterSet2::GetRegisters` Methode ist für Plattformen erforderlich, die über mehr als 64 Register verfügen. Beispielsweise hat ia64 128 allgemeine Register und 128 Gleit Komma Register, sodass Sie mehr als 64 Bits in der Bitmaske benötigen.  
  
 Wenn Sie nicht über mehr als 64 Register verfügen, wie es bei Plattformen wie z. b. x86 der Fall ist, `GetRegisters` übersetzt die Methode nur die Bytes im `mask` Bytearray in ein `ULONG64` und ruft dann die [ICorDebugRegisterSet:: GetRegisters](icordebugregisterset-getregisters-method.md) -Methode auf, die die `ULONG64` Maske annimmt.  
  
## <a name="requirements"></a>Anforderungen

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet-Schnittstelle](icordebugregisterset-interface.md)
