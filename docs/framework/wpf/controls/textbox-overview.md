---
title: Übersicht über TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 46600fd1a3023a80d49fae6f020279be6131916a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951488"
---
# <a name="textbox-overview"></a>Übersicht über TextBox
Die <xref:System.Windows.Controls.TextBox> -Klasse ermöglicht es Ihnen, unformatierten Text anzuzeigen oder zu bearbeiten. Eine häufige Verwendung eines <xref:System.Windows.Controls.TextBox> ist die Bearbeitung von unformatiertem Text in einem Formular. Beispielsweise würde ein Formular, das den Namen des Benutzers, die Telefonnummer usw. anfordert, Steuerelemente für Texteingaben verwenden <xref:System.Windows.Controls.TextBox> . In diesem Thema wird <xref:System.Windows.Controls.TextBox> die-Klasse vorgestellt, und es werden Beispiele für die Verwendung C#in und bereitstellt. [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]  

<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>TextBox oder RichTextBox?  
 Sowohl <xref:System.Windows.Controls.TextBox> als <xref:System.Windows.Controls.RichTextBox> auch ermöglichen es Benutzern, Text einzugeben, aber die beiden Steuerelemente werden für verschiedene Szenarien verwendet. Eine <xref:System.Windows.Controls.TextBox> benötigt weniger Systemressourcen als eine <xref:System.Windows.Controls.RichTextBox> , sodass Sie ideal ist, wenn nur nur-Text bearbeitet werden muss (d. h. die Verwendung in einem Formular). Eine <xref:System.Windows.Controls.RichTextBox> ist eine bessere Wahl, wenn der Benutzer formatierten Text, Bilder, Tabellen oder andere unterstützte Inhalte bearbeiten muss. Beispielsweise wird das Bearbeiten eines Dokuments, Artikels oder Blogs, das Formatierungen, Bilder usw. erfordert, am besten <xref:System.Windows.Controls.RichTextBox>mit einem erreicht. In der folgenden Tabelle werden die primären Features <xref:System.Windows.Controls.TextBox> von <xref:System.Windows.Controls.TextBox>und zusammengefasst.  
  
|Steuerelement|Rechtschreibprüfung in Echtzeit|Kontextmenü|Formatieren von <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> Befehlen wie (CTR + B)|<xref:System.Windows.Documents.FlowDocument>Inhalt wie Bilder, Absätze, Tabellen usw.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Ja|Ja|Nein|Nein.|  
|<xref:System.Windows.Controls.RichTextBox>|Ja|Ja|Ja (Siehe [Übersicht über RichTextBox](richtextbox-overview.md))|Ja (Siehe [Übersicht über RichTextBox](richtextbox-overview.md))|  
  
