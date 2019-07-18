---
title: ICorDebugThread::CreateEval-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41bd4c0bb4e84b6d6f267e24808baafa57f71882
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771116"
---
# <a name="icordebugthreadcreateeval-method"></a>ICorDebugThread::CreateEval-Methode
Erstellt ein ICorDebugEval-Objekt, das erfasst und macht die Funktionalität dieses ICorDebugThread.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppEval`  
 [out] Ein Zeiger auf die Adresse einer `ICorDebugEval` -Objekt, das erfasst und macht die Funktionalität dieses Threads.  
  
## <a name="remarks"></a>Hinweise  
 Das Auswertungsobjekt wird eine neue Kette für den Thread vor seiner Berechnung übertragen werden. Dies unterbricht die Berechnung, die aktuell ausgeführte für den Thread bis zum Abschluss der Auswertung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
