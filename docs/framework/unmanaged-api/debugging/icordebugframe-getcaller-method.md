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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a637cebb9e1aef20c600353eb14fe900ad7513c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754169"
---
# <a name="icordebugframegetcaller-method"></a>ICorDebugFrame::GetCaller-Methode
Ruft einen Zeiger auf das ICorDebugFrame-Objekt, in der aktuellen Kette, die diesem Frame aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppFrame`  
 [out] Ein Zeiger auf die Adresse einer `ICorDebugFrame` -Objekt, das den Aufrufframe darstellt. Dieser Wert ist null, wenn der aufgerufene Frame in der aktuellen Kette der äußerste Frame ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
