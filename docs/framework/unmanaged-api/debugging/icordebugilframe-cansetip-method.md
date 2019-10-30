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
ms.openlocfilehash: 57d83d1f301cbfd43f8f553d9aef4beb3baf95f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131085"
---
# <a name="icordebugilframecansetip-method"></a>ICorDebugILFrame::CanSetIP-Methode
Ruft ein HRESULT ab, das angibt, ob es sicher ist, den Anweisungs Zeiger auf die angegebene Offset Position im MSIL-Code (Microsoft Intermediate Language) festzulegen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `nOffset`  
 in Die gewünschte Einstellung für den Anweisungs Zeiger.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die `CanSetIP`-Methode, bevor Sie die [ICorDebugILFrame:: abtip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) -Methode aufrufen. Wenn `CanSetIP` ein anderes HRESULT als S_OK zurückgibt, können Sie weiterhin `ICorDebugILFrame::SetIP`aufrufen, aber es gibt keine Garantie dafür, dass der Debugger die sichere und korrekte Ausführung des debuggten Codes fortsetzt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug, h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
