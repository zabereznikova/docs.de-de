---
title: "&#220;bersicht &#252;ber TextBox | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Steuerelemente, TextBox"
  - "TextBox-Steuerelement, Informationen über das TextBox-Steuerelement"
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# &#220;bersicht &#252;ber TextBox
Mit der <xref:System.Windows.Controls.TextBox>\-Klasse können Sie unformatierten Text anzeigen oder bearbeiten.  <xref:System.Windows.Controls.TextBox> wird häufig verwendet, um unformatierten Text in einem Formular zu bearbeiten.  Zum Beispiel verwendet ein Formular, in dem nach dem Benutzernamen, der Telefonnummer usw. gefragt wird, <xref:System.Windows.Controls.TextBox>\-Steuerelemente für die Texteingabe.  In diesem Thema wird die <xref:System.Windows.Controls.TextBox>\-Klasse eingeführt. Außerdem sind Beispiele für ihre Verwendung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)] enthalten.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="textbox_or_richtextbox"></a>   
## TextBox oder RichTextBox?  
 Sowohl mit <xref:System.Windows.Controls.TextBox> als auch mit <xref:System.Windows.Controls.RichTextBox> können Benutzer Text eingeben. Die zwei Steuerelemente werden jedoch in unterschiedlichen Szenarien eingesetzt.  Ein <xref:System.Windows.Controls.TextBox> erfordert weniger Systemressourcen als ein <xref:System.Windows.Controls.RichTextBox>. Es ist daher ideal, wenn nur reiner Text bearbeitet werden muss \(d. h. bei der Verwendung in einem Formular\).  Ein <xref:System.Windows.Controls.RichTextBox> ist die bessere Wahl, wenn der Benutzer formatierten Text, Bilder, Tabellen oder andere unterstützte Inhalte bearbeiten muss.  So lässt sich das Bearbeiten von Dokumenten, Artikeln oder Blogs, die Formatierung, Bilder usw. benötigen, am besten mit einem <xref:System.Windows.Controls.RichTextBox> erreichen.  In der folgenden Tabelle werden die primären Features von <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.TextBox> zusammengefasst.  
  
|Steuerelement|Rechtschreibprüfung in Echtzeit|Kontextmenü|Formatierungsbefehle wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(STRG\+B\)|<xref:System.Windows.Documents.FlowDocument>\-Inhalte wie Bilder, Absätze, Tabellen usw.|  
|-------------------|-------------------------------------|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Ja|Ja|Nein|Nein.|  
|<xref:System.Windows.Controls.RichTextBox>|Ja|Ja|Ja \(siehe [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)\)|Ja \(siehe [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)\)|  
  
> [!NOTE]
>  Obwohl <xref:System.Windows.Controls.TextBox> keine formatierungsbezogenen Bearbeitungsbefehle wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(STRG\+B\) unterstützt, werden viele Grundbefehle, z. B. <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>, von beiden Steuerelementen unterstützt.  Weitere Informationen finden Sie unter <xref:System.Windows.Documents.EditingCommands>.  
  
 Von <xref:System.Windows.Controls.TextBox> unterstützte Features werden in den Abschnitten weiter unten behandelt.  Weitere Informationen über <xref:System.Windows.Controls.RichTextBox> finden Sie unter [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md).  
  
