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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b12ba5ad5c85643d1f4c91585cf7abca210d22bd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752938"
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
 [out] Zeiger auf die Adresse eines ICorDebugValue-Objekts, das die Ergebnisse dieser Auswertung darstellt, wenn die Auswertung normal abgeschlossen wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetResult` Methode gilt, wenn die Auswertung abgeschlossen ist.  
  
 Wenn die Auswertung abgeschlossen, in der Regel wurde `ppResult` gibt die Ergebnisse. Wenn sie mit einer Ausnahme beendet wird, ist das Ergebnis die ausgelöste Ausnahme. Wenn die Auswertung für ein neues Objekt war, ist das Ergebnis der Verweis auf das neue Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
