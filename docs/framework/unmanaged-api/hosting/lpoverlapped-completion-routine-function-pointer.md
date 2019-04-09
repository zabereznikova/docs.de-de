---
title: LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce2ce6dd1210eef94e77b5d6a2d58a35cf971e6d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138774"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a>LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger
Zeigt auf eine Funktion, die den Host benachrichtigt, wenn eine überlappende (d. h. asynchrone) E/A auf einem Gerät abgeschlossen ist.  
  
 Dieser Funktionszeiger ist veraltet, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwErrorCode`  
 [in] Ein Wert, der einen Fehlercode ist, wenn das Gerät geschlossen wurde. Andernfalls ist dieser Wert 0 (null).  
  
 Schließen eines Geräts bewirkt, dass alle ausstehenden e/a an das Gerät nicht sofort abgeschlossen werden.  
  
 `dwNumberOfBytesTransfered`  
 [in] Die Anzahl der Bytes der e/a-Vorgang übertragen.  
  
 `lpOverlapped`  
 [in] Ein Zeiger auf eine Struktur, die Informationen enthält, die verwendet werden, um die e/a-Anforderung abgeschlossen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion, die die `LPOVERLAPPED_COMPLETION_ROUTINE` ist eine Callback-Funktion und muss vom Writer der hostanwendung implementiert werden. Die Callback-Funktion kann der Host die abgeschlossene e/a-Anforderung zu verarbeiten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorWks.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
