---
title: ICorDebugCode::CreateBreakpoint-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.CreateBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 211435025fe06eff180244430138be9d42c5eb86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodecreatebreakpoint-method"></a>ICorDebugCode::CreateBreakpoint-Methode
Erstellt einen Breakpoint in dieses Codesegment am angegebenen Offset.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `offset`  
 [in] Der Offset, bei der den Breakpoint erstellt werden soll.  
  
 `ppBreakpoint`  
 [out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugFunctionBreakpoint", das den Haltepunkt darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Bevor der Haltepunkt aktiv ist, müssen sie das Prozessobjekt hinzugefügt werden.  
  
 Wenn dieser Code Microsoft intermediate Language (MSIL)-Code wird aus, und es eine just-in-Time (JIT gibt)-kompilierte, systemeigene Version des Codes, der Haltepunkt wird in der JIT-kompilierten Code als auch angewendet werden. (Die gleiche ist true, wenn der Code JIT-kompilierten höher ist.)  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 
