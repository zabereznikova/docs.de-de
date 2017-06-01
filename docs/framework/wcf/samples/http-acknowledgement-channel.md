---
title: "HTTP-Best&#228;tigungskanal | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 469f3056-5ef2-4753-8acf-b574d23d83cf
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# HTTP-Best&#228;tigungskanal
Der HTTP\-Bestätigungskanal ist ein Beispiel für einen geschichteten Kanal, der das unidirektionale Nachrichtenmuster ändert, sodass nicht automatisch beim Eingang eine Bestätigung gesendet wird, sondern ein Dienst eingehende Nachrichten bestätigen oder ablehnen kann.Der HTTP\-Bestätigungskanal ermöglicht es auch, dass der Dienst die Bestätigung verzögern kann, bis auf Geschäftsebene garantiert werden kann, dass die Nachricht verarbeitet wird.  
  
## Veranschaulicht  
 <xref:System.ServiceModel.Channels.ReceiveContext>, Beispiel für geschichteten Kanal \(HTTP\-Bestätigungskanal\).  
  
## Diskussion  
 Der HTTP\-Bestätigungskanal implementiert <xref:System.ServiceModel.Channels.ReceiveContext>, um das HTTP\-Anforderungs\-\/Antwortnachrichtenmuster in ein unidirektionales Muster mit verzögerter Bestätigung umzugestalten.Mit diesem neuen Muster kann ein Dienst die Nachrichtenverarbeitung sicherstellen, indem eine Bestätigung in Form des HTTP\-Statuscodes 200 \(OK\) gesendet wird, ohne dass der Client blockiert wird, solange die Nachrichtenverarbeitung nicht abgeschlossen ist. Oder er kann eine Fehlermeldung an den Client in Form des HTTP\-Statuscodes 500 \(Interner Serverfehler\) senden.Ein Dienst könnte z. B. eine Bestätigung senden, nachdem er eine Nachricht in eine Warteschlange geschrieben hat, und anschließend mit der asynchronen Verarbeitung der Nachricht fortfahren.In diesem Szenario könnte ein Client sicherstellen, dass seine Nachrichten mindestens einmal vom Dienst verarbeitet wurden, indem er jede Nachricht so oft sendet, bis er eine Bestätigung vom Dienst erhält.Hinweis: Wenn ein Dienst eine schnelle asynchrone Nachrichtenverarbeitung über HTTP ohne Garantie der Nachrichtenverarbeitung erfordert, ist das <xref:System.ServiceModel.Channels.OneWayBindingElement> eine bessere Wahl.  
  
 <xref:System.ServiceModel.Channels.ReceiveContext> wird zum Halten der Nachricht verwendet, während festgestellt wird, ob die Nachricht beim Dienst verarbeitet werden kann.Die Fähigkeit eines Diensts, die Nachricht erfolgreich zu verarbeiten, wird durch Aufrufen der Complete\-Methode im <xref:System.ServiceModel.Channels.ReceiveContext>\-Objekt, das einen HTTP\-OK\-Statuscode sendet, angegeben. Durch Aufrufen der `Abandon`\-Methode von <xref:System.ServiceModel.Channels.ReceiveContext> im <xref:System.ServiceModel.Channels.ReceiveContext>\-Objekt wird angegeben, ob der Dienst die Nachricht verarbeiten kann.  
  
 In diesem Beispiel fordert der Client die Verarbeitung von Informationen, indem er eine Mitarbeiter\-ID sendet.Wenn die beim Dienst eingegangene Mitarbeiter\-ID größer als 50 ist, sendet der Dienst den HTTP\-Statuscode 500 \(Interner Serverfehler\) an den Client zurück, andernfalls wird davon ausgegangen, dass die Verarbeitung erfolgreich ausgeführt werden kann, und der HTTP\-Statuscode 200 \(Erfolgreich\) wird an den Client gesendet.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Öffnen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] mit Administratorrechten.  
  
2.  Öffnen Sie die Projektmappe **HttpAckChannel**.  
  
3.  Starten Sie eine neue Instanz des **Service**\-Projekts, indem Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt klicken und **Debuggen** auswählen und danach im Kontextmenü auf **Neue Instanz starten** klicken.  
  
4.  Starten Sie eine neue Instanz des **Client**\-Projekts, indem Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt klicken und **Debuggen** auswählen und danach im Kontextmenü auf **Neue Instanz starten** klicken.  
  
5.  Sobald der Dienst gestartet wurde, drücken Sie im Clientfenster auf die EINGABETASTE, damit der Client eine Nachricht an den Dienst sendet.  
  
6.  Die erste Nachricht wird vom Dienst verarbeitet, und er sendet einen HTTP\-OK\-Statuscode an den Client zurück.  
  
7.  Die zweite Nachricht ist fehlgeschlagen, und er sendet den HTTP\-Statuscode für einen internen Serverfehler an den Client zurück, der eine <xref:System.ServiceModel.CommunicationException> auf dem Client auslöst.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpAckChannel`