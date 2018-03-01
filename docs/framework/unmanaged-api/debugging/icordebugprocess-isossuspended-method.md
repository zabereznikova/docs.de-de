---
title: ICorDebugProcess::IsOSSuspended-Methode
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
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 97c394e3084007227cf157c62a12df3f5cfac8e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessisossuspended-method"></a>ICorDebugProcess::IsOSSuspended-Methode
Ruft einen Wert, der angibt, ob die angegebene Thread aufgrund der Debugger, beenden diesen Prozess angehalten wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a>Parameter  
 `threadID`  
 [in] Die ID des betreffenden Threads.  
  
 `pbSuspended`  
 [out] Ein Zeiger auf einen booleschen Wert, der `true` Wenn der angegebene Thread angehalten, und andernfalls wurde *`pbSuspended` ist `false`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der angegebenen Threads als Ergebnis der Debugger, beenden diesen Prozess angehalten wurde, den angegebenen Thread Win32 Unterbrechungszähler wird um eins erhöht. Die Debugger-Benutzeroberfläche (UI) sollten diese Informationen berücksichtigt werden, wenn angezeigt wird das Betriebssystem (BS) Unterbrechungszähler des Threads für den Benutzer.  
  
 Die `IsOSSuspended` Methode ist sinnvoll, nur im Kontext von nicht verwaltetem Debuggen. Während des verwalteten Debuggens werden Threads kooperativ und nicht OS angehalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
