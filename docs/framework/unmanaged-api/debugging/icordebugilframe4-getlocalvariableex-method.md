---
title: ICorDebugILFrame4::GetLocalVariableEx-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
ms.openlocfilehash: 7c43c32e10d8e10b0f843795bbc3f0f3bc20529c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544244"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a>ICorDebugILFrame4::GetLocalVariableEx-Methode
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Ruft den Wert einer spezifizierten lokalen Variable in deren Intermediate Language (IL)-Stapelrahmen ab, und greift optional auf eine Variable zu, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,
   [in] DWORD dwIndex,
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `flags`  
 in Ein [ilcodekind](ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob eine in der Profiler-ReJIT-Instrumentation hinzugefügte Variable im Frame enthalten ist.  
  
 `dwIndex`  
 [in] Der Index der lokalen Variable im IL-Stapelrahmen.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das den abgerufenen Wert darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ähnelt der [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) -Methode, außer dass Sie optional auf eine Variable zugreift, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurde. Das Aufrufen dieser Methode mit einem `flags` Wert von `ILCODE_ORIGINAL_IL` entspricht dem Aufrufen von [GetLocalVariable](icordebugilframe-getlocalvariable-method.md). wenn die Methode mit zusätzlichen lokalen Variablen instrumentiert ist, kann auf diese Variablen nicht zugegriffen werden. `ILCODE_REJIT_IL` ermöglicht dem Debugger Zugriff auf die lokalen Variablen, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden. Ist die IL nicht instrumentiert, gibt die Methode `E_INVALIDARG` zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugILFrame4-Schnittstelle](icordebugilframe4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [ReJIT: Anleitung](/archive/blogs/davbr/rejit-a-how-to-guide)
