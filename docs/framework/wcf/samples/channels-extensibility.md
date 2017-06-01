---
title: "Erweiterbarkeit von Kan&#228;len | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Erweiterbarkeit von Kan&#228;len
Die Beispiele in diesem Abschnitt veranschaulichen benutzerdefinierte Kanäle.  
  
## In diesem Abschnitt  
 [Lokaler Kanal](../../../../docs/framework/wcf/samples/local-channel.md)  
 Veranschaulicht den lokalen Kanal, einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Transportkanal, der für die Kommunikation innerhalb derselben Anwendungsdomäne verwendet wird.  
  
 [Reliable Secure Profile](../../../../docs/framework/wcf/samples/reliable-secure-profile.md)  
 Veranschaulicht, wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und Reliable Secure Profile \(RSP\) verfasst werden.  
  
 [Benutzerdefinierter Kanalverteiler](../../../../docs/framework/wcf/samples/custom-channel-dispatcher.md)  
 Zeigt, wie der Kanalstapel auf benutzerdefinierte Weise erstellt wird, indem <xref:System.ServiceModel.ServiceHostBase> direkt implementiert wird, und wie ein benutzerdefinierter Kanalverteiler in einer Webhostumgebung erstellt wird.  
  
 [Segmentierungskanal](../../../../docs/framework/wcf/samples/chunking-channel.md)  
 Veranschaulicht, wie die Menge des Arbeitsspeichers begrenzt wird, der zur Pufferung von großen, mithilfe von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gesendeten Nachrichten verwendet wird.  
  
 [HTTP\-Bestätigungskanal](../../../../docs/framework/wcf/samples/http-acknowledgement-channel.md)  
 Veranschaulicht einen geschichteten Kanal, der das unidirektionale Nachrichtenmuster ändert.  
  
 [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md)  
 Zeigt, wie ein benutzerdefinierter Protokollkanal zum Verwenden von HTTP\-Cookies zur Sitzungsverwaltung erstellt wird.  
  
 [Benutzerdefinierter Nachrichteninterceptor](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
 Zeigt, wie ein benutzerdefiniertes Bindungselement implementiert wird, das Kanalfactorys und Kanallistener erstellt, um sämtliche ein\- und ausgehenden Nachrichten an einer bestimmten Stelle im Laufzeitstapel abzufangen.