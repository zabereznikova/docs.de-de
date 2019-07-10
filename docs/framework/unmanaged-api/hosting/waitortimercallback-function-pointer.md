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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65af5303468904ee40da4d567381782af70bfb38
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776500"
---
# <a name="waitortimercallback-function-pointer"></a>WAITORTIMERCALLBACK-Funktionszeiger
Verweist auf eine Funktion, die benachrichtigt den Host, die ein Wait-handle (<xref:System.Threading.WaitHandle>) hat signalisiert wurde oder das Timeout.  
  
 Dieser Funktionszeiger wurde in .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `lpParameter`  
 [in] Ein Zeiger auf ein Objekt, das vom Host definierten Informationen enthält.  
  
 `TimerOrWaitFired`  
 [in] `true` Wenn Wait-Handles, die ein Timeout oder `false` , wenn ein Signal gesendet wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion, die die `WAITORTIMERCALLBACK` ist eine Callback-Funktion und muss vom Writer der hostanwendung implementiert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorWks.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
