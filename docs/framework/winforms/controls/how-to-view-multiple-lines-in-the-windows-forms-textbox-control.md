---
title: 'Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 47404f02a753fe143dd573bdf73143416872af9d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324187"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="5d82f-102">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d82f-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="5d82f-103">Standardmäßig wird die Windows-Formulare <xref:System.Windows.Forms.TextBox> -Steuerelement zeigt eine einzelne Textzeile an und zeigt keine Bildlaufleisten.</span><span class="sxs-lookup"><span data-stu-id="5d82f-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="5d82f-104">Wenn der Text länger als der verfügbare Speicherplatz ist, ist nur ein Teil des Texts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d82f-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="5d82f-105">Sie können dieses Standardverhalten ändern, durch Festlegen der <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, und <xref:System.Windows.Forms.TextBox.ScrollBars%2A> Eigenschaften auf die entsprechenden Werte.</span><span class="sxs-lookup"><span data-stu-id="5d82f-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="5d82f-106">Um einen Wagenrücklauf in der TextBox-Steuerelement anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d82f-106">To display a carriage return in the TextBox control</span></span>  
  
-   <span data-ttu-id="5d82f-107">Zum Anzeigen von eines Wagenrücklauf in ein mehrzeiliges <xref:System.Windows.Forms.TextBox>, verwenden Sie die <xref:System.Environment.NewLine%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5d82f-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="5d82f-108">Beachten Sie, die die Interpretation von Escapezeichen (\\) ist sprachspezifisch.</span><span class="sxs-lookup"><span data-stu-id="5d82f-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="5d82f-109">Visual Basic verwendet `Chr$(13) & Chr$(10)` für die Kombination aus Wagenrücklauf- und Zeilenvorschubzeichen.</span><span class="sxs-lookup"><span data-stu-id="5d82f-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="5d82f-110">Um mehrere Zeilen im TextBox-Steuerelement anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d82f-110">To view multiple lines in the TextBox control</span></span>  
  
1. <span data-ttu-id="5d82f-111">Legen Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="5d82f-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="5d82f-112">Wenn <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> ist `true` (Standardeinstellung), dann wird der Text im Steuerelement als eine oder mehrere Absätze angezeigt; andernfalls wird es als eine Liste, in dem einige Zeilen können, am Rand des Steuerelements abgeschnitten werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d82f-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2. <span data-ttu-id="5d82f-113">Legen Sie für die <xref:System.Windows.Forms.TextBox.ScrollBars%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="5d82f-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="5d82f-114">Wert</span><span class="sxs-lookup"><span data-stu-id="5d82f-114">Value</span></span>|<span data-ttu-id="5d82f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d82f-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="5d82f-116">Verwenden Sie diesen Wert aus, wenn der Text eines Absatzes sein soll, die fast immer passt das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5d82f-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="5d82f-117">Benutzer können den Mauszeiger auf das Steuerelement bewegen, wenn der Text zu lang, um alle auf einmal anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d82f-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="5d82f-118">Verwenden Sie diesen Wert sollten Sie eine Liste der Zeilen anzuzeigen, von denen einige möglicherweise länger als die Breite der <xref:System.Windows.Forms.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5d82f-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="5d82f-119">Verwenden Sie diesen Wert, wenn die Liste mehr als die Höhe des Steuerelements sein kann.</span><span class="sxs-lookup"><span data-stu-id="5d82f-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3. <span data-ttu-id="5d82f-120">Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="5d82f-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="5d82f-121">Wert</span><span class="sxs-lookup"><span data-stu-id="5d82f-121">Value</span></span>|<span data-ttu-id="5d82f-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d82f-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="5d82f-123">Text im Steuerelement wird nicht automatisch umbrochen, damit sie nach rechts Scrollen wird, bis ein Zeilenumbruch eingefügt erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="5d82f-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="5d82f-124">Wenn Sie ausgewählt haben, verwenden Sie diesen Wert <xref:System.Windows.Forms.ScrollBars.Horizontal> Scrollleisten oder <xref:System.Windows.Forms.ScrollBars.Both>weiter oben.</span><span class="sxs-lookup"><span data-stu-id="5d82f-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |`true` <span data-ttu-id="5d82f-125">(Standard)</span><span class="sxs-lookup"><span data-stu-id="5d82f-125">(default)</span></span>|<span data-ttu-id="5d82f-126">Die horizontale Bildlaufleiste wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d82f-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="5d82f-127">Wenn Sie ausgewählt haben, verwenden Sie diesen Wert <xref:System.Windows.Forms.ScrollBars.Vertical> Scrollleisten oder <xref:System.Windows.Forms.ScrollBars.None>weiter oben, um einen oder mehrere Absätze anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d82f-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d82f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d82f-128">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="5d82f-129">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5d82f-129">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="5d82f-130">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d82f-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="5d82f-131">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d82f-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="5d82f-132">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="5d82f-132">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="5d82f-133">Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="5d82f-133">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="5d82f-134">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d82f-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="5d82f-135">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5d82f-135">TextBox Control</span></span>](textbox-control-windows-forms.md)
