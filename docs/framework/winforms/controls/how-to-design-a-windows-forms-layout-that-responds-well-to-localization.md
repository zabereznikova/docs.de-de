---
title: 'Gewusst wie: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7f35a61c4ef8bbda544e36939fe4986a1017fe31
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="33e4f-102">Gewusst wie: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist</span><span class="sxs-lookup"><span data-stu-id="33e4f-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="33e4f-103">Mit der Erstellung von Formularen, die bereit für die Lokalisierung sind, lässt sich die Entwicklung für internationale Märkte erheblich beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="33e4f-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="33e4f-104">Sie können das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement verwenden, um Layouts zu implementieren, die sich problemlos an die Größenänderung von Steuerelementen aufgrund von Änderungen der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaftswerte anpassen.</span><span class="sxs-lookup"><span data-stu-id="33e4f-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33e4f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="33e4f-105">Example</span></span>  
 <span data-ttu-id="33e4f-106">Dieses Formular zeigt, wie ein Layout erstellt wird, dass sich proportional anpasst, wenn Sie angezeigte Zeichenfolgenwerte in andere Sprachen übersetzen.</span><span class="sxs-lookup"><span data-stu-id="33e4f-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="33e4f-107">Diese Art der Übersetzung wird als *Lokalisierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="33e4f-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="33e4f-108">Weitere Informationen finden Sie unter [Lokalisierung](../../../../docs/standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="33e4f-108">For more information, see [Localization](../../../../docs/standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="33e4f-109">Visual Studio bietet umfassende Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="33e4f-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="33e4f-110">Siehe auch [Exemplarische Vorgehensweise: Erstellen eines Layouts, das sich proportional an die Lokalisierung anpasst](http://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="33e4f-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](http://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  <span data-ttu-id="33e4f-111">[Vorgehensweise: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="33e4f-111">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="33e4f-112">[Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="33e4f-112">[Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="33e4f-113">[Vorgehensweise: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="33e4f-113">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="33e4f-114">[Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="33e4f-114">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
5.  <span data-ttu-id="33e4f-115">[Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="33e4f-115">[Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span></span>  
  
6.  <span data-ttu-id="33e4f-116">[Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="33e4f-116">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
7.  <span data-ttu-id="33e4f-117">[Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="33e4f-117">[Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span></span>  
  
8.  <span data-ttu-id="33e4f-118">[Vorgehensweise: Unterstützen der Lokalisierung in Windows Forms mithilfe von AutoSize und dem TableLayoutPanel-Steuerelement](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="33e4f-118">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span></span>  
  
9. <span data-ttu-id="33e4f-119">[Exemplarische Vorgehensweise: Erstellen eines in der Größe veränderbaren Windows Forms für die Dateneingabe](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="33e4f-119">[Walkthrough: Creating a Resizable Windows Form for Data Entry](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="33e4f-120">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="33e4f-120">Compiling the Code</span></span>  
 <span data-ttu-id="33e4f-121">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="33e4f-121">This example requires:</span></span>  
  
-   <span data-ttu-id="33e4f-122">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="33e4f-122">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="33e4f-123">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="33e4f-123">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="33e4f-124">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="33e4f-124">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="33e4f-125">Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="33e4f-125">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e4f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33e4f-126">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [<span data-ttu-id="33e4f-127">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="33e4f-127">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)
