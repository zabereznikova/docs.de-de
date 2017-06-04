---
title: "LINQ-Meldungsabfragekorrelation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# LINQ-Meldungsabfragekorrelation
Dieses Beispiel veranschaulicht, wie die inhaltsbasierte Korrelation mithilfe einer benutzerdefinierten <xref:System.ServiceModel.Dispatcher.MessageQuery>\-Implementierung im Gegensatz zu der vom System bereitgestellten <xref:System.ServiceModel.XPathMessageQuery> erfolgt.  
  
## Veranschaulicht  
 Benutzerdefinierte <xref:System.ServiceModel.Dispatcher.MessageQuery>, inhaltsbasierte Korrelation.  
  
## Diskussion  
 In diesem Beispiel wird veranschaulicht, wie zum Zwecke der Korrelation eine Erweiterung von der <xref:System.ServiceModel.Dispatcher.MessageQuery>\-Basisklasse durchgeführt wird.Die benutzerdefinierte Implementierung, `LinqMessageQuery`, ermöglicht es Benutzern, einen XName anzugeben, der innerhalb der Meldung mit XLinq gesucht werden soll.Die von der Abfrage abgerufenen Daten werden verwendet, um den Korrelationsschlüssel zu bilden, mit dem Meldungen an die entsprechende Workflowinstanz weitergeleitet werden.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Dieses Beispiel macht einen Workflowdienst mithilfe von HTTP\-Endpunkten verfügbar.Um dieses Beispiel auszuführen, müssen richtige URL\-ACLs hinzugefügt werden \(weitere Informationen finden Sie unter [Konfigurieren von HTTP und HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353)\), entweder durch Ausführen von Visual Studio als Administrator oder durch Ausführen des folgenden Befehls an einer Eingabeaufforderung mit erhöhten Rechten, um die entsprechenden ACLs hinzuzufügen.Stellen Sie sicher, dass die Domäne und der Benutzername ersetzt werden.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  Sobald die URL\-ACLs hinzugefügt wurden, führen Sie die folgenden Schritte aus.  
  
    1.  Erstellen Sie die Projektmappe.  
  
    2.  Legen Sie mehrere Startprojekte fest, indem Sie mit der rechten Maustaste auf die Projektmappe klicken und **Startprojekte festlegen** auswählen.Füge Sie **Dienst** und **Client** \(in dieser Reihenfolge\) als mehrere Startprojekte hinzu.  
  
    3.  Führen Sie die Anwendung aus.Die Clientkonsole zeigt einen Workflow, der eine Bestellung sendet und die Bestell\-ID empfängt und dann daraufhin den Auftrag bestätigt.Das Fenster "Dienst" zeigt die Anforderungen, die verarbeitet werden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`