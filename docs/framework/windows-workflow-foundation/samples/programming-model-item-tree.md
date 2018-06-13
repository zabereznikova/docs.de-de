---
title: Programmiermodell-Elementstruktur
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: c5bbbba4f599801c5bffdbd19e14295ff239dfcd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516473"
---
# <a name="programming-model-item-tree"></a>Programmiermodell-Elementstruktur
In diesem Beispiel wird veranschaulicht, wie zum Navigieren der <xref:System.Activities.Presentation.Model.ModelItem> -Struktur mit der deklarativen Datenbindung der Strukturansicht Windows Presentation Foundation (WPF).  
  
## <a name="sample-details"></a>Beispieldetails  
 Die <xref:System.Activities.Presentation.Model.ModelItem>-Struktur ist die von der [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]-Infrastruktur verwendete Abstraktion zur Verfügbarmachung der Daten zur zugrunde liegenden Instanz, die bearbeitet wird. Die folgende Abbildung ist eine Darstellung der verschiedenen Ebenen der Infrastruktur innerhalb des [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].  
  
 ![Workflow-Designer-Architektur](../../../../docs/framework/windows-workflow-foundation/samples/media/workflowdesignerarch.JPG "WorkflowDesignerArch")  
  
 Ein <xref:System.Activities.Presentation.Model.ModelItem> enthält einen Zeiger auf den zugrunde liegenden Wert sowie eine Auflistung von <xref:System.Activities.Presentation.Model.ModelProperty>-Objekten. Ein <xref:System.Activities.Presentation.Model.ModelProperty>-Objekt umfasst wiederum Daten wie beispielsweise Name und Typ der Eigenschaft und einen Zeiger auf den Wert, bei dem es sich wiederum um ein <xref:System.Activities.Presentation.Model.ModelItem> handelt. Einige der von einer <xref:System.Activities.Presentation.Model.ModelItem> zurückgegebenen <xref:System.Activities.Presentation.Model.ModelProperty>-Elemente werden mit einem Wertkonverter bearbeitet, um sie korrekt in der Strukturansicht anzuzeigen. Im Beispiel wird dann die imperative Programmierung für die <xref:System.Activities.Presentation.Model.ModelItem>-Struktur mit der imperativen Syntax veranschaulicht wie im Folgenden gezeigt.  
  
```csharp  
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;  
ModelProperty mp = mi.Properties["Activities"];  
mp.Collection.Add(new Persist());  
ModelItem justAdded = mp.Collection.Last();  
justAdded.Properties["DisplayName"].SetValue("new name");  
```  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappe "ProgrammingModelItemTree.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe durch Auswahl **Projektmappe** aus der **erstellen** Menü.  
  
3.  Drücken Sie F5, um die Anwendung auszuführen. Das [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]-Formular wird angezeigt.  
  
4.  Klicken Sie auf die **Load WF** Schaltfläche beim Laden der <xref:System.Activities.Presentation.Model.ModelItem> und an die Strukturansicht zu binden.  
  
5.  Klicken auf die **Change Model Item Tree** Schaltfläche führt den vorangehenden Code aus, um der Struktur ein Element hinzuzufügen und eine Eigenschaft festzulegen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Data.IValueConverter>
