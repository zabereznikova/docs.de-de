---
title: 'Vorgehensweise: Größe der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt'
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 74947e529a472c9e9a681fcb436ce8aff990c0af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640406"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="f6147-102">Vorgehensweise: Größe der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt</span><span class="sxs-lookup"><span data-stu-id="f6147-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="f6147-103">Die Windows-Formulare <xref:System.Windows.Forms.Label> Steuerelement kann ein- oder mehrzeiligen sein und können werden entweder eine feste Größe oder selbst umfassen können automatisch angepasst.</span><span class="sxs-lookup"><span data-stu-id="f6147-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="f6147-104">Die <xref:System.Windows.Forms.Label.AutoSize%2A> Eigenschaft können Sie die Steuerelemente entsprechend vergrößert oder verkleinert Beschriftungen, die Größe der ist besonders nützlich, wenn sich die Beschriftung zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="f6147-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="f6147-105">Um ein Bezeichnungsfeld-Steuerelement, das Ändern der Größe dynamisch an dessen Inhalt angepasst zu machen.</span><span class="sxs-lookup"><span data-stu-id="f6147-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1.  <span data-ttu-id="f6147-106">Legen Sie dessen <xref:System.Windows.Forms.Label.AutoSize%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="f6147-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="f6147-107">Wenn <xref:System.Windows.Forms.Label.AutoSize%2A> nastaven NA hodnotu `false`, im angegebenen Wörter enthalten die <xref:System.Windows.Forms.Label.Text%2A> Eigenschaft möglichst auf die nächste Zeile umbrochen, aber das Steuerelement wird nicht vergrößert.</span><span class="sxs-lookup"><span data-stu-id="f6147-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6147-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6147-108">See also</span></span>
- [<span data-ttu-id="f6147-109">Vorgehensweise: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="f6147-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="f6147-110">Übersicht über das Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f6147-110">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)
- [<span data-ttu-id="f6147-111">Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f6147-111">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
