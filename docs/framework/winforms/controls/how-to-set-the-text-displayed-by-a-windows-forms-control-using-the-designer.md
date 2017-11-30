---
title: "Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 59d66df2c6f18ad28ad4b912c00e35f786d773da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="d6107-102">Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="d6107-102">How to: Set the Text Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="d6107-103">Windows Forms-Steuerelemente zeigen in der Regel Text an, die mit der Hauptfunktion des Steuerelements zusammenhängt.</span><span class="sxs-lookup"><span data-stu-id="d6107-103">Windows Forms controls typically display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="d6107-104">Angenommen, ein <xref:System.Windows.Forms.Button> -Steuerelement zeigt in der Regel eine Beschriftung, der angibt, welche Aktion ausgeführt wird, wenn die Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="d6107-104">For example, a <xref:System.Windows.Forms.Button> control typically displays a caption that indicates what action will be performed when the button is clicked.</span></span> <span data-ttu-id="d6107-105">Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d6107-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="d6107-106">Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6107-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a><span data-ttu-id="d6107-107">Festlegen der Text und die Schriftart mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="d6107-107">To set the text and font with the designer</span></span>  
  
1.  <span data-ttu-id="d6107-108">Legen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft des Steuerelements in eine entsprechende Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="d6107-108">In the Properties window, set the <xref:System.Windows.Forms.Control.Text%2A> property of the control to an appropriate string.</span></span>  
  
     <span data-ttu-id="d6107-109">So erstellen eine unterstrichene Zugriffstaste enthält ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die die Verknüpfung als Schlüssel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d6107-109">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>  
  
2.  <span data-ttu-id="d6107-110">Klicken Sie im Fenster Eigenschaften auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.Control.Font%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d6107-110">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
     <span data-ttu-id="d6107-111">Wählen Sie in der standard Schriftart (Dialogfeld) Schriftart, Schriftschnitt, Größe, Auswirkungen (z. B. durchgestrichen oder unterstrichen), und Skripts, die Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="d6107-111">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6107-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6107-112">See Also</span></span>  
 [<span data-ttu-id="d6107-113">Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts</span><span class="sxs-lookup"><span data-stu-id="d6107-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="d6107-114">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="d6107-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="d6107-115">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="d6107-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
