---
title: ICorDebugProcess::GetThread-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5cbdd19fa14a41d8bd2eadec80dbafcea7b720d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766431"
---
# <a name="icordebugprocessgetthread-method"></a>ICorDebugProcess::GetThread-Methode
Ruft den Thread dieses Prozesses, die die angegebenen Betriebssystem (OS)-Thread-ID.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwThreadId`  
 [in] Die Betriebssystem-thread-ID des Threads abgerufen werden sollen.  
  
 `ppThread`  
 [out] Ein Zeiger auf die Adresse des ein ICorDebugThread-Objekt, das den Thread darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
