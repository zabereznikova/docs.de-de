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
ms.openlocfilehash: d266ec7f82d7d4c7c66f137aafc1c8865d6f8889
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792804"
---
# <a name="icordebugnativeframecansetip-method"></a>ICorDebugNativeFrame::CanSetIP-Methode
Ruft ein HRESULT ab, das angibt, ob es sicher ist, den Anweisungs Zeiger (IP) an die angegebene Offset Position im systemeigenen Code festzulegen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `nOffset`  
 in Die gewünschte Einstellung für den Anweisungs Zeiger.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die `CanSetIP`-Methode vor dem Aufrufen der [ICorDebugNativeFrame:: settip](icordebugnativeframe-setip-method.md) -Methode. Wenn `CanSetIP` ein anderes HRESULT als S_OK zurückgibt, können Sie weiterhin `ICorDebugNativeFrame::SetIP`aufrufen, aber es gibt keine Garantie dafür, dass der Debugger die sichere und korrekte Ausführung des debuggten Codes fortsetzt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
