---
title: Verwenden der WorkflowInvoker-Klasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f5310b2adefa24d2d16733965395a34cc5cb69d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-workflowinvoker-class"></a>Verwenden der WorkflowInvoker-Klasse
Dieses Beispiel veranschaulicht, wie die <xref:System.Activities.WorkflowInvoker>-Klasse verwendet wird, um eine Aktivität wie eine Methode aufzurufen.  
  
## <a name="sample-details"></a>Beispieldetails  
 Die Verwendung der <xref:System.Activities.WorkflowInvoker>-Klasse ist die einfachste Möglichkeit, eine Aktivität auszuführen. Damit kann eine Aktivität direkt ausgeführt werden, als ob es sich um einen Methodenaufruf handeln würde. Dabei handelt es sich um eine schlanke, leistungsstarke und benutzerfreundliche API, die für Szenarios verwendet werden kann, in denen die Ausführung einer Aktivität nicht die von anderen Hostingvarianten bereitgestellte Steuerungsinfrastruktur erfordert.  
  
 Das Beispiel verwendet eine benutzerdefinierte Aktivität, die abgeleitet <xref:System.Activities.CodeActivity%601>< Int32\> mit dem Namen `Add` , addiert zwei <xref:System.Activities.InArgument%601>, `X` und `Y`, und gibt eine `Result` <xref:System.Activities.OutArgument%601>. (<xref:System.Activities.CodeActivity%601>\<T > leitet sich von <xref:System.Activities.Activity%601>< T\>, verfügt über eine <xref:System.Activities.OutArgument%601> \<T > mit dem Namen `Result`.) Ein `Dictionary` \<string, object > wird verwendet, um die Übergabe von Argumenten in einer Aktivität aufgerufen wird, über <xref:System.Activities.WorkflowInvoker>. Der Schlüssel des Wörterbuchs entspricht dem Namen eines Arguments für die aufgerufene Aktivität. Der einem bestimmten Schlüssel zugeordnete Wert wird an das durch den Schlüssel identifizierte Argument gebunden.  
  
 Im Beispiel wird <xref:System.Activities.WorkflowInvoker.Invoke%2A> aufgerufen und ein Wörterbuch übergeben, das Werte für `X` und `Y` enthält. Die <xref:System.Activities.WorkflowInvoker>-Klasse bindet diese Werte an die Argumente der `Add`-Aktivität, führt die Aktivität aus und gibt das Ergebnis zurück.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "Invoker.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`  
  
## <a name="see-also"></a>Siehe auch
