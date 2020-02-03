---
title: Navigieren durch Daten mit BindingNavigator-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingNavigator control [Windows Forms], navigating data
- data [Windows Forms], navigating
- data navigation
- examples [Windows Forms], BindingNavigator control
ms.assetid: 0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb
ms.openlocfilehash: 10508cb447e70cc387f9d98effa3bc4b5ccbbaa9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736000"
---
# <a name="how-to-navigate-data-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="0c1cc-102">Gewusst wie: Datennavigation mithilfe des DataNavigator-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c1cc-102">How to: Navigate Data with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="0c1cc-103">Die Einführung des <xref:System.Windows.Forms.BindingNavigator>-Steuerelements in Windows Forms ermöglicht es Entwicklern, Endbenutzern eine einfache Benutzeroberfläche für die Datennavigation und -bearbeitung auf den Formularen bereitzustellen, die sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-103">The advent of the <xref:System.Windows.Forms.BindingNavigator> control in Windows Forms enables developers to provide end users with a simple data navigation and manipulation user interface on the forms they create.</span></span>  
  
 <span data-ttu-id="0c1cc-104">Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement ist ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement mit Schaltflächen, die für die Navigation zum ersten, letzten, nächsten und vorherigen Datensatz in einem Dataset vorkonfiguriert sind, sowie mit Schaltflächen zum Hinzufügen und Löschen von Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-104">The <xref:System.Windows.Forms.BindingNavigator> control is a <xref:System.Windows.Forms.ToolStrip> control with buttons preconfigured for navigation to the first, last, next, and previous record in a data set, as well as buttons to add and delete records.</span></span> <span data-ttu-id="0c1cc-105">Schaltflächen lassen sich ganz einfach zu dem <xref:System.Windows.Forms.BindingNavigator>-Steuerelement hinzufügen, da es ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement ist.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-105">Adding buttons to the <xref:System.Windows.Forms.BindingNavigator> control is easy, because it is a <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="0c1cc-106">Beispiele finden Sie unter Gewusst [wie: Hinzufügen der Schaltflächen "Laden", "Speichern" und "Abbrechen" zum Windows Forms BindingNavigator-Steuer](load-save-and-cancel-bindingnavigator.md)Element.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-106">For examples, see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](load-save-and-cancel-bindingnavigator.md).</span></span>  
  
 <span data-ttu-id="0c1cc-107">Für jede Schaltfläche im <xref:System.Windows.Forms.BindingNavigator>-Steuerelement gibt es einen entsprechenden Member der <xref:System.Windows.Forms.BindingSource>-Komponente, die dieselbe Funktionalität programmgesteuert bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-107">For each button on the <xref:System.Windows.Forms.BindingNavigator> control, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically allows the same functionality.</span></span> <span data-ttu-id="0c1cc-108">Beispielsweise entspricht die <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A>-Schaltfläche der <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>-Methode der <xref:System.Windows.Forms.BindingSource>-Komponente, die <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A>-Schaltfläche der <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A>-Methode usw.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-108">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span> <span data-ttu-id="0c1cc-109">Demzufolge ist das Aktivieren des <xref:System.Windows.Forms.BindingNavigator>-Steuerelements für die Navigation zwischen Datensätzen ebenso einfach wie das Festlegen seiner <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A>-Eigenschaft auf die entsprechende <xref:System.Windows.Forms.BindingSource>-Komponente auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-109">As a result, enabling the <xref:System.Windows.Forms.BindingNavigator> control to navigate data records is a simple as setting its <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the appropriate <xref:System.Windows.Forms.BindingSource> component on the form.</span></span>  
  
### <a name="to-set-up-the-bindingnavigator-control"></a><span data-ttu-id="0c1cc-110">So richten Sie das BindingNavigator-Steuerelement ein</span><span class="sxs-lookup"><span data-stu-id="0c1cc-110">To set up the BindingNavigator control</span></span>  
  
1. <span data-ttu-id="0c1cc-111">Fügen Sie eine <xref:System.Windows.Forms.BindingSource>-Komponente namens `bindingSource1` und zwei <xref:System.Windows.Forms.TextBox>-Steuerelemente namens `textBox1` und `textBox2` hinzu.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-111">Add a <xref:System.Windows.Forms.BindingSource> component named `bindingSource1` and two <xref:System.Windows.Forms.TextBox> controls named `textBox1` and `textBox2`.</span></span>  
  
2. <span data-ttu-id="0c1cc-112">Binden Sie `bindingSource1` an Daten und die TextBox-Steuerelemente an `bindingSource1`.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-112">Bind `bindingSource1` to data, and the textbox controls to `bindingSource1`.</span></span> <span data-ttu-id="0c1cc-113">Fügen Sie zu diesem Zweck den folgenden Code in Ihr Formular ein, und rufen Sie `LoadData` aus dem Konstruktor des Formulars oder der <xref:System.Windows.Forms.Form.Load>-Ereignisbehandlungsmethode heraus auf.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-113">To do this, paste the following code into your form and call `LoadData` from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="0c1cc-114">Fügen Sie Ihrem Formular ein <xref:System.Windows.Forms.BindingNavigator>-Steuerelement namens `bindingNavigator1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-114">Add a <xref:System.Windows.Forms.BindingNavigator> control named `bindingNavigator1` to your form.</span></span>  
  
4. <span data-ttu-id="0c1cc-115">Legen Sie die <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A>-Eigenschaft für `bindingNavigator1` auf `bindingSource1` fest.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-115">Set the <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property for `bindingNavigator1` to `bindingSource1`.</span></span> <span data-ttu-id="0c1cc-116">Dies ist mit dem Designer oder im Code möglich.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-116">You can do this with the designer or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="0c1cc-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c1cc-117">Example</span></span>  
 <span data-ttu-id="0c1cc-118">Das folgende Codebeispiel ist das vollständige Beispiel für die zuvor aufgeführten Schritte.</span><span class="sxs-lookup"><span data-stu-id="0c1cc-118">The following code example is the complete example for the steps listed previously.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0c1cc-119">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0c1cc-119">Compiling the Code</span></span>  
 <span data-ttu-id="0c1cc-120">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0c1cc-120">This example requires:</span></span>  
  
- <span data-ttu-id="0c1cc-121">Verweise auf die Assemblys "System", "System.Data", "System.Drawing", "System.Windows.Forms" und "System.Xml".</span><span class="sxs-lookup"><span data-stu-id="0c1cc-121">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c1cc-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c1cc-122">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="0c1cc-123">BindingNavigator-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0c1cc-123">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="0c1cc-124">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0c1cc-124">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
