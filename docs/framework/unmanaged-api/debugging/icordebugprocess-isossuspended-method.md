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
ms.openlocfilehash: 275f62c8211f71f067d310dd4b3af2ddb11e93d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755463"
---
# <a name="icordebugprocessisossuspended-method"></a>ICorDebugProcess::IsOSSuspended-Methode
Ruft einen Wert, der angibt, ob der angegebene Thread durch den Debugger Beenden dieses Prozesses angehalten wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
