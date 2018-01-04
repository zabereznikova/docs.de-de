---
title: FilterInputMessage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7e76f9863b68d5c7c34bca8adc872210527d6c17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="filterinputmessage"></a>FilterInputMessage
Wird immer dann von "PresentationHost.exe" aufgerufen, wenn eine Meldung empfangen wurde, es sei denn, E_NOTIMPL wurde zurückgegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a>Parameter  
 `pMsg`  
  
 [in] Die WM_INPUT-Meldung, die an das Fenster gesendet wurde, das die unformatierte Eingabe erhält.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT:  
  
 S_OK – Der Filter hat die Meldung nicht verarbeitet, und weitere Verarbeitungsschritte können folgen.  
  
 S_FALSE – Der Filter hat diese Meldung verarbeitet, und es sollten keine weiteren Verarbeitungsschritte folgen.  
  
 E_NOTIMPL – Wenn dieser Wert zurückgegeben wird, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) nicht erneut aufgerufen wird. Dieser Wert wird möglicherweise von einer Hostanwendung zurückgegeben, die nur daran interessiert ist, benutzerdefinierte Status- und Fehlerbenutzeroberflächen für "PresentationHost.exe" bereitzustellen, und nicht dafür vorgesehen ist, unformatierte Eingabemeldungen von "PresentationHost.exe" weiterzuleiten.  
  
## <a name="remarks"></a>Hinweise  
 "PresentationHost.exe" ist das Ziel von verschiedenen Geräten für unformatierte Eingabe, einschließlich Tastatur, Mäusen und Fernsteuerungen. Manchmal hängt das Verhalten in der Hostanwendung von einer Eingabe ab, die andernfalls von "PresentationHost.exe" verarbeitet werden würde. Beispielsweise kann für eine Hostanwendung das Empfangen bestimmter Eingabemeldungen erforderlich sein, um bestimmen zu können, ob bestimmte Elemente der Benutzeroberfläche angezeigt werden sollen oder nicht.  
  
 Damit wird die hostanwendung zum Empfangen von erforderlichen Eingabenachrichten diese Verhaltensweisen angeben, leitet PresentationHost.exe entsprechenden unformatierte eingehende Nachrichten für die gehostete Anwendung durch Aufrufen von [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).  
  
 Die gehostete Anwendung empfängt unformatierte Eingabenachrichten durch Registrieren mit dem Satz von unformatierten Eingabegeräte (Human Interface Devices) zurückgegebene [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).  
  
## <a name="see-also"></a>Siehe auch  
 [WM_INPUT-Benachrichtigung](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
