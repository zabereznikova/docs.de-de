---
title: 'Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: 4d3f12bd2606e40b5ceeef716d8f5d264bc46622
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707377"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="356fa-102">Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="356fa-102">How to: Set the Text Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="356fa-103">Windows Forms-Steuerelemente zeigen in der Regel Text an, die für die primäre Funktion des Steuerelements zusammenhängt.</span><span class="sxs-lookup"><span data-stu-id="356fa-103">Windows Forms controls typically display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="356fa-104">Z. B. eine <xref:System.Windows.Forms.Button> Steuerelement in der Regel über eine Beschriftung, der angibt, welche Aktion ausgeführt wird, wenn die Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="356fa-104">For example, a <xref:System.Windows.Forms.Button> control typically displays a caption that indicates what action will be performed when the button is clicked.</span></span> <span data-ttu-id="356fa-105">Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="356fa-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="356fa-106">Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="356fa-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a><span data-ttu-id="356fa-107">Die Text und die Schriftart mit dem Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="356fa-107">To set the text and font with the designer</span></span>  
  
1.  <span data-ttu-id="356fa-108">Legen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft des Steuerelements in eine entsprechende Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="356fa-108">In the Properties window, set the <xref:System.Windows.Forms.Control.Text%2A> property of the control to an appropriate string.</span></span>  
  
     <span data-ttu-id="356fa-109">Erstellen Sie eine unterstrichene Zugriffstaste, ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die die Tastenkombination.</span><span class="sxs-lookup"><span data-stu-id="356fa-109">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>  
  
2.  <span data-ttu-id="356fa-110">Klicken Sie im Fenster Eigenschaften auf die Schaltfläche mit den Auslassungspunkten (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.Control.Font%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="356fa-110">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
     <span data-ttu-id="356fa-111">Wählen Sie im Dialogfeld Standardformen für Schriftarten die Schriftart, Schriftschnitt, Größe, Effekte (z. B. durchgestrichen oder unterstrichen) und Skripts, die Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="356fa-111">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="356fa-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="356fa-112">See also</span></span>
- [<span data-ttu-id="356fa-113">Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="356fa-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="356fa-114">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="356fa-114">Using Fonts and Text</span></span>](../advanced/using-fonts-and-text.md)
- [<span data-ttu-id="356fa-115">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="356fa-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
