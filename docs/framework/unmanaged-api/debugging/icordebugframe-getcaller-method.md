---
title: ICorDebugFrame::GetCaller-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
ms.openlocfilehash: 843399b7e3de522e2c4574963897430aa60a5a50
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114799"
---
# <a name="icordebugframegetcaller-method"></a>ICorDebugFrame::GetCaller-Methode
Ruft einen Zeiger auf das ICorDebug Frame-Objekt in der aktuellen Kette ab, das diesen Frame aufgerufen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppFrame`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugFrame` Objekts, das den aufrufenden Frame darstellt. Dieser Wert ist NULL, wenn der aufgerufene Frame der äußerste Frame in der aktuellen Kette ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
