---
title: Übersicht über das Splitter-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 934efd707f2a52da5ba604139c8e4510aad4606b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964459"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="65646-102">Übersicht über das Splitter-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="65646-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="65646-103">Obwohl <xref:System.Windows.Forms.SplitContainer> das <xref:System.Windows.Forms.Splitter>-Steuerelement vorheriger Versionen ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.Splitter>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="65646-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="65646-104">Windows Forms <xref:System.Windows.Forms.Splitter> Steuerelemente werden verwendet, um die Größe angedockter Steuerelemente zur Laufzeit zu ändern.</span><span class="sxs-lookup"><span data-stu-id="65646-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="65646-105">Das <xref:System.Windows.Forms.Splitter> -Steuerelement wird häufig in Formularen mit Steuerelementen verwendet, die unterschiedliche Längen von Daten aufweisen, wie Windows-Explorer, deren Datenbereiche zu unterschiedlichen Zeiten Informationen mit unterschiedlichen breiten enthalten.</span><span class="sxs-lookup"><span data-stu-id="65646-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="65646-106">Arbeiten mit dem Splitter Steuerelement</span><span class="sxs-lookup"><span data-stu-id="65646-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="65646-107">Wenn der Benutzer mit dem Mauszeiger auf den nicht angedockten Rand eines Steuer Elements zeigt, dessen Größe durch ein Splitter Steuerelement geändert werden kann, ändert der Zeiger seine Darstellung, um anzugeben, dass die Größe des Steuer Elements geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="65646-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="65646-108">Mit dem Splitter Steuerelement kann der Benutzer die Größe des angedockten Steuer Elements ändern, das sich unmittelbar vor dem Steuerelement befindet.</span><span class="sxs-lookup"><span data-stu-id="65646-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="65646-109">Damit der Benutzer die Größe eines angedockten Steuer Elements zur Laufzeit ändern kann, docken Sie das Steuerelement so an, dass es an einen Rand eines Containers angepasst wird, und Andocken Sie dann ein Splitter Steuerelement an dieselbe Seite dieses Containers.</span><span class="sxs-lookup"><span data-stu-id="65646-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65646-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65646-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="65646-111">Vorgehensweise: Steuerelemente auf Windows Forms Andocken</span><span class="sxs-lookup"><span data-stu-id="65646-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="65646-112">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="65646-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
