---
title: Übersicht über RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: 689094bda355f095c30d6cc2a462e6d0e630753b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378196"
---
# <a name="richtextbox-overview"></a>Übersicht über RichTextBox
Die <xref:System.Windows.Controls.RichTextBox> -Steuerelement können Sie zum Anzeigen oder Bearbeiten von fortlaufenden Inhalt wie Absätze, Bilder, Tabellen und vieles mehr. In diesem Thema werden die <xref:System.Windows.Controls.TextBox> -Klasse und stellt Beispiele für die Verwendung in beiden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und C#.  
  
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>TextBox oder RichTextBox?  
 Beide <xref:System.Windows.Controls.RichTextBox> und <xref:System.Windows.Controls.TextBox> Benutzerberechtigungen zum Bearbeiten von Text, jedoch die beiden Steuerelemente in verschiedenen Szenarien verwendet werden. Ein <xref:System.Windows.Controls.RichTextBox> ist eine bessere Wahl, wenn der Benutzer formatierten Text, Bilder, Tabellen oder andere umfangreiche Inhalte bearbeiten muss. Z. B. Bilder bearbeiten ein Dokument, Artikel oder Blogs, die Formatierung, erforderlich sind, usw. erfolgt am besten mithilfe einer <xref:System.Windows.Controls.RichTextBox>. Ein <xref:System.Windows.Controls.TextBox> benötigt weniger Systemressourcen und dann eine <xref:System.Windows.Controls.RichTextBox> und eignet sich ideal, wenn nur nur-Text sein muss (d. h. die Verwendung in Formularen) bearbeitet. Finden Sie unter [Übersicht über TextBox](textbox-overview.md) für Weitere Informationen zu <xref:System.Windows.Controls.TextBox>. In der folgenden Tabelle werden die Hauptfunktionen von <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.RichTextBox>.  
  
|Steuerelement|Rechtschreibprüfung in Echtzeit|Kontextmenü|Formatierungsbefehle wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (STRG + B)|<xref:System.Windows.Documents.FlowDocument> Inhalte wie Bilder, Absätze, Tabellen usw.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Ja|Ja|Nein|Nein.|  
|<xref:System.Windows.Controls.RichTextBox>|Ja|Ja|Ja|Ja|  
  
 **Hinweis**: Obwohl <xref:System.Windows.Controls.TextBox> unterstützt keine verknüpften Formatierungsbefehle wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (STRG + B), viele grundlegende Befehle werden von beiden Steuerelementen unterstützt, z. B. <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.  
  
 Die Funktionen aus der obigen Tabelle werden später ausführlicher behandelt.  
  
