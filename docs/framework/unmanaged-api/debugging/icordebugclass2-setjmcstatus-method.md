---
title: ICorDebugClass2::SetJMCStatus-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5fa9de4482b674173dba6a8316491507330f6376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass2setjmcstatus-method"></a>ICorDebugClass2::SetJMCStatus-Methode
Für jede Methode der Klasse wird einen Wert, der angibt, ob die Methode benutzerdefinierten Code.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `bIsJustMyCode`  
 [in] Legen Sie auf `true` um anzugeben, dass die Methode eine benutzerdefinierte ist code; legen Sie andernfalls auf `false`.  
  
## <a name="remarks"></a>Hinweise  
 Eine nur-mein-Code ("JMC") zugeordnetem wird Code nicht auf eine benutzerdefinierte übersprungen wird. Benutzerdefinierter Code muss eine Teilmenge von debugfähigem Code.  
  
 `SetJMCStatus`Gibt einen HRESULT-Wert von "S_FALSE" zurück, wenn sie zum Festlegen des Werts für eine beliebige Methode schlägt fehl, selbst wenn der Wert für alle anderen Methoden erfolgreich festgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
