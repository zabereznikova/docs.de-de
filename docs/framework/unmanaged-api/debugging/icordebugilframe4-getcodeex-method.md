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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb50459e36cfeb76a0c9a1e1cd4544260d484f45
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926794"
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
 in Ein [ilcodekind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob die von der ReJIT-Anforderung des Profilers definierte zwischen Sprache (IL) im Frame enthalten ist.  
  
 `ppCode`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugCode-Objekts, das den Code darstellt, der von diesem Stapel Rahmen ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ähnelt der [ICorDebugFrame:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) -Methode, mit der Ausnahme, dass Sie optional auf Code zugreift, der von der ReJIT-Anforderung des Profilers definiert wird. Das Aufrufen dieser Methode mit `flags` einem Wert `ILCODE_ORIGINAL_IL` von entspricht dem Aufrufen von [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); wenn die Methode instrumentiert ist, kann auf Ihre Il nicht zugegriffen werden. `ILCODE_REJIT_IL`ermöglicht dem Debugger den Zugriff auf die von der ReJIT-Anforderung des Profilers definierte Il. Wenn die Il nicht instrumentiert ist, `ppCode` ist **null**, und die Methode gibt `S_OK`zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugILFrame4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT Leitfaden](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
