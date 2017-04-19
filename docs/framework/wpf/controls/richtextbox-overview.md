---
title: "&#220;bersicht &#252;ber RichTextBox | Microsoft Docs"
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
  - "Steuerelemente, RichTextBox"
  - "RichTextBox-Steuerelement [WPF], Informationen über das RichTextBox-Steuerelement"
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bersicht &#252;ber RichTextBox
Das <xref:System.Windows.Controls.RichTextBox>\-Steuerelement ermöglicht es Ihnen, fortlaufenden Inhalt, einschließlich Absätze, Bilder, Tabellen und mehr, anzuzeigen oder zu bearbeiten.  In diesem Thema wird die <xref:System.Windows.Controls.TextBox>\-Klasse eingeführt. Außerdem sind Beispiele für ihre Verwendung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)] enthalten.  
  
   
  
<a name="textbox_or_richtextbox"></a>   
## TextBox oder RichTextBox?  
 Sowohl mit <xref:System.Windows.Controls.RichTextBox> als auch mit <xref:System.Windows.Controls.TextBox> können Benutzer Text bearbeiten. Die zwei Steuerelemente werden jedoch in unterschiedlichen Szenarien eingesetzt.  Ein <xref:System.Windows.Controls.RichTextBox> ist die bessere Wahl, wenn der Benutzer formatierten Text, Bilder, Tabellen oder andere umfangreiche Inhalte bearbeiten muss.  So lässt sich das Bearbeiten von Dokumenten, Artikeln oder Blogs, die Formatierung, Bilder usw. benötigen, am besten mit einem <xref:System.Windows.Controls.RichTextBox> erreichen.  Ein <xref:System.Windows.Controls.TextBox>\-Element erfordert weniger Systemressourcen als ein <xref:System.Windows.Controls.RichTextBox>\-Element. Es ist ideal, wenn nur reiner Text bearbeitet werden muss \(d. h.  bei der Verwendung in Formularen\).  Weitere Informationen zum <xref:System.Windows.Controls.TextBox> finden Sie unter [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md).  In der unten stehenden Tabelle werden die wichtigsten Features von <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.RichTextBox> zusammengefasst.  
  
|Steuerelement|Rechtschreibprüfung in Echtzeit|Kontextmenü|Formatierungsbefehle wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(STRG\+B\)|<xref:System.Windows.Documents.FlowDocument>\-Inhalte wie Bilder, Absätze, Tabellen usw.|  
|-------------------|-------------------------------------|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Ja|Ja|Nein|Nein.|  
|<xref:System.Windows.Controls.RichTextBox>|Ja|Ja|Ja|Ja|  
  
 **Hinweis:** Obwohl <xref:System.Windows.Controls.TextBox> keine formatierungsbezogenen Befehle wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(STRG\+B\) unterstützt, werden viele Grundbefehle, z. B. <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>, von beiden Steuerelementen unterstützt.  
  
 Die Features aus der vorstehenden Tabelle werden später ausführlicher behandelt.  
  
