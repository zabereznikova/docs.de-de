---
title: Einfacher Ressourcendienst
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4360063e-cc8c-4648-846e-c05a5af51a7a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 68edbf5a2c96893bdf0e3a7a923084adea9e3c21
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="basic-resource-service"></a>Einfacher Ressourcendienst
In diesem Beispiel wird veranschaulicht, wie ein HTTP-basierter Dienst mithilfe des [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST-Programmiermodells implementiert wird, das eine Auflistung von Kunden verfügbar macht, die die Vorgänge zum Abrufen, Hinzufügen, Löschen und Ersetzen unterstützt. Dieses Beispiel besteht aus zwei Komponenten – einem selbst gehosteten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-HTTP-Dienst (Service.cs) und einer Konsolenanwendung (program.cs), die den Dienst erstellt und Aufrufe an den Dienst durchführt.  
  
## <a name="sample-details"></a>Beispieldetails  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst macht eine Auflistung der Kunden auf ressourcenorientierte/REST-Weise verfügbar. Kurz gesagt gehören dazu eindeutige URIs für die Auflistung der Kunden und für jeden Kunden in der Auflistung. Der Dienst unterstützt das Senden von HTTP `GET` am Auflistungs-URI, um die gesamte Auflistung abzurufen, und das Senden von HTTP `POST` am Auflistungs-URI, um der Auflistung einen neuen Kunden hinzuzufügen. Der Dienst unterstützt am URI für einen einzelnen Kunden außerdem HTTP `GET`, um die Kundendetails abzurufen, HTTP `PUT`, um die Kundendetails zu ersetzen, und HTTP `DELETE`, um den Kunden aus der Auflistung zu entfernen. Wenn der Auflistung ein neuer Kunde hinzugefügt wird, weist der Dienst ihm einen eindeutigen URI zu und speichert den URI zusammen mit den anderen Kundendetails. Der Dienst verwendet außerdem den HTTP-Speicherortheader der Antwort, um den URI dem Client mitzuteilen.  
  
 Die Datei App.config konfiguriert den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst mit einem Standard-<xref:System.ServiceModel.Description.WebHttpEndpoint>, für den die <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A>-Eigenschaft auf `true` festgelegt ist. Daraufhin erstellt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eine automatische HTML-basierte Hilfeseite unter `http://localhost:8000/Customers/help`, die Informationen dazu bereitstellt, wie HTTP-Anforderungen an den Dienst erstellt werden und wie auf die HTTP-Antwort des Diensts – z. B. die Darstellung der Kundendetails in XML und JSON – zugegriffen werden kann.  
  
 Indem der Client die Kundenauflistung (und, allgemeiner ausgedrückt, jede Ressource) auf diese Weise verfügbar macht, kann er mithilfe von URIs sowie HTTP `GET`, `PUT`, `DELETE` und `POST` auf einheitliche Weise mit der Auflistung interagieren. Program.cs veranschaulicht, wie ein solcher Client mit <xref:System.Net.HttpWebRequest> erstellt werden kann. Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST-Dienst darstellt. Es ist auch möglich, mit anderen .NET Framework-Klassen wie <xref:System.ServiceModel.ChannelFactory> und <xref:System.Net.WebClient> auf den Dienst zuzugreifen. Weitere Beispiele im SDK (wie z. B. die [grundlegenden HTTP-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md) Beispiel und die [automatische Formatauswahl](../../../../docs/framework/wcf/samples/automatic-format-selection.md) Beispiel) zeigen, wie Sie diese Klassen verwenden, um die Kommunikation mit einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst.  
  
 Das Beispiel umfasst einen selbst gehosteten Dienst und einen Client, die in einer Konsolenanwendung ausgeführt werden. Während die Konsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappe für das Beispiel eines grundlegenden Ressourcendiensts. Sie müssen [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] als Administrator ausführen, damit das Beispiel erfolgreich ausgeführt werden kann. Zu diesem Zweck mit der rechten Maustaste die [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] und wählen Sie dann **als Administrator ausführen** aus dem Kontextmenü.  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen, und dann STRG+F5, um die Konsolenanwendung auszuführen. Im eingeblendeten Konsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt. Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben. Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.  
  
3.  Drücken Sie eine beliebige Taste, um das Beispiel zu beenden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicResourceService`  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegende HTTP-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md)  
 [Automatische Formatauswahl](../../../../docs/framework/wcf/samples/automatic-format-selection.md)
