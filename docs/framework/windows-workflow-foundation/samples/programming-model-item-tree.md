---
title: Programmiermodell-Elementstruktur
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: efda69ac568b0ad9c5fdcf4d42722c5b7dadd3f3
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715666"
---
# <a name="programming-model-item-tree"></a>Programmiermodell-Elementstruktur
In diesem Beispiel wird veranschaulicht, wie die <xref:System.Activities.Presentation.Model.ModelItem> Struktur mithilfe der deklarativen Datenbindung aus der Windows Presentation Foundation (WPF)-Strukturansicht navigiert wird.

## <a name="sample-details"></a>Beispieldetails
 Die <xref:System.Activities.Presentation.Model.ModelItem> Tree ist die Abstraktion, die von der Windows Workflow-Designer-Infrastruktur verwendet wird, um die Daten über die zugrunde liegende Instanz verfügbar zu machen, die bearbeitet wird. Die folgende Abbildung zeigt eine Darstellung der verschiedenen Ebenen der Infrastruktur innerhalb der Workflow-Designer.

 ![Diagramm, das die Workflow-Designer Architektur anzeigt.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 Ein <xref:System.Activities.Presentation.Model.ModelItem> enthält einen Zeiger auf den zugrunde liegenden Wert sowie eine Auflistung von <xref:System.Activities.Presentation.Model.ModelProperty>-Objekten. Ein <xref:System.Activities.Presentation.Model.ModelProperty>-Objekt umfasst wiederum Daten wie beispielsweise Name und Typ der Eigenschaft und einen Zeiger auf den Wert, bei dem es sich wiederum um ein <xref:System.Activities.Presentation.Model.ModelItem> handelt. Einige der von einer <xref:System.Activities.Presentation.Model.ModelItem> zurückgegebenen <xref:System.Activities.Presentation.Model.ModelProperty>-Elemente werden mit einem Wertkonverter bearbeitet, um sie korrekt in der Strukturansicht anzuzeigen. Im Beispiel wird dann die imperative Programmierung für die <xref:System.Activities.Presentation.Model.ModelItem>-Struktur mit der imperativen Syntax veranschaulicht wie im Folgenden gezeigt.

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie die Projekt Mappe "programmingmudelitemtree. sln" in Visual Studio 2010.

2. Erstellen Sie die Projekt Mappe, indem Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen** auswählen.

3. Drücken Sie F5, um die Anwendung auszuführen. Daraufhin wird das WPF-Formular angezeigt.

4. Klicken Sie auf die Schaltfläche **WF laden** , um die <xref:System.Activities.Presentation.Model.ModelItem> zu laden und an die Strukturansicht zu binden.

5. Wenn Sie auf die Schaltfläche **Modellelement Struktur ändern** klicken, wird der vorangehende Code ausgeführt, um der Struktur ein Element hinzuzufügen und eine Eigenschaft festzulegen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.IValueConverter>
