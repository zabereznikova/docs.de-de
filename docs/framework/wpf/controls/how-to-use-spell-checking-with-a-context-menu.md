---
title: "Gewusst wie: Verwenden der Rechtschreibprüfung mit einem Kontextmenü"
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
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a85426dc526e1e8560f494bcde5247fc394f7bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="de3f9-102">Gewusst wie: Verwenden der Rechtschreibprüfung mit einem Kontextmenü</span><span class="sxs-lookup"><span data-stu-id="de3f9-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="de3f9-103">Standardmäßig, wenn Sie die Rechtschreibprüfung in einem Bearbeitungssteuerelement aktivieren wie <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox>, erhalten Sie die Rechtschreibprüfung Auswahlen im Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="de3f9-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="de3f9-104">Z. B. wenn der Benutzer ein falsch geschriebenes Wort mit der rechten Maustaste, erhalten sie einen Satz von Rechtschreibvorschläge oder die Option zum **ignorieren alle**.</span><span class="sxs-lookup"><span data-stu-id="de3f9-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="de3f9-105">Allerdings beim Überschreiben des standardmäßigen Kontextmenüs mit Ihren eigenen benutzerdefinierten Kontextmenü diese Funktionalität ist verloren und müssen Sie Code schreiben, um die Rechtschreibprüfung-Funktion in im Kontextmenü den Befehl erneut zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="de3f9-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="de3f9-106">Das folgende Beispiel zeigt, wie Sie dies für eine <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="de3f9-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de3f9-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de3f9-107">Example</span></span>  
 <span data-ttu-id="de3f9-108">Das folgende Beispiel zeigt die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , erstellt eine <xref:System.Windows.Controls.TextBox> mit einige Ereignisse, die verwendet werden, um im Kontextmenü den Befehl zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="de3f9-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="de3f9-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de3f9-109">Example</span></span>  
 <span data-ttu-id="de3f9-110">Das folgende Beispiel zeigt den Code, der im Kontextmenü den Befehl implementiert.</span><span class="sxs-lookup"><span data-stu-id="de3f9-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="de3f9-111">Der Code verwendet, um dieses Ziel mit einer <xref:System.Windows.Controls.RichTextBox> ähnelt.</span><span class="sxs-lookup"><span data-stu-id="de3f9-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="de3f9-112">Der Hauptunterschied in der an übergebene Parameter ist die `GetSpellingError` Methode.</span><span class="sxs-lookup"><span data-stu-id="de3f9-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="de3f9-113">Für eine <xref:System.Windows.Controls.TextBox>, den ganzzahlige Index, der die Position des Textcursors übergeben:</span><span class="sxs-lookup"><span data-stu-id="de3f9-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="de3f9-114">Für eine <xref:System.Windows.Controls.RichTextBox>, übergeben Sie die <xref:System.Windows.Documents.TextPointer> , der die Position des Textcursors angibt:</span><span class="sxs-lookup"><span data-stu-id="de3f9-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="de3f9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de3f9-115">See Also</span></span>  
 [<span data-ttu-id="de3f9-116">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="de3f9-116">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="de3f9-117">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="de3f9-117">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="de3f9-118">Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement</span><span class="sxs-lookup"><span data-stu-id="de3f9-118">Enable Spell Checking in a Text Editing Control</span></span>](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)  
 [<span data-ttu-id="de3f9-119">Verwenden eines benutzerdefinierten Kontextmenüs mit "TextBox"</span><span class="sxs-lookup"><span data-stu-id="de3f9-119">Use a Custom Context Menu with a TextBox</span></span>](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)
