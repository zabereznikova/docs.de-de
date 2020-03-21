---
title: Programmiermodell-Elementstruktur
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: f14b140fdac95f3763cc5625841a725793876fa4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142692"
---
# <a name="programming-model-item-tree"></a>Programmiermodell-Elementstruktur
In diesem Beispiel wird <xref:System.Activities.Presentation.Model.ModelItem> veranschaulicht, wie Sie mithilfe der deklarativen Datenbindung aus der Windows Presentation Foundation (WPF)-Strukturansicht durch die Struktur navigieren.

## <a name="sample-details"></a>Beispieldetails
 Die <xref:System.Activities.Presentation.Model.ModelItem> Struktur ist die Abstraktion, die von der Windows Workflow Designer-Infrastruktur verwendet wird, um die Daten über die zugrunde liegende Instanz verfügbar zu machen, die bearbeitet wird. Die folgende Abbildung zeigt die verschiedenen Infrastrukturebenen im Workflow-Designer.

 ![Diagramm, das die Workflow Designer-Architektur zeigt.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 Ein <xref:System.Activities.Presentation.Model.ModelItem> enthält einen Zeiger auf den zugrunde liegenden Wert sowie eine Auflistung von <xref:System.Activities.Presentation.Model.ModelProperty>-Objekten. Ein <xref:System.Activities.Presentation.Model.ModelProperty>-Objekt umfasst wiederum Daten wie beispielsweise Name und Typ der Eigenschaft und einen Zeiger auf den Wert, bei dem es sich wiederum um ein <xref:System.Activities.Presentation.Model.ModelItem> handelt. Einige der von einer <xref:System.Activities.Presentation.Model.ModelItem> zurückgegebenen <xref:System.Activities.Presentation.Model.ModelProperty>-Elemente werden mit einem Wertkonverter bearbeitet, um sie korrekt in der Strukturansicht anzuzeigen. Im Beispiel wird dann die imperative Programmierung für die <xref:System.Activities.Presentation.Model.ModelItem>-Struktur mit der imperativen Syntax veranschaulicht wie im Folgenden gezeigt.

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie die Lösung ProgrammingModelItemTree.sln in Visual Studio 2010.

2. Erstellen Sie die Lösung, indem Sie im Menü **Build** die Option **Lösung erstellen** auswählen.

3. Drücken Sie die Taste F5, um die Anwendung auszuführen. Anschließend wird das WPF-Formular angezeigt.

4. Klicken Sie auf die <xref:System.Activities.Presentation.Model.ModelItem> Schaltfläche **WF laden,** um sie zu laden und an die Strukturansicht zu binden.

5. Wenn Sie auf die Schaltfläche **Modellelementstruktur** ändern klicken, wird der vorherige Code ausgeführt, um der Struktur ein Element hinzuzufügen und eine Eigenschaft festzulegen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Data.IValueConverter>
