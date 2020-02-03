---
title: Deaktivieren von Schaltflächen in einer Schaltflächen Spalte im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 691781a43005d66e13029ab8110eb7f9daacc35f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745952"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8b625-102">Gewusst wie: Deaktivieren von Schaltflächen in einer Schaltflächenspalte im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b625-102">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8b625-103">Das <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält die <xref:System.Windows.Forms.DataGridViewButtonCell>-Klasse, über die Zellen mit einer schaltflächenähnlichen Benutzeroberfläche angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="8b625-103">The <xref:System.Windows.Forms.DataGridView> control includes the <xref:System.Windows.Forms.DataGridViewButtonCell> class for displaying cells with a user interface (UI) like a button.</span></span> <span data-ttu-id="8b625-104"><xref:System.Windows.Forms.DataGridViewButtonCell> bietet jedoch keine Möglichkeit, die Darstellung der in der Zelle angezeigten Schaltfläche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8b625-104">However, <xref:System.Windows.Forms.DataGridViewButtonCell> does not provide a way to disable the appearance of the button displayed by the cell.</span></span>  
  
 <span data-ttu-id="8b625-105">Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.Windows.Forms.DataGridViewButtonCell>-Klasse angepasst wird, um Schaltflächen anzuzeigen, die deaktiviert angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="8b625-105">The following code example demonstrates how to customize the <xref:System.Windows.Forms.DataGridViewButtonCell> class to display buttons that can appear disabled.</span></span> <span data-ttu-id="8b625-106">Im Beispiel wird der neue Zellentyp `DataGridViewDisableButtonCell` definiert, der aus <xref:System.Windows.Forms.DataGridViewButtonCell> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="8b625-106">The example defines a new cell type, `DataGridViewDisableButtonCell`, that derives from <xref:System.Windows.Forms.DataGridViewButtonCell>.</span></span> <span data-ttu-id="8b625-107">Dieser Zellentyp stellt eine neue `Enabled`-Eigenschaft bereit, die auf `false` festgelegt werden kann, um eine deaktivierte Schaltfläche in der Zelle zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="8b625-107">This cell type provides a new `Enabled` property that can be set to `false` to draw a disabled button in the cell.</span></span> <span data-ttu-id="8b625-108">Im Beispiel wird auch der neue Spaltentyp `DataGridViewDisableButtonColumn` definiert, der `DataGridViewDisableButtonCell`-Objekte anzeigt.</span><span class="sxs-lookup"><span data-stu-id="8b625-108">The example also defines a new column type, `DataGridViewDisableButtonColumn`, that displays `DataGridViewDisableButtonCell` objects.</span></span> <span data-ttu-id="8b625-109">Zur Veranschaulichung dieses neuen Zellen- und Spaltentyps wird durch den aktuellen Wert jeder <xref:System.Windows.Forms.DataGridViewCheckBoxCell> im übergeordneten <xref:System.Windows.Forms.DataGridView> bestimmt, ob die `Enabled`-Eigenschaft der `DataGridViewDisableButtonCell` in derselben Zeile gleich `true` oder gleich `false` ist.</span><span class="sxs-lookup"><span data-stu-id="8b625-109">To demonstrate this new cell and column type, the current value of each <xref:System.Windows.Forms.DataGridViewCheckBoxCell> in the parent <xref:System.Windows.Forms.DataGridView> determines whether the `Enabled` property of the `DataGridViewDisableButtonCell` in the same row is `true` or `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b625-110">Wenn Sie aus <xref:System.Windows.Forms.DataGridViewCell> oder <xref:System.Windows.Forms.DataGridViewColumn> ableiten und der abgeleiteten Klasse neue Eigenschaften hinzufügen, müssen Sie die `Clone`-Methode überschreiben, damit die neuen Eigenschaften bei Klonvorgängen kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="8b625-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="8b625-111">Außerdem sollten Sie die `Clone`-Methode der Basisklasse aufrufen, damit die Eigenschaften der Basisklasse in die neue Zelle oder Spalte kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="8b625-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b625-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b625-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8b625-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8b625-113">Compiling the Code</span></span>  
 <span data-ttu-id="8b625-114">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8b625-114">This example requires:</span></span>  
  
- <span data-ttu-id="8b625-115">Verweise auf die Assemblys "System", "System.Drawing", "System.Windows.Forms" und "System.Windows.Forms.VisualStyles".</span><span class="sxs-lookup"><span data-stu-id="8b625-115">References to the System, System.Drawing, System.Windows.Forms and System.Windows.Forms.VisualStyles assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b625-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b625-116">See also</span></span>

- [<span data-ttu-id="8b625-117">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b625-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8b625-118">Architektur des DataGridView-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="8b625-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="8b625-119">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b625-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
