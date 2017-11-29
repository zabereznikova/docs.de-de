---
title: ICorDebugILFrame4::GetCodeEx-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.GetLocalVariableEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc80882353bd7a9861f4db79b83493d1cef7bfee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
  
#### <a name="parameters"></a>Parameter  
 `flags`  
 [in] Ein [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) Enumerationsmember, der angibt, ob die intermediate Language (IL), die durch die Profiler-ReJIT-Anfrage definiert, die im Rahmen enthalten ist.  
  
 `ppCode`  
 [out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugCode", das den Code darstellt, den diesem Stapelrahmen ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ähnelt der [ICorDebugFrame:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) -Methode, mit dem Unterschied, dass sie optional durch den Profiler-ReJIT-Anfrage definiert Code zugreift. Beim Aufrufen dieser Methode mit einem `flags` Wert `ILCODE_ORIGINAL_IL` entspricht dem Aufruf [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); Wenn die Methode instrumentiert ist, die IL nicht zugegriffen werden. `ILCODE_REJIT_IL`kann der Debugger den IL-Code durch den Profiler-ReJIT-Anfrage definiert den Zugriff auf. Wenn die IL nicht instrumentiert, `ppCode` ist **null**, und die Methode gibt `S_OK`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugILFrame4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ReJIT: Eine Anleitung](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
