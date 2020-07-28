---
title: Übersicht über RichTextBox
description: Erfahren Sie, wie das Windows Presentation Foundation RichTextBox-Steuerelement Benutzern das Anzeigen oder Bearbeiten von Inhalten wie Text, Bildern und Tabellen ermöglicht. Weitere Informationen finden Sie unter XAML und c#-Beispiele.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: 525e27f9602136c68f160c738fd1c92ea761536c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166239"
---
# <a name="richtextbox-overview"></a>Übersicht über RichTextBox

Das- <xref:System.Windows.Controls.RichTextBox> Steuerelement ermöglicht es Ihnen, fortlaufenden Inhalt einschließlich Absätzen, Bilder, Tabellen usw. anzuzeigen oder zu bearbeiten. Dieses Thema <xref:System.Windows.Controls.TextBox> enthält eine Einführung in die-Klasse und bietet Beispiele für die Verwendung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und c#.

<a name="textbox_or_richtextbox"></a>

## <a name="textbox-or-richtextbox"></a>TextBox oder RichTextBox?

Sowohl <xref:System.Windows.Controls.RichTextBox> als auch <xref:System.Windows.Controls.TextBox> ermöglichen es Benutzern, Text zu bearbeiten. die beiden Steuerelemente werden jedoch in verschiedenen Szenarien verwendet. Eine <xref:System.Windows.Controls.RichTextBox> ist eine bessere Wahl, wenn der Benutzer formatierten Text, Bilder, Tabellen oder andere Rich-Inhalte bearbeiten muss. Beispielsweise wird das Bearbeiten eines Dokuments, Artikels oder Blogs, das Formatierungen, Bilder usw. erfordert, am besten mit einem erreicht <xref:System.Windows.Controls.RichTextBox> . Ein <xref:System.Windows.Controls.TextBox> benötigt weniger Systemressourcen als eine <xref:System.Windows.Controls.RichTextBox> und ist ideal, wenn nur nur-Text bearbeitet werden muss (d. h. die Verwendung in Formularen). Weitere Informationen zu finden Sie unter [Übersicht über TextBox](textbox-overview.md) <xref:System.Windows.Controls.TextBox> . In der folgenden Tabelle werden die Hauptfunktionen von und zusammengefasst <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> .

|Control|Rechtschreibprüfung in Echtzeit|Kontextmenü|Formatieren von Befehlen wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTR + B)|<xref:System.Windows.Documents.FlowDocument>Inhalt wie Bilder, Absätze, Tabellen usw.|
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<xref:System.Windows.Controls.TextBox>|Ja|Ja|Nein|Nein.|
|<xref:System.Windows.Controls.RichTextBox>|Ja|Ja|Ja|Ja|

> [!NOTE]
> Obwohl <xref:System.Windows.Controls.TextBox> das Formatieren von zugehörigen Befehlen wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTR + B) nicht unterstützt, werden viele grundlegende Befehle von beiden Steuerelementen wie unterstützt <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A> .

Die Funktionen aus der obigen Tabelle werden später ausführlicher behandelt.

<a name="creating_a_richtextbox"></a>

## <a name="creating-a-richtextbox"></a>Erstellen eines RichTextBox-Steuerelements

Der folgende Code zeigt, wie ein erstellt wird <xref:System.Windows.Controls.RichTextBox> , in dem ein Benutzer Rich-Content bearbeiten kann.

[!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]

Insbesondere ist der Inhalt, der in einem bearbeitet wird, der fortlaufende <xref:System.Windows.Controls.RichTextBox> Inhalt. Fortlaufender Inhalt kann viele Arten von Elementen enthalten, darunter formatierten Text, Bilder, Listen und Tabellen. Ausführliche Informationen zu Flussdokumenten finden Sie unter [Übersicht über Flussdokumente](../advanced/flow-document-overview.md). Um fortlaufenden Inhalt zu enthalten, <xref:System.Windows.Controls.RichTextBox> hostet ein- <xref:System.Windows.Documents.FlowDocument> Objekt, das wiederum den bearbeitbaren Inhalt enthält. Zum Veranschaulichen von fortlaufendem Inhalt in einem <xref:System.Windows.Controls.RichTextBox> zeigt der folgende Code, wie ein <xref:System.Windows.Controls.RichTextBox> mit einem Absatz und einem fett formatierten Text erstellt wird.

[!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]

