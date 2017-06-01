---
title: "Verwenden der WorkflowInvoker-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Verwenden der WorkflowInvoker-Klasse
Dieses Beispiel veranschaulicht, wie die <xref:System.Activities.WorkflowInvoker>\-Klasse verwendet wird, um eine Aktivität wie eine Methode aufzurufen.  
  
## Beispieldetails  
 Die Verwendung der <xref:System.Activities.WorkflowInvoker>\-Klasse ist die einfachste Möglichkeit, eine Aktivität auszuführen.Damit kann eine Aktivität direkt ausgeführt werden, als ob es sich um einen Methodenaufruf handeln würde.Dabei handelt es sich um eine schlanke, leistungsstarke und benutzerfreundliche API, die für Szenarios verwendet werden kann, in denen die Ausführung einer Aktivität nicht die von anderen Hostingvarianten bereitgestellte Steuerungsinfrastruktur erfordert.  
  
 Im Beispiel wird eine von <xref:System.Activities.CodeActivity%601>\<Int32\> abgeleitete benutzerdefinierte Aktivität mit dem Namen `Add` verwendet, die zwei <xref:System.Activities.InArgument%601>\-Werte \(`X` und `Y`\) hinzufügt und einen `Result` <xref:System.Activities.OutArgument%601>\-Wert zurückgibt.\(Die <xref:System.Activities.CodeActivity%601>\<T\> ist von der <xref:System.Activities.Activity%601>\<T\> abgeleitet, die ein <xref:System.Activities.OutArgument%601>\<T\> mit dem Namen `Result` aufweist.\) Zur Übergabe von Argumenten in eine mit <xref:System.Activities.WorkflowInvoker> aufgerufene Aktivität wird ein `Dictionary`\<Zeichenfolge, Objekt\> verwendet.Der Schlüssel des Wörterbuchs entspricht dem Namen eines Arguments für die aufgerufene Aktivität.Der einem bestimmten Schlüssel zugeordnete Wert wird an das durch den Schlüssel identifizierte Argument gebunden.  
  
 Im Beispiel wird <xref:System.Activities.WorkflowInvoker.Invoke%2A> aufgerufen und ein Wörterbuch übergeben, das Werte für `X` und `Y` enthält.Die <xref:System.Activities.WorkflowInvoker>\-Klasse bindet diese Werte an die Argumente der `Add`\-Aktivität, führt die Aktivität aus und gibt das Ergebnis zurück.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "Invoker.sln".  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`  
  
## Siehe auch