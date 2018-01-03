---
title: ICorDebugChain::EnumerateFrames-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.EnumerateFrames
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d9df99c239568948c04f61ca4ec5e2b9207930f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchainenumerateframes-method"></a>ICorDebugChain::EnumerateFrames-Methode
Ruft ein Enumerator, der alle verwalteten Stapelrahmen in der Kette enthält, beginnend mit den aktuellsten Frame ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppFrames`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugFrameEnum-Objekts, das den Enumerator für Stapelrahmen darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die Kette stellt die physische Aufrufliste für den Thread dar.  
  
 Die `EnumerateFrames` Methode sollte nur für verwaltete Ketten aufgerufen werden. Die Debug-API stellt keine Methoden zum Abrufen von Frames, die in nicht verwalteten Ketten bereit. Der Debugger muss auf andere Weise verwenden, um diese Informationen abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
