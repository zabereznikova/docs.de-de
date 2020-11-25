---
title: INotifySink2::OnSyncCallReturn-Methode
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
ms.openlocfilehash: fe2db3df688f91ec6e1aadd8cc3bb43726e5c30f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719956"
---
# <a name="inotifysink2onsynccallreturn-method"></a>INotifySink2::OnSyncCallReturn-Methode

Wird aufgerufen, wenn ein Aufruf zurückgegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `in_CallID`  
 in ID des von zurückgegebenen Aufrufes. Siehe [CALL_ID Struktur](call-id-structure.md).  
  
 `in_pBuffer`  
 in Der Rückruf Puffer.  
  
 `in_BufferSize`  
 in Größe des Aufrufpuffers in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Weitere Informationen

- [INotifySink2-Schnittstelle](inotifysink2-interface.md)
- [INotifySource2-Schnittstelle](inotifysource2-interface.md)
- [INotifyConnection2-Schnittstelle](inotifyconnection2-interface.md)
