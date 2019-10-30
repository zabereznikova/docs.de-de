---
title: ICorDebugILCode::GetEHClauses-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
ms.openlocfilehash: df9859f33b4146486a046253cf4705cd19c66adf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131098"
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
  
## <a name="parameters"></a>Parameter  
 `cClauses`  
 [in] Die Speicherkapazität für das `clauses`-Array. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 `pcClauses`  
 [out] Die Anzahl der Klauseln, über die Informationen in das `clauses`-Array geschrieben werden.  
  
 Klauseln  
 vorgenommen Ein Array von [cordebugehclause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) -Objekten, die Informationen zu Ausnahme Behandlungs Klauseln enthalten, die für diese Il definiert sind.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `cClauses` 0 und `pcClauses` ungleich**null**ist, wird `pcClauses` auf die Anzahl der verfügbaren Klauseln für die Ausnahmebehandlung festgelegt. Wenn `cClauses` nicht NULL ist, stellt es die Speicherkapazität des `clauses`-Arrays dar. Bei Zurückgabe der Methode enthält `clauses` maximal `cClauses` Elemente, und `pcClauses` ist auf die Anzahl der Klauseln eingestellt, die tatsächlich in das `clauses`-Array geschrieben sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugILCode-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)
- [CorDebugEHClause-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
