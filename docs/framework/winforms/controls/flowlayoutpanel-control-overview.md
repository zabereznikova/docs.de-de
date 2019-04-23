---
title: Übersicht über das FlowLayoutPanel-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 260146cd901fe2b80a73c01060ccd55958cd169e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203040"
---
# <a name="flowlayoutpanel-control-overview"></a><span data-ttu-id="fb2a9-102">Übersicht über das FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fb2a9-102">FlowLayoutPanel Control Overview</span></span>
<span data-ttu-id="fb2a9-103">Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement ordnet seinen Inhalt in horizontaler oder vertikaler Flussrichtung an.</span><span class="sxs-lookup"><span data-stu-id="fb2a9-103">The <xref:System.Windows.Forms.FlowLayoutPanel> control arranges its contents in a horizontal or vertical flow direction.</span></span> <span data-ttu-id="fb2a9-104">Dieser Inhalt kann von einer Zeile zur nächsten oder von einer Spalte zur nächsten umgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="fb2a9-104">You can wrap the control's contents from one row to the next, or from one column to the next.</span></span> <span data-ttu-id="fb2a9-105">Wahlweise können Sie den Inhalt auch abschneiden statt ihn umzubrechen.</span><span class="sxs-lookup"><span data-stu-id="fb2a9-105">Alternately, you can clip instead of wrap its contents.</span></span>  
  
 <span data-ttu-id="fb2a9-106">Sie können die Flussrichtung angeben, indem Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="fb2a9-106">You can specify the flow direction by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> property.</span></span> <span data-ttu-id="fb2a9-107">Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement kehrt seine Flussrichtung in Layouts mit Leserichtung von rechts nach links (RTL) entsprechend um.</span><span class="sxs-lookup"><span data-stu-id="fb2a9-107">The <xref:System.Windows.Forms.FlowLayoutPanel> control correctly reverses its flow direction in Right-to-Left (RTL) layouts.</span></span> <span data-ttu-id="fb2a9-108">Darüber hinaus können Sie angeben, ob der Inhalt des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements umgebrochen oder abgeschnitten wird, indem Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="fb2a9-108">You can also specify whether the <xref:System.Windows.Forms.FlowLayoutPanel> control's contents are wrapped or clipped by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> property.</span></span>  
  
 <span data-ttu-id="fb2a9-109">Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement wird automatisch an seinen Inhalt angepasst, wenn Sie die <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="fb2a9-109">The <xref:System.Windows.Forms.FlowLayoutPanel> control automatically sizes to its contents when you set the <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="fb2a9-110">Es bietet auch eine **FlowBreak** Eigenschaft für seine untergeordneten Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="fb2a9-110">It also provides a **FlowBreak** property to its child controls.</span></span> <span data-ttu-id="fb2a9-111">Wenn Sie den Wert der FlowBreak-Eigenschaft auf `true` festlegen, ordnet das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement andere Steuerelemente nicht mehr in der aktuellen Flussrichtung an und bricht diese auch nicht mehr in die nächste Zeile oder Spalte um.</span><span class="sxs-lookup"><span data-stu-id="fb2a9-111">Setting the value of the FlowBreak property to `true` causes the <xref:System.Windows.Forms.FlowLayoutPanel> control to stop laying out controls in the current flow direction and wrap to the next row or column.</span></span>  
  
 <span data-ttu-id="fb2a9-112">Jedes Windows Forms-Steuerelement kann ein untergeordnetes Element des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements sein, einschließlich anderer Instanzen von <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="fb2a9-112">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.FlowLayoutPanel> control, including other instances of <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="fb2a9-113">Dadurch sind Sie in der Lage, anspruchsvolle Layouts zu erstellen, die sich zur Laufzeit an die Maße des Formulars anpassen.</span><span class="sxs-lookup"><span data-stu-id="fb2a9-113">With this capability, you can construct sophisticated layouts that adapt to your form's dimensions at run time.</span></span>  
  
 <span data-ttu-id="fb2a9-114">Siehe auch [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="fb2a9-114">Also see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2a9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb2a9-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="fb2a9-116">FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fb2a9-116">FlowLayoutPanel Control</span></span>](flowlayoutpanel-control-windows-forms.md)
