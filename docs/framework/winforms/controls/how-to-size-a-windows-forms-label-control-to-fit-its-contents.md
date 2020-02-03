---
title: Größe eines Label-Steuer Elements an seinen Inhalt anpassen
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 6a563693feaa5074f5d13f0b82cc4d0305a79c23
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743776"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="45f80-102">Gewusst wie: Anpassen der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt</span><span class="sxs-lookup"><span data-stu-id="45f80-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="45f80-103">Das Windows Forms <xref:System.Windows.Forms.Label>-Steuerelement kann einzeilige oder mehrzeilige Elemente sein, und es kann entweder die Größe oder die Größe automatisch ändern, um die Beschriftung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="45f80-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="45f80-104">Mit der <xref:System.Windows.Forms.Label.AutoSize%2A>-Eigenschaft können Sie die Größe der Steuerelemente für größere oder kleinere Untertitel anpassen. Dies ist besonders nützlich, wenn sich die Beschriftung zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="45f80-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="45f80-105">So ändern Sie die Größe eines Label-Steuer Elements dynamisch, um seinen Inhalt anzupassen</span><span class="sxs-lookup"><span data-stu-id="45f80-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1. <span data-ttu-id="45f80-106">Legen Sie die <xref:System.Windows.Forms.Label.AutoSize%2A>-Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="45f80-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="45f80-107">Wenn <xref:System.Windows.Forms.Label.AutoSize%2A> auf `false`festgelegt ist, werden die in der <xref:System.Windows.Forms.Label.Text%2A>-Eigenschaft angegebenen Wörter nach Möglichkeit in die nächste Zeile eingebunden, aber das Steuerelement wird nicht vergrößert.</span><span class="sxs-lookup"><span data-stu-id="45f80-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f80-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45f80-108">See also</span></span>

- [<span data-ttu-id="45f80-109">Gewusst wie: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="45f80-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="45f80-110">Übersicht über das Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="45f80-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="45f80-111">Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="45f80-111">Label Control</span></span>](label-control-windows-forms.md)
