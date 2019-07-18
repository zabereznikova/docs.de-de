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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6594bb72ce9cd2fbfa9cdafebc152a90618b810
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995487"
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
 [in] Ein [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob eine Variable in der Profiler-ReJIT-Instrumentierung hinzugefügt wurde, im Rahmen enthalten ist.  
  
 `dwIndex`  
 [in] Der Index der lokalen Variable im IL-Stapelrahmen.  
  
 `ppValue`  
 [out] Ein Zeiger auf die Adresse ein "ICorDebugValue"-Objekt, das den abgerufenen Wert darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ähnelt der [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) -Methode, mit dem Unterschied, dass sie optional eine Variable, die in der Profiler-ReJIT-Instrumentierung hinzugefügt zugreift. Beim Aufruf dieser Methode eine `flags` Wert `ILCODE_ORIGINAL_IL` entspricht dem Aufruf [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); Wenn die Methode mit zusätzlichen lokalen Variablen instrumentiert ist dieser Variablen können nicht zugegriffen werden kann. `ILCODE_REJIT_IL` ermöglicht dem Debugger Zugriff auf die lokalen Variablen in der Profiler-ReJIT-Instrumentierung hinzugefügt. Ist die IL nicht instrumentiert, gibt die Methode `E_INVALIDARG` zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugILFrame4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT: Einen Leitfaden zur Vorgehensweise](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
