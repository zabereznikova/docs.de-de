---
title: "Übersicht über TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d1116093ddcd95c99deac8a1e1b14fef3b0a458f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="textbox-overview"></a>Übersicht über TextBox
Die <xref:System.Windows.Controls.TextBox> -Klasse ermöglicht es Ihnen, anzeigen oder Bearbeiten von nicht formatiertem Text. Eine häufige Verwendung einer <xref:System.Windows.Controls.TextBox> Bearbeiten von nicht formatiertem Text in einem Formular ist. Z. B. ein Formular in der der Benutzername, Telefonnummer, usw. verwenden <xref:System.Windows.Controls.TextBox> Steuerelemente für die Texteingabe. Dieses Thema enthält die <xref:System.Windows.Controls.TextBox> -Klasse und stellt Beispiele für die Verwendung in beiden [!INCLUDE[TLA#tla_xaml](./../../../includes/tlasharptla-xaml-md.md)] und [!INCLUDE[TLA#tla_lhcshrp](./../../../includes/tlasharptla-lhcshrp-md.md)].  
  
 
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>TextBox oder RichTextBox?  
 Beide <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.RichTextBox> ermöglicht Benutzern die Eingabe von Text, jedoch die beiden Steuerelemente für verschiedene Szenarien verwendet werden. Ein <xref:System.Windows.Controls.TextBox> erfordert weniger Systemressourcen und dann eine <xref:System.Windows.Controls.RichTextBox> daher ist es ideal, wenn nur nur-Text bearbeitet werden muss (d. h. die Verwendung in einem Formular). Ein <xref:System.Windows.Controls.RichTextBox> ist die bessere Wahl, wenn es ist notwendig, damit der Benutzer bearbeiten formatierten Text, Bilder, Tabellen oder anderen unterstützten Inhalt. Z. B. Bilder bearbeiten, ein Dokument, Artikel oder Blogs, die Formatierung erforderlich sind, usw. erfolgt am besten mit einer <xref:System.Windows.Controls.RichTextBox>. In der folgenden Tabelle werden die wichtigsten Features von zusammengefasst <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.TextBox>.  
  
|Steuerelement|Rechtschreibprüfung in Echtzeit|Kontextmenü|Befehle wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (STRG + B)|<xref:System.Windows.Documents.FlowDocument>Inhalt wie Bilder, Absätze, Tabellen usw.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Ja|Ja|Nein|Nein.|  
|<xref:System.Windows.Controls.RichTextBox>|Ja|Ja|Ja (Siehe [Übersicht über RichTextBox](./../../../docs/framework/wpf/controls/richtextbox-overview.md))|Ja (Siehe [Übersicht über RichTextBox](./../../../docs/framework/wpf/controls/richtextbox-overview.md))|  
  
> [!NOTE]
>  Obwohl <xref:System.Windows.Controls.TextBox> wird nicht unterstützt, die Formatierung der zugehörigen bearbeiten wie Befehle <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (STRG + B) viele grundlegende Befehle werden von beide Steuerelemente unterstützt, z. B. <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>. Weitere Informationen finden Sie unter <xref:System.Windows.Documents.EditingCommands>.  
  
 Funktionen, die von unterstützt <xref:System.Windows.Controls.TextBox> werden in den folgenden Abschnitten behandelt. Weitere Informationen zu <xref:System.Windows.Controls.RichTextBox>, finden Sie unter [RichTextBox Overview](./../../../docs/framework/wpf/controls/richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Rechtschreibprüfung in Echtzeit  
 Sie können die Rechtschreibprüfung in Echtzeit in ein <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox>. Wenn die Rechtschreibprüfung aktiviert ist, wird eine rote Linie unter falsch geschriebenen Wörtern angezeigt (siehe Abbildung unten).  
  
 ![TextBox mit Rechtschreibprüfung](./../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Wie Sie die Rechtschreibprüfung aktivieren, erfahren Sie unter [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](./../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### <a name="context-menu"></a>Kontextmenü  
 Standardmäßig sowohl <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.RichTextBox> haben Sie ein Kontextmenü, das angezeigt wird, wenn ein Benutzer auf das Steuerelement klickt. Das Kontextmenü ermöglicht dem Benutzer das Ausschneiden, Kopieren und Einfügen (siehe Bild unten).  
  
 ![TextBox mit Kontextmenü](./../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Sie können Ihr eigenes benutzerdefiniertes Kontextmenü erstellen, um das Standardverhalten zu überschreiben. Weitere Informationen finden Sie unter [Verwenden eines benutzerdefinierten Kontextmenüs mit „TextBox“](./../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>Erstellen von TextBoxes  
 Ein <xref:System.Windows.Controls.TextBox> kann eine einzelne Zeile im Höhe oder mehrere Zeilen umfassen. Eine einzelne Zeile <xref:System.Windows.Controls.TextBox> ist am besten für kleine Mengen von nur-Text (d. h. eingeben „Name“, „Telefonnummer“ usw. in einem Formular). Im folgende Beispiel wird gezeigt, wie zum Erstellen einer einzelnen Zeile <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 Sie können auch erstellen eine <xref:System.Windows.Controls.TextBox> , mit dessen Hilfe des Benutzers, mehrere Textzeilen einzugeben. Z. B. wenn das Formular für einen Lebenslaufs der Benutzer aufgefordert werden, würde möchten Sie verwenden eine <xref:System.Windows.Controls.TextBox> , die mehrere Textzeilen unterstützt. Das folgende Beispiel zeigt, wie Sie [!INCLUDE[TLA#tla_xaml](./../../../includes/tlasharptla-xaml-md.md)] zum Definieren einer <xref:System.Windows.Controls.TextBox> Steuerelement, das automatisch vergrößert, um mehrere Textzeilen.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Festlegen der <xref:System.Windows.Controls.TextBox.TextWrapping%2A> -Attribut auf `Wrap` bewirkt, dass Text umbrochen, um eine neue Zeile am Rand des der <xref:System.Windows.Controls.TextBox> Steuerelement erreicht ist der <xref:System.Windows.Controls.TextBox> Steuerelement, um Platz für eine neue Zeile enthalten, bei Bedarf.  
  
 Festlegen der <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> -Attribut auf `true` bewirkt, dass eine neue Zeile eingefügt, wenn die RETURN-Taste wieder automatisch zu erweitern gedrückt wird, die <xref:System.Windows.Controls.TextBox> Platz für eine neue Zeile bei Bedarf enthalten.  
  
 Die <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> Attribut fügt eine Bildlaufleiste, um die <xref:System.Windows.Controls.TextBox>, sodass den Inhalt des der <xref:System.Windows.Controls.TextBox> Bildlauf durchgeführt werden kann, wenn die <xref:System.Windows.Controls.TextBox> erweitert die Größe des den Frame oder das Fenster, das es umschließt.  
  
 Weitere Informationen über andere Aufgaben im Zusammenhang mit der Verwendung einer <xref:System.Windows.Controls.TextBox>, finden Sie unter [Gewusst-wie-Themen](./../../../docs/framework/wpf/controls/textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Erkennen, wenn Inhalt geändert wird  
 In der Regel die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Ereignis sollte ermitteln, wann verwendet werden der Text in einer <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox> geändert wird, klicken Sie dann stattdessen <xref:System.Windows.UIElement.KeyDown> wie zu erwarten. Ein Beispiel finden Sie unter [Erkennen von Änderungen an Text in einem Textfeld](./../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Themen zur Vorgehensweise](./../../../docs/framework/wpf/controls/textbox-how-to-topics.md)  
 [Übersicht über RichTextBox](./../../../docs/framework/wpf/controls/richtextbox-overview.md)