> [!NOTE]
> Obwohl <xref:System.Windows.Controls.TextBox> das <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> formatieren<xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>von zugehörigen Bearbeitungs Befehlen wie (CTR + B) nicht unterstützt, werden viele grundlegende Befehle von beiden Steuerelementen wie unterstützt. Weitere Informationen finden Sie unter <xref:System.Windows.Documents.EditingCommands>.  
  
 Die von <xref:System.Windows.Controls.TextBox> unterstützten Funktionen werden in den folgenden Abschnitten behandelt. Weitere Informationen zu finden <xref:System.Windows.Controls.RichTextBox>Sie unter [Übersicht über RichTextBox](richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Rechtschreibprüfung in Echtzeit  
 Sie können Rechtschreibprüfung in Echtzeit in einem <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox>in aktivieren. Wenn die Rechtschreibprüfung aktiviert ist, wird eine rote Linie unter falsch geschriebenen Wörtern angezeigt (siehe Abbildung unten).  
  
 ![TextBox mit Rechtschreibprüfung](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Wie Sie die Rechtschreibprüfung aktivieren, erfahren Sie unter [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### <a name="context-menu"></a>Kontextmenü  
 Standardmäßig verfügen sowohl <xref:System.Windows.Controls.TextBox> als <xref:System.Windows.Controls.RichTextBox> auch über ein Kontextmenü, das angezeigt wird, wenn ein Benutzer mit der rechten Maustaste auf das Steuerelement klickt. Das Kontextmenü ermöglicht dem Benutzer das Ausschneiden, Kopieren und Einfügen (siehe Bild unten).  
  
 ![TextBox mit Kontextmenü](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Sie können Ihr eigenes benutzerdefiniertes Kontextmenü erstellen, um das Standardverhalten zu überschreiben. Weitere Informationen finden Sie unter [Verwenden eines benutzerdefinierten Kontextmenüs mit „TextBox“](how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>Erstellen von TextBoxes  
 Ein <xref:System.Windows.Controls.TextBox> kann eine einzelne Zeile in Höhe oder mehrere Zeilen umfassen. Eine einzelne Zeile <xref:System.Windows.Controls.TextBox> eignet sich am besten zum Einfügen kleiner Mengen von Klartext (d. h. „Name“, „Telefonnummer“ usw. in einem Formular). Im folgenden Beispiel wird gezeigt, wie eine einzelne Zeile <xref:System.Windows.Controls.TextBox>erstellt wird.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 Sie können auch eine <xref:System.Windows.Controls.TextBox> erstellen, die es dem Benutzer ermöglicht, mehrere Textzeilen einzugeben. Wenn Ihr Formular z. b. eine biografische Darstellung des Benutzers angefordert hat, sollten Sie eine <xref:System.Windows.Controls.TextBox> verwenden, die mehrere Textzeilen unterstützt. Im folgenden Beispiel wird gezeigt, wie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verwendet wird, <xref:System.Windows.Controls.TextBox> um ein Steuerelement zu definieren, das automatisch erweitert wird, um mehrere Textzeilen anzupassen.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Wenn das <xref:System.Windows.Controls.TextBox.TextWrapping%2A> -Attribut `Wrap` auf festgelegt wird, wird Text in eine neue Zeile eingeschlossen, <xref:System.Windows.Controls.TextBox> wenn der Rand des Steuer Elements erreicht <xref:System.Windows.Controls.TextBox> wird. das Steuerelement wird automatisch erweitert, sodass es bei Bedarf den Raum für eine neue Zeile einschließt.  
  
 Das Festlegen <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> des- `true` Attributs auf bewirkt, dass eine neue Zeile eingefügt wird, wenn die Rückgabetaste gedrückt wird. <xref:System.Windows.Controls.TextBox> wenn dies der Fall ist, wird das automatisch erweitert, um Platz für eine neue Zeile einzuschließen.  
  
 Das <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> -Attribut fügt der <xref:System.Windows.Controls.TextBox>eine Bild Lauf Leiste hinzu, sodass der Inhalt des <xref:System.Windows.Controls.TextBox> durchlaufen werden kann, wenn die <xref:System.Windows.Controls.TextBox> über die Größe des Frame oder Fensters hinausgeht, in dem Sie eingeschlossen wird.  
  
 Weitere Informationen zu verschiedenen Aufgaben im Zusammenhang mit der <xref:System.Windows.Controls.TextBox>Verwendung von finden Sie in [den Themen](textbox-how-to-topics.md)zur Vorgehensweise.  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Erkennen, wenn Inhalt geändert wird  
 Normalerweise <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> sollte das-Ereignis verwendet werden, um zu erkennen, <xref:System.Windows.Controls.TextBox> wann <xref:System.Windows.Controls.RichTextBox> der Text in einer <xref:System.Windows.UIElement.KeyDown> -oder-Datei geändert wird. Ein Beispiel finden Sie unter [Erkennen von Änderungen an Text in einem Textfeld](how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## <a name="see-also"></a>Siehe auch

- [Themen zu Vorgehensweisen](textbox-how-to-topics.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
