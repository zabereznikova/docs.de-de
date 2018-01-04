---
title: "Gewusst wie: Anpassen der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2c34506ca33af80b83f365893e56a5a9d437b89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="9a3ac-102">Gewusst wie: Anpassen der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt</span><span class="sxs-lookup"><span data-stu-id="9a3ac-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="9a3ac-103">Windows Forms <xref:System.Windows.Forms.Label> Steuerelement kann es sich um einzeilige oder mehrzeilige und können werden entweder eine feste Größe oder können automatisch ändern, ihre Beschriftung angepasst.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="9a3ac-104">Die <xref:System.Windows.Forms.Label.AutoSize%2A> -Eigenschaft hilft Ihnen bei der Steuerelemente größere oder kleinere Beschriftungen, Anpassen der ist besonders nützlich, wenn sich die Beschriftung zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="9a3ac-105">Um ein Bezeichnungsfeld-Steuerelement dynamisch angepasst seinen Inhalt zu machen.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1.  <span data-ttu-id="9a3ac-106">Legen Sie dessen <xref:System.Windows.Forms.Label.AutoSize%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="9a3ac-107">Wenn <xref:System.Windows.Forms.Label.AutoSize%2A> auf festgelegt ist `false`, den angegebenen Wörtern in der <xref:System.Windows.Forms.Label.Text%2A> Eigenschaft nach Möglichkeit die nächste Zeile umbrochen, aber das Steuerelement wird nicht vergrößert.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a3ac-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a3ac-108">See Also</span></span>  
 [<span data-ttu-id="9a3ac-109">Gewusst wie: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="9a3ac-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [<span data-ttu-id="9a3ac-110">Übersicht über das Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9a3ac-110">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="9a3ac-111">Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9a3ac-111">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
