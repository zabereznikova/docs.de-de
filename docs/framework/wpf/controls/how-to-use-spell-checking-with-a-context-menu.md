---
title: "Gewusst wie: Verwenden der Rechtschreibpr&#252;fung mit einem Kontextmen&#252; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Aktivieren der Rechtschreibprüfung in einem Textfeld [WPF]"
  - "Erneutes Aktivieren der Rechtschreibprüfung in einem Textfeld [WPF]"
  - "Rechtschreibprüfung mit einem Kontextmenü [WPF]"
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Verwenden der Rechtschreibpr&#252;fung mit einem Kontextmen&#252;
Wenn Sie die Rechtschreibprüfung in einem Bearbeitungssteuerelement wie <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox> aktivieren, werden die Optionen standardmäßig im Kontextmenü angezeigt.  Beispiel: Wenn ein Benutzer mit der rechten Maustaste auf ein falsch geschriebenes Wort klickt, werden Rechtschreibvorschläge und die Option **Alle ignorieren** angezeigt.  Wenn Sie jedoch das Standardkontextmenü mit einem selbst erstellten Kontextmenü überschreiben, ist diese Funktion nicht mehr verfügbar, und Sie müssen Code schreiben, um die Rechtschreibprüfung im Kontextmenü erneut zu aktivieren.  Das folgende Beispiel zeigt, wie Sie dieses für ein <xref:System.Windows.Controls.TextBox> aktivieren.  
  
## Beispiel  
 Im folgenden Beispiel wird mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ein <xref:System.Windows.Controls.TextBox> mit einigen Ereignissen erstellt, die zur Implementierung des Kontextmenüs dienen.  
  
 [!code-xml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## Beispiel  
 Das folgende Beispiel zeigt den Code zur Implementierung des Kontextmenüs.  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 Der für die Variante mit einem <xref:System.Windows.Controls.RichTextBox> verwendete Code ist ähnlich.  Der Hauptunterschied besteht in dem Parameter, der an die `GetSpellingError`\-Methode übergeben wird.  Übergeben Sie für ein <xref:System.Windows.Controls.TextBox> den ganzzahligen Index der Caretposition:  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 Übergeben Sie für ein <xref:System.Windows.Controls.RichTextBox> den <xref:System.Windows.Documents.TextPointer>, der die Caretposition angibt:  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)   
 [Verwenden eines benutzerdefinierten Kontextmenüs mit "TextBox"](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)