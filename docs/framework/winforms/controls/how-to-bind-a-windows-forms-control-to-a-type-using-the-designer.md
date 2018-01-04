---
title: 'Gewusst wie: Binden eines Windows Forms-Steuerelements an einen Typ mithilfe des Designers'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a25b0dc81a6511698394eb86343f09051befc87f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="dbae1-102">Gewusst wie: Binden eines Windows Forms-Steuerelements an einen Typ mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="dbae1-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>
<span data-ttu-id="dbae1-103">Beim Erstellen von Steuerelementen, die mit Daten interagieren, ist es manchmal erforderlich, ein Steuerelement an einen Typ statt an ein Objekt zu binden.</span><span class="sxs-lookup"><span data-stu-id="dbae1-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="dbae1-104">Sie müssen normalerweise ein Steuerelement zur Entwurfszeit an einen Typ binden, wenn Daten möglicherweise nicht verfügbar sind, aber die datengebundenen Steuerelemente dennoch Daten von der öffentlichen Schnittstelle eines Typs anzeigen sollen.</span><span class="sxs-lookup"><span data-stu-id="dbae1-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="dbae1-105">Die folgenden Verfahren wird gezeigt, wie zum Erstellen eines neuen <xref:System.Windows.Forms.BindingSource> also an einen Typ gebunden, und klicken Sie dann eine der Eigenschaften des Typs binden der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft eine <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="dbae1-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="dbae1-106">So binden Sie die BindingSource an einen Typen</span><span class="sxs-lookup"><span data-stu-id="dbae1-106">To bind the BindingSource to a type</span></span>  
  
1.  <span data-ttu-id="dbae1-107">Erstellen Sie ein Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="dbae1-107">Create a Windows Forms project.</span></span>  
  
     <span data-ttu-id="dbae1-108">Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="dbae1-108">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="dbae1-109">In **Entwurf** anzuzeigen, ziehen Sie eine <xref:System.Windows.Forms.BindingSource> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="dbae1-109">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>  
  
3.  <span data-ttu-id="dbae1-110">In der **Eigenschaften** Fenster, klicken Sie auf den Pfeil für den <xref:System.Windows.Forms.BindingSource.DataSource%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="dbae1-110">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>  
  
4.  <span data-ttu-id="dbae1-111">Klicken Sie im **DataSource-UI-Typ-Editor** auf **Projektdatenquelle hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dbae1-111">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>  
  
5.  <span data-ttu-id="dbae1-112">Wählen Sie auf der Seite **Datenquellentyp auswählen** die Option **Objekt** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dbae1-112">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>  
  
6.  <span data-ttu-id="dbae1-113">Wählen Sie den Typ aus, an den gebunden werden soll:</span><span class="sxs-lookup"><span data-stu-id="dbae1-113">Select the type to bind to:</span></span>  
  
    -   <span data-ttu-id="dbae1-114">Wenn sich der Typ, den Sie binden möchten, im aktuellen Projekt befindet oder die Assembly, die den Typ enthält, bereits als Verweis hinzugefügt ist, müssen Sie die Knoten erweitern, um den gewünschten Typ zu suchen. Wählen Sie ihn anschließend aus.</span><span class="sxs-lookup"><span data-stu-id="dbae1-114">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>  
  
         <span data-ttu-id="dbae1-115">- oder - </span><span class="sxs-lookup"><span data-stu-id="dbae1-115">-or-</span></span>  
  
    -   <span data-ttu-id="dbae1-116">Wenn sich der Typ, den Sie binden möchten, in einer anderen Assembly befindet, die derzeit nicht in der Liste der Verweise erscheint, klicken Sie auf **Verweis hinzufügen** und anschließend auf die Registerkarte **Projekte**. Wählen Sie das Projekt aus, das das gewünschte Geschäftsobjekt enthält, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbae1-116">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="dbae1-117">Dieses Projekt erscheint in der Liste der Assemblys. Dadurch können Sie die Knoten erweitern, um den gewünschten Typ zu suchen und ihn anschließend auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="dbae1-117">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="dbae1-118">Deaktivieren Sie das Dialogfeld **Assemblys ausblenden, die mit „Microsoft“ oder „System“ beginnen**, wenn Sie an einen Typen in einem Framework oder einer Microsoft-Assembly binden möchten.</span><span class="sxs-lookup"><span data-stu-id="dbae1-118">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>  
  
7.  <span data-ttu-id="dbae1-119">Klicken Sie auf **Weiter** und anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="dbae1-119">Click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="dbae1-120">So binden Sie das Steuerelement an die BindingSource</span><span class="sxs-lookup"><span data-stu-id="dbae1-120">To bind the control to the BindingSource</span></span>  
  
1.  <span data-ttu-id="dbae1-121">Fügen Sie dem Formular eine <xref:System.Windows.Forms.TextBox> hinzu.</span><span class="sxs-lookup"><span data-stu-id="dbae1-121">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>  
  
2.  <span data-ttu-id="dbae1-122">Erweitern Sie im Fenster **Eigenschaften** den Knoten **(DataBindings)**.</span><span class="sxs-lookup"><span data-stu-id="dbae1-122">In the **Properties** window, expand the **(DataBindings)** node.</span></span>  
  
3.  <span data-ttu-id="dbae1-123">Klicken Sie auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="dbae1-123">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
4.  <span data-ttu-id="dbae1-124">In der **DataSource UI-Typ-Editor**, erweitern Sie den Knoten für die <xref:System.Windows.Forms.BindingSource> zuvor hinzugefügt, und wählen Sie die Eigenschaft des gebundenen Typs, die Sie binden möchten die <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft von der <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="dbae1-124">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbae1-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbae1-125">See Also</span></span>  
 [<span data-ttu-id="dbae1-126">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="dbae1-126">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="dbae1-127">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="dbae1-127">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [<span data-ttu-id="dbae1-128">Binden von Steuerelementen an Daten in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dbae1-128">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
