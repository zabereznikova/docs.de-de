---
title: ICorDebugThread::CreateEval-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 766677d9eef60c811c8537bc60bb8db29dd988c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadcreateeval-method"></a>ICorDebugThread::CreateEval-Methode
Erstellt ein ICorDebugEval-Objekt, das erfasst und die Funktionen dieses ICorDebugThread verfügbar macht.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppEval`  
 [out] Ein Zeiger auf die Adresse des ein `ICorDebugEval` Objekt, das erfasst und die Funktionen dieses Threads verfügbar macht.  
  
## <a name="remarks"></a>Hinweise  
 Das Auswertungsobjekt wird eine neue Kette für den Thread push, vor dem Ausführen von seiner Berechnung. Dies unterbricht die Berechnung, die derzeit ausgeführten für den Thread bis zum Abschluss der Auswertung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
