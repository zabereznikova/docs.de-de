---
title: 'Vorgehensweise: Festlegen des ToolStrip-Renderers zur Laufzeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripManager class [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 525e2347-0804-49aa-b9a3-9b2cabbf1c35
ms.openlocfilehash: 90a80ba421698a108cd7a358f89b64810b06efc9
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591617"
---
# <a name="how-to-set-the-toolstrip-renderer-at-run-time"></a><span data-ttu-id="68531-102">Vorgehensweise: Festlegen des ToolStrip-Renderers zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="68531-102">How to: Set the ToolStrip Renderer at Run Time</span></span>
<span data-ttu-id="68531-103">Sie können die Darstellung des <xref:System.Windows.Forms.ToolStrip>-Steuerelements anpassen, indem Sie eine benutzerdefinierte `ProfessionalColorTable`-Klasse erstellen.</span><span class="sxs-lookup"><span data-stu-id="68531-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> control by creating a custom `ProfessionalColorTable` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68531-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="68531-104">Example</span></span>  
 <span data-ttu-id="68531-105">Im folgenden Codebeispiel wird veranschaulicht, wie eine benutzerdefinierte `ProfessionalColorTable`-Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="68531-105">The following code example demonstrates how to create a custom `ProfessionalColorTable` class.</span></span> <span data-ttu-id="68531-106">Diese Klasse definiert Farbverläufe für ein <xref:System.Windows.Forms.MenuStrip>- und ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="68531-106">This class defines gradients for a <xref:System.Windows.Forms.MenuStrip> and a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
 <span data-ttu-id="68531-107">Um dieses Codebeispiel zu verwenden, kompilieren Sie die Anwendung, führen Sie die Anwendung aus, und klicken Sie dann auf **Change Colors** (Farben ändern), um die Farbverläufe anzuwenden, die in der benutzerdefinierten `ProfessionalColorTable`-Klasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="68531-107">To use this code example, compile and run the application, and then click **Change Colors** to apply the gradients defined in the custom `ProfessionalColorTable` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="defining-a-custom-professionalcolortable-class"></a><span data-ttu-id="68531-108">Definieren einer benutzerdefinierten ProfessionalColorTable-Klasse</span><span class="sxs-lookup"><span data-stu-id="68531-108">Defining a Custom ProfessionalColorTable class</span></span>  
 <span data-ttu-id="68531-109">Die benutzerdefinierten Farbverläufe sind in der `CustomProfessionalColors`-Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="68531-109">The custom gradients are defined in the `CustomProfessionalColors` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#30)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#30)]  
  
## <a name="assigning-a-custom-renderer"></a><span data-ttu-id="68531-110">Zuweisen eines benutzerdefinierten Renderers</span><span class="sxs-lookup"><span data-stu-id="68531-110">Assigning a Custom Renderer</span></span>  
 <span data-ttu-id="68531-111">Erstellen Sie eine neue `ToolStripProfessionalRenderer`-Instanz mit der `CustomProfessionalColors`-Klasse, und weisen Sie diese Instanz der <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>-Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="68531-111">Create a new `ToolStripProfessionalRenderer` with a `CustomProfessionalColors` class, and assign it to the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#22)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="68531-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="68531-112">Compiling the Code</span></span>  
 <span data-ttu-id="68531-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="68531-113">This example requires:</span></span>  
  
- <span data-ttu-id="68531-114">Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="68531-114">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68531-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68531-115">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="68531-116">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="68531-116">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
