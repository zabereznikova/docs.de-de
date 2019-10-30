---
title: ICorDebugThread::GetCurrentException-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
ms.openlocfilehash: 8082b2a3654f1605f18f3b68f54464dc83c8e60a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133488"
---
# <a name="icordebugthreadgetcurrentexception-method"></a>ICorDebugThread::GetCurrentException-Methode
Ruft einen Schnittstellen Zeiger auf ein ICorDebugValue-Objekt ab, das eine Ausnahme darstellt, die zurzeit von verwaltetem Code ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppExceptionObject`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugValue` Objekts, das die Ausnahme darstellt, die zurzeit von verwaltetem Code ausgelöst wird.  
  
## <a name="remarks"></a>Hinweise  
 Das Ausnahme Objekt ist von dem Zeitpunkt vorhanden, zu dem die Ausnahme ausgelöst wird, bis zum Ende des `catch` Blocks. Bei einer Funktions Auswertung, die von den ICorDebugEval-Methoden ausgeführt wird, wird das Ausnahme Objekt beim Setup gelöscht und bei Abschluss wieder hergestellt.  
  
 Ausnahmen können gescht werden (z. b. Wenn eine Ausnahme in einem Filter oder in einer Funktions Auswertung ausgelöst wird), sodass es möglicherweise mehrere ausstehende Ausnahmen in einem einzelnen Thread gibt. `GetCurrentException` gibt die aktuelle Ausnahme zurück.  
  
 Das Ausnahme Objekt und der Typ können sich während der gesamten Lebensdauer der Ausnahme ändern. Wenn z. b. eine Ausnahme vom Typ "x" ausgelöst wird, kann die Common Language Runtime (CLR) nicht genügend Arbeitsspeicher aufweisen und Sie auf eine Ausnahme aufgrund von nicht genügend Arbeitsspeicher herauf Stufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
