---
title: Übersicht über TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 86b2cf8cb0c72186fd92bdad0af6bf5bd3fa9f3f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174431"
---
# <a name="textbox-overview"></a>Übersicht über TextBox
Die- <xref:System.Windows.Controls.TextBox> Klasse ermöglicht es Ihnen, unformatierten Text anzuzeigen oder zu bearbeiten. Eine häufige Verwendung eines <xref:System.Windows.Controls.TextBox> ist die Bearbeitung von unformatiertem Text in einem Formular. Beispielsweise würde ein Formular, das den Namen des Benutzers, die Telefonnummer usw. anfordert, Steuer <xref:System.Windows.Controls.TextBox> Elemente für Texteingaben verwenden. Dieses Thema <xref:System.Windows.Controls.TextBox> enthält eine Einführung in die-Klasse und bietet Beispiele für die Verwendung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und c#.  

<a name="textbox_or_richtextbox"></a>
## <a name="textbox-or-richtextbox"></a>TextBox oder RichTextBox?  
 Sowohl <xref:System.Windows.Controls.TextBox> als auch <xref:System.Windows.Controls.RichTextBox> ermöglichen es Benutzern, Text einzugeben, aber die beiden Steuerelemente werden für verschiedene Szenarien verwendet. Eine <xref:System.Windows.Controls.TextBox> benötigt weniger Systemressourcen als eine, <xref:System.Windows.Controls.RichTextBox> sodass Sie ideal ist, wenn nur nur-Text bearbeitet werden muss (d. h. die Verwendung in einem Formular). Eine <xref:System.Windows.Controls.RichTextBox> ist eine bessere Wahl, wenn der Benutzer formatierten Text, Bilder, Tabellen oder andere unterstützte Inhalte bearbeiten muss. Beispielsweise wird das Bearbeiten eines Dokuments, Artikels oder Blogs, das Formatierungen, Bilder usw. erfordert, am besten mit einem erreicht <xref:System.Windows.Controls.RichTextBox> . In der folgenden Tabelle werden die primären Features von und zusammengefasst <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> .  
  
|Control|Rechtschreibprüfung in Echtzeit|Kontextmenü|Formatieren von Befehlen wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTR + B)|<xref:System.Windows.Documents.FlowDocument>Inhalt wie Bilder, Absätze, Tabellen usw.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Ja|Ja|Nein|Nein.|  
|<xref:System.Windows.Controls.RichTextBox>|Ja|Ja|Ja (Siehe [Übersicht über RichTextBox](richtextbox-overview.md))|Ja (Siehe [Übersicht über RichTextBox](richtextbox-overview.md))|  
  
