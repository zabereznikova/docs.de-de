---
title: ICorDebugNativeFrame::CanSetIP-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.CanSetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33b5efe6352d3a0c30179990205315c76f3a704d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframecansetip-method"></a>ICorDebugNativeFrame::CanSetIP-Methode
Ruft ein HRESULT, das angibt, ob Anweisungszeigers (IP) auf die angegebene Offsetposition in systemeigenem Code festgelegt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `nOffset`  
 [in] Die gewünschte Einstellung für den Anweisungszeiger.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `CanSetIP` Methode vor dem Aufruf der [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) Methode. Wenn `CanSetIP` gibt jeden HRESULT-Wert als S_OK, können Sie weiterhin aufrufen `ICorDebugNativeFrame::SetIP`, aber es gibt keine Garantie, dass der Debugger die ordnungsgemäße und sichere Ausführung des gedebuggten Codes fortgesetzt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 
