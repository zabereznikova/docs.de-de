---
title: ICorDebugEval::GetResult-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.GetResult
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7379237c73d79d9e8c66112a101edadca357cb10
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalgetresult-method"></a>ICorDebugEval::GetResult-Methode
Ruft den Ergebnissen dieser Auswertung ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppResult`  
 [out] Zeiger auf die Adresse eines ICorDebugValue-Objekts, das die Ergebnissen dieser Auswertung darstellt, wenn die Auswertung normal abgeschlossen wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetResult` Methode gilt nur, nachdem die Auswertung abgeschlossen ist.  
  
 Wenn in der Regel wird die Auswertung abgeschlossen `ppResult` gibt die Ergebnisse an. Wenn sie mit einer Ausnahme beendet wird, ist das Ergebnis die ausgelöste Ausnahme. Wenn die Auswertung für ein neues Objekt war, ist das Ergebnis der Verweis auf das neue Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
