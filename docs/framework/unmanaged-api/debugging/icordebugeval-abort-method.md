---
title: ICorDebugEval::Abort-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 052c467f5570119cd08b4719c768d178dd52aba2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752208"
---
# <a name="icordebugevalabort-method"></a>ICorDebugEval::Abort-Methode
Bricht ab, der Berechnung, die dieses ICorDebugEval Objekt derzeit ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Auswertung geschachtelt ist, und es nicht der aktuellste Auftrag ist, der `Abort` -Methode schlägt möglicherweise fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
