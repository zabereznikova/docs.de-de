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
ms.openlocfilehash: 39175e338e4fd98dd4af1325138da732ed81c764
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137919"
---
# <a name="icordebugframegetfunction-method"></a>ICorDebugFrame::GetFunction-Methode
Ruft die Funktion ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppFunction`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugFunction-Objekts, das die Funktion darstellt, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.  
  
## <a name="remarks"></a>Hinweise  
 Bei der `GetFunction`-Methode tritt möglicherweise ein Fehler auf, wenn der Frame keiner bestimmten Funktion zugeordnet ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
