---
title: Einfacher Ressourcendienst
ms.date: 03/30/2017
ms.assetid: 4360063e-cc8c-4648-846e-c05a5af51a7a
ms.openlocfilehash: 2d55aecfdf6579b1de4c0cc324e59e23c251b12d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520135"
---
# <a name="basic-resource-service"></a>Einfacher Ressourcendienst
Dieses Beispiel veranschaulicht das Implementieren eines HTTP-basierter Diensts mithilfe der Windows Communication Foundation (WCF) REST-Programmiermodell, das eine Auflistung von Kunden verfügbar macht, die unterstützt das Abrufen, hinzufügen, löschen und Ersetzen-Vorgänge. In diesem Beispiel besteht aus 2 Komponenten – einen selbst gehosteten WCF-HTTP-Dienst (Service.cs) und eine Konsolenanwendung (program.cs), die der Dienst erstellt und Aufrufe durchführt.  
  
## <a name="sample-details"></a>Beispieldetails  
 Der WCF-Dienst macht eine Auflistung von Kunden auf eine Ressource ressourcenorientierte/REST-Weise verfügbar. Kurz gesagt gehören dazu eindeutige URIs für die Auflistung der Kunden und für jeden Kunden in der Auflistung. Der Dienst unterstützt das Senden von HTTP `GET` am Auflistungs-URI, um die gesamte Auflistung abzurufen, und das Senden von HTTP `POST` am Auflistungs-URI, um der Auflistung einen neuen Kunden hinzuzufügen. Der Dienst unterstützt am URI für einen einzelnen Kunden außerdem HTTP `GET`, um die Kundendetails abzurufen, HTTP `PUT`, um die Kundendetails zu ersetzen, und HTTP `DELETE`, um den Kunden aus der Auflistung zu entfernen. Wenn der Auflistung ein neuer Kunde hinzugefügt wird, weist der Dienst ihm einen eindeutigen URI zu und speichert den URI zusammen mit den anderen Kundendetails. Der Dienst verwendet außerdem den HTTP-Speicherortheader der Antwort, um den URI dem Client mitzuteilen.  
  
 Die Datei App.config konfiguriert den WCF-Dienst mit einem Standard-<xref:System.ServiceModel.Description.WebHttpEndpoint>, für den die <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A>-Eigenschaft auf `true` festgelegt ist. Daher erstellt die WCF eine automatische HTML-basierte Hilfeseite unter `http://localhost:8000/Customers/help` , bereitstellt, finden Sie Informationen zum Erstellen von HTTP-Anforderungen für den Dienst und wie die HTTP-Antwort des Diensts – z. B. den Zugriff auf verdeutlicht, wie die Details des Kunden wird in XML und JSON dargestellt.  
  
 Indem der Client die Kundenauflistung (und, allgemeiner ausgedrückt, jede Ressource) auf diese Weise verfügbar macht, kann er mithilfe von URIs sowie HTTP `GET`, `PUT`, `DELETE` und `POST` auf einheitliche Weise mit der Auflistung interagieren. Program.cs veranschaulicht, wie ein solcher Client mit <xref:System.Net.HttpWebRequest> erstellt werden kann. Beachten Sie, dass dies nur eine Möglichkeit, einen WCF REST-Dienst zuzugreifen. Es ist auch möglich, mit anderen .NET Framework-Klassen wie <xref:System.ServiceModel.ChannelFactory> und <xref:System.Net.WebClient> auf den Dienst zuzugreifen. In anderen Beispielen im SDK (z. B. die [grundlegenden HTTP-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md) Beispiel und die [automatische Formatauswahl](../../../../docs/framework/wcf/samples/automatic-format-selection.md) Beispiel) zeigen, wie Sie diese Klassen verwenden, um die Kommunikation mit einem WCF-Dienst.  
  
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicResourceService`  
  
## <a name="see-also"></a>Siehe auch  
 [Einfacher HTTP-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md)  
 [Automatische Formatauswahl](../../../../docs/framework/wcf/samples/automatic-format-selection.md)
