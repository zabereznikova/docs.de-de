---
title: 'Vorgehensweise: Verwenden der Rechtschreibprüfung mit einem Kontextmenü'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 72b24c386eb99140c9c2729688994b81f92e1a6f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192978"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a>Vorgehensweise: Verwenden der Rechtschreibprüfung mit einem Kontextmenü
Standardmäßig werden beim Aktivieren der Rechtschreibprüfung in einem Bearbeitungssteuerelement wie <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox>, erhalten Sie die Optionen im Kontextmenü. Beispielsweise Benutzern ein falsch geschriebenes Wort mit der rechten Maustaste, erhalten sie einen Satz von Rechtschreibvorschläge oder die Option zum **alle ignorieren**. Wenn Sie das Standard-Kontextmenü mit Ihr eigenes benutzerdefiniertes Kontextmenü überschreiben, jedoch dieser Funktionalität verloren gegangen ist, und Sie Code schreiben, um die Rechtschreibprüfung-Funktion im Kontextmenü erneut aktivieren möchten. Das folgende Beispiel zeigt, wie Sie dies aktivieren, auf eine <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] erstellt eine <xref:System.Windows.Controls.TextBox> mit einigen Ereignissen, die verwendet werden, um das Kontextmenü zu implementieren.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt den Code, der das Kontextmenü implementiert.  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 Der Code verwendet hierfür mit einem <xref:System.Windows.Controls.RichTextBox> ist ähnlich. Der Hauptunterschied besteht in der an übergebene Parameter die `GetSpellingError` Methode. Für eine <xref:System.Windows.Controls.TextBox>, übergeben Sie den ganzzahlige Index der Position der Einfügemarke:  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 Für eine <xref:System.Windows.Controls.RichTextBox>, übergeben die <xref:System.Windows.Documents.TextPointer> , der die Position der Einfügemarke angibt:  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
- [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](how-to-enable-spell-checking-in-a-text-editing-control.md)
- [Verwenden eines benutzerdefinierten Kontextmenüs mit "TextBox"](how-to-use-a-custom-context-menu-with-a-textbox.md)
