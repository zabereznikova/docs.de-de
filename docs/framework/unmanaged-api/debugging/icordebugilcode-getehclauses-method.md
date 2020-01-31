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
ms.openlocfilehash: ac9a4e4b54b302afeae4ede1dd574c15ded3ff12
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788605"
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
  
## <a name="parameters"></a>Parameters  
 `cClauses`  
 [in] Die Speicherkapazität für das `clauses`-Array. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 `pcClauses`  
 [out] Die Anzahl der Klauseln, über die Informationen in das `clauses`-Array geschrieben werden.  
  
 Klauseln  
 vorgenommen Ein Array von [cordebugehclause](cordebugehclause-structure.md) -Objekten, die Informationen zu Ausnahme Behandlungs Klauseln enthalten, die für diese Il definiert sind.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `cClauses` 0 und `pcClauses` ungleich**null**ist, wird `pcClauses` auf die Anzahl der verfügbaren Klauseln für die Ausnahmebehandlung festgelegt. Wenn `cClauses` nicht NULL ist, stellt es die Speicherkapazität des `clauses`-Arrays dar. Bei Zurückgabe der Methode enthält `clauses` maximal `cClauses` Elemente, und `pcClauses` ist auf die Anzahl der Klauseln eingestellt, die tatsächlich in das `clauses`-Array geschrieben sind.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugILCode-Schnittstelle](icordebugilcode-interface.md)
- [CorDebugEHClause-Struktur](cordebugehclause-structure.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
