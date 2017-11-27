---
title: ICorDebugThread::CreateStepper-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.CreateStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b66c3e536104a46b65c92fe038fb5a92d79db299
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadcreatestepper-method"></a>ICorDebugThread::CreateStepper-Methode
Erstellt ein ICorDebugStepper-Objekt, das schrittweise Ausführen des aktiven Frames dieses ICorDebugThread ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppStepper`  
 [out] Ein Zeiger auf die Adresse des ein `ICorDebugStepper` Objekt, das schrittweise Ausführen des aktiven Frames dieses Threads ermöglicht.  
  
## <a name="remarks"></a>Hinweise  
 Der aktive Frame möglicherweise nicht verwaltetem Code.  
  
 Die `ICorDebugStepper` Schnittstelle muss für die schrittweise Ausführung verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
