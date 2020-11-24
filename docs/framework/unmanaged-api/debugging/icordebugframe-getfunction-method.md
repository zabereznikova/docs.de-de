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
ms.openlocfilehash: 9f9a6238057f56459eb8dca2375da412c3cd569d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690316"
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

 Die `GetFunction` Methode schlägt möglicherweise fehl, wenn der Frame keiner bestimmten Funktion zugeordnet ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