<a name="creating_a_richtextbox"></a>   
## Erstellen eines RichTextBox\-Elements  
 Der folgende Code veranschaulicht, wie ein <xref:System.Windows.Controls.RichTextBox>\-Element erstellt wird, in dem ein Benutzer umfangreichen Inhalt bearbeiten kann.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 Genauer gesagt handelt es sich bei dem Inhalt, der in einem <xref:System.Windows.Controls.RichTextBox> bearbeitet wird, um fortlaufenden Inhalt.  Fortlaufender Inhalt kann viele Elementtypen einschließlich formatierten Texts, Bilder, Listen und Tabellen enthalten.  Ausführliche Informationen zu Flussdokumenten finden Sie unter [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  Für die Aufnahme von fortlaufendem Inhalt hostet ein <xref:System.Windows.Controls.RichTextBox>\-Element ein <xref:System.Windows.Documents.FlowDocument>\-Objekt, das wiederum den bearbeitbaren Inhalt enthält.  Zur Veranschaulichung von fortlaufendem Inhalt in einem <xref:System.Windows.Controls.RichTextBox> zeigt der folgende Code, wie ein <xref:System.Windows.Controls.RichTextBox> mit einem Absatz und fett formatiertem Text erstellt wird.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![RichTextBox mit Inhalt](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-content.png "Editing\_RichTextBox\_with\_Content")  
  
 Elemente wie <xref:System.Windows.Documents.Paragraph> und <xref:System.Windows.Documents.Bold> bestimmen, wie der Inhalt in einem <xref:System.Windows.Controls.RichTextBox> angezeigt wird.  Wenn ein Benutzer <xref:System.Windows.Controls.RichTextBox>\-Inhalt bearbeitet, wird damit dieser fortlaufende Inhalt geändert.  Weitere Informationen über die Features von fortlaufendem Inhalt und die Arbeit mit ihnen finden Sie unter [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
 **Hinweis:** Fortlaufender Inhalt in einer <xref:System.Windows.Controls.RichTextBox> verhält sich nicht genau wie in anderen Steuerelementen enthaltener fortlaufender Inhalt.  Zum Beispiel gibt es in einer <xref:System.Windows.Controls.RichTextBox> keine Spalten und somit auch keine automatische Größenanpassung.  Auch die integrierten Features wie die Suchfunktion, der Anzeigemodus, die Seitennavigation und die Zoomfunktion stehen in einem <xref:System.Windows.Controls.RichTextBox> nicht zur Verfügung.  
  
<a name="realtime_spellechecking"></a>   
## Rechtschreibprüfung in Echtzeit  
 Sie können die Rechtschreibprüfung in Echtzeit in einem <xref:System.Windows.Controls.TextBox> oder einem <xref:System.Windows.Controls.RichTextBox> aktivieren.  Bei aktivierter Rechtschreibprüfung wird eine rote Linie unter allen falsch geschriebenen Wörtern angezeigt \(siehe Abbildung unten\).  
  
 ![TextBox mit Rechtschreibprüfung](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing\_TextBox\_with\_Spellchecking")  
  
 Weitere Informationen zur Aktivierung der Rechtschreibprüfung finden Sie unter [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
<a name="context_menu"></a>   
## Kontextmenü  
 Standardmäßig verfügen <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.RichTextBox> über ein Kontextmenü, das angezeigt wird, wenn ein Benutzer mit der rechten Maustaste auf das Steuerelement klickt.  Mithilfe des Kontextmenüs kann der Benutzer die Vorgänge Ausschneiden, Kopieren bzw. Einfügen ausführen \(siehe Abbildung unten\).  
  
 ![TextBox mit Kontextmenü](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing\_TextBox\_with\_Context\_Menu")  
  
 Sie können ein eigenes benutzerdefiniertes Kontextmenü erstellen, um das Standardmenü zu überschreiben.  Weitere Informationen finden Sie unter [Positionieren eines benutzerdefinierten Kontextmenüs in einer RichTextBox](../../../../docs/framework/wpf/controls/how-to-position-a-custom-context-menu-in-a-richtextbox.md).  
  
<a name="detect_when_content_changes"></a>   
## Bearbeitungsbefehle  
 Bearbeitungsbefehle ermöglichen es Benutzern, bearbeitbaren Inhalt in einem <xref:System.Windows.Controls.RichTextBox> zu formatieren.  Außer grundlegenden Bearbeitungsbefehlen umfasst ein <xref:System.Windows.Controls.RichTextBox> Formatierungsbefehle, die ein <xref:System.Windows.Controls.TextBox> nicht unterstützt.  Bei der Arbeit in einem <xref:System.Windows.Controls.RichTextBox> kann zum Beispiel durch Drücken von STRG\+B die Fettformatierung von Text aktiviert oder deaktiviert werden.  Eine vollständige Liste der verfügbaren Befehle finden Sie unter <xref:System.Windows.Documents.EditingCommands>.  Neben der Verwendung von Tastenkombinationen können Sie Befehle mit anderen Steuerelementen wie Schaltflächen verknüpfen.  Im folgenden Beispiel wird veranschaulicht, wie Sie eine einfache Symbolleiste mit Schaltflächen erstellen, mit denen die Textformatierung geändert werden kann.  
  
 [!code-xml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel angezeigt wird.  
  
 ![RichTextBox mit ToolBar](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-toobar.png "Editing\_RichTextBox\_with\_TooBar")  
  
<a name="editing_commands"></a>   
## Erkennen von Inhaltsänderungen  
 Sie sollten i. d. R. mit dem <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>\-Ereignis ermitteln, wann Text in einem <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox> geändert wird, und dafür nicht, wie zu erwarten wäre, <xref:System.Windows.UIElement.KeyDown> verwenden.  Ein Beispiel finden Sie unter [Erkennen von Änderungen an Text in einem Textfeld](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## Speichern, Laden und Drucken von RichTextBox\-Inhalt  
 Im folgenden Beispiel wird gezeigt, wie Sie den Inhalt eines <xref:System.Windows.Controls.RichTextBox>\-Elements in eine Datei speichern, den Inhalt dann wieder in das <xref:System.Windows.Controls.RichTextBox>\-Element laden und anschließend den Inhalt drucken.  Im Folgenden finden Sie das Markup für das Beispiel.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 Im Folgenden finden Sie den Code\-Behind für das Beispiel.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## Siehe auch  
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/richtextbox-how-to-topics.md)   
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)