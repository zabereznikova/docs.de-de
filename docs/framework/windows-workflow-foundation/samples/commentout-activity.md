---
title: CommentOut-Aktivität
ms.date: 03/30/2017
ms.assetid: 340204c3-f827-45fb-870e-55e2ac457ca5
ms.openlocfilehash: 7847f4e1d77c2927a27be6b83f4016a22e4e3b32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515195"
---
# <a name="commentout-activity"></a><span data-ttu-id="08fed-102">CommentOut-Aktivität</span><span class="sxs-lookup"><span data-stu-id="08fed-102">CommentOut Activity</span></span>
<span data-ttu-id="08fed-103">Dieses Beispiel veranschaulicht, wie eine benutzerdefinierte Aktivität geschrieben wird, die andere Aktivitäten vom Ausführungspfad entfernt, indem sie effektiv auskommentiert werden.</span><span class="sxs-lookup"><span data-stu-id="08fed-103">This sample demonstrates how to write a custom activity that removes other activities from the path of execution, effectively commenting them out.</span></span>  
  
## <a name="the-commentout-activity"></a><span data-ttu-id="08fed-104">Die CommentOut-Aktivität</span><span class="sxs-lookup"><span data-stu-id="08fed-104">The CommentOut Activity</span></span>  
 <span data-ttu-id="08fed-105">Hierzu leitet sich die CommentOut-Aktivität von der <xref:System.Activities.CodeActivity>-Basisklasse ab und implementiert eine leere <xref:System.Activities.CodeActivity.Execute%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="08fed-105">To achieve its goal, the CommentOut activity derives from the <xref:System.Activities.CodeActivity> base class and implements an empty <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
}  
```  
  
 <span data-ttu-id="08fed-106">Die Klasse wird wie im folgenden Beispiel gezeigt deklariert.</span><span class="sxs-lookup"><span data-stu-id="08fed-106">The class is declared as shown in the following example.</span></span>  
  
```  
[Designer(typeof(CommentOutDesigner))]  
[ContentProperty("Body")]  
public sealed class CommentOut : CodeActivity  
```  
  
 <span data-ttu-id="08fed-107">Das `Designer`-Attribut gibt die Klasse an, die zur Entwurfszeit die grafische Schnittstelle der Aktivität implementiert.</span><span class="sxs-lookup"><span data-stu-id="08fed-107">The `Designer` attribute specifies the class that implements the visual interface of the activity at design time.</span></span> <span data-ttu-id="08fed-108">Das `ContentProperty`-Attribut deklariert, dass die `"Body"`-Eigenschaft in der XAML-Darstellung einer Instanz dieser Aktivität übersprungen werden kann.</span><span class="sxs-lookup"><span data-stu-id="08fed-108">The `ContentProperty` attribute declares that the `"Body"` property can be skipped in the XAML representation of an instance of this activity.</span></span>  
  
```  
<Border x:Uid="Border_1" BorderThickness ="1">  
    <sad:WorkflowItemPresenter   
    x:Uid="sad:WorkflowItemPresenter_1" AutomationProperties.AutomationId="Body" Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
    AllowedItemType="{x:Type sa:Activity}"  
    HintText="Drop activity here"   
    Margin="5,5,5,5" />  
</Border>  
```  
  
 <span data-ttu-id="08fed-109">In der Designerklasse wird XAML verwendet, um eine benutzerdefinierte visuelle Darstellung der Aktivität zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="08fed-109">In the designer class, XAML is used to create a custom visual representation of the activity.</span></span> <span data-ttu-id="08fed-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> ist eine Klasse, die den visuellen Editor bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="08fed-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> is a class that provides the visual editor.</span></span>  
  
 <span data-ttu-id="08fed-111">Eine einzelne Aktivität kann auf der Oberfläche der `CommentOut`-Aktivität abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="08fed-111">A single activity can be dropped onto the `CommentOut` activity surface.</span></span> <span data-ttu-id="08fed-112">Wenn Sie dieser Oberfläche mehrere Aktivitäten hinzufügen möchten, fügen Sie zunächst eine Sequenzaktivität hinzu.</span><span class="sxs-lookup"><span data-stu-id="08fed-112">If you want to add multiple activities to this surface, drag a sequence activity here first.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="08fed-113">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="08fed-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="08fed-114">Öffnen Sie "CommentOut.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08fed-114">Open CommentOut.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="08fed-115">Kompilieren Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="08fed-115">Compile the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="08fed-116">Starten Sie das Beispiel ohne Debugging, indem Sie STRG+F5 drücken.</span><span class="sxs-lookup"><span data-stu-id="08fed-116">Start the sample without debugging by pressing CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="08fed-117">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="08fed-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="08fed-118">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="08fed-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="08fed-119">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="08fed-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="08fed-120">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="08fed-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`
