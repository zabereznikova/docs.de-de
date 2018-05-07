---
title: ICorDebugThread::EnumerateChains-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caeb60c33580f7171a6959c3046cf7312868851b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugthreadenumeratechains-method"></a>ICorDebugThread::EnumerateChains-Methode
Ruft einen Schnittstellenzeiger auf einem ICorDebugChainEnum-Enumerator, der alle Stapelketten in diesem ICorDebugThread-Objekt enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppChains`  
 [out] Ein Zeiger auf die Adresse des ein `ICorDebugChainEnum` Objekt, das Enumeration aller ermöglicht, die in diesem Thread, beginnend mit der Kette aktiv (d. h. die aktuellste) verkettet ist.  
  
## <a name="remarks"></a>Hinweise  
 Die Stapelkette stellt die physische Aufrufliste für den Thread dar. Die folgenden Situationen erstellen Stapel Kette Grenze:  
  
-   Ein Übergang verwaltet, nicht verwaltete oder nicht verwaltet zu verwaltet.  
  
-   Ein Wechsel des Ausführungskontexts.  
  
-   Ein debugger Übernahme eines Benutzerthreads.  
  
 Im einfachen Fall für einen Thread, der ausschließlich verwalteten Code in einem einzigen Kontext ausgeführt wird, wird eine 1: 1-Entsprechung zwischen Threads und Stapelketten vorhanden sein.  
  
 Ein Debugger möchte die physischen Aufruflisten aller Threads in logischen Aufruflisten neu anzuordnen. Dies würde das Sortieren der Threads Ketten ihre Aufrufer-/Aufgerufener-Beziehungen und liefern ihnen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
