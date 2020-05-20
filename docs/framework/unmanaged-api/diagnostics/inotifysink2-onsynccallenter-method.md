---
title: INotifySink2::OnSyncCallEnter-Methode
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
ms.openlocfilehash: 85f00698f42f120b209cca14f293a58ae4c65f6f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442032"
---
# <a name="inotifysink2onsynccallenter-method"></a>INotifySink2::OnSyncCallEnter-Methode
Wird aufgerufen, wenn ein-Aufruf eingegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `in_CallID`  
 in ID des aufzurufenden Aufrufes. Siehe [CALL_ID Struktur](call-id-structure.md).  
  
 `in_pBuffer`  
 in Der Rückruf Puffer.  
  
 `in_BufferSize`  
 in Größe des Aufrufpuffers in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Siehe auch

- [INotifySink2-Schnittstelle](inotifysink2-interface.md)
- [INotifySource2-Schnittstelle](inotifysource2-interface.md)
- [INotifyConnection2-Schnittstelle](inotifyconnection2-interface.md)
