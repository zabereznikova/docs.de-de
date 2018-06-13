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
ms.openlocfilehash: cd4b7ffef9c0ba3aba54387245b2d5c9ec1ae906
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441755"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a>LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger
Zeigt auf eine Funktion, die den Host benachrichtigt, wenn eine überlappende (d. h. asynchrone) E/A auf einem Gerät abgeschlossen ist.  
  
 Diese Funktionszeiger ist veraltet die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwErrorCode`  
 [in] Ein Wert, der einen Fehlercode ist, wenn das Gerät geschlossen wurde. Dieser Wert ist, andernfalls 0 (null).  
  
 Schließen eines Geräts führt dazu, dass alle ausstehenden e/a auf das Gerät sofort abgeschlossen werden.  
  
 `dwNumberOfBytesTransfered`  
 [in] Die Anzahl der Bytes, die von der e/a-Operation übertragen.  
  
 `lpOverlapped`  
 [in] Ein Zeiger auf eine Struktur, die Informationen enthält, die verwendet werden, um die e/a-Anforderung abgeschlossen werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion, die die `LPOVERLAPPED_COMPLETION_ROUTINE` Punkt ist eine Rückruffunktion und muss vom Writer der Hostinganwendung implementiert werden. Die Rückruffunktion kann der Host die abgeschlossene e/a-Anforderung zu verarbeiten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscorwks.dll"  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
