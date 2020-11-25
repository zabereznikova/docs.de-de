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
ms.openlocfilehash: 194065e53d550c9bbd0486de54462309a4d9ffa1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695737"
---
# <a name="icordebugnativeframecansetip-method"></a>ICorDebugNativeFrame::CanSetIP-Methode

Ruft ein HRESULT ab, das angibt, ob es sicher ist, den Anweisungs Zeiger (IP) an die angegebene Offset Position im systemeigenen Code festzulegen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `nOffset`  
 in Die gewünschte Einstellung für den Anweisungs Zeiger.  
  
## <a name="remarks"></a>Hinweise  

 Verwenden Sie die- `CanSetIP` Methode vor dem Aufrufen der [ICorDebugNativeFrame:: settip](icordebugnativeframe-setip-method.md) -Methode. Wenn `CanSetIP` ein anderes HRESULT als S_OK zurückgibt, können Sie trotzdem aufrufen `ICorDebugNativeFrame::SetIP` , aber es gibt keine Garantie dafür, dass der Debugger die sichere und korrekte Ausführung des debuggten Codes fortsetzt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
