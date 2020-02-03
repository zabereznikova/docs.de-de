---
title: Anzeigen mehrerer Zeilen im TextBox-Steuerelement
ms.date: 03/30/2017
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
ms.openlocfilehash: 61ea671c1e86fa8254bfc1b043a46f3b7aa6af1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728287"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="499ca-102">Gewusst wie: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="499ca-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="499ca-103">Standardmäßig zeigt das Windows Forms <xref:System.Windows.Forms.TextBox>-Steuerelement eine einzelne Textzeile an und zeigt keine Schiebe leisten an.</span><span class="sxs-lookup"><span data-stu-id="499ca-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="499ca-104">Wenn der Text länger als der verfügbare Platz ist, ist nur ein Teil des Texts sichtbar.</span><span class="sxs-lookup"><span data-stu-id="499ca-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="499ca-105">Sie können dieses Standardverhalten ändern, indem Sie die Eigenschaften <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>und <xref:System.Windows.Forms.TextBox.ScrollBars%2A> auf entsprechende Werte festlegen.</span><span class="sxs-lookup"><span data-stu-id="499ca-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="499ca-106">So zeigen Sie einen Wagen Rücklauf im TextBox-Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="499ca-106">To display a carriage return in the TextBox control</span></span>  
  
- <span data-ttu-id="499ca-107">Um einen Wagen Rücklauf in einer mehrzeiligen <xref:System.Windows.Forms.TextBox>anzuzeigen, verwenden Sie die <xref:System.Environment.NewLine%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="499ca-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="499ca-108">Beachten Sie, dass die Interpretation von Escapezeichen (\\) sprachspezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="499ca-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="499ca-109">Visual Basic verwendet `Chr$(13) & Chr$(10)` für die Kombination aus Wagen Rücklauf und Zeilenvorschub Zeichen.</span><span class="sxs-lookup"><span data-stu-id="499ca-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="499ca-110">So zeigen Sie mehrere Zeilen im TextBox-Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="499ca-110">To view multiple lines in the TextBox control</span></span>  
  
1. <span data-ttu-id="499ca-111">Setzen Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A>-Eigenschaft auf `true`.</span><span class="sxs-lookup"><span data-stu-id="499ca-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="499ca-112">Wenn <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `true` (Standard) ist, wird der Text im-Steuerelement in einem oder mehreren Absätzen angezeigt. Andernfalls wird Sie als Liste angezeigt, in der einige Zeilen am Rand des Steuer Elements abgeschnitten werden können.</span><span class="sxs-lookup"><span data-stu-id="499ca-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2. <span data-ttu-id="499ca-113">Legen Sie für die <xref:System.Windows.Forms.TextBox.ScrollBars%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="499ca-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="499ca-114">value</span><span class="sxs-lookup"><span data-stu-id="499ca-114">Value</span></span>|<span data-ttu-id="499ca-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="499ca-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="499ca-116">Verwenden Sie diesen Wert, wenn es sich bei dem Text um einen Absatz handelt, der fast immer dem Steuerelement entspricht.</span><span class="sxs-lookup"><span data-stu-id="499ca-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="499ca-117">Der Benutzer kann mit dem Mauszeiger im Steuerelement navigieren, wenn der Text zu lang ist, um alle gleichzeitig anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="499ca-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="499ca-118">Verwenden Sie diesen Wert, wenn Sie eine Liste von Zeilen anzeigen möchten, von denen einige möglicherweise länger als die Breite des <xref:System.Windows.Forms.TextBox> Steuer Elements sind.</span><span class="sxs-lookup"><span data-stu-id="499ca-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="499ca-119">Verwenden Sie diesen Wert, wenn die Liste möglicherweise länger als die Höhe des Steuer Elements ist.</span><span class="sxs-lookup"><span data-stu-id="499ca-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3. <span data-ttu-id="499ca-120">Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="499ca-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="499ca-121">value</span><span class="sxs-lookup"><span data-stu-id="499ca-121">Value</span></span>|<span data-ttu-id="499ca-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="499ca-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="499ca-123">Der Text im-Steuerelement wird nicht automatisch umschließt, sodass er nach rechts verschoben wird, bis ein Zeilenumbruch erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="499ca-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="499ca-124">Verwenden Sie diesen Wert, wenn Sie oben <xref:System.Windows.Forms.ScrollBars.Horizontal> Scrollleisten oder <xref:System.Windows.Forms.ScrollBars.Both>ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="499ca-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="499ca-125">`true` (Standard)</span><span class="sxs-lookup"><span data-stu-id="499ca-125">`true` (default)</span></span>|<span data-ttu-id="499ca-126">Die horizontale Scrollleiste wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="499ca-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="499ca-127">Verwenden Sie diesen Wert, wenn Sie <xref:System.Windows.Forms.ScrollBars.Vertical> Scrollleisten oder <xref:System.Windows.Forms.ScrollBars.None>oben ausgewählt haben, um einen oder mehrere Absätze anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="499ca-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="499ca-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="499ca-128">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="499ca-129">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="499ca-129">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="499ca-130">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="499ca-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="499ca-131">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="499ca-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="499ca-132">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="499ca-132">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="499ca-133">Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="499ca-133">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="499ca-134">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="499ca-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="499ca-135">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="499ca-135">TextBox Control</span></span>](textbox-control-windows-forms.md)
