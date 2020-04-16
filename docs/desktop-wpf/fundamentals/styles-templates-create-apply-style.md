---
title: Erstellen eines Stils für ein Steuerelement
description: Erfahren Sie, wie Sie einen Steuerelementstil in Windows Presentation Foundation und .NET Core erstellen und darauf verweisen.
author: thraka
ms.author: adegeo
ms.date: 09/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: 2956dbf93a1d34feca31d3ab10536f5089010189
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "81432557"
---
# <a name="create-a-style-for-a-control-in-wpf"></a>Erstellen eines Stils für ein Steuerelement in WPF

Mit Windows Presentation Foundation (WPF) können Sie das Erscheinungsbild eines vorhandenen Steuerelements mit einem eigenen wiederverwendbaren Stil anpassen. Formatvorlagen können global auf Ihre App, Fenster und Seiten oder direkt auf Steuerelemente angewendet werden.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="create-a-style"></a>Erstellen eines Stils

Sie können sich <xref:System.Windows.Style> eine als bequeme Möglichkeit vorstellen, einen Satz von Eigenschaftswerten auf ein oder mehrere Elemente anzuwenden. Sie können einen Stil für jedes Element <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> verwenden, <xref:System.Windows.Window> das <xref:System.Windows.Controls.Button>von oder von einem oder einem abgeleitet wird.

Die häufigste Möglichkeit zum Deklarieren eines `Resources` Stils ist als Ressource im Abschnitt in einer XAML-Datei. Da Stile Ressourcen sind, befolgen sie die gleichen Bereichsregeln, die für alle Ressourcen gelten. Einfach ausgedrückt, wobei Sie einen Stil deklarieren, wirkt sich darauf aus, wo der Stil angewendet werden kann. Wenn Sie beispielsweise den Stil im Stammelement Ihrer App-Definitions-XAML-Datei deklarieren, kann der Stil an beliebiger Stelle in ihrer App verwendet werden.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/App.xaml#AppResources)]

Wenn Sie den Stil in einer der XAML-Dateien der App deklarieren, kann der Stil nur in dieser XAML-Datei verwendet werden. Weitere Informationen zu Bereichsregeln für Ressourcen finden Sie unter [XAML-Ressourcen](xaml-resources-define.md).

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowSingleResource.xaml#WindowResources)]

Ein Stil besteht `<Setter>` aus untergeordneten Elementen, die Eigenschaften für die Elemente festlegen, auf die der Stil angewendet wird. Beachten Sie im obigen Beispiel, dass `TextBlock` der Stil `TargetType` so eingestellt ist, dass er auf Typen über das Attribut angewendet wird. Der Stil setzt <xref:System.Windows.Controls.Control.FontSize%2A> `15` die <xref:System.Windows.Controls.Control.FontWeight%2A> Einstellung `ExtraBold`bis und die an . Fügen `<Setter>` Sie für jede Eigenschaft eine hinzu, die sich durch den Stil ändert.

## <a name="apply-a-style-implicitly"></a>Anwenden eines Stils implizit

A <xref:System.Windows.Style> ist eine bequeme Möglichkeit, einen Satz von Eigenschaftswerten auf mehr als ein Element anzuwenden. Betrachten Sie beispielsweise <xref:System.Windows.Controls.TextBlock> die folgenden Elemente und ihre Standarddarstellung in einem Fenster.

[!code-xaml[TextBlocks](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetTextBlocks)]

