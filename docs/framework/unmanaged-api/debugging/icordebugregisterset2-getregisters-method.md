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
ms.openlocfilehash: 54a5fb50a0177fe9886582c112f16ce871ea9df4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792064"
---
# <a name="icordebugregisterset2getregisters-method"></a>ICorDebugRegisterSet2::GetRegisters-Methode
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
  
## <a name="parameters"></a>Parameters  
 `maskCount`  
 in Die Größe des `mask` Arrays in Bytes.  
  
 `mask`  
 in Ein Bytearray, das jedem Bit entspricht, das einem Register entspricht. Wenn das Bit 1 ist, wird der zugehörige Registrierungs Wert abgerufen.  
  
 `regCount`  
 in Die Anzahl der abzurufenden Registrierungs Werte.  
  
 `regBuffer`  
 vorgenommen Ein Array von `CORDB_REGISTER`-Objekten, von denen jede den Wert eines Register empfängt.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetRegisters`-Methode gibt ein Array von Werten aus den Registern zurück, die von der Maske angegeben werden. Das Array enthält keine Werte von Registern, deren Masken Bit nicht festgelegt ist. Folglich muss die Größe des `regBuffer` Arrays gleich der Anzahl von 1 sein. Wenn der Wert von `regCount` für die Anzahl der von der Maske festgelegten Register zu klein ist, werden die Werte der höheren nummerierten Register vom Satz abgeschnitten. Wenn `regCount` zu groß ist, werden die nicht verwendeten `regBuffer` Elemente unverändert geändert.  
  
 Wenn ein nicht verfügbares Register durch die Maske angegeben wird, wird für dieses Register ein unbestimmter Wert zurückgegeben.  
  
 Die `ICorDebugRegisterSet2::GetRegisters`-Methode ist für Plattformen erforderlich, die über mehr als 64 Register verfügen. Beispielsweise hat ia64 128 allgemeine Register und 128 Gleit Komma Register, sodass Sie mehr als 64 Bits in der Bitmaske benötigen.  
  
 Wenn Sie nicht über mehr als 64 Register verfügen, wie es bei Plattformen wie z. b. x86 der Fall ist, übersetzt die `GetRegisters`-Methode tatsächlich lediglich die Bytes im `mask` Bytearray in eine `ULONG64` und ruft dann die [ICorDebugRegisterSet:: GetRegisters](icordebugregisterset-getregisters-method.md) -Methode auf, die die `ULONG64` Maske annimmt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet-Schnittstelle](icordebugregisterset-interface.md)
