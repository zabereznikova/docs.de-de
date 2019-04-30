---
title: ICorDebugILFrame::CanSetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49cef22e88613fe4c4dfb3fb35a92977977b1827
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988636"
---
# <a name="icordebugilframecansetip-method"></a>ICorDebugILFrame::CanSetIP-Methode
Ruft ein HRESULT, der angibt, ob den Anweisungszeiger auf der angegebenen Offsetposition im Microsoft Intermediate Language (MSIL)-Code festgelegt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `nOffset`  
 [in] Die gewünschte Einstellung für den Anweisungszeiger.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `CanSetIP` Methode vor dem Aufruf der [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) Methode. Wenn `CanSetIP` gibt ein HRESULT S_OK, können Sie weiterhin aufrufen `ICorDebugILFrame::SetIP`, aber es gibt keine Garantie, dass der Debugger die ordnungsgemäße und sichere Ausführung des debuggten Codes weiterhin.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug,h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
