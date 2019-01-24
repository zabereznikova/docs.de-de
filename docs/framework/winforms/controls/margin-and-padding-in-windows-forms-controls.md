---
title: Rand und Abstand in Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
ms.openlocfilehash: be5d1ae308b9412f914f1cde91d1cc5834212df8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570550"
---
# <a name="margin-and-padding-in-windows-forms-controls"></a><span data-ttu-id="c53f5-102">Rand und Abstand in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c53f5-102">Margin and Padding in Windows Forms Controls</span></span>
<span data-ttu-id="c53f5-103">Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert.</span><span class="sxs-lookup"><span data-stu-id="c53f5-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="c53f5-104">Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace bietet Ihnen hierfür zahlreiche Layoutfunktionen.</span><span class="sxs-lookup"><span data-stu-id="c53f5-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout features to accomplish this.</span></span> <span data-ttu-id="c53f5-105">Zwei der wichtigsten Funktionen sind die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c53f5-105">Two of the most important are the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties.</span></span>  
  
 <span data-ttu-id="c53f5-106">Die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft definiert den Bereich um das Steuerelement, durch den andere Steuerelemente einen bestimmten Abstand von den Rändern des Steuerelements einhalten müssen.</span><span class="sxs-lookup"><span data-stu-id="c53f5-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="c53f5-107">Die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft definiert den Bereich innerhalb eines Steuerelements, durch den der Inhalt des Steuerelements (z. B. der Wert seiner <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft) einen bestimmten Abstand von den Rändern des Steuerelements einhalten muss.</span><span class="sxs-lookup"><span data-stu-id="c53f5-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="c53f5-108">Die folgende Abbildung zeigt die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft für ein Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="c53f5-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="c53f5-109">![Ränder und Abstände für Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="c53f5-109">![Padding And Margin for Windows Forms Controls](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="c53f5-110">Diese Funktion wird zur Entwurfszeit in Visual Studio unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c53f5-110">There is design-time support for this feature in Visual Studio.</span></span>  <span data-ttu-id="c53f5-111">Siehe auch [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="c53f5-111">Also see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c53f5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c53f5-112">See also</span></span>
- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
