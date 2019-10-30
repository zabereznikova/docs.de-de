---
title: ICorDebugThread::GetActiveChain-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
ms.openlocfilehash: 99a617ef21ee3c3319b1ebe7d3ab8367659b6ef8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133558"
---
# <a name="icordebugthreadgetactivechain-method"></a>ICorDebugThread::GetActiveChain-Methode
Ruft einen Schnittstellen Zeiger auf die aktive (letzte) Stapel Kette für dieses ICorDebugThread-Objekt ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppChain`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das die Stapel Kette darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Der `ppChain`-Parameter ist NULL, wenn derzeit keine Stapel Kette aktiv ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
