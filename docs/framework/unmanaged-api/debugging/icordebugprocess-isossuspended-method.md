---
title: ICorDebugProcess::IsOSSuspended-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 039dc0d9befb038e643abc4e2524c133234f460b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492074"
---
# <a name="icordebugprocessisossuspended-method"></a>ICorDebugProcess::IsOSSuspended-Methode
Ruft einen Wert, der angibt, ob der angegebene Thread durch den Debugger Beenden dieses Prozesses angehalten wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a>Parameter  
 `threadID`  
 [in] Die ID des betreffenden Threads.  
  
 `pbSuspended`  
 [out] Ein Zeiger auf einen booleschen Wert, der `true` , wenn der angegebene Thread angehalten, andernfalls wurde *`pbSuspended` ist `false`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der angegebene Thread durch den Debugger Beenden dieses Prozesses angehalten wurde, den angegebenen Thread Win32 Unterbrechungszähler um eins erhöht. Die Debugger-Benutzeroberfläche (UI) sollten diese Informationen berücksichtigt werden, wenn angezeigt wird das Betriebssystem (OS) Unterbrechungszähler des Threads für den Benutzer.  
  
 Die `IsOSSuspended` Methode ist sinnvoll, nur im Kontext nicht verwaltetes debugging. Sind während des Debuggens verwalteten Threads kooperativ und nicht-Betriebssystem-angehalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
