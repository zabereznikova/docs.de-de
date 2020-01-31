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
ms.openlocfilehash: e77344a99189ec8e234129262d45698c794dc249
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788515"
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
  
## <a name="parameters"></a>Parameters  
 `flags`  
 in Ein [ilcodekind](ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob die von der ReJIT-Anforderung des Profilers definierte zwischen Sprache (IL) im Frame enthalten ist.  
  
 `ppCode`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugCode-Objekts, das den Code darstellt, der von diesem Stapel Rahmen ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ähnelt der [ICorDebugFrame:: GetCode](icordebugframe-getcode-method.md) -Methode, mit der Ausnahme, dass Sie optional auf Code zugreift, der von der ReJIT-Anforderung des Profilers definiert wird. Das Aufrufen dieser Methode mit einem `flags` Wert `ILCODE_ORIGINAL_IL` entspricht dem Aufrufen von [GetCode](icordebugframe-getcode-method.md); Wenn die Methode instrumentiert ist, kann auf Ihre Il nicht zugegriffen werden. mit `ILCODE_REJIT_IL` kann der Debugger auf die von der ReJIT-Anforderung des Profilers definierte Il zugreifen. Wenn die Il nicht instrumentiert ist, ist `ppCode` **null**, und die Methode gibt `S_OK`zurück.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugILFrame4-Schnittstelle](icordebugilframe4-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [ReJIT: Anleitung](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
