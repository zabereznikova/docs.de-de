---
title: ICorDebugILCode::GetEHClauses-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode.GetEHClauses
api_location: mscordbi.dll
api_type: COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 39d30ef572423d8cb988c074971de095f1709e8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcodegetehclauses-method"></a>ICorDebugILCode::GetEHClauses-Methode
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Gibt einen Zeiger auf eine Liste mit Ausnahmebehandlung (Exception Handling, EH)-Klauseln an, die für diese Intermediate Language IL definiert sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cClauses`  
 [in] Die Speicherkapazität des `clauses`-Arrays. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 `pcClauses`  
 [out] Die Anzahl der Klauseln, über die Informationen in das `clauses`-Array geschrieben werden.  
  
 Klauseln  
 [out] Ein Array von [CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Objekte, die Informationen zu Ausnahmebehandlungsklauseln für diese IL definiert enthalten.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `cClauses` ist 0 und `pcClauses` nicht**null**, `pcClauses` auf die Anzahl der verfügbaren Ausnahmebehandlungsklauseln festgelegt ist. Wenn `cClauses` nicht NULL ist, stellt es die Speicherkapazität des `clauses`-Arrays dar. Bei Zurückgabe der Methode enthält `clauses` maximal `cClauses` Elemente, und `pcClauses` ist auf die Anzahl der Klauseln eingestellt, die tatsächlich in das `clauses`-Array geschrieben sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugILCode-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 [CorDebugEHClause-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
