---
title: "Übersicht über RichTextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41b423235fc2ed9c0e0612c90017d41ab0e83d0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="richtextbox-overview"></a>Übersicht über RichTextBox
Die <xref:System.Windows.Controls.RichTextBox> Steuerelement können Sie zum Anzeigen oder Bearbeiten von fortlaufenden Inhalt, einschließlich Absätze, Bilder und Tabellen. Dieses Thema enthält die <xref:System.Windows.Controls.TextBox> -Klasse und stellt Beispiele für die Verwendung in beiden [!INCLUDE[TLA#tla_xaml](./../../../includes/tlasharptla-xaml-md.md)] und [!INCLUDE[TLA#tla_lhcshrp](./../../../includes/tlasharptla-lhcshrp-md.md)].  
  
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>TextBox oder RichTextBox?  
 Beide <xref:System.Windows.Controls.RichTextBox> und <xref:System.Windows.Controls.TextBox> Benutzerberechtigungen zum Bearbeiten von Text, allerdings die beiden Steuerelemente in verschiedenen Szenarien verwendet werden. Ein <xref:System.Windows.Controls.RichTextBox> ist eine bessere Wahl, wenn es für Benutzer formatierten Text, Bilder, Tabellen oder andere umfangreiche Inhalte bearbeiten erforderlich ist. Z. B. Bilder bearbeiten, ein Dokument, Artikel oder Blogs, die Formatierung erforderlich sind, usw. erfolgt am besten mit einer <xref:System.Windows.Controls.RichTextBox>. Ein <xref:System.Windows.Controls.TextBox> erfordert weniger Systemressourcen und dann eine <xref:System.Windows.Controls.RichTextBox> und eignet sich ideal, wenn nur nur-Text werden muss (d. h. der Verwendung in Formularen) bearbeitet. Finden Sie unter [TextBox Overview](./../../../docs/framework/wpf/controls/textbox-overview.md) Weitere Informationen zu <xref:System.Windows.Controls.TextBox>. In der folgenden Tabelle werden die Hauptfunktionen von <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.RichTextBox>.  
  
|Steuerelement|Rechtschreibprüfung in Echtzeit|Kontextmenü|Befehle wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (STRG + B)|<xref:System.Windows.Documents.FlowDocument>Inhalt wie Bilder, Absätze, Tabellen usw.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Ja|Ja|Nein|Nein.|  
|<xref:System.Windows.Controls.RichTextBox>|Ja|Ja|Ja|Ja|  
  
 **Hinweis:** zwar <xref:System.Windows.Controls.TextBox> unterstützt keine Formatierung verwandter Befehle wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (STRG + B) viele grundlegende Befehle werden von beide Steuerelemente unterstützt, z. B. <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.  
  
 Die Funktionen aus der obigen Tabelle werden später ausführlicher behandelt.  
  
<a name="creating_a_richtextbox"></a>   
## <a name="creating-a-richtextbox"></a>Erstellen eines RichTextBox-Steuerelements  
 Der folgende Code veranschaulicht das Erstellen einer <xref:System.Windows.Controls.RichTextBox> , dass ein Benutzer mit umfangreichen Inhalt bearbeiten kann.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 Insbesondere der Inhalt weder bearbeitet, einem <xref:System.Windows.Controls.RichTextBox> fortlaufendem Inhalt ist. Fortlaufender Inhalt kann viele Arten von Elementen enthalten, darunter formatierten Text, Bilder, Listen und Tabellen. Ausführliche Informationen zu Flussdokumenten finden Sie unter [Übersicht über Flussdokumente](./../../../docs/framework/wpf/advanced/flow-document-overview.md). Um fortlaufendem Inhalt enthalten eine <xref:System.Windows.Controls.RichTextBox> Hosts eine <xref:System.Windows.Documents.FlowDocument> Objekt, das wiederum den bearbeitbaren Inhalt enthält. Zur Veranschaulichung der Funktion fortlaufendem Inhalt in einen <xref:System.Windows.Controls.RichTextBox>, der folgende Code zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.RichTextBox> mit einem Absatz und Text in Fettdruck angezeigt.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![RichTextBox mit Inhalt](./../../../docs/framework/wpf/controls/media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")  
  
 Elemente wie <xref:System.Windows.Documents.Paragraph> und <xref:System.Windows.Documents.Bold> zu bestimmen wie die Inhalte innerhalb einer <xref:System.Windows.Controls.RichTextBox> angezeigt wird. Wenn ein Benutzer bearbeitet <xref:System.Windows.Controls.RichTextBox> Inhalt aus, ändern sie diese fortlaufendem Inhalt. Weitere Informationen über die Funktionen von fortlaufendem Inhalt und das Arbeiten damit finden Sie unter [Übersicht über Flussdokumente](./../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
 **Hinweis:** fortlaufende Inhalte innerhalb einer <xref:System.Windows.Controls.RichTextBox> verhält sich nicht genau wie bei anderen Steuerelementen enthaltener Flow-Inhalt. Beispielsweise, sind keine Spalten in einem <xref:System.Windows.Controls.RichTextBox> und daher keine automatische Größenanpassungsverhalten. Auch die integrierten Funktionen wie suchen, Anzeigemodus Seitennavigation und Zoom nicht innerhalb einer <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="realtime_spellechecking"></a>   
## <a name="real-time-spell-checking"></a>Rechtschreibprüfung in Echtzeit  
 Sie können die Rechtschreibprüfung in Echtzeit in ein <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox>. Wenn die Rechtschreibprüfung aktiviert ist, wird eine rote Linie unter falsch geschriebenen Wörtern angezeigt (siehe Abbildung unten).  
  
 ![TextBox mit Rechtschreibprüfung](./../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Wie Sie die Rechtschreibprüfung aktivieren, erfahren Sie unter [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](./../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
<a name="context_menu"></a>   
## <a name="context-menu"></a>Kontextmenü  
 Standardmäßig sowohl <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.RichTextBox> haben Sie ein Kontextmenü, das angezeigt wird, wenn ein Benutzer auf das Steuerelement klickt. Das Kontextmenü ermöglicht dem Benutzer das Ausschneiden, Kopieren und Einfügen (siehe Abbildung unten).  
  
 ![TextBox mit Kontextmenü](./../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Sie können Ihr eigenes benutzerdefiniertes Kontextmenü erstellen, um den Standard zu überschreiben. Weitere Informationen finden Sie unter [Positionieren eines benutzerdefinierten Kontextmenüs in einem „RichTextBox“-Element](./../../../docs/framework/wpf/controls/how-to-position-a-custom-context-menu-in-a-richtextbox.md).  
  
<a name="detect_when_content_changes"></a>   
## <a name="editing-commands"></a>Bearbeitungsbefehle  
 Bearbeitungsbefehle ermöglichen es Benutzern, formatieren Sie bearbeitbaren Inhalt in einem <xref:System.Windows.Controls.RichTextBox>. Neben dem Basic Bearbeitungsbefehle <xref:System.Windows.Controls.RichTextBox> enthält Formatierung-Befehle, <xref:System.Windows.Controls.TextBox> nicht unterstützt. Beispielsweise, wenn in Bearbeitung einer <xref:System.Windows.Controls.RichTextBox>, ein Benutzer konnten drücken STRG + B, um Text fett formatieren umzuschalten. Finden Sie unter <xref:System.Windows.Documents.EditingCommands> für eine vollständige Liste der verfügbaren Befehle. Zusätzlich zu Tastenkombinationen können Sie Befehle mit anderen Steuerelementen wie Schaltflächen verknüpfen. Im folgenden Beispiel wird veranschaulicht, wie eine einfache Symbolleiste mit Schaltflächen erstellt wird, mit denen der Benutzer die Textformatierung ändern kann.  
  
 [!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel angezeigt wird.  
  
 ![RichTextBox mit ToolBar](./../../../docs/framework/wpf/controls/media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Erkennen, wenn Inhalt geändert wird  
 In der Regel die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Ereignis sollte ermitteln, wann verwendet werden der Text in eine <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox> ändert vielmehr <xref:System.Windows.UIElement.KeyDown> wie zu erwarten. Ein Beispiel finden Sie unter [Erkennen von Änderungen an Text in einem Textfeld](./../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## <a name="save-load-and-print-richtextbox-content"></a>Speichern, Laden und Drucken von RichTextBox-Inhalt  
 Im folgende Beispiel wird gezeigt, wie zum Speichern des Inhalts einer <xref:System.Windows.Controls.RichTextBox> in eine Datei zu laden, den Inhalt dann wieder in den <xref:System.Windows.Controls.RichTextBox>, und Drucken des Inhalts. Im Folgenden sehen Sie das Markup für das Beispiel.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 Im Folgenden sehen Sie den Code für das Beispiel.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Themen zur Vorgehensweise](./../../../docs/framework/wpf/controls/richtextbox-how-to-topics.md)  
 [Übersicht über TextBox](./../../../docs/framework/wpf/controls/textbox-overview.md)
