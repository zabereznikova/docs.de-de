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
ms.openlocfilehash: 76b231f00651186518d3bccfafa5780f258c4f75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688184"
---
# <a name="icordebugthreadenumeratechains-method"></a>ICorDebugThread::EnumerateChains-Methode

Ruft einen Schnittstellen Zeiger auf einen ICorDebugChainEnum-Enumerator ab, der alle Stapel Ketten in diesem ICorDebugThread-Objekt enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppChains`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugChainEnum` Objekts, das die Enumeration aller Stapel Ketten in diesem Thread ermöglicht, beginnend bei der aktiven (d. h. der neuesten) Kette.  
  
## <a name="remarks"></a>Hinweise  

 Die Stapel Kette stellt die physische aufrufsstapel für den Thread dar. In den folgenden Situationen wird eine Stapel Ketten Grenze erstellt:  
  
- Ein durchgängig verwalteter oder nicht verwalteter Übergang.  
  
- Ein Kontextwechsel.  
  
- Ein Debugger, der einen Benutzer Thread Hijacking hat.  
  
 Im einfachen Fall für einen Thread, der reinen verwalteten Code in einem einzigen Kontext ausführen wird, besteht eine 1:1-Entsprechung zwischen Threads und Stapel Ketten.  
  
 Möglicherweise möchte ein Debugger die physischen Aufruf Listen aller Threads in logischen Aufruf Listen neu anordnen. Dies würde dazu führen, dass alle Threads der Threads nach ihren Aufrufer-/Aufgerufener-Beziehungen sortiert und erneut gruppiert werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
