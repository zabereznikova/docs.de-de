---
title: GetStartupNotificationEvent-Funktion
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
ms.openlocfilehash: fb158b35165fb229fc78169e2508679b6749752e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122956"
---
# <a name="getstartupnotificationevent-function"></a>GetStartupNotificationEvent-Funktion
Erstellt oder öffnet ein Ereignishandle, das über jede CLR-Runtime (Common Language Runtime) benachrichtigt wird, die im angegebenen Zielprozess geladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a>Parameter  
 `debuggeePID`  
 [in] Prozessbezeichner des Zielprozesses, von dem CLR-Startbenachrichtigungen empfangen werden.  
  
 `phStartupEvent`  
 [out] Ein Zeiger auf ein Handle, das von einer CRL beim Start signalisiert wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Das Handle für das Start-Benachrichtigungsereignis wurde wurde erfolgreich empfangen.  
  
 E_INVALIDARG  
 `phStartupEvent` ist Null oder `debuggeePID` bezieht sich nicht auf einen Prozess, der derzeit ausgeführt wird.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Das Handle zum Start-Benachrichtigungsereignis konnte nicht abgerufen werden.  
  
## <a name="remarks"></a>Hinweise  
 Unter dem Windows-Betriebssystem wird `debuggeePID` einem Betriebssystem-Prozessbezeichner zugeordnet.  
  
 Das Ereignis wird signalisiert, bevor irgendwelcher verwalteter Code von der CLR ausgeführt wurde, die das Ereignis signalisiert hat.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** dbgshim. h  
  
 **Bibliothek:** dbgshim. dll  
  
 **.NET Framework Versionen:** 3,5 SP1
