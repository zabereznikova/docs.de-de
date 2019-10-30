---
title: ICorDebugChain::EnumerateFrames-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: 0b024d3396dfe1796fcb18afa122d4aee39c4ccc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132721"
---
# <a name="icordebugchainenumerateframes-method"></a>ICorDebugChain::EnumerateFrames-Methode
Ruft einen Enumerator ab, der alle verwalteten Stapel Rahmen in der Kette enthält, beginnend mit dem letzten Frame.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppFrames`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das der Enumerator für die Stapel Rahmen ist.  
  
## <a name="remarks"></a>Hinweise  
 Die Kette stellt die physische aufrufsstapel für den Thread dar.  
  
 Die `EnumerateFrames`-Methode sollte nur für verwaltete Ketten aufgerufen werden. Die Debug-API stellt keine Methoden zum Abrufen von Frames bereit, die in nicht verwalteten Ketten enthalten sind. Der Debugger muss andere Mittel zum Abrufen dieser Informationen verwenden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
