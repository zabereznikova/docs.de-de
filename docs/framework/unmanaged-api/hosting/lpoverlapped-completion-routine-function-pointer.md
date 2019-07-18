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
ms.openlocfilehash: dcf63000de549b42d92ba157a7e550ac605bbfcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768378"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a>LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger
Zeigt auf eine Funktion, die den Host benachrichtigt, wenn eine überlappende (d. h. asynchrone) E/A auf einem Gerät abgeschlossen ist.  
  
 Dieser Funktionszeiger wurde in .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
