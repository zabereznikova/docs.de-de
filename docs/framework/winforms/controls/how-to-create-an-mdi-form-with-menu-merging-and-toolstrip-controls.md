---
title: "Gewusst wie: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelementen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b99f68c970efc096bc4dfab264183de11beb135
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="0b66b-102">Gewusst wie: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="0b66b-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="0b66b-103">Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace unterstützt MDI-Anwendungen (Multiple Document Interface, Schnittstelle für mehrere Dokumente), und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement unterstützt das Zusammenführen von Menüs.</span><span class="sxs-lookup"><span data-stu-id="0b66b-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="0b66b-104">MDI-Formulare können auch <xref:System.Windows.Forms.ToolStrip>-Steuerelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="0b66b-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="0b66b-105">In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]wird dieses Feature umfassend unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0b66b-105">There is extensive support for this feature in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="0b66b-106">Siehe auch [Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente](http://msdn.microsoft.com/library/ms233676\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="0b66b-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](http://msdn.microsoft.com/library/ms233676\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b66b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b66b-107">Example</span></span>  
 <span data-ttu-id="0b66b-108">Im folgenden Codebeispiel wird veranschaulicht, wie Sie <xref:System.Windows.Forms.ToolStripPanel>-Steuerelemente mit einem MDI-Formular verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0b66b-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="0b66b-109">Das Formular unterstützt auch Zusammenführen von Menüs mit untergeordneten Menüs.</span><span class="sxs-lookup"><span data-stu-id="0b66b-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0b66b-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0b66b-110">Compiling the Code</span></span>  
 <span data-ttu-id="0b66b-111">Für dieses Codebeispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0b66b-111">This code example requires:</span></span>  
  
-   <span data-ttu-id="0b66b-112">Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="0b66b-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="0b66b-113">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Erstellen über die Befehlszeile mit „csc.exe“](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="0b66b-113">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0b66b-114">Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="0b66b-114">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="0b66b-115">Siehe auch [Vorgehensweise: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="0b66b-115">Also sssee [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b66b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b66b-116">See Also</span></span>  
 [<span data-ttu-id="0b66b-117">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0b66b-117">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
