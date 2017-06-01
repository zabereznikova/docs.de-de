---
title: "OperationScope | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# OperationScope
Dieses Beispiel veranschaulicht, wie die Messagingaktivitäten <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> verwendet werden können, um in einem Workflowdienst eine vorhandene benutzerdefinierte Aktivität als Vorgang verfügbar zu machen.Dieses Beispiel umfasst eine neue benutzerdefinierte Aktivität, die als `OperationScope` bezeichnet wird.Sie ist dazu vorgesehen, die Entwicklung eines Workflowdiensts zu vereinfachen, indem Benutzer den Textkörper der Vorgänge als benutzerdefinierte Aktivitäten getrennt erstellen können und sie dann einfach als Dienstvorgänge mit der `OperationScope`\-Aktivität verfügbar machen können.Eine benutzerdefinierte `Add`\-Aktivität, die zwei `in`\-Argumente annimmt und ein `out`\-Argument zurückgibt, könnte z. B. als `Add`\-Vorgang mit dem Workflowdienst verfügbar gemacht werden, indem es in einer `OperationScope`\-Aktivität abgelegt wird.  
  
 Der Bereich funktioniert, indem er die als Textkörper bereitgestellte Aktivität überprüft.Alle ungebundenen `in`\-Argumente werden als Eingaben von der eingehenden Nachricht betrachtet.Alle `out`\-Argumente, unabhängig davon, ob sie gebunden sind, werden als Ausgaben in der nachfolgenden Antwortnachricht betrachtet.Der Name des verfügbar gemachten Vorgangs wird dem Anzeigenamen der `OperationScope`\-Aktivität entnommen.Das Endergebnis ist, dass die Textaktivität mit den Parametern aus den Nachrichten, die an die Argumente der Aktivität gebunden sind, von <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> umschlossen wird.  
  
 Dieses Beispiel macht einen Workflowdienst mithilfe von HTTP\-Endpunkten verfügbar.Für die Ausführung müssen richtige URL\-ACLs hinzugefügt werden.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Konfigurieren von HTTP und HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).Die Ausführung des folgenden Befehls an einer Eingabeaufforderung mit erhöhten Rechten fügt die entsprechenden ACLs hinzu \(stellen Sie sicher, dass die Domäne und der Benutzername für% DOMAIN%\\%UserName% ersetzt werden\).  
  
 **netsh http add urlacl url\=http:\/\/\+:8000\/ user\=%DOMAIN%\\%UserName%**  
  
### So führen Sie das Beispiel aus  
  
1.  Öffnen Sie die Projektmappe "OperationScope.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Legen Sie mehrere Startprojekte fest, indem Sie mit der rechten Maustaste auf die Projektmappe im Projektmappen\-Explorer klicken und **Startprojekte festlegen** auswählen.Fügen Sie Scenario und Scenario\_Client \(in dieser Reihenfolge\) als mehrere Startprojekte hinzu.  
  
3.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
    > [!WARNING]
    >  Dieser Schritt ist aufgrund der benutzerdefinierten `OperationScope`\-Aktivität zum Anzeigen des Workflows "BankService.xaml" erforderlich.  
  
4.  Drücken Sie STRG\+F5, um die Anwendung auszuführen.Die Konsole Scenario\_Client fordert Sie zu Eingaben auf, und die entsprechende Ausgabe wird in der Konsole Scenario dargestellt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`  
  
## Siehe auch