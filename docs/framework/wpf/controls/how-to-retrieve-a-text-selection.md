---
title: 'Gewusst wie: Abrufen einer Textauswahl'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32be79811de4b8056449c2c6d6c53eca8cc063f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="febe7-102">Gewusst wie: Abrufen einer Textauswahl</span><span class="sxs-lookup"><span data-stu-id="febe7-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="febe7-103">Dieses Beispiel zeigt eine Möglichkeit zum Verwenden der <xref:System.Windows.Controls.TextBox.SelectedText%2A> Eigenschaft, um Text abzurufen, die der Benutzer, in ausgewählt hat einem <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="febe7-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="febe7-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="febe7-104">Example</span></span>  
 <span data-ttu-id="febe7-105">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel zeigt die Definition eine <xref:System.Windows.Controls.TextBox> Steuerelement, das Text ausgewählt haben, enthält und eine <xref:System.Windows.Controls.Button> Steuerelement mit einem angegebenen <xref:System.Windows.Controls.Button.OnClick%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="febe7-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="febe7-106">In diesem Beispiel eine Schaltfläche mit einem zugeordneten <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignishandler dient zum Abrufen der Textauswahl.</span><span class="sxs-lookup"><span data-stu-id="febe7-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="febe7-107">Wenn der Benutzer die Schaltfläche klickt der <xref:System.Windows.Controls.Button.OnClick%2A> Methode alle markierten Text im Textfeld in eine Zeichenfolge kopiert.</span><span class="sxs-lookup"><span data-stu-id="febe7-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="febe7-108">Die besonderen Umständen nach denen die Textauswahl abgerufen wird (Klicken auf eine Schaltfläche), sowie die Aktion, die mit dieser Auswahl (kopieren den markierten Text in eine Zeichenfolge), können problemlos geändert werden, um eine Vielzahl von Szenarien zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="febe7-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="febe7-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="febe7-109">Example</span></span>  
 <span data-ttu-id="febe7-110">Die folgenden [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] Beispiel zeigt eine <xref:System.Windows.Controls.Button.OnClick%2A> -Ereignishandler für die Schaltfläche definiert, der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für dieses Beispiel.</span><span class="sxs-lookup"><span data-stu-id="febe7-110">The following [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="febe7-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="febe7-111">See Also</span></span>  
 [<span data-ttu-id="febe7-112">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="febe7-112">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="febe7-113">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="febe7-113">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
