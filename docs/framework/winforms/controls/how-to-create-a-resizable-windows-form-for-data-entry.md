---
title: 'Gewusst wie: Erstellen von in der Größe veränderbaren Windows Forms für die Dateneingabe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: a319fba43c6735cd5552dd71d1fb614a6192da97
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46326019"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a><span data-ttu-id="0d3f2-102">Gewusst wie: Erstellen von in der Größe veränderbaren Windows Forms für die Dateneingabe</span><span class="sxs-lookup"><span data-stu-id="0d3f2-102">How to: Create a Resizable Windows Form for Data Entry</span></span>
<span data-ttu-id="0d3f2-103">Ein gutes Layout reagiert angemessen auf Änderungen in den Dimensionen des übergeordneten Formulars.</span><span class="sxs-lookup"><span data-stu-id="0d3f2-103">A good layout responds well to changes in the dimensions of its parent form.</span></span> <span data-ttu-id="0d3f2-104">Sie können das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement verwenden, um das Layout Ihres Formulars so zu gestalten, dass die Größe und die Position Ihrer Steuerelemente auf konsistente Weise geändert werden, wenn sich die Dimensionen des Formulars ändern.</span><span class="sxs-lookup"><span data-stu-id="0d3f2-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to arrange the layout of your form to resize and position your controls in a consistent way as the form's dimensions change.</span></span> <span data-ttu-id="0d3f2-105">Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement ist auch nützlich, wenn Änderungen am Inhalt Ihrer Steuerelemente Änderungen im Layout verursachen.</span><span class="sxs-lookup"><span data-stu-id="0d3f2-105">The <xref:System.Windows.Forms.TableLayoutPanel> control is also useful when changes in the contents of your controls cause changes in the layout.</span></span> <span data-ttu-id="0d3f2-106">Der in diesem Verfahren beschriebene Vorgang kann innerhalb der Visual Studio-Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0d3f2-106">The process covered in this procedure can be done within the Visual Studio environment.</span></span>  <span data-ttu-id="0d3f2-107">Siehe auch [Exemplarische Vorgehensweise: Erstellen eines in der Größe veränderbaren Windows Forms für die Dateneingabe](https://msdn.microsoft.com/library/991eahec\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="0d3f2-107">Also see [Walkthrough: Creating a Resizable Windows Form for Data Entry](https://msdn.microsoft.com/library/991eahec\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d3f2-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d3f2-108">Example</span></span>  
 <span data-ttu-id="0d3f2-109">Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement zum Erstellen eines Layouts verwendet wird, das angemessen reagiert, wenn der Benutzer die Größe des Formulars ändert.</span><span class="sxs-lookup"><span data-stu-id="0d3f2-109">The following example demonstrates how to use a <xref:System.Windows.Forms.TableLayoutPanel> control to build a layout that responds well when the user resizes the form.</span></span> <span data-ttu-id="0d3f2-110">Außerdem wird ein Layout gezeigt, das für Lokalisierung gut geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="0d3f2-110">It also demonstrates a layout that responds well to localization.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0d3f2-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0d3f2-111">Compiling the Code</span></span>  
 <span data-ttu-id="0d3f2-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0d3f2-112">This example requires:</span></span>  
  
-   <span data-ttu-id="0d3f2-113">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="0d3f2-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="0d3f2-114">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="0d3f2-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0d3f2-115">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="0d3f2-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="0d3f2-116">Siehe auch: [Vorgehensweise Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="0d3f2-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d3f2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d3f2-117">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="0d3f2-118">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0d3f2-118">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="0d3f2-119">Gewusst wie: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist</span><span class="sxs-lookup"><span data-stu-id="0d3f2-119">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="0d3f2-120">Microsoft Windows-Benutzererfahrung, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)</span><span class="sxs-lookup"><span data-stu-id="0d3f2-120">Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)</span></span>](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
