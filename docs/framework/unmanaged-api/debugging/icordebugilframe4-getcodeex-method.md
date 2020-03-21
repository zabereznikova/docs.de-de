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
ms.openlocfilehash: ef2e4bc0caddd6b13c8dbe8edb59e0673519421b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178783"
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
 [in] Ein [ILCodeKind](ilcodekind-enumeration.md) ILCodeKind-Enumerationsmember, der angibt, ob die zwischengeschaltete Sprache (IL), die durch die ReJIT-Anforderung des Profilers definiert wird, im Frame enthalten ist.  
  
 `ppCode`  
 [out] Ein Zeiger auf die Adresse eines "ICorDebugCode"-Objekts, das den Code darstellt, den dieser Stapelrahmen ausführt.  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Methode ähnelt der [ICorDebugFrame::GetCode-Methode,](icordebugframe-getcode-method.md) mit der Ausnahme, dass sie optional auf Code zugreift, der von der ReJIT-Anforderung des Profilers definiert wird. Aufrufen dieser Methode `flags` mit `ILCODE_ORIGINAL_IL` einem Wert von entspricht dem Aufrufen von [GetCode](icordebugframe-getcode-method.md); Wenn die Methode instrumentiert ist, ist auf ihre IL nicht zugegriffen. `ILCODE_REJIT_IL`ermöglicht dem Debugger den Zugriff auf die IL, die durch die ReJIT-Anforderung des Profilers definiert ist. Wenn die IL nicht `ppCode` instrumentiert ist, ist `S_OK` **null**, und die Methode gibt zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugILFrame4-Schnittstelle](icordebugilframe4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [ReJIT: Ein Anleitung](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
