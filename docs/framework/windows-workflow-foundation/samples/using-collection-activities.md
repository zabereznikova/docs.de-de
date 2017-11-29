---
title: "Verwenden von Auflistungsaktivitäten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: aa7b3b6815adfba9367585174b242aa7410d578e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-collection-activities"></a><span data-ttu-id="f4247-102">Verwenden von Auflistungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="f4247-102">Using Collection Activities</span></span>
<span data-ttu-id="f4247-103">In diesem Beispiel wird veranschaulicht, wie die Auflistungsaktivitäten mit (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601> und <xref:System.Activities.Statements.RemoveFromCollection%601>) mit einer Klasse verwendet werden, die die <xref:System.Collections.ICollection>-Schnittstelle implementiert, und wie eine benutzerdefinierte Aktivität erstellt wird, die eine Auflistung durchläuft, um den Inhalt jedes Elements in der Auflistung auszugeben.</span><span class="sxs-lookup"><span data-stu-id="f4247-103">This sample demonstrates how to use the collection activities (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601>, and <xref:System.Activities.Statements.RemoveFromCollection%601>) with a class that implements the <xref:System.Collections.ICollection> interface and how to create a custom activity that iterates over a collection to print out the contents of each element in the collection.</span></span> <span data-ttu-id="f4247-104">Die benutzerdefinierte Aktivität mit dem Namen `PrintCollection` gibt die Elementmember einer Auflistung mit dem Namen `Numbers` in der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="f4247-104">The custom activity, which is named `PrintCollection`, prints to the console the item members of a collection named `Numbers`.</span></span>  
  
 <span data-ttu-id="f4247-105">In der folgenden Tabelle werden die vier Aktivitäten beschrieben, die eine Auflistungsbearbeitung für Workflows bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f4247-105">The following table describes the four activities that provide collection manipulation for workflows.</span></span>  
  
|<span data-ttu-id="f4247-106">Name der Aktivität</span><span class="sxs-lookup"><span data-stu-id="f4247-106">Activity name</span></span>|<span data-ttu-id="f4247-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4247-107">Description</span></span>|  
|-------------------|-----------------|  
|<xref:System.Activities.Statements.AddToCollection%601>|<span data-ttu-id="f4247-108">Fügt einer Auflistung ein Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4247-108">Adds an item to a collection.</span></span>|  
|<xref:System.Activities.Statements.ClearCollection%601>|<span data-ttu-id="f4247-109">Löscht alle Elemente aus einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="f4247-109">Clears all items in a collection</span></span>|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|<span data-ttu-id="f4247-110">Gibt `true` zurück, wenn das angegebene Element in einer Auflistung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f4247-110">Returns `true` if specified item exists in collection.</span></span>|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|<span data-ttu-id="f4247-111">Entfernt ein Element aus einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="f4247-111">Removes an item from a collection.</span></span>|  
  
 <span data-ttu-id="f4247-112">Das Beispiel besteht aus zwei Projektmappen, eine im Verzeichnis "CodedWorkflow", und die andere im Verzeichnis "DesignerWorkflow".</span><span class="sxs-lookup"><span data-stu-id="f4247-112">The sample consists of two solutions, one under the CodedWorkflow directory and the other under the DesignerWorkflow directory.</span></span> <span data-ttu-id="f4247-113">Diese veranschaulichen zwei verschiedene Möglichkeiten der Verwendung der Aktivitäten zu den gleichen Zwecken.</span><span class="sxs-lookup"><span data-stu-id="f4247-113">They demonstrate two different ways of using the activities for the same purposes.</span></span>  
  
|<span data-ttu-id="f4247-114">Lösung</span><span class="sxs-lookup"><span data-stu-id="f4247-114">Solution</span></span>|<span data-ttu-id="f4247-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4247-115">Description</span></span>|<span data-ttu-id="f4247-116">Hauptdateien</span><span class="sxs-lookup"><span data-stu-id="f4247-116">Main Files</span></span>|  
|-|-|-|  
|<span data-ttu-id="f4247-117">CodedWorkflow</span><span class="sxs-lookup"><span data-stu-id="f4247-117">CodedWorkflow</span></span>|<span data-ttu-id="f4247-118">Beispielclientanwendung, die veranschaulicht, wie die Auflistungsaktivitäten programmgesteuert aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f4247-118">Sample client application that demonstrates how to invoke the collection activities programmatically.</span></span>|<span data-ttu-id="f4247-119">**PrintCollection.cs**: hilfsaktivität zum an die Konsole jedes Element in einer Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="f4247-119">**PrintCollection.cs**: helper activity to print out to the console every item in a collection.</span></span><br /><br /> <span data-ttu-id="f4247-120">**Datei "Program.cs"**: erstellt programmgesteuert eine Sequenzaktivität, die eine Reihe von auflistungsaktivitäten enthält, und führt diese.</span><span class="sxs-lookup"><span data-stu-id="f4247-120">**Program.cs**: programmatically builds a sequence activity that contains a series of collection activities, and executes it.</span></span>|  
|<span data-ttu-id="f4247-121">DesignerWorkflow</span><span class="sxs-lookup"><span data-stu-id="f4247-121">DesignerWorkflow</span></span>|<span data-ttu-id="f4247-122">Beispielclientanwendung, die veranschaulicht, wie die Auflistungsaktivitäten im Workflow-Designer deklarativ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4247-122">Sample client application that demonstrates how to use the collection activities declaratively in the workflow designer.</span></span>|<span data-ttu-id="f4247-123">**CollectionWorkflow.xaml**: eines Workflows deklarativ erstellt, mit dem Designer, der die auflistungsaktivitäten verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4247-123">**CollectionWorkflow.xaml**: a workflow created declaratively with the designer that uses the collection activities.</span></span><br /><br /> <span data-ttu-id="f4247-124">**PrintCollection.cs**: hilfsaktivität zum an die Konsole jedes Element in einer Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="f4247-124">**PrintCollection.cs**: helper activity to print out to the console every item in a collection.</span></span><br /><br /> <span data-ttu-id="f4247-125">**Datei "Program.cs"**: Ruft die in Collectionworklflow.XAML beschriebenen Workflow auf.</span><span class="sxs-lookup"><span data-stu-id="f4247-125">**Program.cs**: invokes the workflow described in CollectionWorkflow.xaml.</span></span>|  
  
 <span data-ttu-id="f4247-126">In der Demo werden die Elementmember der Auflistung `Numbers` mit einer individuell definierten Aktivität mit dem Namen `PrintCollection` in der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f4247-126">In the demonstration, the item members of collection `Numbers` are printed on the console using a custom-defined activity called `PrintCollection`.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f4247-127">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4247-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="f4247-128">Öffnen Sie die Projektmappendatei "Collection.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4247-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Collection.sln solution file.</span></span>  
  
2.  <span data-ttu-id="f4247-129">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4247-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="f4247-130">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f4247-130">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f4247-131">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f4247-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f4247-132">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f4247-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f4247-133">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="f4247-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f4247-134">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f4247-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`  
  
## <a name="see-also"></a><span data-ttu-id="f4247-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4247-135">See Also</span></span>
