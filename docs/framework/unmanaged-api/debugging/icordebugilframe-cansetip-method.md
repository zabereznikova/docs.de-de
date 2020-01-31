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
ms.openlocfilehash: c6a02b080739d00667893008be4a19b4fa9a6ef2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788593"
---
# <a name="icordebugilframecansetip-method"></a>ICorDebugILFrame::CanSetIP-Methode
Ruft ein HRESULT ab, das angibt, ob es sicher ist, den Anweisungs Zeiger auf die angegebene Offset Position im MSIL-Code (Microsoft Intermediate Language) festzulegen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `nOffset`  
 in Die gewünschte Einstellung für den Anweisungs Zeiger.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die `CanSetIP`-Methode, bevor Sie die [ICorDebugILFrame:: abtip](icordebugilframe-setip-method.md) -Methode aufrufen. Wenn `CanSetIP` ein anderes HRESULT als S_OK zurückgibt, können Sie weiterhin `ICorDebugILFrame::SetIP`aufrufen, aber es gibt keine Garantie dafür, dass der Debugger die sichere und korrekte Ausführung des debuggten Codes fortsetzt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug, h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
