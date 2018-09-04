---
title: HTTP-Bestätigungskanal
ms.date: 03/30/2017
ms.assetid: 469f3056-5ef2-4753-8acf-b574d23d83cf
ms.openlocfilehash: d83f3aa590471aa3d83b8f7bd1464ec1e6e106fc
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43559542"
---
# <a name="http-acknowledgement-channel"></a>HTTP-Bestätigungskanal
Der HTTP-Bestätigungskanal ist ein Beispiel für einen geschichteten Kanal, der das unidirektionale Nachrichtenmuster ändert, sodass nicht automatisch beim Eingang eine Bestätigung gesendet wird, sondern ein Dienst eingehende Nachrichten bestätigen oder ablehnen kann. Der HTTP-Bestätigungskanal ermöglicht es auch, dass der Dienst die Bestätigung verzögern kann, bis auf Geschäftsebene garantiert werden kann, dass die Nachricht verarbeitet wird.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.ServiceModel.Channels.ReceiveContext>, Beispiel für geschichteten Kanal (HTTP-Bestätigungskanal).  
  
## <a name="discussion"></a>Diskussion  
 Der HTTP-Bestätigungskanal implementiert <xref:System.ServiceModel.Channels.ReceiveContext>, um das HTTP-Anforderungs-/Antwortnachrichtenmuster in ein unidirektionales Muster mit verzögerter Bestätigung umzugestalten. Mit diesem neuen Muster kann ein Dienst die Nachrichtenverarbeitung sicherstellen, indem eine Bestätigung in Form des HTTP-Statuscodes 200 (OK) gesendet wird, ohne dass der Client blockiert wird, solange die Nachrichtenverarbeitung nicht abgeschlossen ist. Oder er kann eine Fehlermeldung an den Client in Form des HTTP-Statuscodes 500 (Interner Serverfehler) senden. Ein Dienst könnte z. B. eine Bestätigung senden, nachdem er eine Nachricht in eine Warteschlange geschrieben hat, und anschließend mit der asynchronen Verarbeitung der Nachricht fortfahren. In diesem Szenario könnte ein Client sicherstellen, dass seine Nachrichten mindestens einmal vom Dienst verarbeitet wurden, indem er jede Nachricht so oft sendet, bis er eine Bestätigung vom Dienst erhält. Hinweis: Wenn ein Dienst eine schnelle asynchrone Nachrichtenverarbeitung über HTTP ohne Garantie der Nachrichtenverarbeitung erfordert, ist das <xref:System.ServiceModel.Channels.OneWayBindingElement> eine bessere Wahl.  
  
 <xref:System.ServiceModel.Channels.ReceiveContext> wird zum Halten der Nachricht verwendet, während festgestellt wird, ob die Nachricht beim Dienst verarbeitet werden kann. Die Fähigkeit eines Diensts, die Nachricht erfolgreich zu verarbeiten, wird durch Aufrufen der Complete-Methode im <xref:System.ServiceModel.Channels.ReceiveContext>-Objekt, das einen HTTP-OK-Statuscode sendet, angegeben. Durch Aufrufen der <xref:System.ServiceModel.Channels.ReceiveContext>-Methode von `Abandon` im <xref:System.ServiceModel.Channels.ReceiveContext>-Objekt wird angegeben, ob der Dienst die Nachricht verarbeiten kann.  
  
 In diesem Beispiel fordert der Client die Verarbeitung von Informationen, indem er eine Mitarbeiter-ID sendet. Wenn die beim Dienst eingegangene Mitarbeiter-ID größer als 50 ist, sendet der Dienst den HTTP-Statuscode 500 (Interner Serverfehler) an den Client zurück, andernfalls wird davon ausgegangen, dass die Verarbeitung erfolgreich ausgeführt werden kann, und der HTTP-Statuscode 200 (Erfolgreich) wird an den Client gesendet.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] mit Administratorrechten.  
  
2.  Öffnen der **HttpAckChannel** Lösung.  
  
3.  Starten Sie eine neue Instanz der der **Service** Projekt mit der rechten Maustaste das Projekt im **Projektmappen-Explorer**, und wählen **Debuggen**, **neue Instanz starten** aus dem Kontextmenü.  
  
4.  Starten Sie eine neue Instanz der der **Client** Projekt mit der rechten Maustaste das Projekt im **Projektmappen-Explorer**, und wählen **Debuggen**, und **neue Instanz starten** aus dem Kontextmenü.  
  
5.  Sobald der Dienst gestartet wurde, drücken Sie im Clientfenster auf die EINGABETASTE, damit der Client eine Nachricht an den Dienst sendet.  
  
6.  Die erste Nachricht wird vom Dienst verarbeitet, und er sendet einen HTTP-OK-Statuscode an den Client zurück.  
  
7.  Die zweite Nachricht ist fehlgeschlagen, und er sendet den HTTP-Statuscode für einen internen Serverfehler an den Client zurück, der eine <xref:System.ServiceModel.CommunicationException> auf dem Client auslöst.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpAckChannel`
