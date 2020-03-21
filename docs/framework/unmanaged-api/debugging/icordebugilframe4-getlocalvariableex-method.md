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
ms.openlocfilehash: ee263e8c49cd6da7278bd2299557336629720d2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178776"
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
 [in] Ein [ILCodeKind](ilcodekind-enumeration.md) ILCodeKind-Enumerationsmember, der angibt, ob eine Variable, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurde, im Frame enthalten ist.  
  
 `dwIndex`  
 [in] Der Index der lokalen Variable im IL-Stapelrahmen.  
  
 `ppValue`  
 [out] Ein Zeiger auf die Adresse eines "ICorDebugValue"-Objekts, das den abgerufenen Wert darstellt.  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Methode ähnelt der [GetLocalVariable-Methode,](icordebugilframe-getlocalvariable-method.md) mit der Ausnahme, dass sie optional auf eine Variable zugreift, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurde. Aufrufen dieser Methode `flags` mit `ILCODE_ORIGINAL_IL` einem Wert von entspricht dem Aufrufen von [GetLocalVariable](icordebugilframe-getlocalvariable-method.md); Wenn die Methode mit zusätzlichen lokalen Variablen instrumentiert ist, kann nicht auf diese Variablen zugegriffen werden. `ILCODE_REJIT_IL`ermöglicht dem Debugger den Zugriff auf die lokalen Variablen, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden. Ist die IL nicht instrumentiert, gibt die Methode `E_INVALIDARG` zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugILFrame4-Schnittstelle](icordebugilframe4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [ReJIT: Ein Anleitung](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
