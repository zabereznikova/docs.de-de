---
title: 'Gewusst wie: Strecken einer ToolStripTextBox zum Ausfüllen der verbleibenden Breite eines ToolStrip (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: bd58cbd109b8e3dd04c6a284dc6926e95830fb61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537719"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="bed4d-102">Gewusst wie: Strecken einer ToolStripTextBox zum Ausfüllen der verbleibenden Breite eines ToolStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="bed4d-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="bed4d-103">Beim Festlegen der <xref:System.Windows.Forms.ToolStrip.Stretch%2A> Eigenschaft von einem <xref:System.Windows.Forms.ToolStrip> die Steuerung an `true`, das Steuerelement füllt den Container von einem Ende zum anderen Ende und ändert, wenn die Größe des Containers ändert.</span><span class="sxs-lookup"><span data-stu-id="bed4d-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="bed4d-104">In dieser Konfiguration können Sie finden es vielleicht hilfreich, ein Element im Steuerelement, z. B. Strecken einer <xref:System.Windows.Forms.ToolStripTextBox>, um den verfügbaren Platz ausfüllen und Größe ändern, wenn die Größe des Steuerelements ändert.</span><span class="sxs-lookup"><span data-stu-id="bed4d-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="bed4d-105">Dieses Strecken ist nützlich, z. B. Wenn Sie Darstellung und das Verhalten ähnlich wie die Adresszeile in Microsoft® Internet Explorer erzielen möchten.</span><span class="sxs-lookup"><span data-stu-id="bed4d-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bed4d-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bed4d-106">Example</span></span>  
 <span data-ttu-id="bed4d-107">Im folgenden Codebeispiel stellt eine Klasse abgeleitet wurde. <xref:System.Windows.Forms.ToolStripTextBox> aufgerufen `ToolStripSpringTextBox`.</span><span class="sxs-lookup"><span data-stu-id="bed4d-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="bed4d-108">Diese Klasse überschreibt die <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> Methode zum Berechnen der verfügbaren Breite des übergeordneten Elements <xref:System.Windows.Forms.ToolStrip> steuern, nachdem die kombinierte Breite aller anderen Elemente subtrahiert wurde.</span><span class="sxs-lookup"><span data-stu-id="bed4d-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="bed4d-109">In diesem Codebeispiel wird zudem eine <xref:System.Windows.Forms.Form> Klasse und einer `Program` Klasse, um das neue Verhalten zeigen.</span><span class="sxs-lookup"><span data-stu-id="bed4d-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bed4d-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="bed4d-110">Compiling the Code</span></span>  
 <span data-ttu-id="bed4d-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bed4d-111">This example requires:</span></span>  
  
-   <span data-ttu-id="bed4d-112">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="bed4d-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed4d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bed4d-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripTextBox>  
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="bed4d-114">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="bed4d-114">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="bed4d-115">Gewusst wie: Interaktive Verwendung der Spring-Eigenschaft in StatusStrip</span><span class="sxs-lookup"><span data-stu-id="bed4d-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
