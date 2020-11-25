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
ms.openlocfilehash: 74256f35804ff59f04952a1ac20ac7866e8f5683
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732813"
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
  
 **Bibliothek:** MSCorWks.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
