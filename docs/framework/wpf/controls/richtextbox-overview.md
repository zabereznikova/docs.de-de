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
ms.openlocfilehash: bfed42bcf3693ef744b3ed2b54ebe070931513a9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855734"
---
# <a name="richtextbox-overview"></a>Übersicht über RichTextBox

Das <xref:System.Windows.Controls.RichTextBox> -Steuerelement ermöglicht es Ihnen, fortlaufenden Inhalt einschließlich Absätzen, Bilder, Tabellen usw. anzuzeigen oder zu bearbeiten. In diesem Thema wird <xref:System.Windows.Controls.TextBox> die-Klasse vorgestellt, und es werden Beispiele für die Verwendung C#in und bereitstellt. [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]

<a name="textbox_or_richtextbox"></a>

## <a name="textbox-or-richtextbox"></a>TextBox oder RichTextBox?

Sowohl <xref:System.Windows.Controls.RichTextBox> als <xref:System.Windows.Controls.TextBox> auch ermöglichen es Benutzern, Text zu bearbeiten. die beiden Steuerelemente werden jedoch in verschiedenen Szenarien verwendet. Eine <xref:System.Windows.Controls.RichTextBox> ist eine bessere Wahl, wenn der Benutzer formatierten Text, Bilder, Tabellen oder andere Rich-Inhalte bearbeiten muss. Beispielsweise wird das Bearbeiten eines Dokuments, Artikels oder Blogs, das Formatierungen, Bilder usw. erfordert, am besten <xref:System.Windows.Controls.RichTextBox>mit einem erreicht. Ein <xref:System.Windows.Controls.TextBox> benötigt weniger Systemressourcen als eine <xref:System.Windows.Controls.RichTextBox> und ist ideal, wenn nur nur-Text bearbeitet werden muss (d. h. die Verwendung in Formularen). Weitere Informationen zu finden Sie unter Übersicht über <xref:System.Windows.Controls.TextBox> [TextBox](textbox-overview.md) . In der folgenden Tabelle werden die Hauptfunktionen <xref:System.Windows.Controls.TextBox> von <xref:System.Windows.Controls.RichTextBox>und zusammengefasst.

|Steuerelement|Rechtschreibprüfung in Echtzeit|Kontextmenü|Formatieren von <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> Befehlen wie (CTR + B)|<xref:System.Windows.Documents.FlowDocument>Inhalt wie Bilder, Absätze, Tabellen usw.|
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<xref:System.Windows.Controls.TextBox>|Ja|Ja|Nein|Nein.|
|<xref:System.Windows.Controls.RichTextBox>|Ja|Ja|Ja|Ja|

> [!NOTE]
> Obwohl <xref:System.Windows.Controls.TextBox> das Formatieren von zugehörigen Befehlen wie <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTR + B) nicht unterstützt, werden viele grundlegende Befehle <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>von beiden Steuerelementen wie unterstützt.

Die Funktionen aus der obigen Tabelle werden später ausführlicher behandelt.

<a name="creating_a_richtextbox"></a>

## <a name="creating-a-richtextbox"></a>Erstellen eines RichTextBox-Steuerelements

Der folgende Code zeigt, wie ein <xref:System.Windows.Controls.RichTextBox> erstellt wird, in dem ein Benutzer Rich-Content bearbeiten kann.

[!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]

Insbesondere ist der Inhalt, der in <xref:System.Windows.Controls.RichTextBox> einem bearbeitet wird, der fortlaufende Inhalt. Fortlaufender Inhalt kann viele Arten von Elementen enthalten, darunter formatierten Text, Bilder, Listen und Tabellen. Ausführliche Informationen zu Flussdokumenten finden Sie unter [Übersicht über Flussdokumente](../advanced/flow-document-overview.md). Um fortlaufenden Inhalt zu enthalten, <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Documents.FlowDocument> hostet ein-Objekt, das wiederum den bearbeitbaren Inhalt enthält. Zum Veranschaulichen von fortlaufendem <xref:System.Windows.Controls.RichTextBox>Inhalt in einem zeigt der folgende Code, wie <xref:System.Windows.Controls.RichTextBox> ein mit einem Absatz und einem fett formatierten Text erstellt wird.

[!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]

