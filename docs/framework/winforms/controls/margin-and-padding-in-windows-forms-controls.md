---
title: Rand und Abstand in Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
ms.openlocfilehash: a3218ad029735f4a5d70b3166951dcd93e061c26
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "56665224"
---
# <a name="margin-and-padding-in-windows-forms-controls"></a><span data-ttu-id="e032c-102">Rand und Abstand in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="e032c-102">Margin and Padding in Windows Forms Controls</span></span>
<span data-ttu-id="e032c-103">Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert.</span><span class="sxs-lookup"><span data-stu-id="e032c-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="e032c-104">Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace bietet Ihnen hierfür zahlreiche Layoutfunktionen.</span><span class="sxs-lookup"><span data-stu-id="e032c-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout features to accomplish this.</span></span> <span data-ttu-id="e032c-105">Zwei der wichtigsten Funktionen sind die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e032c-105">Two of the most important are the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties.</span></span>  
  
 <span data-ttu-id="e032c-106">Die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft definiert den Bereich um das Steuerelement, durch den andere Steuerelemente einen bestimmten Abstand von den Rändern des Steuerelements einhalten müssen.</span><span class="sxs-lookup"><span data-stu-id="e032c-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="e032c-107">Die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft definiert den Bereich innerhalb eines Steuerelements, durch den der Inhalt des Steuerelements (z. B. der Wert seiner <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft) einen bestimmten Abstand von den Rändern des Steuerelements einhalten muss.</span><span class="sxs-lookup"><span data-stu-id="e032c-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="e032c-108">Die folgende Abbildung zeigt die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft für ein Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e032c-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="e032c-109">![Ränder und Abstände für Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="e032c-109">![Padding And Margin for Windows Forms Controls](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="e032c-110">Diese Funktion wird zur Entwurfszeit in Visual Studio unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e032c-110">There is design-time support for this feature in Visual Studio.</span></span> <span data-ttu-id="e032c-111">Siehe auch [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](windows-forms-controls-padding-autosize.md).</span><span class="sxs-lookup"><span data-stu-id="e032c-111">Also see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](windows-forms-controls-padding-autosize.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e032c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e032c-112">See also</span></span>
- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
