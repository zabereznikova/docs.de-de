---
title: ICorDebugNativeFrame::CanSetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93a8c8650822c5d986e21a456d58b2dc0327f05b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479519"
---
# <a name="icordebugnativeframecansetip-method"></a>ICorDebugNativeFrame::CanSetIP-Methode
Ruft ein HRESULT, der angibt, ob den Anweisungszeiger (IP) auf die angegebenen Offsetposition im nativen Code festgelegt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `nOffset`  
 [in] Die gewünschte Einstellung für den Anweisungszeiger.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `CanSetIP` aufrufen, bevor die [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) Methode. Wenn `CanSetIP` gibt ein HRESULT S_OK, können Sie weiterhin aufrufen `ICorDebugNativeFrame::SetIP`, aber es gibt keine Garantie, dass der Debugger die ordnungsgemäße und sichere Ausführung des debuggten Codes weiterhin.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