[!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
[!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]

Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.

![RichTextBox mit Inhalt](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")

Elemente wie <xref:System.Windows.Documents.Paragraph> und <xref:System.Windows.Documents.Bold> bestimmen, wie der Inhalt in <xref:System.Windows.Controls.RichTextBox> einer angezeigt wird. Wenn ein Benutzer <xref:System.Windows.Controls.RichTextBox> Inhalt bearbeitet, ändert er diesen fortlaufenden Inhalt. Weitere Informationen über die Funktionen von fortlaufendem Inhalt und das Arbeiten damit finden Sie unter [Übersicht über Flussdokumente](../advanced/flow-document-overview.md).

> [!NOTE]
> Fortlaufendem Inhalt <xref:System.Windows.Controls.RichTextBox> in einem verhält sich nicht genau wie fortlaufenden Inhalt in anderen Steuerelementen. Beispielsweise gibt es keine Spalten in einem <xref:System.Windows.Controls.RichTextBox> und somit kein automatisches Verhalten bei der Änderung der Größe. Außerdem sind integrierte Features wie suchen, Anzeigemodus, Seitennavigation und Zoom nicht in <xref:System.Windows.Controls.RichTextBox>verfügbar.

<a name="realtime_spellechecking"></a>

## <a name="real-time-spell-checking"></a>Rechtschreibprüfung in Echtzeit

Sie können die Rechtschreibprüfung in Echtzeit in <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox>aktivieren. Wenn die Rechtschreibprüfung aktiviert ist, wird eine rote Linie unter falsch geschriebenen Wörtern angezeigt (siehe Abbildung unten).

![TextBox mit Rechtschreibprüfung](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")

Wie Sie die Rechtschreibprüfung aktivieren, erfahren Sie unter [Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement](how-to-enable-spell-checking-in-a-text-editing-control.md).

<a name="context_menu"></a>

## <a name="context-menu"></a>Kontextmenü

Standardmäßig verfügen sowohl <xref:System.Windows.Controls.TextBox> als <xref:System.Windows.Controls.RichTextBox> auch über ein Kontextmenü, das angezeigt wird, wenn ein Benutzer mit der rechten Maustaste auf das Steuerelement klickt. Das Kontextmenü ermöglicht dem Benutzer das Ausschneiden, Kopieren und Einfügen (siehe Abbildung unten).

![TextBox mit Kontextmenü](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")

Sie können Ihr eigenes benutzerdefiniertes Kontextmenü erstellen, um den Standard zu überschreiben. Weitere Informationen finden Sie unter [Positionieren eines benutzerdefinierten Kontextmenüs in einem „RichTextBox“-Element](how-to-position-a-custom-context-menu-in-a-richtextbox.md).

<a name="detect_when_content_changes"></a>

## <a name="editing-commands"></a>Bearbeitungsbefehle

Bearbeitungsbefehle ermöglichen es Benutzern, bearbeitbaren Inhalt in <xref:System.Windows.Controls.RichTextBox>einem zu formatieren. Neben grundlegenden Bearbeitungs Befehlen <xref:System.Windows.Controls.RichTextBox> schließt Formatierungsbefehle <xref:System.Windows.Controls.TextBox> ein, die von nicht unterstützt werden. Wenn z. B. in einem <xref:System.Windows.Controls.RichTextBox>bearbeitet wird, könnte ein Benutzer CTR + B drücken, um die Fett formatierte Textformatierung zu ändern. Eine <xref:System.Windows.Documents.EditingCommands> komplette Liste der verfügbaren Befehle finden Sie unter. Zusätzlich zu Tastenkombinationen können Sie Befehle mit anderen Steuerelementen wie Schaltflächen verknüpfen. Im folgenden Beispiel wird veranschaulicht, wie eine einfache Symbolleiste mit Schaltflächen erstellt wird, mit denen der Benutzer die Textformatierung ändern kann.

[!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]

Die folgende Abbildung zeigt, wie dieses Beispiel angezeigt wird.

![RichTextBox mit ToolBar](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")

<a name="editing_commands"></a>

## <a name="detect-when-content-changes"></a>Erkennen, wenn Inhalt geändert wird

In der <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Regel sollte das-Ereignis verwendet werden, um zu erkennen <xref:System.Windows.Controls.TextBox> , wann immer der <xref:System.Windows.UIElement.KeyDown> Text in einer-oder <xref:System.Windows.Controls.RichTextBox> -Datei geändert wird. Ein Beispiel finden Sie unter [Erkennen von Änderungen an Text in einem Textfeld](how-to-detect-when-text-in-a-textbox-has-changed.md).

<a name="save_load_and_print_richtextbox_content"></a>

## <a name="save-load-and-print-richtextbox-content"></a>Speichern, Laden und Drucken von RichTextBox-Inhalt

Im folgenden Beispiel wird gezeigt, wie Inhalt <xref:System.Windows.Controls.RichTextBox> eines in einer Datei gespeichert, der Inhalt wieder in das <xref:System.Windows.Controls.RichTextBox>geladen und der Inhalt gedruckt wird. Im Folgenden sehen Sie das Markup für das Beispiel.

[!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]

Im Folgenden sehen Sie den Code für das Beispiel.

[!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
[!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]

## <a name="see-also"></a>Siehe auch

- [Themen zu Vorgehensweisen](richtextbox-how-to-topics.md)
- [Übersicht über TextBox](textbox-overview.md)
