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
ms.openlocfilehash: a486935d5d53a6fc7d862160ed1186c5774814c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084799"
---
# <a name="icordebugeval2rudeabort-method"></a>ICorDebugEval2::RudeAbort-Methode
Bricht die Berechnung ab, die von diesem `ICorDebugEval2` gerade durchgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a>Hinweise  
 `RudeAbort` gibt keine Sperren frei, die der Auswertung enthält, sodass die Debugsitzung in einem unsicheren Zustand bleibt. Diese Methode wird mit äußerster Vorsicht aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
