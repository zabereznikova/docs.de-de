---
title: ICorDebugFunction2::GetJMCStatus-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d23a0a489cfe13201b7798920feb3528db3b0709
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494609"
---
# <a name="icordebugfunction2getjmcstatus-method"></a>ICorDebugFunction2::GetJMCStatus-Methode
Ruft einen Wert, der angibt, ob die Funktion, die von diesem ICorDebugFunction2-Objekt dargestellt wird als Benutzercode markiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbIsJustMyCode`  
 [out] Ein Zeiger auf einen booleschen Wert, der `true`, wenn diese Funktion als Benutzercode markiert ist; andernfalls ist des Werts `false`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Funktion von diesem dargestellt `ICorDebugFunction2` kann nicht debuggt werden kann, `pbIsJustMyCode` immer `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
