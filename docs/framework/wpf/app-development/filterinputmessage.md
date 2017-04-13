---
title: "FilterInputMessage | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "FilterInputMessage-Methode"
  - "Rohdateneingabe [WPF]"
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# FilterInputMessage
Wird immer dann von "PresentationHost.exe" aufgerufen, wenn eine Meldung empfangen wurde, es sei denn, E\_NOTIMPL wurde zurückgegeben.  
  
## Syntax  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### Parameter  
 `pMsg`  
  
 \[in\] Die WM\_INPUT\-Meldung, die an das Fenster gesendet wurde, das die unformatierte Eingabe erhält.  
  
## Eigenschaftswert\/Rückgabewert  
 HRESULT:  
  
 S\_OK – Der Filter hat die Meldung nicht verarbeitet, und weitere Verarbeitungsschritte können folgen.  
  
 S\_FALSE – Der Filter hat diese Meldung verarbeitet, und es sollten keine weiteren Verarbeitungsschritte folgen.  
  
 E\_NOTIMPL – Bei diesem Rückgabewert wird [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) nicht erneut aufgerufen.  Dieser Wert wird möglicherweise von einer Hostanwendung zurückgegeben, die nur daran interessiert ist, benutzerdefinierte Status\- und Fehlerbenutzeroberflächen für "PresentationHost.exe" bereitzustellen, und nicht dafür vorgesehen ist, unformatierte Eingabemeldungen von "PresentationHost.exe" weiterzuleiten.  
  
## Hinweise  
 "PresentationHost.exe" ist das Ziel von verschiedenen Geräten für unformatierte Eingabe, einschließlich Tastatur, Mäusen und Fernsteuerungen.  Manchmal hängt das Verhalten in der Hostanwendung von einer Eingabe ab, die andernfalls von "PresentationHost.exe" verarbeitet werden würde.  Beispielsweise kann für eine Hostanwendung das Empfangen bestimmter Eingabemeldungen erforderlich sein, um bestimmen zu können, ob bestimmte Elemente der Benutzeroberfläche angezeigt werden sollen oder nicht.  
  
 Damit die Hostanwendung die hierfür erforderlichen Eingabemeldungen empfangen kann, leitet "PresentationHost.exe" entsprechende unformatierte Eingabemeldungen durch Aufrufen von [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) an die gehostete Anwendung weiter.  
  
 Die gehostete Anwendung empfängt unformatierte Eingabemeldungen, indem sie für die Gruppe von Geräten für unformatierte Eingabe \(Eingabegeräte\) registriert wird, die von [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md) zurückgegeben werden.  
  
## Siehe auch  
 [WM\_INPUT\-Benachrichtigung](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)