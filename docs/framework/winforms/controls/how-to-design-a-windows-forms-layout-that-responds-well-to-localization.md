---
title: 'Vorgehensweise: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: 131dc688d2a742fa7a0d99ec7858d4e280c9882f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310758"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="32409-102">Vorgehensweise: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist</span><span class="sxs-lookup"><span data-stu-id="32409-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="32409-103">Mit der Erstellung von Formularen, die bereit für die Lokalisierung sind, lässt sich die Entwicklung für internationale Märkte erheblich beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="32409-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="32409-104">Sie können das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement verwenden, um Layouts zu implementieren, die sich problemlos an die Größenänderung von Steuerelementen aufgrund von Änderungen der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaftswerte anpassen.</span><span class="sxs-lookup"><span data-stu-id="32409-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32409-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32409-105">Example</span></span>  
 <span data-ttu-id="32409-106">Dieses Formular zeigt, wie ein Layout erstellt wird, dass sich proportional anpasst, wenn Sie angezeigte Zeichenfolgenwerte in andere Sprachen übersetzen.</span><span class="sxs-lookup"><span data-stu-id="32409-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="32409-107">Diese Art der Übersetzung wird als *Lokalisierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="32409-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="32409-108">Weitere Informationen finden Sie unter [Lokalisierung](../../../standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="32409-108">For more information, see [Localization](../../../standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="32409-109">Visual Studio bietet umfassende Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="32409-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="32409-110">Siehe auch [Exemplarische Vorgehensweise: Erstellen eines Layouts, das sich proportional für die Lokalisierung anpasst](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="32409-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a><span data-ttu-id="32409-111">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="32409-111">Additional resources</span></span>
1. [<span data-ttu-id="32409-112">Vorgehensweise: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="32409-112">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="32409-113">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="32409-113">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3. [<span data-ttu-id="32409-114">Vorgehensweise: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="32409-114">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="32409-115">Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="32409-115">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5. [<span data-ttu-id="32409-116">Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags für Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="32409-116">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6. [<span data-ttu-id="32409-117">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="32409-117">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7. [<span data-ttu-id="32409-118">Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="32409-118">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)  
  
8. [<span data-ttu-id="32409-119">Vorgehensweise: Unterstützen der Lokalisierung in Windows Forms mithilfe von AutoSize und dem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="32409-119">How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))  
  
9. [<span data-ttu-id="32409-120">Exemplarische Vorgehensweise: Erstellen in der Größe veränderbaren Windows Forms für die Dateneingabe</span><span class="sxs-lookup"><span data-stu-id="32409-120">Walkthrough: Creating a Resizable Windows Form for Data Entry</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32409-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="32409-121">Compiling the Code</span></span>  
 <span data-ttu-id="32409-122">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="32409-122">This example requires:</span></span>  
  
-   <span data-ttu-id="32409-123">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="32409-123">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="32409-124">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="32409-124">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="32409-125">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="32409-125">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32409-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32409-126">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="32409-127">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="32409-127">Localization</span></span>](../../../standard/globalization-localization/localization.md)
