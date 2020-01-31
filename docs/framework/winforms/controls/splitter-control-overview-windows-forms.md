---
title: Übersicht über das Splitter-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 3d6da8daf9bb0e8df4f69554a87725a7ddb65acb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742897"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="0a8f9-102">Übersicht über das Splitter-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0a8f9-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="0a8f9-103">Obwohl <xref:System.Windows.Forms.SplitContainer> das <xref:System.Windows.Forms.Splitter>-Steuerelement vorheriger Versionen ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.Splitter>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="0a8f9-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="0a8f9-104">Windows Forms <xref:System.Windows.Forms.Splitter>-Steuerelemente verwendet werden, um die Größe angedockter Steuerelemente zur Laufzeit zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0a8f9-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="0a8f9-105">Das <xref:System.Windows.Forms.Splitter> Steuerelement wird häufig in Formularen mit Steuerelementen verwendet, die unterschiedliche Daten Längen aufweisen, wie Windows Explorer, deren Datenbereiche zu unterschiedlichen Zeiten Informationen mit unterschiedlichen breiten enthalten.</span><span class="sxs-lookup"><span data-stu-id="0a8f9-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="0a8f9-106">Arbeiten mit dem Splitter Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0a8f9-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="0a8f9-107">Wenn der Benutzer mit dem Mauszeiger auf den nicht angedockten Rand eines Steuer Elements zeigt, dessen Größe durch ein Splitter Steuerelement geändert werden kann, ändert der Zeiger seine Darstellung, um anzugeben, dass die Größe des Steuer Elements geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="0a8f9-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="0a8f9-108">Mit dem Splitter Steuerelement kann der Benutzer die Größe des angedockten Steuer Elements ändern, das sich unmittelbar vor dem Steuerelement befindet.</span><span class="sxs-lookup"><span data-stu-id="0a8f9-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="0a8f9-109">Damit der Benutzer die Größe eines angedockten Steuer Elements zur Laufzeit ändern kann, docken Sie das Steuerelement so an, dass es an einen Rand eines Containers angepasst wird, und Andocken Sie dann ein Splitter Steuerelement an dieselbe Seite dieses Containers.</span><span class="sxs-lookup"><span data-stu-id="0a8f9-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8f9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a8f9-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="0a8f9-111">Gewusst wie: Andocken von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0a8f9-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="0a8f9-112">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="0a8f9-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
