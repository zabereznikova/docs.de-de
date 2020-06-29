---
title: Erstellen eines Stils für ein Steuerelement
description: In diesem Artikel erfahren Sie, wie Sie einen Stil für ein Steuerelement in Windows Presentation Foundation und .NET Core erstellen und darauf verweisen.
author: adegeo
ms.author: adegeo
ms.date: 09/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: de186cd6da83ffef8a5cd59df581e88b24bc474d
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325790"
---
# <a name="create-a-style-for-a-control-in-wpf"></a>Erstellen eines Stils für ein Steuerelement in WPF

Mit Windows Presentation Foundation (WPF) können Sie eigene, wiederverwendbare Stile für vorhandene Steuerelemente festlegen. Stile können global auf Apps, Fenster und Seiten oder direkt auf Steuerelemente angewendet werden.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="create-a-style"></a>Erstellen eines Stils

<xref:System.Windows.Style> ist eine einfache Möglichkeit, mehrere Eigenschaftswerte auf mindestens ein Element anzuwenden. Stile lassen sich auf alle Elemente anwenden, die von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitet sind, z. B. <xref:System.Windows.Window> oder <xref:System.Windows.Controls.Button>.

Stile werden üblicherweise deklariert, indem sie im Abschnitt `Resources` einer XML-Datei als Ressource deklariert werden. Da es sich bei Stilen um Ressourcen handelt, unterliegen sie denselben Regeln für Gültigkeitsbereiche, die für alle Ressourcen gelten. Einfach ausgedrückt: Wo Sie einen Stil deklarieren, bestimmt darüber, wo der Stil angewendet werden kann. Wenn Sie den Stil z. B. im Stammelement Ihrer XML-Datei mit der App-Definition deklarieren, kann der Stil überall in der App verwendet werden.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/App.xaml#AppResources)]

Wenn Sie den Stil in einer der XAML-Dateien der App deklarieren, ist der Anwendungsbereich des Stils nur auf diese XAML-Datei begrenzt. Weitere Informationen zu Bereichsregeln für Ressourcen finden Sie unter [XAML-Ressourcen](xaml-resources-define.md).

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowSingleResource.xaml#WindowResources)]

Ein Stil besteht aus untergeordneten `<Setter>`-Elementen, die Eigenschaften für die Elemente festlegen, auf die der Stil angewendet wurde. Beachten Sie im obigen Beispiel, dass der Stil so konfiguriert ist, dass er über das Attribut `TargetType` auf `TextBlock`-Typen angewendet wird. Der Stil legt <xref:System.Windows.Controls.Control.FontSize%2A> auf `15` und <xref:System.Windows.Controls.Control.FontWeight%2A> auf `ExtraBold` fest. Fügen Sie für jede Eigenschaft, die durch den Stil geändert wird, eine `<Setter>`-Eigenschaft hinzu.

## <a name="apply-a-style-implicitly"></a>Implizites Anwenden eines Stils

<xref:System.Windows.Style> ist eine einfache Möglichkeit, mehrere Eigenschaftswerte auf mehr als ein Element anzuwenden. Sehen Sie sich z. B. die folgenden <xref:System.Windows.Controls.TextBlock>-Elemente und deren Standarddarstellung in einem Fenster an:

[!code-xaml[TextBlocks](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetTextBlocks)]

