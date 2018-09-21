---
title: 'Gewusst wie: Binden eines Windows Forms-Steuerelements an einen Typ mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 33df9e050dd8c2b3ace8ff89cbd5939b538fcd95
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46471355"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="c3ec2-102">Gewusst wie: Binden eines Windows Forms-Steuerelements an einen Typ mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="c3ec2-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>
<span data-ttu-id="c3ec2-103">Beim Erstellen von Steuerelementen, die mit Daten interagieren, ist es manchmal erforderlich, ein Steuerelement an einen Typ statt an ein Objekt zu binden.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="c3ec2-104">Sie müssen normalerweise ein Steuerelement zur Entwurfszeit an einen Typ binden, wenn Daten möglicherweise nicht verfügbar sind, aber die datengebundenen Steuerelemente dennoch Daten von der öffentlichen Schnittstelle eines Typs anzeigen sollen.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="c3ec2-105">Die folgenden Verfahren wird veranschaulicht, wie zum Erstellen eines neuen <xref:System.Windows.Forms.BindingSource> , an einen Typ gebunden, und klicken Sie dann eine der Eigenschaften des Typs zu binden der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft eine <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="c3ec2-106">So binden Sie die BindingSource an einen Typen</span><span class="sxs-lookup"><span data-stu-id="c3ec2-106">To bind the BindingSource to a type</span></span>  
  
1.  <span data-ttu-id="c3ec2-107">Erstellen Sie ein Windows Forms-Projekt (**Datei** > **neu** > **Projekt** > **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="c3ec2-107">Create a Windows Forms project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="c3ec2-108">In **Entwurf** anzuzeigen, ziehen Sie eine <xref:System.Windows.Forms.BindingSource> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-108">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>  
  
3.  <span data-ttu-id="c3ec2-109">In der **Eigenschaften** Fenster, klicken Sie auf den Pfeil für die <xref:System.Windows.Forms.BindingSource.DataSource%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-109">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>  
  
4.  <span data-ttu-id="c3ec2-110">Klicken Sie im **DataSource-UI-Typ-Editor** auf **Projektdatenquelle hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-110">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>  
  
5.  <span data-ttu-id="c3ec2-111">Wählen Sie auf der Seite **Datenquellentyp auswählen** die Option **Objekt** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-111">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>  
  
6.  <span data-ttu-id="c3ec2-112">Wählen Sie den Typ aus, an den gebunden werden soll:</span><span class="sxs-lookup"><span data-stu-id="c3ec2-112">Select the type to bind to:</span></span>  
  
    -   <span data-ttu-id="c3ec2-113">Wenn sich der Typ, den Sie binden möchten, im aktuellen Projekt befindet oder die Assembly, die den Typ enthält, bereits als Verweis hinzugefügt ist, müssen Sie die Knoten erweitern, um den gewünschten Typ zu suchen. Wählen Sie ihn anschließend aus.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-113">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>  
  
         <span data-ttu-id="c3ec2-114">- oder - </span><span class="sxs-lookup"><span data-stu-id="c3ec2-114">-or-</span></span>  
  
    -   <span data-ttu-id="c3ec2-115">Wenn sich der Typ, den Sie binden möchten, in einer anderen Assembly befindet, die derzeit nicht in der Liste der Verweise erscheint, klicken Sie auf **Verweis hinzufügen** und anschließend auf die Registerkarte **Projekte**. Wählen Sie das Projekt aus, das das gewünschte Geschäftsobjekt enthält, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-115">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="c3ec2-116">Dieses Projekt erscheint in der Liste der Assemblys. Dadurch können Sie die Knoten erweitern, um den gewünschten Typ zu suchen und ihn anschließend auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-116">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c3ec2-117">Deaktivieren Sie das Dialogfeld **Assemblys ausblenden, die mit „Microsoft“ oder „System“ beginnen**, wenn Sie an einen Typen in einem Framework oder einer Microsoft-Assembly binden möchten.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-117">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>  
  
7.  <span data-ttu-id="c3ec2-118">Klicken Sie auf **Weiter** und anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-118">Click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="c3ec2-119">So binden Sie das Steuerelement an die BindingSource</span><span class="sxs-lookup"><span data-stu-id="c3ec2-119">To bind the control to the BindingSource</span></span>  
  
1.  <span data-ttu-id="c3ec2-120">Fügen Sie dem Formular eine <xref:System.Windows.Forms.TextBox> hinzu.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-120">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>  
  
2.  <span data-ttu-id="c3ec2-121">Erweitern Sie im Fenster **Eigenschaften** den Knoten **(DataBindings)**.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-121">In the **Properties** window, expand the **(DataBindings)** node.</span></span>  
  
3.  <span data-ttu-id="c3ec2-122">Klicken Sie auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-122">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
4.  <span data-ttu-id="c3ec2-123">In der **DataSource UI Type Editor**, erweitern Sie den Knoten für die <xref:System.Windows.Forms.BindingSource> zuvor hinzugefügt werden soll, und wählen Sie die Eigenschaft des gebundenen Typen Sie binden möchten die <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft der <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-123">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ec2-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3ec2-124">See Also</span></span>  
 [<span data-ttu-id="c3ec2-125">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="c3ec2-125">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="c3ec2-126">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="c3ec2-126">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [<span data-ttu-id="c3ec2-127">Binden von Steuerelementen an Daten in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c3ec2-127">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
