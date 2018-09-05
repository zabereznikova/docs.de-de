---
title: Verwenden der WorkflowInvoker-Klasse
ms.date: 03/30/2017
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
ms.openlocfilehash: d6525dbbd30aae95be4c4ee1de267736e557a541
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748705"
---
# <a name="using-the-workflowinvoker-class"></a>Verwenden der WorkflowInvoker-Klasse
Dieses Beispiel veranschaulicht, wie die <xref:System.Activities.WorkflowInvoker>-Klasse verwendet wird, um eine Aktivität wie eine Methode aufzurufen.  
  
## <a name="sample-details"></a>Beispieldetails  
 Die Verwendung der <xref:System.Activities.WorkflowInvoker>-Klasse ist die einfachste Möglichkeit, eine Aktivität auszuführen. Damit kann eine Aktivität direkt ausgeführt werden, als ob es sich um einen Methodenaufruf handeln würde. Dabei handelt es sich um eine schlanke, leistungsstarke und benutzerfreundliche API, die für Szenarios verwendet werden kann, in denen die Ausführung einer Aktivität nicht die von anderen Hostingvarianten bereitgestellte Steuerungsinfrastruktur erfordert.  
  
 Das Beispiel verwendet eine benutzerdefinierte Aktivität, die von abgeleitet <xref:System.Activities.CodeActivity%601>< Int32\> mit dem Namen `Add` , addiert zwei <xref:System.Activities.InArgument%601>, `X` und `Y`, und gibt eine `Result` <xref:System.Activities.OutArgument%601>. (<xref:System.Activities.CodeActivity%601>\<T > leitet sich von <xref:System.Activities.Activity%601>< T\>, die eine <xref:System.Activities.OutArgument%601> \<T > mit dem Namen `Result`.) Ein `Dictionary` \<string, object > wird verwendet, um die Übergabe von Argumenten in eine aufgerufene Aktivität wird <xref:System.Activities.WorkflowInvoker>. Der Schlüssel des Wörterbuchs entspricht dem Namen eines Arguments für die aufgerufene Aktivität. Der einem bestimmten Schlüssel zugeordnete Wert wird an das durch den Schlüssel identifizierte Argument gebunden.  
  
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`