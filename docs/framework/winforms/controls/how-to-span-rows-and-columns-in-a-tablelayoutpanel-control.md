---
title: 'Vorgehensweise: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: 02db78b07930676235e55e535fb24f6ff618d823
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012970"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="aaa86-102">Vorgehensweise: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="aaa86-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="aaa86-103">Steuerelemente in einem <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement kann angrenzenden Zeilen und Spalten umfassen.</span><span class="sxs-lookup"><span data-stu-id="aaa86-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aaa86-104">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="aaa86-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="aaa86-105">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="aaa86-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="aaa86-106">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="aaa86-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-span-columns-and-rows"></a><span data-ttu-id="aaa86-107">Spalten und Zeilen umfassen.</span><span class="sxs-lookup"><span data-stu-id="aaa86-107">To span columns and rows</span></span>  
  
1. <span data-ttu-id="aaa86-108">Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="aaa86-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2. <span data-ttu-id="aaa86-109">Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die linke obere Zelle des der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="aaa86-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3. <span data-ttu-id="aaa86-110">Legen Sie die <xref:System.Windows.Forms.Button> des Steuerelements **ColumnSpan** Eigenschaft **2**.</span><span class="sxs-lookup"><span data-stu-id="aaa86-110">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="aaa86-111">Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement umfasst die erste und zweite Spalte.</span><span class="sxs-lookup"><span data-stu-id="aaa86-111">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>  
  
4. <span data-ttu-id="aaa86-112">Legen Sie die <xref:System.Windows.Forms.Button> des Steuerelements **RowSpan** Eigenschaft **2**.</span><span class="sxs-lookup"><span data-stu-id="aaa86-112">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="aaa86-113">Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement umfasst die ersten und zweiten Zeile.</span><span class="sxs-lookup"><span data-stu-id="aaa86-113">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>  
  
5. <span data-ttu-id="aaa86-114">Legen Sie die <xref:System.Windows.Forms.Button> des Steuerelements **ColumnSpan** Eigenschaft **1**.</span><span class="sxs-lookup"><span data-stu-id="aaa86-114">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="aaa86-115">Beachten Sie, dass die <xref:System.Windows.Forms.Button> Steuerelement in der ersten Spalte verschoben werden und umfasst die ersten und zweiten Zeile.</span><span class="sxs-lookup"><span data-stu-id="aaa86-115">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa86-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aaa86-116">See also</span></span>

- [<span data-ttu-id="aaa86-117">TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="aaa86-117">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
