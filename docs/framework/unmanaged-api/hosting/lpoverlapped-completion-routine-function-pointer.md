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
ms.openlocfilehash: a3a45a13073cf422064d28554a274e068db6f517
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727509"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a>LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger

Zeigt auf eine Funktion, die den Host benachrichtigt, wenn eine überlappende (d. h. asynchrone) E/A auf einem Gerät abgeschlossen ist.  
  
 Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.  
  
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
 in Ein-Wert, bei dem es sich um einen Fehlercode handelt, wenn das Gerät geschlossen wurde. Andernfalls ist dieser Wert 0 (null).  
  
 Das Schließen eines Geräts bewirkt, dass alle ausstehenden e/a-Vorgänge auf dem Gerät sofort abgeschlossen werden.  
  
 `dwNumberOfBytesTransfered`  
 in Die Anzahl von Bytes, die vom e/a-Vorgang übertragen werden.  
  
 `lpOverlapped`  
 in Ein Zeiger auf eine-Struktur, die Informationen enthält, die verwendet werden, um die e/a-Anforderung abzuschließen.  
  
## <a name="remarks"></a>Hinweise  

 Die Funktion, auf die `LPOVERLAPPED_COMPLETION_ROUTINE` verweist, ist eine Rückruffunktion und muss vom Writer der Hostinganwendung implementiert werden. Die Rückruffunktion ermöglicht es dem Host, die abgeschlossene e/a-Anforderung zu verarbeiten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorWks.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
