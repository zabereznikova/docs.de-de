---
title: INotifySink2::OnSyncCallOut-Methode
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
ms.openlocfilehash: ce0e192a9d7d5abf56a55f844cf886c386f1c563
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441993"
---
# <a name="inotifysink2onsynccallout-method"></a>INotifySink2::OnSyncCallOut-Methode
Wird aufgerufen, wenn ein-Aufruf ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `in_CallID`  
 in ID des aufzurufenden Aufrufes. Siehe [CALL_ID Struktur](call-id-structure.md).  
  
 `out_ppBuffer`  
 vorgenommen Der Rückruf Puffer.  
  
 `out_pBufferSize`  
 vorgenommen Größe des Aufrufpuffers in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Siehe auch

- [INotifySink2-Schnittstelle](inotifysink2-interface.md)
- [INotifySource2-Schnittstelle](inotifysource2-interface.md)
- [INotifyConnection2-Schnittstelle](inotifyconnection2-interface.md)
