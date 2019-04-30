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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4baa4eb4da48b923ab0137ca25d9d819c94e33d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994031"
---
# <a name="icordebugthreadgetcurrentexception-method"></a>ICorDebugThread::GetCurrentException-Methode
Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das eine Ausnahme darstellt, die derzeit von verwaltetem Code ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppExceptionObject`  
 [out] Ein Zeiger auf die Adresse einer `ICorDebugValue` -Objekt, das die Ausnahme darstellt, die aktuell von ausgelöst wird, wird von verwaltetem Code.  
  
## <a name="remarks"></a>Hinweise  
 Die Exception-Objekt ist vorhanden, ab dem Zeitpunkt, der die Ausnahme, bis zum Ende ausgelöst wird der `catch` Block. Eine funktionsauswertung, die von den ICorDebugEval-Methoden ausgeführt wird, wird das Ausnahmeobjekt Setup lösche und stellen sie bei Abschluss.  
  
 Ausnahmen können geschachtelt sein (beispielsweise, wenn eine Ausnahme in einem Filter oder eine funktionsauswertung ausgelöst wird), sodass mehrere ausstehende Ausnahmen in einem einzelnen Thread möglicherweise. `GetCurrentException` Gibt die aktuelle Ausnahme zurück.  
  
 Die Exception-Objekt und der Typ können über die gesamte Lebensdauer der Ausnahme ändern. Nachdem eine Ausnahme vom Typ X ausgelöst wird, kann die common Language Runtime (CLR) z. B. nicht über ausreichend Arbeitsspeicher und Stufen Sie ihn auf eine Out-of-Memory-Ausnahme.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
