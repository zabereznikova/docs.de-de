---
title: Programmiermodell-Elementstruktur
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: f2d89cb2a3b0f6167f043148ea793ec1c264a556
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038175"
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="07298-102">Programmiermodell-Elementstruktur</span><span class="sxs-lookup"><span data-stu-id="07298-102">Programming Model Item Tree</span></span>
<span data-ttu-id="07298-103">In diesem Beispiel wird veranschaulicht, wie <xref:System.Activities.Presentation.Model.ModelItem> die Struktur mithilfe der deklarativen Datenbindung aus der Windows Presentation Foundation (WPF)-Strukturansicht navigiert wird.</span><span class="sxs-lookup"><span data-stu-id="07298-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>

## <a name="sample-details"></a><span data-ttu-id="07298-104">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="07298-104">Sample Details</span></span>
 <span data-ttu-id="07298-105">Die <xref:System.Activities.Presentation.Model.ModelItem>-Struktur ist die von der [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]-Infrastruktur verwendete Abstraktion zur Verfügbarmachung der Daten zur zugrunde liegenden Instanz, die bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="07298-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="07298-106">Die folgende Abbildung ist eine Darstellung der verschiedenen Ebenen der Infrastruktur innerhalb des [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07298-106">The following illustration is a depiction of the various layers of infrastructure within the [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>

 ![Diagramm, das die Workflow-Designer Architektur anzeigt.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <span data-ttu-id="07298-108">Ein <xref:System.Activities.Presentation.Model.ModelItem> enthält einen Zeiger auf den zugrunde liegenden Wert sowie eine Auflistung von <xref:System.Activities.Presentation.Model.ModelProperty>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="07298-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="07298-109">Ein <xref:System.Activities.Presentation.Model.ModelProperty>-Objekt umfasst wiederum Daten wie beispielsweise Name und Typ der Eigenschaft und einen Zeiger auf den Wert, bei dem es sich wiederum um ein <xref:System.Activities.Presentation.Model.ModelItem> handelt.</span><span class="sxs-lookup"><span data-stu-id="07298-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="07298-110">Einige der von einer <xref:System.Activities.Presentation.Model.ModelItem> zurückgegebenen <xref:System.Activities.Presentation.Model.ModelProperty>-Elemente werden mit einem Wertkonverter bearbeitet, um sie korrekt in der Strukturansicht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="07298-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="07298-111">Im Beispiel wird dann die imperative Programmierung für die <xref:System.Activities.Presentation.Model.ModelItem>-Struktur mit der imperativen Syntax veranschaulicht wie im Folgenden gezeigt.</span><span class="sxs-lookup"><span data-stu-id="07298-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="07298-112">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="07298-112">To use this sample</span></span>

1. <span data-ttu-id="07298-113">Öffnen Sie die Projekt Mappe "programmingmudelitemtree. sln" in Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="07298-113">Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="07298-114">Erstellen Sie die Projekt Mappe, indem Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="07298-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>

3. <span data-ttu-id="07298-115">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="07298-115">Press F5 to run the application.</span></span> <span data-ttu-id="07298-116">Daraufhin wird das WPF-Formular angezeigt.</span><span class="sxs-lookup"><span data-stu-id="07298-116">The WPF form is then displayed.</span></span>

4. <span data-ttu-id="07298-117">Klicken Sie auf die Schaltfläche zum Laden <xref:System.Activities.Presentation.Model.ModelItem> von **WF** , um das zu laden und an die Strukturansicht zu binden.</span><span class="sxs-lookup"><span data-stu-id="07298-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>

5. <span data-ttu-id="07298-118">Wenn Sie auf die Schaltfläche **Modellelement Struktur ändern** klicken, wird der vorangehende Code ausgeführt, um der Struktur ein Element hinzuzufügen und eine Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="07298-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07298-119">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="07298-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="07298-120">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="07298-120">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="07298-121">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="07298-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="07298-122">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="07298-122">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="07298-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07298-123">See also</span></span>

- <xref:System.Windows.Data.IValueConverter>
