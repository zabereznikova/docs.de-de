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
ms.openlocfilehash: 3377dcd5d45ca8e31a57a75bd81366d41837c12c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860713"
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
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** dbgshim. h  
  
 **Bibliothek:** dbgshim. dll  
  
 **.NET Framework Versionen:** 3,5 SP1
