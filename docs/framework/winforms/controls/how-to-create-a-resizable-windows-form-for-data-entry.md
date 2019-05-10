---
title: 'Vorgehensweise: Erstellen von in der Größe veränderbaren Windows Forms für die Dateneingabe'
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
ms.openlocfilehash: 724dfa79358548530eab49683f1cb2db55f889c8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625979"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a><span data-ttu-id="d31c9-102">Vorgehensweise: Erstellen von in der Größe veränderbaren Windows Forms für die Dateneingabe</span><span class="sxs-lookup"><span data-stu-id="d31c9-102">How to: Create a Resizable Windows Form for Data Entry</span></span>
<span data-ttu-id="d31c9-103">Ein gutes Layout reagiert angemessen auf Änderungen in den Dimensionen des übergeordneten Formulars.</span><span class="sxs-lookup"><span data-stu-id="d31c9-103">A good layout responds well to changes in the dimensions of its parent form.</span></span> <span data-ttu-id="d31c9-104">Sie können das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement verwenden, um das Layout Ihres Formulars so zu gestalten, dass die Größe und die Position Ihrer Steuerelemente auf konsistente Weise geändert werden, wenn sich die Dimensionen des Formulars ändern.</span><span class="sxs-lookup"><span data-stu-id="d31c9-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to arrange the layout of your form to resize and position your controls in a consistent way as the form's dimensions change.</span></span> <span data-ttu-id="d31c9-105">Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement ist auch nützlich, wenn Änderungen am Inhalt Ihrer Steuerelemente Änderungen im Layout verursachen.</span><span class="sxs-lookup"><span data-stu-id="d31c9-105">The <xref:System.Windows.Forms.TableLayoutPanel> control is also useful when changes in the contents of your controls cause changes in the layout.</span></span> <span data-ttu-id="d31c9-106">Der in diesem Verfahren beschriebene Vorgang kann innerhalb der Visual Studio-Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d31c9-106">The process covered in this procedure can be done within the Visual Studio environment.</span></span>  <span data-ttu-id="d31c9-107">Siehe auch [Exemplarische Vorgehensweise: Erstellen in der Größe veränderbaren Windows Forms für die Dateneingabe](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d31c9-107">Also see [Walkthrough: Creating a Resizable Windows Form for Data Entry](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d31c9-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d31c9-108">Example</span></span>  
 <span data-ttu-id="d31c9-109">Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement zum Erstellen eines Layouts verwendet wird, das angemessen reagiert, wenn der Benutzer die Größe des Formulars ändert.</span><span class="sxs-lookup"><span data-stu-id="d31c9-109">The following example demonstrates how to use a <xref:System.Windows.Forms.TableLayoutPanel> control to build a layout that responds well when the user resizes the form.</span></span> <span data-ttu-id="d31c9-110">Außerdem wird ein Layout gezeigt, das für Lokalisierung gut geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="d31c9-110">It also demonstrates a layout that responds well to localization.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d31c9-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d31c9-111">Compiling the Code</span></span>  
 <span data-ttu-id="d31c9-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d31c9-112">This example requires:</span></span>  
  
- <span data-ttu-id="d31c9-113">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="d31c9-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d31c9-114">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d31c9-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d31c9-115">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="d31c9-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d31c9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d31c9-116">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="d31c9-117">Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d31c9-117">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="d31c9-118">Vorgehensweise: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist</span><span class="sxs-lookup"><span data-stu-id="d31c9-118">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="d31c9-119">Microsoft Windows-Benutzererfahrung, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)</span><span class="sxs-lookup"><span data-stu-id="d31c9-119">Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)</span></span>](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
