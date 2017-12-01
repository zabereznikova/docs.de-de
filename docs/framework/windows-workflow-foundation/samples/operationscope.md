---
title: OperationScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b90ab7e38f40cb515166d4d08e0316ffb9061be3
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
---
# <a name="operationscope"></a>OperationScope
Dieses Beispiel veranschaulicht, wie die Messagingaktivitäten <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> verwendet werden können, um in einem Workflowdienst eine vorhandene benutzerdefinierte Aktivität als Vorgang verfügbar zu machen. Dieses Beispiel umfasst eine neue benutzerdefinierte Aktivität, die als `OperationScope` bezeichnet wird. Sie ist dazu vorgesehen, die Entwicklung eines Workflowdiensts zu vereinfachen, indem Benutzer den Textkörper der Vorgänge als benutzerdefinierte Aktivitäten getrennt erstellen können und sie dann einfach als Dienstvorgänge mit der `OperationScope`-Aktivität verfügbar machen können. Eine benutzerdefinierte `Add`-Aktivität, die zwei `in`-Argumente annimmt und ein `out`-Argument zurückgibt, könnte z. B. als `Add`-Vorgang mit dem Workflowdienst verfügbar gemacht werden, indem es in einer `OperationScope`-Aktivität abgelegt wird.  
  
 Der Bereich funktioniert, indem er die als Textkörper bereitgestellte Aktivität überprüft. Alle ungebundenen `in`-Argumente werden als Eingaben von der eingehenden Nachricht betrachtet. Alle `out`-Argumente, unabhängig davon, ob sie gebunden sind, werden als Ausgaben in der nachfolgenden Antwortnachricht betrachtet. Der Name des verfügbar gemachten Vorgangs wird dem Anzeigenamen der `OperationScope`-Aktivität entnommen. Das Endergebnis ist, dass die Textaktivität mit den Parametern aus den Nachrichten, die an die Argumente der Aktivität gebunden sind, von <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> umschlossen wird.  
  
 Dieses Beispiel macht einen Workflowdienst mithilfe von HTTP-Endpunkten verfügbar. Für die Ausführung müssen richtige URL-ACLs hinzugefügt werden. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Konfigurieren von HTTP und HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353). Ausführen des folgenden Befehls an einer Eingabeaufforderung mit erhöhten Rechten fügt die entsprechenden ACLs hinzu (Stellen Sie sicher, dass die Domäne und den Benutzernamen, für die Domäne ersetzt werden %\\%UserName%).  
  
 **Netsh http Urlacl Url hinzufügen = http: / / +: 8000 / Benutzer = "% Domäne"\\%UserName%**  
  
### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Öffnen Sie die Projektmappe "OperationScope.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Mehrere Startprojekte festlegen, indem Sie die Projektmappe im Projektmappen-Explorer mit der rechten Maustaste und auswählen **Startprojekte festlegen**. Fügen Sie Scenario und Scenario_Client (in dieser Reihenfolge) als mehrere Startprojekte hinzu.  
  
3.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
    > [!WARNING]
    >  Dieser Schritt ist aufgrund der benutzerdefinierten `OperationScope`-Aktivität zum Anzeigen des Workflows "BankService.xaml" erforderlich.  
  
4.  Drücken Sie STRG+F5, um die Anwendung auszuführen. Die Konsole Scenario_Client fordert Sie zu Eingaben auf, und die entsprechende Ausgabe wird in der Konsole Scenario dargestellt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`