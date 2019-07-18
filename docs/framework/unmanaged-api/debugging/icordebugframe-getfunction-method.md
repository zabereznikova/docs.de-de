---
title: ICorDebugFrame::GetFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f801dae69f16f2848b4ffa30f458c084fe9750a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754894"
---
# <a name="icordebugframegetfunction-method"></a>ICorDebugFrame::GetFunction-Methode
Ruft die Funktion, die den Code für diesen Stapelrahmen enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppFunction`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugFunction-Objekts, das die Funktion, in den Code für diesen Stapelrahmen darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetFunction` -Methode schlägt möglicherweise fehl, wenn der Frame keine bestimmte Funktion zugeordnet ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