<a name="creating_a_richtextbox"></a>   
## <a name="creating-a-richtextbox"></a>Erstellen eines RichTextBox-Steuerelements  
 Der folgende Code zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.RichTextBox> , dass ein Benutzer mit umfangreichen Inhalt bearbeiten kann.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 Insbesondere der Inhalt weder bearbeitet, einem <xref:System.Windows.Controls.RichTextBox> fortlaufendem Inhalt ist. Fortlaufender Inhalt kann viele Arten von Elementen enthalten, darunter formatierten Text, Bilder, Listen und Tabellen. Ausführliche Informationen zu Flussdokumenten finden Sie unter [Übersicht über Flussdokumente](../advanced/flow-document-overview.md). Um fortlaufenden Inhalt, enthalten eine <xref:System.Windows.Controls.RichTextBox> Hosts eine <xref:System.Windows.Documents.FlowDocument> Objekt, das wiederum den bearbeitbaren Inhalt enthält. Zur Veranschaulichung von fortlaufendem Inhalt in einem <xref:System.Windows.Controls.RichTextBox>, der folgende Code zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.RichTextBox> mit einem Absatz und fett formatiertem Text.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![RichTextBox mit Inhalt](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")  
  
 Elemente wie <xref:System.Windows.Documents.Paragraph> und <xref:System.Windows.Documents.Bold> zu bestimmen wie die Inhalte innerhalb von einer <xref:System.Windows.Controls.RichTextBox> angezeigt wird. Wenn ein Benutzer bearbeitet <xref:System.Windows.Controls.RichTextBox> Inhalt aus, ändern sie diesen fortlaufenden Inhalt. Weitere Informationen über die Funktionen von fortlaufendem Inhalt und das Arbeiten damit finden Sie unter [Übersicht über Flussdokumente](../advanced/flow-document-overview.md).  
  
 **Hinweis**: Fortlaufender Inhalt in einem <xref:System.Windows.Controls.RichTextBox> verhält sich nicht genau wie fortlaufender Inhalt innerhalb anderer Steuerelemente. Beispielsweise gibt es sind keine Spalten in einer <xref:System.Windows.Controls.RichTextBox> und daher kein automatisches Größenänderungsverhalten. Auch die integrierten Funktionen wie Suche, Anzeigemodus, Seitennavigation und Zoom nicht verfügbar sind ein <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="realtime_spellechecking"></a>   
## <a name="real-time-spell-checking"></a>Rechtschreibprüfung in Echtzeit  
 Sie können die Rechtschreibprüfung in Echtzeit in einem <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox>. Wenn die Rechtschreibprüfung aktiviert ist, wird eine rote Linie unter falsch geschriebenen Wörtern angezeigt (siehe Abbildung unten).  
  
 ![TextBox mit Rechtschreibprüfung](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Wie Sie die Rechtschreibprüfung aktivieren, erfahren Sie unter [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
<a name="context_menu"></a>   
## <a name="context-menu"></a>Kontextmenü  
 Standardmäßig sowohl <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.RichTextBox> haben Sie ein Kontextmenü, das angezeigt wird, wenn ein Benutzer auf das Steuerelement klickt. Das Kontextmenü ermöglicht dem Benutzer das Ausschneiden, Kopieren und Einfügen (siehe Abbildung unten).  
  
 ![TextBox mit Kontextmenü](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Sie können Ihr eigenes benutzerdefiniertes Kontextmenü erstellen, um den Standard zu überschreiben. Weitere Informationen finden Sie unter [Positionieren eines benutzerdefinierten Kontextmenüs in einem „RichTextBox“-Element](how-to-position-a-custom-context-menu-in-a-richtextbox.md).  
  
<a name="detect_when_content_changes"></a>   
## <a name="editing-commands"></a>Bearbeitungsbefehle  
 Bearbeitungsbefehle ermöglichen es Benutzern, bearbeitbaren Inhalt in Formatieren einer <xref:System.Windows.Controls.RichTextBox>. Neben grundlegenden Bearbeitungsbefehlen <xref:System.Windows.Controls.RichTextBox> enthält Formatierungsbefehle, <xref:System.Windows.Controls.TextBox> wird nicht unterstützt. Beispielsweise wird beim Bearbeiten in einer <xref:System.Windows.Controls.RichTextBox>, ein Benutzer kann STRG + B, um fetten textformatierung zu wechseln. drücken. Finden Sie unter <xref:System.Windows.Documents.EditingCommands> für eine vollständige Liste der verfügbaren Befehle. Zusätzlich zu Tastenkombinationen können Sie Befehle mit anderen Steuerelementen wie Schaltflächen verknüpfen. Im folgenden Beispiel wird veranschaulicht, wie eine einfache Symbolleiste mit Schaltflächen erstellt wird, mit denen der Benutzer die Textformatierung ändern kann.  
  
 [!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel angezeigt wird.  
  
 ![RichTextBox mit ToolBar](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Erkennen, wenn Inhalt geändert wird  
 In der Regel die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Ereignis sollte verwendet werden, um zu ermitteln des Texts in einem <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox> ändert und nicht <xref:System.Windows.UIElement.KeyDown> wie zu erwarten. Ein Beispiel finden Sie unter [Erkennen von Änderungen an Text in einem Textfeld](how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## <a name="save-load-and-print-richtextbox-content"></a>Speichern, Laden und Drucken von RichTextBox-Inhalt  
 Das folgende Beispiel zeigt, wie zum Speichern von Inhalt einer <xref:System.Windows.Controls.RichTextBox> in eine Datei zu laden, dieser Inhalt zurück in die <xref:System.Windows.Controls.RichTextBox>, und Drucken des Inhalts. Im Folgenden sehen Sie das Markup für das Beispiel.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 Im Folgenden sehen Sie den Code für das Beispiel.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- [Themen zu Vorgehensweisen](richtextbox-how-to-topics.md)
- [Übersicht über TextBox](textbox-overview.md)
