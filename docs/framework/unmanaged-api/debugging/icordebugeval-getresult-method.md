---
title: ICorDebugEval::GetResult-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 86c017f581c7b980b8b0cb8bd7bdc1b0aa439afe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705821"
---
# <a name="icordebugevalgetresult-method"></a>ICorDebugEval::GetResult-Methode

Ruft die Ergebnisse dieser Auswertung ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppResult`  
 vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das die Ergebnisse dieser Auswertung darstellt, wenn die Auswertung normal abgeschlossen wird.  
  
## <a name="remarks"></a>Hinweise  

 Die- `GetResult` Methode ist nur gültig, wenn die Auswertung abgeschlossen ist.  
  
 Wenn die Auswertung normal abgeschlossen wird, `ppResult` gibt die Ergebnisse an. Wenn Sie mit einer Ausnahme beendet wird, ist das Ergebnis die ausgelöste Ausnahme. Wenn die Auswertung für ein neues Objekt erfolgte, ist das Ergebnis der Verweis auf das neue-Objekt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