![Styling-Beispiel-Screenshot](./media/styles-and-templates-overview/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")

Sie können die Standarddarstellung ändern, <xref:System.Windows.Controls.Control.FontSize%2A> indem <xref:System.Windows.Controls.Control.FontFamily%2A>Sie <xref:System.Windows.Controls.TextBlock> Eigenschaften wie und für jedes Element direkt festlegen. Wenn Sie jedoch <xref:System.Windows.Controls.TextBlock> möchten, dass Ihre Elemente einige <xref:System.Windows.Style> Eigenschaften `Resources` gemeinsam nutzen, können Sie im Abschnitt der XAML-Datei eine erstellen, wie hier gezeigt.

[!code-xaml[DefaultTextBlockStyle](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetDefaultTextBlockStyle)]

Wenn Sie <xref:System.Windows.Style.TargetType%2A> den Stil des <xref:System.Windows.Controls.TextBlock> Stils auf `x:Key` den Typ festlegen und <xref:System.Windows.Controls.TextBlock> das Attribut weglassen, wird der Stil auf alle Elemente angewendet, die auf den Stil beschränkt sind, der im Allgemeinen die XAML-Datei selbst ist.

Nun <xref:System.Windows.Controls.TextBlock> werden die Elemente wie folgt angezeigt.

![Styling-Beispiel-Screenshot](./media/styles-and-templates-overview/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")

## <a name="apply-a-style-explicitly"></a>Anwenden eines Stils explizit

Wenn Sie `x:Key` der Formatvorlage ein Attribut mit Wert hinzufügen, wird der <xref:System.Windows.Style.TargetType%2A>Stil nicht mehr implizit auf alle Elemente von angewendet. Nur Elemente, die explizit auf den Stil verweisen, werden auf den Stil angewendet.

Hier ist der Stil aus dem vorherigen `x:Key` Abschnitt, der jedoch mit dem Attribut deklariert wurde.

[!code-xaml[ExplicitStyleDeclare](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleDeclare)]

Um den Stil anzuwenden, legen Sie <xref:System.Windows.FrameworkElement.Style%2A> `x:Key` die Eigenschaft für das Element auf den Wert fest, indem Sie eine [StaticResource-Markuperweiterung](../../framework/wpf/advanced/staticresource-markup-extension.md)verwenden, wie hier gezeigt.

[!code-xaml[ExplicitStyleReference](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleReference)]

Beachten Sie, <xref:System.Windows.Controls.TextBlock> dass für das erste Element die Formatvorlage angewendet wird, während das zweite TextBlock-Element unverändert bleibt. Der implizite Stil aus dem vorherigen Abschnitt `x:Key` wurde in einen Stil geändert, der das Attribut deklariert hat, was bedeutet, dass das einzige Element, das von der Formatvorlage betroffen ist, das Element ist, das direkt auf den Stil verweist.

![Styling-Beispiel-Screenshot](./media/styles-and-templates-overview/create-a-style-explicit-textblock.png "create-a-style-explicit-textblock")

Sobald ein Stil explizit oder implizit angewendet wird, wird er versiegelt und kann nicht mehr geändert werden. Wenn Sie einen angewendeten Stil ändern möchten, erstellen Sie einen neuen Stil, um den vorhandenen stilgleich zu ersetzen. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Style.IsSealed%2A>-Eigenschaft.

Sie können ein Objekt erstellen, das einen Stil auf Grundlage einer benutzerdefinierten Logik auswählt. Ein Beispiel finden Sie im <xref:System.Windows.Controls.StyleSelector> Beispiel für die Klasse.

## <a name="apply-a-style-programmatically"></a>Programmgesteuert anwenden

Um einem Element programmgesteuert einen benannten Stil zuzuweisen, rufen Sie den Stil <xref:System.Windows.FrameworkElement.Style%2A> aus der Ressourcenauflistung ab, und weisen Sie ihn der Eigenschaft des Elements zu. Die Elemente in einer Ressourcenauflistung sind vom Typ <xref:System.Object>. Daher müssen Sie den abgerufenen <xref:System.Windows.Style?displayProperty=fullName> Stil in eine `Style` umwerfen, bevor Sie ihn der Eigenschaft zuweisen. Der folgende Code legt z. `TextBlock` B. den Stil eines benannten `textblock1` auf den definierten Stil `TitleText`fest.

[!code-csharp[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml.cs#SnippetSetStyleCode)]
[!code-vb[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/MainWindow.xaml.vb#SnippetSetStyleCode)]

## <a name="extend-a-style"></a>Erweitern eines Stils

Vielleicht möchten Sie, dass Ihre beiden <xref:System.Windows.Controls.TextBlock> Elemente <xref:System.Windows.Controls.Control.FontFamily%2A> einige Eigenschaftswerte gemeinsam nutzen, z. B. die und die zentrierte <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>. Sie möchten jedoch auch, dass der Text **"Meine Bilder"** einige zusätzliche Eigenschaften enthält. Sie können dies tun, indem Sie einen neuen Stil erstellen, der auf dem ersten Stil basiert, wie hier gezeigt.

[!code-xaml[DefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

[!code-xaml[TextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

Dieser `TextBlock` Stil ist nun zentriert, verwendet `Comic Sans MS` eine `26`Schriftart mit der <xref:System.Windows.Media.LinearGradientBrush> Größe von , und die Vordergrundfarbe wird auf die im Beispiel gezeigte festgelegt. Beachten Sie, dass <xref:System.Windows.Controls.Control.FontSize%2A> der Wert des Basisstils überschrieben wird. Wenn mehr als eine <xref:System.Windows.Setter> Eigenschaft auf dieselbe <xref:System.Windows.Style>Eigenschaft `Setter` in einem verweist, hat die, die als letzte deklariert wird, Vorrang.

Im Folgenden wird <xref:System.Windows.Controls.TextBlock> gezeigt, wie die Elemente jetzt aussehen:

![Formatierte TextBlocks](./media/styles-and-templates-overview/stylingintro-textblocks.png "StylingIntro_TextBlocks")

Dieser `TitleText` Stil erweitert den Stil, der <xref:System.Windows.Controls.TextBlock> für den `BasedOn="{StaticResource {x:Type TextBlock}}"`Typ erstellt wurde und auf den mit verwiesen wird. Sie können auch einen Stil `x:Key` erweitern, `x:Key` der über einen Stil verfügt, indem Sie den Stil verwenden. Wenn z. B. ein `Header1` Stil mit dem Namen vorhanden `BasedOn="{StaticResource Header1}"`ist und Sie diesen Stil erweitern möchten, verwenden Sie .

## <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Beziehung zwischen der TargetType-Eigenschaft und dem x:Key-Attribut

Wie bereits gezeigt, <xref:System.Windows.Style.TargetType%2A> führt `TextBlock` das Festlegen der `x:Key` Eigenschaft zu , ohne <xref:System.Windows.Controls.TextBlock> den Stil an zuzuweisen, dazu, dass der Stil auf alle Elemente angewendet wird. In diesem Fall wird `x:Key` implizit auf `{x:Type TextBlock}` festgelegt. Dies bedeutet, dass, `x:Key` wenn Sie `{x:Type TextBlock}`den <xref:System.Windows.Style> Wert explizit auf etwas `TextBlock` anderes als festlegen, der nicht automatisch auf alle Elemente angewendet wird. Stattdessen müssen Sie den Stil (mit dem `x:Key` `TextBlock` Wert) explizit auf die Elemente anwenden. Wenn sich Ihr Stil im Ressourcenabschnitt befindet `TargetType` und Sie die Eigenschaft nicht `x:Key` für Ihren Stil festlegen, müssen Sie das Attribut festlegen.

Zusätzlich zur Angabe eines Standardwerts für die `x:Key`gibt die `TargetType` Eigenschaft den Typ an, auf den Settereigenschaften angewendet werden. Wenn Sie keine `TargetType`angeben, müssen Sie die <xref:System.Windows.Setter> Eigenschaften in Ihren Objekten mit `Property="ClassName.Property"`einem Klassennamen mithilfe der Syntax qualifizieren. Anstatt z. `Property="FontSize"`B. festzulegen, <xref:System.Windows.Setter.Property%2A> `"TextBlock.FontSize"` müssen `"Control.FontSize"`Sie auf oder festlegen.

Beachten Sie außerdem, dass viele WPF-Steuerelemente aus einer Kombination anderer WPF-Steuerelemente bestehen. Wenn Sie einen Stil erstellen, das für alle Steuerelemente eines Typs gilt, erhalten Sie möglicherweise unerwartete Ergebnisse. Wenn Sie z. B. eine <xref:System.Windows.Controls.TextBlock> Formatvorlage <xref:System.Windows.Window>erstellen, die auf `TextBlock` den Typ in einem `TextBlock` abzielt, wird der Stil <xref:System.Windows.Controls.ListBox>auf alle Steuerelemente im Fenster angewendet, auch wenn der Teil eines anderen Steuerelements ist, z. B. einer .

## <a name="see-also"></a>Weitere Informationen

<!-- - [Create a style for a control](styles-templates-create-apply-template.md) -->
- [Überblick über XAML-Ressourcen](xaml-resources-define.md)
- [XAML-Übersicht (WPF & .NET Core)](xaml.md)
