---
title: "Grundlegende Aktivit&#228;tserstellung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Grundlegende Aktivit&#228;tserstellung
In diesem Beispiel wird veranschaulicht, wie benutzerdefinierte Aktivitäten und vom System bereitgestellte Aktivitäten so zusammengesetzt werden, dass weitere benutzerdefinierte Aktivitäten entstehen.  
  
 Der Workflow, der die Survey\-Aktivität verwendet, plant die Umfrage mit einer Liste von Fragen, und gibt dann die erhaltenen Antworten aus.  
  
## Beispieldetails  
 Das Beispiel verwendet drei benutzerdefinierte Aktivitäten.`ReadLine` ist eine einfache <xref:System.Activities.NativeActivity>\<string\>, die <xref:System.Activities.Bookmark> erstellt, wenn dieses geplant ist, und anschließend `Return`<xref:System.Activities.OutArgument%601> auf den Wert festlegt, mit dem <xref:System.Activities.Bookmark> fortgesetzt wird.`Prompt` ist eine <xref:System.Activities.Activity%601>\<string\>, die eine <xref:System.Activities.InArgument%601>\<string\> mit dem Namen `Text` akzeptiert und die Benutzerantwort in der `Result`<xref:System.Activities.OutArgument%601>\<string\> zurückgibt.Die `Prompt`\-Aktivität verwendet die <xref:System.Activities.Statements.Sequence>\-Aktivität und die <xref:System.Activities.Statements.WriteLine>\-Aktivität, die im Lieferumfang von .NET Framework enthalten sind, von .NET Framework, und integriert auch die benutzerdefinierte `ReadLine`\-Aktivität zum Abrufen von Benutzereingaben.Die letzte benutzerdefinierte Aktivität ist die `Survey`\-Aktivität.Es handelt sich um eine <xref:System.Activities.Activity>\<ICollection\<\-Zeichenfolge\>\>.Diese Aktivität akzeptiert eine <xref:System.Activities.InArgument%601>\<IEnumerable\<\-Zeichenfolge\>\> mit dem Namen `Questions` und füllt das out\-Argument für `Result` mit den Antworten auf.Die `Survey`\-Aktivität verwendet <xref:System.Activities.Statements.ForEach>, <xref:System.Activities.Statements.Sequence> und <xref:System.Activities.Statements.AddToCollection%601> von .NET Framework und verwendet die `Prompt`\-Aktivität, um die Fragen der Umfrage zu stellen und die Antworten abzurufen.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Öffnen Sie die Beispielprojektmappe **BasicActivityComposition.sln** in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`  
  
## Siehe auch