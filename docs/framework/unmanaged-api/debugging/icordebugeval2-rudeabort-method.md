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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a1adb79e5081fc909d0cd180d8161eccea7e58e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754349"
---
# <a name="icordebugeval2rudeabort-method"></a>ICorDebugEval2::RudeAbort-Methode
Bricht ab, der Berechnung, die dieses `ICorDebugEval2` wird derzeit ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a>Hinweise  
 `RudeAbort` Alle sperren, die die Auswertung enthält, wird nicht freigegeben werden, damit sie die Debugsitzung in einem unsicheren Zustand verlässt. Rufen Sie diese Methode mit äußerster Vorsicht.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
