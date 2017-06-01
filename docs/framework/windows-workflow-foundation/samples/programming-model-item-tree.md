---
title: "Programmiermodell-Elementstruktur | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Programmiermodell-Elementstruktur
Dieses Beispiel veranschaulicht, wie in der <xref:System.Activities.Presentation.Model.ModelItem>\-Struktur mit der deklarativen Datenbindung der [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]\-Strukturansicht navigiert wird.  
  
## Beispieldetails  
 Die <xref:System.Activities.Presentation.Model.ModelItem>\-Struktur ist die von der [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]\-Infrastruktur verwendete Abstraktion zum Verfügbarmachen der Daten, die sich auf die zugrunde liegende, bearbeitete Instanz beziehen.Die folgende Abbildung ist eine Darstellung der verschiedenen Ebenen der Infrastruktur innerhalb des [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].  
  
 ![Workflow Designer&#45;Architektur](../../../../docs/framework/windows-workflow-foundation/samples/media/workflowdesignerarch.JPG "WorkflowDesignerArch")  
  
 Ein <xref:System.Activities.Presentation.Model.ModelItem> enthält einen Zeiger auf den zugrunde liegenden Wert sowie eine Auflistung von <xref:System.Activities.Presentation.Model.ModelProperty>\-Objekten.Ein <xref:System.Activities.Presentation.Model.ModelProperty>\-Objekt umfasst wiederum Daten wie beispielsweise Name und Typ der Eigenschaft und einen Zeiger auf den Wert, bei dem es sich wiederum um ein <xref:System.Activities.Presentation.Model.ModelItem> handelt.Einige der von einer <xref:System.Activities.Presentation.Model.ModelProperty> zurückgegebenen <xref:System.Activities.Presentation.Model.ModelItem>\-Elemente werden mit einem Wertkonverter bearbeitet, um sie korrekt in der Strukturansicht anzuzeigen.Im Beispiel wird dann die imperative Programmierung für die <xref:System.Activities.Presentation.Model.ModelItem>\-Struktur mit der imperativen Syntax veranschaulicht wie im Folgenden gezeigt.  
  
```csharp  
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;  
ModelProperty mp = mi.Properties["Activities"];  
mp.Collection.Add(new Persist());  
ModelItem justAdded = mp.Collection.Last();  
justAdded.Properties["DisplayName"].SetValue("new name");  
  
```  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappe "ProgrammingModelItemTree.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Klicken Sie zum Erstellen der Projektmappe im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
3.  Drücken Sie F5, um die Anwendung auszuführen.Das [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]\-Formular wird angezeigt.  
  
4.  Klicken Sie auf die Schaltfläche **Load WF**, um die <xref:System.Activities.Presentation.Model.ModelItem>\-Struktur zu laden und an die Strukturansicht zu binden.  
  
5.  Durch Klicken auf die Schaltfläche **Change Model Item Tree** führen Sie den vorangehenden Code aus, um der Struktur ein Element hinzuzufügen und eine Eigenschaft festzulegen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie den Vorgang fortsetzen.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## Siehe auch  
 <xref:System.Windows.Data.IValueConverter>