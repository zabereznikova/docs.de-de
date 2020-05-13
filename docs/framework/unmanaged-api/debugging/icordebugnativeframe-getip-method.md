---
title: ICorDebugNativeFrame::GetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
ms.openlocfilehash: 53576ca938074fb7e5974a96bb53a84cb6ed67ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213594"
---
# <a name="icordebugnativeframegetip-method"></a>ICorDebugNativeFrame::GetIP-Methode
Ruft den Speicherort des systemeigenen Codes ab, auf den der Anweisungs Zeiger aktuell festgelegt ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pnOffset`  
 vorgenommen Ein Zeiger auf die Offset Position im systemeigenen Code.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Stapel Rahmen, der durch diesen "ICorDebugNativeFrame" dargestellt wird, aktiv ist, entspricht der Offset der Adresse der nächsten Anweisung, die ausgeführt werden soll. Wenn dieser Stapel Rahmen nicht aktiv ist, ist der Offset die Adresse der nächsten Anweisung, die ausgeführt werden soll, wenn der Stapel Rahmen erneut aktiviert wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
