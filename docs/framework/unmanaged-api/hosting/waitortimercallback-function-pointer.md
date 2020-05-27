---
title: WAITORTIMERCALLBACK-Funktionszeiger
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
ms.openlocfilehash: ee5dd611888ec52e360ef45fab4c01e9c5b2d6bb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009448"
---
# <a name="waitortimercallback-function-pointer"></a>WAITORTIMERCALLBACK-Funktionszeiger
Verweist auf eine Funktion, die den Host benachrichtigt, dass ein Wait-Handle ( <xref:System.Threading.WaitHandle> ) entweder signalisiert wurde oder ein Timeout aufgetreten ist.  
  
 Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `lpParameter`  
 in Ein Zeiger auf ein Objekt, das vom Host definierte Informationen enthält.  
  
 `TimerOrWaitFired`  
 [in] `true` , wenn das Wait-Handle abgelaufen ist, oder, `false` Wenn es signalisiert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion, auf die `WAITORTIMERCALLBACK` verweist, ist eine Rückruffunktion und muss vom Writer der Hostinganwendung implementiert werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscorwert. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
