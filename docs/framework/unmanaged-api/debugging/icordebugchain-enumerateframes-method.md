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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7568f8ca3b92ef465ab595348f68895f389d61e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645317"
---
# <a name="icordebugchainenumerateframes-method"></a>ICorDebugChain::EnumerateFrames-Methode
Ruft einen Enumerator, der alle verwalteten Stapelrahmen in der Kette, enthält der letzten Frame ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppFrames`  
 [out] Ein Zeiger auf die Adresse des ICorDebugFrameEnum-Objekts, das den Enumerator für Stapelrahmen.  
  
## <a name="remarks"></a>Hinweise  
 Die Kette stellt die physische Aufrufliste für den Thread dar.  
  
 Die `EnumerateFrames` -Methode nur für verwaltete Ketten aufgerufen werden soll. Die Debug-API bietet keine Methoden zum Abrufen von Frames, die in nicht verwalteten Ketten. Der Debugger muss anderweitig verwenden, um diese Informationen abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