### Rechtschreibprüfung in Echtzeit  
 Sie können die Rechtschreibprüfung in Echtzeit in einem <xref:System.Windows.Controls.TextBox> oder einem <xref:System.Windows.Controls.RichTextBox> aktivieren.  Bei aktivierter Rechtschreibprüfung wird eine rote Linie unter allen falsch geschriebenen Wörtern angezeigt \(siehe Abbildung unten\).  
  
 ![TextBox mit Rechtschreibprüfung](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing\_TextBox\_with\_Spellchecking")  
  
 Weitere Informationen zur Aktivierung der Rechtschreibprüfung finden Sie unter [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### Kontextmenü  
 Standardmäßig verfügen <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.RichTextBox> über ein Kontextmenü, das angezeigt wird, wenn ein Benutzer mit der rechten Maustaste auf das Steuerelement klickt.  Mithilfe des Kontextmenüs kann der Benutzer die Vorgänge Ausschneiden, Kopieren bzw. Einfügen ausführen \(siehe Abbildung unten\).  
  
 ![TextBox mit Kontextmenü](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing\_TextBox\_with\_Context\_Menu")  
  
 Sie können ein eigenes benutzerdefiniertes Kontextmenü erstellen, um das Standardverhalten zu überschreiben.  Weitere Informationen finden Sie unter [Verwenden eines benutzerdefinierten Kontextmenüs mit "TextBox"](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>   
## Erstellen von TextBoxes  
 Ein <xref:System.Windows.Controls.TextBox> kann eine einzelne Zeile hoch sein oder mehrere Zeilen umfassen.  Ein einzeiliges <xref:System.Windows.Controls.TextBox>\-Element eignet sich am besten, um geringe Textmengen im Nur\-Text\-Format einzugeben \(z. B. "  Name", "Telefonnummer" usw.  in einem Formular\).  Im folgenden Beispiel wird das Erstellen eines einfachen einzeiligen <xref:System.Windows.Controls.TextBox>\-Elements veranschaulicht.  
  
 [!code-xml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 Sie können auch ein <xref:System.Windows.Controls.TextBox> erstellen, mit dem der Benutzer mehrere Textzeilen eingeben kann.  Wenn z. B. der Benutzer im Formular um die Eingabe eines kurzen Lebenslaufs gebeten wird, verwenden Sie dazu ein <xref:System.Windows.Controls.TextBox>, das mehrere Zeilen Text aufnimmt.  Im folgenden Beispiel wird verdeutlicht, wie mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ein <xref:System.Windows.Controls.TextBox>\-Steuerelement definiert wird, das sich automatisch vergrößert, um mehrere Zeilen Text aufzunehmen.  
  
 [!code-xml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Durch Festlegen des <xref:System.Windows.Controls.TextBox.TextWrapping%2A>\-Attributs auf `Wrap` wird Text auf eine neue Zeile umbrochen, wenn der Rand des <xref:System.Windows.Controls.TextBox>\-Steuerelements erreicht wird. Dabei wird ggf. automatisch das <xref:System.Windows.Controls.TextBox>\-Steuerelement angepasst, um die neue Zeile aufzunehmen.  
  
 Durch Festlegen des <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>\-Attributs auf `true` wird eine neue Zeile eingefügt, wenn die EINGABETASTE gedrückt wird, wodurch ggf. auch wieder das <xref:System.Windows.Controls.TextBox> automatisch angepasst wird, um die neue Zeile aufzunehmen.  
  
 Das <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>\-Attribut fügt dem <xref:System.Windows.Controls.TextBox> eine Bildlaufleiste hinzu, sodass für die Inhalte des <xref:System.Windows.Controls.TextBox>\-Elements ein Bildlauf durchgeführt werden kann, wenn das <xref:System.Windows.Controls.TextBox> die Größe des umgebenden Rahmens oder Fensters überschreitet.  
  
 Weitere Informationen über andere Aufgaben im Zusammenhang mit dem Verwenden eines <xref:System.Windows.Controls.TextBox>\-Elements finden Sie unter [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>   
## Erkennen von Inhaltsänderungen  
 Sie sollten i. d. R. mit dem <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>\-Ereignis ermitteln, wann Text in einem <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox> geändert wird, und dafür nicht, wie zu erwarten wäre, <xref:System.Windows.UIElement.KeyDown> verwenden.  Ein Beispiel finden Sie unter [Erkennen von Änderungen an Text in einem Textfeld](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## Siehe auch  
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)