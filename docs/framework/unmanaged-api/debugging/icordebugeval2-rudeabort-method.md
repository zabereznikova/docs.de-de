---
title: ICorDebugEval2::RudeAbort-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
ms.openlocfilehash: e901c65824ee8d6949c79c7778944148c0d9eb28
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976056"
---
# <a name="icordebugeval2rudeabort-method"></a>ICorDebugEval2::RudeAbort-Methode
Bricht die aktuell durchführte Berechnung `ICorDebugEval2` ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a>Hinweise  
 `RudeAbort`gibt keine Sperren frei, die der Auswertung enthält, sodass die Debugsitzung in einem unsicheren Zustand bleibt. Diese Methode wird mit äußerster Vorsicht aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
