---
title: 'Vorgehensweise: Abrufen einer Textauswahl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: fdd0e3974964e141c4b65e1c8851f3c371a4d501
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357611"
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="7c601-102">Vorgehensweise: Abrufen einer Textauswahl</span><span class="sxs-lookup"><span data-stu-id="7c601-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="7c601-103">Dieses Beispiel zeigt eine Möglichkeit zur Verwendung der <xref:System.Windows.Controls.TextBox.SelectedText%2A> Eigenschaft, um Text abzurufen, die der Benutzer im ausgewählt verfügt über eine <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7c601-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c601-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c601-104">Example</span></span>  
 <span data-ttu-id="7c601-105">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel zeigt die Definition von einer <xref:System.Windows.Controls.TextBox> -Steuerelement, das Text ausgewählt haben, enthält und eine <xref:System.Windows.Controls.Button> Steuerelement mit einem angegebenen <xref:System.Windows.Controls.Button.OnClick%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="7c601-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="7c601-106">In diesem Beispiel eine Schaltfläche mit einem zugeordneten <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler wird zum Abrufen der Textauswahl.</span><span class="sxs-lookup"><span data-stu-id="7c601-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="7c601-107">Wenn der Benutzer auf die Schaltfläche klickt der <xref:System.Windows.Controls.Button.OnClick%2A> Methode kopiert die ausgewählten Text in das Textfeld in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7c601-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="7c601-108">Die jeweiligen Umstände, die von denen die Textauswahl abgerufen werden (Klicken auf eine Schaltfläche), sowie die Aktion, die mit dem die Auswahl (kopieren die Textauswahl in eine Zeichenfolge), kann problemlos geändert werden, um eine Vielzahl von Szenarien zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7c601-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="7c601-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c601-109">Example</span></span>  
 <span data-ttu-id="7c601-110">Die folgenden C# Beispiel zeigt eine <xref:System.Windows.Controls.Button.OnClick%2A> -Ereignishandler für die Schaltfläche definiert, der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für dieses Beispiel.</span><span class="sxs-lookup"><span data-stu-id="7c601-110">The following C# example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="7c601-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c601-111">See also</span></span>
- [<span data-ttu-id="7c601-112">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="7c601-112">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="7c601-113">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="7c601-113">RichTextBox Overview</span></span>](richtextbox-overview.md)
