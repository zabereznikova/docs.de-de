---
title: Übersicht über TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: c33edcf98f13e637d41de41618e5e6364c69613a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556011"
---
# <a name="textbox-overview"></a>Übersicht über TextBox
Die <xref:System.Windows.Controls.TextBox> -Klasse können Sie anzeigen oder Bearbeiten von nicht formatiertem Text. Eine übliche Verwendung dieser eine <xref:System.Windows.Controls.TextBox> unformatierten Texts in einem Formular bearbeitet wird. Beispielsweise ein Formular in der der Benutzername, Telefonnummer, usw. verwenden <xref:System.Windows.Controls.TextBox> Steuerelemente für die Texteingabe. In diesem Thema werden die <xref:System.Windows.Controls.TextBox> -Klasse und stellt Beispiele für die Verwendung in beiden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und C#.  
  
 
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>TextBox oder RichTextBox?  
 Beide <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.RichTextBox> können Benutzer Text eingeben, aber die beiden Steuerelemente für verschiedene Szenarien verwendet werden. Ein <xref:System.Windows.Controls.TextBox> benötigt weniger Systemressourcen und dann eine <xref:System.Windows.Controls.RichTextBox> daher ist es ideal, wenn ausschließlich reiner Text bearbeitet werden muss (d. h. die Nutzung in einem Formular). Ein <xref:System.Windows.Controls.RichTextBox> ist die bessere Wahl, wenn es erforderlich, um formatierten Text, Bilder, Tabellen zu bearbeiten ist, oder andere unterstützte Inhalt. Z. B. Bilder bearbeiten ein Dokument, Artikel oder Blogs, die Formatierung, erforderlich sind, usw. erfolgt am besten mithilfe einer <xref:System.Windows.Controls.RichTextBox>. Der Tabelle unten sind die wichtigsten Features des <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.TextBox>.  
  
|Steuerelement|Rechtschreibprüfung in Echtzeit|Kontextmenü|Formatierungsbefehle wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (STRG + B)|<xref:System.Windows.Documents.FlowDocument> Inhalte wie Bilder, Absätze, Tabellen usw.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Ja|Ja|Nein|Nein.|  
|<xref:System.Windows.Controls.RichTextBox>|Ja|Ja|Ja (Siehe [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md))|Ja (Siehe [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md))|  
  
> [!NOTE]
>  Obwohl <xref:System.Windows.Controls.TextBox> wird nicht unterstützt, die Formatierung der zugehörigen bearbeiten wie Befehle <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (STRG + B) viele grundlegende Befehle werden von beiden Steuerelementen unterstützt, z. B. <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>. Weitere Informationen finden Sie unter <xref:System.Windows.Documents.EditingCommands>.  
  
 Funktionen, die von unterstützt <xref:System.Windows.Controls.TextBox> werden in den folgenden Abschnitten behandelt. Weitere Informationen zu <xref:System.Windows.Controls.RichTextBox>, finden Sie unter [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Rechtschreibprüfung in Echtzeit  
 Sie können die Rechtschreibprüfung in Echtzeit in einem <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox>. Wenn die Rechtschreibprüfung aktiviert ist, wird eine rote Linie unter falsch geschriebenen Wörtern angezeigt (siehe Abbildung unten).  
  
 ![TextBox mit Rechtschreibprüfung](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Wie Sie die Rechtschreibprüfung aktivieren, erfahren Sie unter [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### <a name="context-menu"></a>Kontextmenü  
 Standardmäßig sowohl <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.RichTextBox> haben Sie ein Kontextmenü, das angezeigt wird, wenn ein Benutzer auf das Steuerelement klickt. Das Kontextmenü ermöglicht dem Benutzer das Ausschneiden, Kopieren und Einfügen (siehe Bild unten).  
  
 ![TextBox mit Kontextmenü](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Sie können Ihr eigenes benutzerdefiniertes Kontextmenü erstellen, um das Standardverhalten zu überschreiben. Weitere Informationen finden Sie unter [Verwenden eines benutzerdefinierten Kontextmenüs mit „TextBox“](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>Erstellen von TextBoxes  
 Ein <xref:System.Windows.Controls.TextBox> können eine einzelne Zeile in der Höhe sein oder aus mehreren Zeilen bestehen. Eine einzelne Zeile <xref:System.Windows.Controls.TextBox> ist am besten für kleine Mengen von nur-Text (d. h. eingeben „Name“, „Telefonnummer“ usw. in einem Formular). Das folgende Beispiel zeigt, wie Sie eine einzelne Zeile erstellen <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 Sie können auch erstellen, eine <xref:System.Windows.Controls.TextBox> , mit der Benutzer mehrere Textzeilen eingeben können. Z. B. wenn das Formular z.B. eine biografische Skizze des Benutzers aufgefordert, Sie würden verwenden möchten eine <xref:System.Windows.Controls.TextBox> , die mehrere Zeilen Text unterstützt. Das folgende Beispiel zeigt, wie Sie mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Definieren einer <xref:System.Windows.Controls.TextBox> -Steuerelement, das automatisch vergrößert, um mehrere Textzeilen aufzunehmen.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Festlegen der <xref:System.Windows.Controls.TextBox.TextWrapping%2A> Attribut `Wrap` bewirkt, dass Text umbrochen, um eine neue Zeile, wenn am Rand des der <xref:System.Windows.Controls.TextBox> Steuerelement erreicht ist, wird automatisch zu erweitern die <xref:System.Windows.Controls.TextBox> Steuerelement eine neue Zeile, ggf. aufzunehmen.  
  
 Festlegen der <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> Attribut `true` bewirkt, dass eine neue Zeile eingefügt werden soll, wenn die RETURN-Taste gedrückt wird, automatisch angepasst wird, die <xref:System.Windows.Controls.TextBox> eine neue Zeile, ggf. aufzunehmen.  
  
 Die <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> -Attribut fügt eine Bildlaufleiste angezeigt, die <xref:System.Windows.Controls.TextBox>, sodass den Inhalt des der <xref:System.Windows.Controls.TextBox> Bildlauf durchgeführt werden können, wenn die <xref:System.Windows.Controls.TextBox> die Größe des Frames oder Fensters überschreitet.  
  
 Weitere Informationen über andere Aufgaben, die mit der Verwendung einer <xref:System.Windows.Controls.TextBox>, finden Sie unter [Gewusst-wie-Themen](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Erkennen, wenn Inhalt geändert wird  
 In der Regel die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Ereignis sollte verwendet werden, um zu ermitteln des Texts in einem <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox> geändert wird, klicken Sie dann stattdessen <xref:System.Windows.UIElement.KeyDown> wie zu erwarten. Ein Beispiel finden Sie unter [Erkennen von Änderungen an Text in einem Textfeld](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## <a name="see-also"></a>Siehe auch
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)
- [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
