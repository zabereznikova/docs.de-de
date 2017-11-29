---
title: ICorDebugFrame::GetCallee-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetCallee
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 54a26ad7d4818aae81b765ab4e6c0e5be821680e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetcallee-method"></a>ICorDebugFrame::GetCallee-Methode
Ruft einen Zeiger auf das ICorDebugFrame-Objekt in der aktuellen Kette, die dieses Rahmens aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppFrame`  
 [out] Ein Zeiger auf die Adresse des ein `ICorDebugFrame` Objekt, das den aufgerufenen Frame darstellt. Dieser Wert ist null, wenn der aufrufende Frame der innerste Rahmen in der aktuellen Kette ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