[!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
[!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]

Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.

![RichTextBox mit Inhalt](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")

Elemente wie <xref:System.Windows.Documents.Paragraph> und <xref:System.Windows.Documents.Bold> bestimmen, wie der Inhalt in einer <xref:System.Windows.Controls.RichTextBox> angezeigt wird. Wenn ein Benutzer Inhalt bearbeitet <xref:System.Windows.Controls.RichTextBox> , ändert er diesen fortlaufenden Inhalt. Weitere Informationen über die Funktionen von fortlaufendem Inhalt und das Arbeiten damit finden Sie unter [Übersicht über Flussdokumente](../advanced/flow-document-overview.md).

> [!NOTE]
> Fortlaufendem Inhalt in einem <xref:System.Windows.Controls.RichTextBox> verhält sich nicht genau wie fortlaufenden Inhalt in anderen Steuerelementen. Beispielsweise gibt es keine Spalten in einem <xref:System.Windows.Controls.RichTextBox> und somit kein automatisches Verhalten bei der Änderung der Größe. Außerdem sind integrierte Features wie suchen, Anzeigemodus, Seitennavigation und Zoom nicht in verfügbar <xref:System.Windows.Controls.RichTextBox> .

<a name="realtime_spellechecking"></a>

## <a name="real-time-spell-checking"></a>Rechtschreibprüfung in Echtzeit

Sie können die Rechtschreibprüfung in Echtzeit in oder aktivieren <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> . Wenn die Rechtschreibprüfung aktiviert ist, wird eine rote Linie unter falsch geschriebenen Wörtern angezeigt (siehe Abbildung unten).

![TextBox mit Rechtschreib&#45;Überprüfung](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")

Wie Sie die Rechtschreibprüfung aktivieren, erfahren Sie unter [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](how-to-enable-spell-checking-in-a-text-editing-control.md).

<a name="context_menu"></a>

## <a name="context-menu"></a>Kontextmenü

Standardmäßig verfügen sowohl <xref:System.Windows.Controls.TextBox> als auch <xref:System.Windows.Controls.RichTextBox> über ein Kontextmenü, das angezeigt wird, wenn ein Benutzer mit der rechten Maustaste auf das Steuerelement klickt. Das Kontextmenü ermöglicht dem Benutzer das Ausschneiden, Kopieren und Einfügen (siehe Abbildung unten).

![TextBox mit Kontextmenü](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")

Sie können Ihr eigenes benutzerdefiniertes Kontextmenü erstellen, um den Standard zu überschreiben. Weitere Informationen finden Sie unter [Positionieren eines benutzerdefinierten Kontextmenüs in einem „RichTextBox“-Element](how-to-position-a-custom-context-menu-in-a-richtextbox.md).

<a name="detect_when_content_changes"></a>

## <a name="editing-commands"></a>Bearbeitungsbefehle

Bearbeitungsbefehle ermöglichen es Benutzern, bearbeitbaren Inhalt in einem zu formatieren <xref:System.Windows.Controls.RichTextBox> . Neben grundlegenden Bearbeitungs Befehlen <xref:System.Windows.Controls.RichTextBox> schließt Formatierungsbefehle ein, die von <xref:System.Windows.Controls.TextBox> nicht unterstützt werden. Wenn z <xref:System.Windows.Controls.RichTextBox> . B. in einem bearbeitet wird, könnte ein Benutzer CTR + B drücken, um die Fett formatierte Textformatierung zu ändern. <xref:System.Windows.Documents.EditingCommands>Eine komplette Liste der verfügbaren Befehle finden Sie unter. Zusätzlich zu Tastenkombinationen können Sie Befehle mit anderen Steuerelementen wie Schaltflächen verknüpfen. Im folgenden Beispiel wird veranschaulicht, wie eine einfache Symbolleiste mit Schaltflächen erstellt wird, mit denen der Benutzer die Textformatierung ändern kann.

[!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]

Die folgende Abbildung zeigt, wie dieses Beispiel angezeigt wird.

![RichTextBox mit ToolBar](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")

<a name="editing_commands"></a>

## <a name="detect-when-content-changes"></a>Erkennen, wenn Inhalt geändert wird

In der Regel sollte das- <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Ereignis verwendet werden, um zu erkennen, wann immer der Text in einer-oder-Datei <xref:System.Windows.Controls.TextBox> geändert wird <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.UIElement.KeyDown> . Ein Beispiel finden Sie unter [Erkennen von Änderungen an Text in einem Textfeld](how-to-detect-when-text-in-a-textbox-has-changed.md).

<a name="save_load_and_print_richtextbox_content"></a>

## <a name="save-load-and-print-richtextbox-content"></a>Speichern, Laden und Drucken von RichTextBox-Inhalt

Im folgenden Beispiel wird gezeigt, wie Inhalt eines <xref:System.Windows.Controls.RichTextBox> in einer Datei gespeichert, der Inhalt wieder in das geladen <xref:System.Windows.Controls.RichTextBox> und der Inhalt gedruckt wird. Im Folgenden sehen Sie das Markup für das Beispiel.

[!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]

Im Folgenden sehen Sie den Code für das Beispiel.

[!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
[!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]

## <a name="see-also"></a>Siehe auch

- [Artikel zu Vorgehensweisen](richtextbox-how-to-topics.md)
- [Übersicht über TextBox](textbox-overview.md)
