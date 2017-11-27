---
title: ICorDebugThread::CreateEval-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.CreateEval
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aebabf12e6dcf12f0e1e1f24ec2ad69ea55ec86c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