![Screenshot: Stilbeispiel](./media/styles-and-templates-overview/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")

Sie können die Standarddarstellung ändern, indem Sie Eigenschaften wie <xref:System.Windows.Controls.Control.FontSize%2A> und <xref:System.Windows.Controls.Control.FontFamily%2A> für jedes <xref:System.Windows.Controls.TextBlock>-Element direkt festlegen. Wenn Ihre <xref:System.Windows.Controls.TextBlock>-Elemente jedoch über gewisse gemeinsame Eigenschaften verfügen sollen, können Sie im Abschnitt `Resources` der XAML-Datei ein <xref:System.Windows.Style>-Objekt erstellen. Im folgenden Codeausschnitt ist dies veranschaulicht.

[!code-xaml[DefaultTextBlockStyle](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetDefaultTextBlockStyle)]

Wenn Sie die Eigenschaft <xref:System.Windows.Style.TargetType%2A> Ihres Stils auf den Typ <xref:System.Windows.Controls.TextBlock> festlegen und das Attribut `x:Key` weglassen, wird der Stil auf alle <xref:System.Windows.Controls.TextBlock>-Elemente angewendet, für die der Stil gilt. Üblicherweise sind dies die Elemente in der XAML-Datei.

Nun werden die <xref:System.Windows.Controls.TextBlock>-Elemente wie folgt angezeigt.

![Screenshot: Stilbeispiel](./media/styles-and-templates-overview/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")

## <a name="apply-a-style-explicitly"></a>Explizites Anwenden eines Stils

Wenn Sie dem Stil ein `x:Key`-Attribut mit einem Wert hinzufügen, wird der Stil nicht mehr implizit auf die Elemente von <xref:System.Windows.Style.TargetType%2A> angewendet. Von nun gilt er nur noch für Elemente, die explizit auf den Stil verweisen.

Im folgenden Codeausschnitt wird der Stil aus dem vorherigen Abschnitt dargestellt, jedoch mit dem Attribut `x:Key` deklariert.

[!code-xaml[ExplicitStyleDeclare](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleDeclare)]

Legen Sie die Eigenschaft <xref:System.Windows.FrameworkElement.Style%2A> des Elements auf den Wert von `x:Key` fest, um den Stil anzuwenden. Verwenden Sie dazu wie im folgenden Codeausschnitt eine [StaticResource-Markuperweiterung](../../framework/wpf/advanced/staticresource-markup-extension.md).

[!code-xaml[ExplicitStyleReference](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleReference)]

Beachten Sie, dass der Stil auf das erste <xref:System.Windows.Controls.TextBlock>-Element angewendet wird, während das zweite TextBlock-Element unverändert bleibt. Der implizite Stil aus dem vorherigen Abschnitt wurde in einen Stil geändert, der durch das Attribut `x:Key` deklariert wird. Dies bedeutet, dass das einzige Element, für das der Stil gilt, dasjenige Element ist, das direkt auf den Stil verweist.

![Screenshot: Stilbeispiel](./media/styles-and-templates-overview/create-a-style-explicit-textblock.png "create-a-style-explicit-textblock")

Wenn ein Stil explizit oder implizit angewendet wird, wird er „versiegelt“ und kann nicht mehr geändert werden. Wenn Sie einen übernommenen Stil ändern möchten, müssen Sie einen neuen Stil erstellen oder den bestehenden ersetzen. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Style.IsSealed%2A>-Eigenschaft.

Sie können ein Objekt erstellen, das einen Stil auf Grundlage einer benutzerdefinierten Logik auswählt. Ein Beispiel finden Sie im Artikel zur Klasse <xref:System.Windows.Controls.StyleSelector>.

## <a name="apply-a-style-programmatically"></a>Programmgesteuertes Anwenden eines Stils

Rufen Sie den Stil aus der Ressourcenauflistung ab, und weisen Sie ihn der <xref:System.Windows.FrameworkElement.Style%2A>-Eigenschaft des Elements zu, um einem Element programmgesteuert einen bestimmten Stil zuzuweisen. Die Elemente in einer Ressourcenauflistung gehören zum Typ <xref:System.Object>. Daher müssen Sie den abgerufenen Stil in ein <xref:System.Windows.Style?displayProperty=fullName>-Element umwandeln, bevor Sie ihn der Eigenschaft `Style` zuweisen können. Im folgenden Code wird z. B. der Stil eines `TextBlock`-Elements namens `textblock1` auf den definierten Stil `TitleText` festgelegt.

[!code-csharp[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml.cs#SnippetSetStyleCode)]
[!code-vb[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/MainWindow.xaml.vb#SnippetSetStyleCode)]

## <a name="extend-a-style"></a>Erweitern eines Stils

In manchen Situationen ist es erforderlich, dass Ihre beiden <xref:System.Windows.Controls.TextBlock>-Elemente gewisse Eigenschaftswerte gemeinsam haben, z. B. <xref:System.Windows.Controls.Control.FontFamily%2A> und <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> (zentriert). Sie möchten jedoch auch, dass der Text **My Pictures** (Meine Bilder) einige zusätzliche Eigenschaften hat. Erstellen Sie in diesem Fall einen neuen Stil, der auf dem ersten Stil basiert. Wie das funktioniert, wird im folgenden Codeausschnitt gezeigt.

[!code-xaml[DefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

[!code-xaml[TextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

Dieser `TextBlock`-Stil ist nun zentriert und verwendet eine `Comic Sans MS`-Schriftart mit einer Größe von `26`. Außerdem wird die Vordergrundfarbe, die auf <xref:System.Windows.Media.LinearGradientBrush> festgelegt ist, im Beispiel angezeigt. Beachten Sie, dass der <xref:System.Windows.Controls.Control.FontSize%2A>-Wert des zugrunde liegenden Stils überschrieben wird. Wenn mehr als ein <xref:System.Windows.Setter>-Objekt in einem <xref:System.Windows.Style>-Objekt auf dieselbe Eigenschaft verweist, hat das zuletzt deklarierte `Setter`-Objekt Vorrang.

Im folgenden Screenshot wird gezeigt, wie die <xref:System.Windows.Controls.TextBlock>-Elemente nun aussehen:

![Formatierte TextBlocks](./media/styles-and-templates-overview/stylingintro-textblocks.png "StylingIntro_TextBlocks")

Dieser `TitleText`-Stil erweitert den Stil, der für den <xref:System.Windows.Controls.TextBlock>-Typ erstellt wurde, auf den mit `BasedOn="{StaticResource {x:Type TextBlock}}"` verwiesen wird. Ein Stil mit einem `x:Key`-Attribut lässt sich auch mit dem `x:Key`-Wert des Stils erweitern. Wenn Sie z. B. einen Stil namens `Header1` erweitern möchten, würden Sie `BasedOn="{StaticResource Header1}"` verwenden.

## <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Beziehung zwischen der Eigenschaft „TargetType“ und dem Attribut „x:Key“

Wenn die Eigenschaft <xref:System.Windows.Style.TargetType%2A> auf `TextBlock` festgelegt wird, ohne dem Stil ein `x:Key`-Attribut zuzuweisen, wird ein Stil, wie bereits gezeigt, auf alle <xref:System.Windows.Controls.TextBlock>-Elemente angewendet. In diesem Fall wird `x:Key` implizit auf `{x:Type TextBlock}` festgelegt. Wenn Sie das Attribut `x:Key` also auf einen anderen Wert als `{x:Type TextBlock}` festlegen, wird <xref:System.Windows.Style> nicht automatisch auf alle `TextBlock`-Elemente angewendet. Stattdessen müssen Sie den Stil (mithilfe des `x:Key`-Werts) auf die `TextBlock`-Elemente explizit anwenden. Wenn sich Ihr Stil im Ressourcenabschnitt befindet und Sie die Eigenschaft `TargetType` nicht für Ihren Stil festlegen, müssen Sie das Attribut `x:Key` festlegen.

Die Eigenschaft `TargetType` stellt nicht nur einen Standardwert für `x:Key` bereit, sondern gibt auch den Typ an, für den die Setter-Eigenschaften gelten. Wenn Sie `TargetType` nicht angeben, müssen Sie die Eigenschaften in den <xref:System.Windows.Setter>-Objekten mit einem Klassennamen in der Syntax `Property="ClassName.Property"` qualifizieren. Anstatt beispielsweise `Property="FontSize"` festzulegen, müssen Sie <xref:System.Windows.Setter.Property%2A> auf `"TextBlock.FontSize"` oder `"Control.FontSize"` festlegen.

Beachten Sie außerdem, dass viele WPF-Steuerelemente aus einer Kombination anderer WPF-Steuerelementen bestehen. Wenn Sie einen Stil erstellen, das für alle Steuerelemente eines Typs gilt, erhalten Sie möglicherweise unerwartete Ergebnisse. Wenn Sie beispielsweise einen Stil für den <xref:System.Windows.Controls.TextBlock>-Typ in einem <xref:System.Windows.Window>-Objekt erstellen, wird der Stil auf alle `TextBlock`-Steuerelemente im Fenster angewendet, auch wenn `TextBlock` Teil eines anderen Steuerelements wie <xref:System.Windows.Controls.ListBox> ist.

## <a name="see-also"></a>Siehe auch

<!-- - [Create a style for a control](styles-templates-create-apply-template.md) -->
- [Überblick über XAML-Ressourcen](xaml-resources-define.md)
- [XAML-Übersicht in WPF](xaml.md)
