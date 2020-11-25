---
title: ICorDebugILFrame4::GetCodeEx-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
ms.openlocfilehash: a88bb02626dc125c494e4bbe68bfe6ed8bfd3b7b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719644"
---
# <a name="icordebugilframe4getcodeex-method"></a>ICorDebugILFrame4::GetCodeEx-Methode

[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Ruft einen Zeiger auf den Code ab, der vom Stapelrahmen ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `flags`  
 in Ein [ilcodekind](ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob die von der ReJIT-Anforderung des Profilers definierte zwischen Sprache (IL) im Frame enthalten ist.  
  
 `ppCode`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugCode-Objekts, das den Code darstellt, der von diesem Stapel Rahmen ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode ähnelt der [ICorDebugFrame:: GetCode](icordebugframe-getcode-method.md) -Methode, mit der Ausnahme, dass Sie optional auf Code zugreift, der von der ReJIT-Anforderung des Profilers definiert wird. Das Aufrufen dieser Methode mit einem `flags` Wert von `ILCODE_ORIGINAL_IL` entspricht dem Aufrufen von [GetCode](icordebugframe-getcode-method.md); wenn die Methode instrumentiert ist, kann auf Ihre Il nicht zugegriffen werden. `ILCODE_REJIT_IL` ermöglicht dem Debugger den Zugriff auf die von der ReJIT-Anforderung des Profilers definierte Il. Wenn die Il nicht instrumentiert ist, `ppCode` ist **null**, und die Methode gibt zurück `S_OK` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugILFrame4-Schnittstelle](icordebugilframe4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [ReJIT: A How-To Guide](/archive/blogs/davbr/rejit-a-how-to-guide)
