---
title: "Gewusst wie: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0e8f39e031835275818504151e66834f0634b7f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="8cc5e-102">Gewusst wie: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8cc5e-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="8cc5e-103">Standardmäßig werden in Windows Forms <xref:System.Windows.Forms.TextBox> Steuerelement zeigt eine einzelne Textzeile an und zeigt keine Bildlaufleisten.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="8cc5e-104">Wenn der Text länger als der verfügbare Platz ist, ist nur ein Teil des Texts sichtbar.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="8cc5e-105">Sie können dieses Standardverhalten ändern, indem Sie die Einstellung der <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, und <xref:System.Windows.Forms.TextBox.ScrollBars%2A> Eigenschaften auf die entsprechenden Werte.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="8cc5e-106">Um einen Wagenrücklauf in das Textfeld-Steuerelement anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-106">To display a carriage return in the TextBox control</span></span>  
  
-   <span data-ttu-id="8cc5e-107">Einen Wagenrücklauf in das mehrzeilige anzuzeigende <xref:System.Windows.Forms.TextBox>, verwenden Sie die <xref:System.Environment.NewLine%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="8cc5e-108">Beachten Sie, die Interpretation von Escapezeichen (\\) ist sprachspezifisch.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="8cc5e-109">Visual Basic verwendet `Chr$(13) & Chr$(10)` für die Kombination aus Wagenrücklauf und Zeilenvorschubzeichen.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="8cc5e-110">So zeigen Sie mehrere Zeilen im TextBox-Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="8cc5e-110">To view multiple lines in the TextBox control</span></span>  
  
1.  <span data-ttu-id="8cc5e-111">Legen Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="8cc5e-112">Wenn <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> ist `true` (Standard), dann erscheint der Text im Steuerelement als ein oder mehrere Absätze; andernfalls erscheint als eine Liste, in dem einige Zeilen am Rand des Steuerelements abgeschnitten werden können.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2.  <span data-ttu-id="8cc5e-113">Legen Sie für die <xref:System.Windows.Forms.TextBox.ScrollBars%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="8cc5e-114">Wert</span><span class="sxs-lookup"><span data-stu-id="8cc5e-114">Value</span></span>|<span data-ttu-id="8cc5e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8cc5e-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="8cc5e-116">Verwenden Sie diesen Wert, wenn der Text eines Absatzes sein soll, die fast immer passt das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="8cc5e-117">Der Benutzer können den Mauszeiger auf das Steuerelement navigieren, wenn der Text für alle auf einmal anzeigen zu lang ist.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="8cc5e-118">Verwenden Sie diesen Wert aus, wenn Sie eine Liste der Zeilen anzuzeigen, von denen einige möglicherweise länger als die Breite des möchten die <xref:System.Windows.Forms.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="8cc5e-119">Verwenden Sie diesen Wert, wenn die Liste mehr als die Höhe des Steuerelements sein kann.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3.  <span data-ttu-id="8cc5e-120">Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="8cc5e-121">Wert</span><span class="sxs-lookup"><span data-stu-id="8cc5e-121">Value</span></span>|<span data-ttu-id="8cc5e-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8cc5e-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="8cc5e-123">Text im Steuerelement wird nicht automatisch umbrochen, damit es Bildlauf nach rechts wird erst ein Zeilenumbruch erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="8cc5e-124">Wenn Sie ausgewählt haben, verwenden Sie diesen Wert <xref:System.Windows.Forms.ScrollBars.Horizontal> Bildlaufleisten oder <xref:System.Windows.Forms.ScrollBars.Both>oben.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="8cc5e-125">`true` (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="8cc5e-125">`true` (default)</span></span>|<span data-ttu-id="8cc5e-126">Die horizontale Bildlaufleiste wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="8cc5e-127">Wenn Sie ausgewählt haben, verwenden Sie diesen Wert <xref:System.Windows.Forms.ScrollBars.Vertical> Bildlaufleisten oder <xref:System.Windows.Forms.ScrollBars.None>oben, um einen oder mehrere Absätze anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8cc5e-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8cc5e-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cc5e-128">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="8cc5e-129">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8cc5e-129">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="8cc5e-130">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8cc5e-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="8cc5e-131">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8cc5e-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="8cc5e-132">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="8cc5e-132">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="8cc5e-133">Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="8cc5e-133">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="8cc5e-134">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8cc5e-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="8cc5e-135">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8cc5e-135">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
