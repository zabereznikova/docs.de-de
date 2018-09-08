---
title: 'Gewusst wie: Zuordnen eines ContextMenuStrip zu einem Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: 7776a5e5ed6e650aad82f7863a7fa1748006b3bc
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44200652"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="b8174-102">Gewusst wie: Zuordnen eines ContextMenuStrip zu einem Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b8174-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="b8174-103">Nachdem Sie Ihre Steuerelemente und Kontextmenüs erstellt haben, verwenden Sie die folgenden Verfahren, um ein bestimmtes Kontextmenü anzuzeigen, wenn der Benutzer mit der rechten Maustaste auf das Steuerelement klickt.</span><span class="sxs-lookup"><span data-stu-id="b8174-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="b8174-104">In diesen Verfahren wird eine <xref:System.Windows.Forms.ContextMenuStrip>-Instanz einem Windows Form-Objekt und einem <xref:System.Windows.Forms.ToolStrip>-Steuerelement zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b8174-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="b8174-105">So ordnen Sie eine ContextMenuStrip-Instanz einem Windows Form-Objekt zu</span><span class="sxs-lookup"><span data-stu-id="b8174-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1.  <span data-ttu-id="b8174-106">Legen Sie die <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>-Eigenschaft auf den Namen der zugeordneten <xref:System.Windows.Forms.ContextMenuStrip>-Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="b8174-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="b8174-107">So ordnen Sie eine ContextMenuStrip-Instanz einem ToolStrip-Steuerelement zu</span><span class="sxs-lookup"><span data-stu-id="b8174-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1.  <span data-ttu-id="b8174-108">Legen Sie die <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>-Eigenschaft des Steuerelements auf den Namen der zugeordneten <xref:System.Windows.Forms.ContextMenuStrip>-Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="b8174-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8174-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8174-109">Example</span></span>  
 <span data-ttu-id="b8174-110">Im folgenden Codebeispiel werden ein Windows Form-Objekt und ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement erstellt, und beiden wird jeweils ein anderes <xref:System.Windows.Forms.ContextMenuStrip>-Steuerelement zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b8174-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b8174-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b8174-111">Compiling the Code</span></span>  
 <span data-ttu-id="b8174-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b8174-112">This example requires:</span></span>  
  
-   <span data-ttu-id="b8174-113">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="b8174-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b8174-114">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b8174-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b8174-115">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="b8174-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="b8174-116">Siehe auch: [Vorgehensweise Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="b8174-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8174-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8174-117">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="b8174-118">Vorgehensweise: Hinzufügen von Menüelementen zu einem ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="b8174-118">How to: Add Menu Items to a ContextMenuStrip</span></span>](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)  
 [<span data-ttu-id="b8174-119">ContextMenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b8174-119">ContextMenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
