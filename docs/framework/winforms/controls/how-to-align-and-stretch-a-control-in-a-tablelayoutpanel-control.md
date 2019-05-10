---
title: 'Vorgehensweise: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210365"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="af216-102">Vorgehensweise: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="af216-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>

<span data-ttu-id="af216-103">Sie können das Ausrichten und Dehnen von Steuerelementen in einem <xref:System.Windows.Forms.TableLayoutPanel> mit der <xref:System.Windows.Forms.Control.Anchor%2A> und <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="af216-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>

## <a name="align-and-stretch-a-control"></a><span data-ttu-id="af216-104">Ausrichten und Strecken eines Steuerelements</span><span class="sxs-lookup"><span data-stu-id="af216-104">Align and stretch a control</span></span>

1. <span data-ttu-id="af216-105">Ziehen Sie in Visual Studio eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="af216-105">In Visual Studio, drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="af216-106">Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die linke obere Zelle des der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="af216-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="af216-107">Die <xref:System.Windows.Forms.Button> Steuerelement in der Zelle zentriert ist.</span><span class="sxs-lookup"><span data-stu-id="af216-107">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>

3. <span data-ttu-id="af216-108">Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft `Left,Right`.</span><span class="sxs-lookup"><span data-stu-id="af216-108">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="af216-109">Die <xref:System.Windows.Forms.Button> -Steuerelement wird an die Breite der Zelle angepasst.</span><span class="sxs-lookup"><span data-stu-id="af216-109">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>

4. <span data-ttu-id="af216-110">Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft `Top,Bottom`.</span><span class="sxs-lookup"><span data-stu-id="af216-110">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="af216-111">Die <xref:System.Windows.Forms.Button> -Steuerelement wird an die Höhe der Zelle angepasst.</span><span class="sxs-lookup"><span data-stu-id="af216-111">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>

5. <span data-ttu-id="af216-112">Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="af216-112">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="af216-113">Die <xref:System.Windows.Forms.Button> Steuerelement wird erweitert, um die gesamte Zelle ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="af216-113">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>

6. <span data-ttu-id="af216-114">Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="af216-114">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="af216-115">Die <xref:System.Windows.Forms.Button> Steuerelement gibt Sie zurück auf seine ursprüngliche Größe und wird in der oberen linken Ecke der Zelle verschoben.</span><span class="sxs-lookup"><span data-stu-id="af216-115">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="af216-116">Die **Windows Forms-Designer** hat die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="af216-116">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>

7. <span data-ttu-id="af216-117">Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft `Bottom,Right`.</span><span class="sxs-lookup"><span data-stu-id="af216-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="af216-118">Die <xref:System.Windows.Forms.Button> -Steuerelement wird in der unteren rechten Ecke der Zelle.</span><span class="sxs-lookup"><span data-stu-id="af216-118">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>

8. <span data-ttu-id="af216-119">Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft <xref:System.Windows.Forms.AnchorStyles.None>.</span><span class="sxs-lookup"><span data-stu-id="af216-119">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="af216-120">Die <xref:System.Windows.Forms.Button> Steuerelement verschoben wird, in die Mitte der Zelle.</span><span class="sxs-lookup"><span data-stu-id="af216-120">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>

## <a name="see-also"></a><span data-ttu-id="af216-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af216-121">See also</span></span>

- [<span data-ttu-id="af216-122">TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="af216-122">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
