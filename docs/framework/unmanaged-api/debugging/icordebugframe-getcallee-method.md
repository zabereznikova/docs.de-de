---
title: ICorDebugFrame::GetCallee-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
ms.openlocfilehash: 6347e0109f256dc46eb0140ffd1f51977c205b51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678804"
---
# <a name="icordebugframegetcallee-method"></a>ICorDebugFrame::GetCallee-Methode

Ruft einen Zeiger auf das ICorDebug Frame-Objekt in der aktuellen Kette ab, das in diesem Frame aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppFrame`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugFrame` Objekts, das den aufgerufenen Frame darstellt. Dieser Wert ist NULL, wenn der aufrufenden Frame der innerste Frame in der aktuellen Kette ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