> [!NOTE]
> Obwohl <xref:System.Windows.Controls.TextBox> das Formatieren von zugehörigen Bearbeitungs Befehlen wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTR + B) nicht unterstützt, werden viele grundlegende Befehle von beiden Steuerelementen wie unterstützt <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A> . Weitere Informationen finden Sie unter <xref:System.Windows.Documents.EditingCommands>.  
  
 Die von unterstützten Funktionen <xref:System.Windows.Controls.TextBox> werden in den folgenden Abschnitten behandelt. Weitere Informationen zu <xref:System.Windows.Controls.RichTextBox> finden Sie unter [Übersicht über RichTextBox](richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Rechtschreibprüfung in Echtzeit  
 Sie können Rechtschreibprüfung in Echtzeit in einem oder in <xref:System.Windows.Controls.TextBox> aktivieren <xref:System.Windows.Controls.RichTextBox> . Wenn die Rechtschreibprüfung aktiviert ist, wird eine rote Linie unter falsch geschriebenen Wörtern angezeigt (siehe Abbildung unten).  
  
 ![TextBox mit Rechtschreib&#45;Überprüfung](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Wie Sie die Rechtschreibprüfung aktivieren, erfahren Sie unter [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### <a name="context-menu"></a>Kontextmenü  
 Standardmäßig verfügen sowohl <xref:System.Windows.Controls.TextBox> als auch <xref:System.Windows.Controls.RichTextBox> über ein Kontextmenü, das angezeigt wird, wenn ein Benutzer mit der rechten Maustaste auf das Steuerelement klickt. Das Kontextmenü ermöglicht dem Benutzer das Ausschneiden, Kopieren und Einfügen (siehe Bild unten).  
  
 ![TextBox mit Kontextmenü](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Sie können Ihr eigenes benutzerdefiniertes Kontextmenü erstellen, um das Standardverhalten zu überschreiben. Weitere Informationen finden Sie unter [Verwenden eines benutzerdefinierten Kontextmenüs mit „TextBox“](how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>
## <a name="creating-textboxes"></a>Erstellen von TextBoxes  
 Ein <xref:System.Windows.Controls.TextBox> kann eine einzelne Zeile in Höhe oder mehrere Zeilen umfassen. Eine einzelne Zeile <xref:System.Windows.Controls.TextBox> eignet sich am besten zum Einfügen kleiner Mengen von Klartext (d. h. "Name", "Telefonnummer" usw.). Im folgenden Beispiel wird gezeigt, wie eine einzelne Zeile erstellt wird <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 Sie können auch eine erstellen <xref:System.Windows.Controls.TextBox> , die es dem Benutzer ermöglicht, mehrere Textzeilen einzugeben. Wenn Ihr Formular z. b. eine biografische Darstellung des Benutzers angefordert hat, sollten Sie eine verwenden, <xref:System.Windows.Controls.TextBox> die mehrere Textzeilen unterstützt. Im folgenden Beispiel wird gezeigt, wie verwendet wird, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] um ein Steuerelement zu definieren <xref:System.Windows.Controls.TextBox> , das automatisch erweitert wird, um mehrere Textzeilen anzupassen.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Wenn das- <xref:System.Windows.Controls.TextBox.TextWrapping%2A> Attribut auf festgelegt `Wrap` wird, wird Text in eine neue Zeile eingeschlossen, wenn der Rand des <xref:System.Windows.Controls.TextBox> Steuer Elements erreicht wird. das Steuerelement wird automatisch erweitert, sodass es bei <xref:System.Windows.Controls.TextBox> Bedarf den Raum für eine neue Zeile einschließt.  
  
 Das Festlegen des- <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> Attributs auf `true` bewirkt, dass eine neue Zeile eingefügt wird, wenn die Rückgabetaste gedrückt wird. wenn dies der Fall ist, wird das automatisch erweitert, <xref:System.Windows.Controls.TextBox> um Platz für eine neue Zeile einzuschließen.  
  
 Das- <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> Attribut fügt der eine Bild Lauf Leiste hinzu <xref:System.Windows.Controls.TextBox> , sodass der Inhalt des <xref:System.Windows.Controls.TextBox> durchlaufen werden kann, wenn die <xref:System.Windows.Controls.TextBox> über die Größe des Frame oder Fensters hinausgeht, in dem Sie eingeschlossen wird.  
  
 Weitere Informationen zu verschiedenen Aufgaben im Zusammenhang mit der Verwendung von finden Sie in <xref:System.Windows.Controls.TextBox> [den Themen](textbox-how-to-topics.md)zur Vorgehensweise.  
  
<a name="editing_commands"></a>
## <a name="detect-when-content-changes"></a>Erkennen, wenn Inhalt geändert wird  
 Normalerweise <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> sollte das-Ereignis verwendet werden, um zu erkennen, wann der Text in einer-oder-Datei <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> geändert wird <xref:System.Windows.UIElement.KeyDown> . Ein Beispiel finden Sie unter [Erkennen von Änderungen an Text in einem Textfeld](how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Artikel zu Vorgehensweisen](textbox-how-to-topics.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
