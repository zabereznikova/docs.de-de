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
# <a name="programming-model-item-tree"></a><span data-ttu-id="ab4d6-102">Programmiermodell-Elementstruktur</span><span class="sxs-lookup"><span data-stu-id="ab4d6-102">Programming Model Item Tree</span></span>
<span data-ttu-id="ab4d6-103">In diesem Beispiel wird <xref:System.Activities.Presentation.Model.ModelItem> veranschaulicht, wie Sie mithilfe der deklarativen Datenbindung aus der Windows Presentation Foundation (WPF)-Strukturansicht durch die Struktur navigieren.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>

## <a name="sample-details"></a><span data-ttu-id="ab4d6-104">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="ab4d6-104">Sample Details</span></span>
 <span data-ttu-id="ab4d6-105">Die <xref:System.Activities.Presentation.Model.ModelItem> Struktur ist die Abstraktion, die von der Windows Workflow Designer-Infrastruktur verwendet wird, um die Daten über die zugrunde liegende Instanz verfügbar zu machen, die bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the Windows Workflow Designer infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="ab4d6-106">Die folgende Abbildung zeigt die verschiedenen Infrastrukturebenen im Workflow-Designer.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-106">The following illustration is a depiction of the various layers of infrastructure within the Workflow Designer.</span></span>

 ![Diagramm, das die Workflow Designer-Architektur zeigt.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <span data-ttu-id="ab4d6-108">Ein <xref:System.Activities.Presentation.Model.ModelItem> enthält einen Zeiger auf den zugrunde liegenden Wert sowie eine Auflistung von <xref:System.Activities.Presentation.Model.ModelProperty>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="ab4d6-109">Ein <xref:System.Activities.Presentation.Model.ModelProperty>-Objekt umfasst wiederum Daten wie beispielsweise Name und Typ der Eigenschaft und einen Zeiger auf den Wert, bei dem es sich wiederum um ein <xref:System.Activities.Presentation.Model.ModelItem> handelt.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="ab4d6-110">Einige der von einer <xref:System.Activities.Presentation.Model.ModelItem> zurückgegebenen <xref:System.Activities.Presentation.Model.ModelProperty>-Elemente werden mit einem Wertkonverter bearbeitet, um sie korrekt in der Strukturansicht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="ab4d6-111">Im Beispiel wird dann die imperative Programmierung für die <xref:System.Activities.Presentation.Model.ModelItem>-Struktur mit der imperativen Syntax veranschaulicht wie im Folgenden gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="ab4d6-112">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="ab4d6-112">To use this sample</span></span>

1. <span data-ttu-id="ab4d6-113">Öffnen Sie die Lösung ProgrammingModelItemTree.sln in Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-113">Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="ab4d6-114">Erstellen Sie die Lösung, indem Sie im Menü **Build** die Option **Lösung erstellen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>

3. <span data-ttu-id="ab4d6-115">Drücken Sie die Taste F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-115">Press F5 to run the application.</span></span> <span data-ttu-id="ab4d6-116">Anschließend wird das WPF-Formular angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-116">The WPF form is then displayed.</span></span>

4. <span data-ttu-id="ab4d6-117">Klicken Sie auf die <xref:System.Activities.Presentation.Model.ModelItem> Schaltfläche **WF laden,** um sie zu laden und an die Strukturansicht zu binden.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>

5. <span data-ttu-id="ab4d6-118">Wenn Sie auf die Schaltfläche **Modellelementstruktur** ändern klicken, wird der vorherige Code ausgeführt, um der Struktur ein Element hinzuzufügen und eine Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab4d6-119">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ab4d6-120">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-120">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ab4d6-121">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ab4d6-122">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ab4d6-122">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="ab4d6-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab4d6-123">See also</span></span>

- <xref:System.Windows.Data.IValueConverter>
