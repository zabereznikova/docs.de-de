---
title: 'Gewusst wie: Verwenden der Rechtschreibprüfung mit einem Kontextmenü'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 966e3adbcb57c30a55d606f6d6b8b51523ee30ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553766"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a>Gewusst wie: Verwenden der Rechtschreibprüfung mit einem Kontextmenü
Standardmäßig, wenn Sie die Rechtschreibprüfung in einem Bearbeitungssteuerelement aktivieren wie <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox>, erhalten Sie die Rechtschreibprüfung Auswahlen im Kontextmenü. Z. B. wenn der Benutzer ein falsch geschriebenes Wort mit der rechten Maustaste, erhalten sie einen Satz von Rechtschreibvorschläge oder die Option zum **ignorieren alle**. Allerdings beim Überschreiben des standardmäßigen Kontextmenüs mit Ihren eigenen benutzerdefinierten Kontextmenü diese Funktionalität ist verloren und müssen Sie Code schreiben, um die Rechtschreibprüfung-Funktion in im Kontextmenü den Befehl erneut zu aktivieren. Das folgende Beispiel zeigt, wie Sie dies für eine <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , erstellt eine <xref:System.Windows.Controls.TextBox> mit einige Ereignisse, die verwendet werden, um im Kontextmenü den Befehl zu implementieren.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt den Code, der im Kontextmenü den Befehl implementiert.  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 Der Code verwendet, um dieses Ziel mit einer <xref:System.Windows.Controls.RichTextBox> ähnelt. Der Hauptunterschied in der an übergebene Parameter ist die `GetSpellingError` Methode. Für eine <xref:System.Windows.Controls.TextBox>, den ganzzahlige Index, der die Position des Textcursors übergeben:  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 Für eine <xref:System.Windows.Controls.RichTextBox>, übergeben Sie die <xref:System.Windows.Documents.TextPointer> , der die Position des Textcursors angibt:  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)  
 [Verwenden eines benutzerdefinierten Kontextmenüs mit "TextBox"](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)
