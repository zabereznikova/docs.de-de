---
title: Übersicht über bidirektionale Features
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: 17167b1afa5037998d9ea8ed679a66c89babe242
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741628"
---
# <a name="bidirectional-features-in-wpf-overview"></a>Übersicht über bidirektionale Features in WPF

Anders als bei jeder anderen Entwicklungsplattform bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viele Features, die eine schnelle Entwicklung bidirektionaler Inhalte unterstützen, z. b. gemischt von links nach rechts und von rechts nach links im gleichen Dokument. Gleichzeitig erstellt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine ausgezeichnete Benutzerfunktion für Benutzer, die bidirektionale Features wie arabische und Hebräisch sprachige Benutzer benötigen.

In den folgenden Abschnitten werden bidirektionale Funktionen sowie Beispiele erklärt, die zeigen, wie die beste Anzeige von bidirektionalem Inhalts erreicht werden kann. In den meisten Beispielen wird XAML verwendet, aber Sie können die Konzepte problemlos auf C# oder Microsoft Visual Basic Code anwenden.

<a name="FlowDirection"></a>

## <a name="flowdirection"></a>FlowDirection

Die grundlegende Eigenschaft, die die Richtung des Inhalts Flusses in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung definiert, ist <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Diese Eigenschaft kann auf einen von zwei Enumerationswerten festgelegt werden, <xref:System.Windows.FlowDirection.LeftToRight> oder <xref:System.Windows.FlowDirection.RightToLeft>. Die-Eigenschaft ist für alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente verfügbar, die von <xref:System.Windows.FrameworkElement>erben.

In den folgenden Beispielen wird die Fluss Richtung eines <xref:System.Windows.Controls.TextBox>-Elements festgelegt.

**Flussrichtung von links nach rechts**

[!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]

**Flussrichtung von rechts nach links**

[!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]

Die folgende Grafik zeigt, wie der vorherige Code gerendert wird.

![Grafik, die die verschiedenen Fluss Richtungen veranschaulicht.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)

Ein Element in einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Struktur erbt die <xref:System.Windows.FrameworkElement.FlowDirection%2A> von seinem Container. Im folgenden Beispiel befindet sich der <xref:System.Windows.Controls.TextBlock> innerhalb eines <xref:System.Windows.Controls.Grid>, der sich in einem <xref:System.Windows.Window>befindet. Wenn Sie die <xref:System.Windows.FrameworkElement.FlowDirection%2A> für die <xref:System.Windows.Window> festlegen, wird die Einstellung für die <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.TextBlock> ebenfalls festgelegt.

Im folgenden Beispiel wird das Festlegen von <xref:System.Windows.FrameworkElement.FlowDirection%2A>veranschaulicht.

[!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]

Die <xref:System.Windows.Window> der obersten Ebene verfügt über eine <xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.FlowDirection>, sodass alle darin enthaltenen Elemente auch denselben <xref:System.Windows.FrameworkElement.FlowDirection%2A>erben. Damit ein Element eine angegebene <xref:System.Windows.FrameworkElement.FlowDirection%2A> außer Kraft setzt, muss es eine explizite Richtung ändern, wie z. b. das zweite <xref:System.Windows.Controls.TextBlock> im vorherigen Beispiel, das in <xref:System.Windows.FlowDirection.LeftToRight>geändert wird. Wenn keine <xref:System.Windows.FrameworkElement.FlowDirection%2A> definiert ist, gilt die Standard <xref:System.Windows.FlowDirection.LeftToRight>.

Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels:

![Grafik, die die explizite Änderung der Fluss Richtung veranschaulicht.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)

<a name="FlowDocument"></a>

## <a name="flowdocument"></a>FlowDocument

Viele Entwicklungsplattformen, z. b. html, Win32 und Java, bieten besondere Unterstützung für die bidirektionale Inhalts Entwicklung. Markup Sprachen, wie z. b. html, geben Inhaltsautoren das erforderliche Markup zum Anzeigen von Text in beliebiger Richtung an, z. b. das HTML 4,0-Tag "dir", das "RTL" oder "ltr" als Werte annimmt. Dieses Tag ähnelt der <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Eigenschaft, aber die <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Eigenschaft arbeitet in einer komplexeren Methode zum Layout von Textinhalten und kann für andere Inhalte als Text verwendet werden.

In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ist ein <xref:System.Windows.Documents.FlowDocument> ein vielseitiges [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Element, das eine Kombination aus Text, Tabellen, Bildern und anderen Elementen hosten kann. Die Beispiele in den folgenden Abschnitten verwenden dieses Element.

Das Hinzufügen von Text zu einem <xref:System.Windows.Documents.FlowDocument> kann auf eine andere Weise erfolgen. Eine einfache Möglichkeit hierfür ist die Verwendung einer <xref:System.Windows.Documents.Paragraph> ein Element auf Blockebene, das zum Gruppieren von Inhalt, z. b. Text, verwendet wird. Zum Hinzufügen von Text zu Elementen auf Inline Ebene werden in den Beispielen <xref:System.Windows.Documents.Span> und <xref:System.Windows.Documents.Run>verwendet. <xref:System.Windows.Documents.Span> ist ein fortlaufendes Inhalts Element auf Inline Ebene, das zum Gruppieren anderer Inline Elemente verwendet wird. ein <xref:System.Windows.Documents.Run> ist ein fortlaufendes Inhalts Element auf Inline Ebene, das eine Ausführung von unformatiertem Text enthalten soll. Eine <xref:System.Windows.Documents.Span> kann mehrere <xref:System.Windows.Documents.Run> Elemente enthalten.

Das erste Dokument Beispiel enthält ein Dokument mit einer Reihe von Netzwerkfreigabe Namen. beispielsweise `\\server1\folder\file.ext`. Egal, ob Sie diesen Netzwerklink in einem arabischen oder einem englischen Dokument haben, Sie möchten, dass es immer auf die gleiche Weise angezeigt wird. Die folgende Grafik veranschaulicht die Verwendung des Span-Elements und zeigt den Link in einem arabischen <xref:System.Windows.FlowDirection.RightToLeft> Dokument:

![Grafik, die die Verwendung des Span-Elements veranschaulicht.](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "FlowDocument")

Da der Text <xref:System.Windows.FlowDirection.RightToLeft>ist, trennen alle Sonderzeichen, wie z. b. "\\", den Text in der Reihenfolge von rechts nach links. Das führt dazu, dass der Link nicht in der richtigen Reihenfolge angezeigt wird. um das Problem zu beheben, muss der Text eingebettet werden, um eine separate <xref:System.Windows.Documents.Run> fließenden <xref:System.Windows.FlowDirection.LeftToRight>zu erhalten. Anstatt eine separate <xref:System.Windows.Documents.Run> für jede Sprache zu haben, ist es besser, das Problem zu beheben, indem der weniger häufig verwendete englische Text in eine größere arabische <xref:System.Windows.Documents.Span>eingebettet wird.

Dies wird in der folgenden Abbildung veranschaulicht, indem das in einem span-Element eingebettete Run-Element verwendet wird:

![Grafik, die das in einem span-Element eingebettete Run-Element veranschaulicht.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)

Im folgenden Beispiel wird die Verwendung von <xref:System.Windows.Documents.Run> und <xref:System.Windows.Documents.Span> Elementen in Dokumenten veranschaulicht.

[!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]

<a name="SpanElements"></a>

## <a name="span-elements"></a>Span-Elemente

Das <xref:System.Windows.Documents.Span>-Element fungiert als Begrenzungs Trennzeichen zwischen Texten mit unterschiedlichen Fluss Richtungen.  Auch <xref:System.Windows.Documents.Span> Elemente, die dieselbe Fluss Richtung aufweisen, werden als verschiedene bidirektionale Bereiche betrachtet, was bedeutet, dass die <xref:System.Windows.Documents.Span> Elemente im <xref:System.Windows.FlowDirection>des Containers angeordnet sind. nur der Inhalt innerhalb des <xref:System.Windows.Documents.Span> Elements folgt dem <xref:System.Windows.FlowDirection> des <xref:System.Windows.Documents.Span>.

Die folgende Grafik zeigt die Fluss Richtung mehrerer <xref:System.Windows.Controls.TextBlock> Elemente.

![Grafik, die Textblöcke mit unterschiedlichen Fluss Richtungen veranschaulicht.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)

Im folgenden Beispiel wird gezeigt, wie die Elemente <xref:System.Windows.Documents.Span> und <xref:System.Windows.Documents.Run> verwendet werden, um die in der vorherigen Grafik dargestellten Ergebnisse zu erzielen.

[!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]

In den <xref:System.Windows.Controls.TextBlock> Elementen im Beispiel werden die <xref:System.Windows.Documents.Span> Elemente entsprechend der <xref:System.Windows.FlowDirection> ihrer übergeordneten Elemente angeordnet, aber der Text in jedem <xref:System.Windows.Documents.Span> Element fließt entsprechend seiner eigenen <xref:System.Windows.FlowDirection>. Dies gilt für Latein und Arabisch - oder jede andere Sprache.

### <a name="adding-xmllang"></a>Hinzufügen von xml:lang

Die folgende Grafik zeigt ein weiteres Beispiel, in dem Zahlen und arithmetische Ausdrücke verwendet werden, z. b. `"200.0+21.4=221.4"`. Beachten Sie, dass nur die <xref:System.Windows.FlowDirection> festgelegt ist.

![Grafik, die Zahlen anzeigt, die nur Fluss Richtung verwenden.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)

Benutzer dieser Anwendung werden von der Ausgabe enttäuscht, auch wenn die <xref:System.Windows.FlowDirection> richtig ist, werden die Zahlen nicht so strukturiert, dass arabische Zahlen formatiert werden sollen.

XAML-Elemente können ein XML-Attribut (`xml:lang`) enthalten, das die Sprache der einzelnen Elemente definiert. XAML unterstützt auch ein XML-sprach Prinzip, wobei `xml:lang` Werte, die auf übergeordnete Elemente in der Struktur angewendet werden, von untergeordneten Elementen verwendet werden. Im vorherigen Beispiel wurde die Standard `xml:lang` verwendet, die für XAML `en-US` ist, da keine Sprache für das <xref:System.Windows.Documents.Run>-Element oder eines seiner Elemente der obersten Ebene definiert wurde. Der interne Zahlen Strukturierungs Algorithmus von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] wählt Zahlen in der entsprechenden Sprache aus – in diesem Fall Englisch. Zum ordnungsgemäßen Rendering der arabischen Zahlen `xml:lang` muss festgelegt werden.

Die folgende Abbildung zeigt das Beispiel mit hinzugefügten `xml:lang`.

![Grafik, die arabische Zahlen veranschaulicht, die von rechts nach links fließen.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)

Im folgenden Beispiel wird `xml:lang` der Anwendung hinzugefügt.

[!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]

Beachten Sie, dass viele Sprachen abhängig von der Zielregion unterschiedliche `xml:lang` Werte haben, z. b. `"ar-SA"` und `"ar-EG"` zwei Variationen von Arabisch darstellen. Die vorherigen Beispiele veranschaulichen, dass Sie sowohl den `xml:lang` als auch <xref:System.Windows.FlowDirection> Werte definieren müssen.

<a name="FlowDirectionNontext"></a>

## <a name="flowdirection-with-non-text-elements"></a>FlowDirection mit Nicht-Text-Elementen

<xref:System.Windows.FlowDirection> definiert nicht nur, wie Text in einem Textelement fließt, sondern auch die Fluss Richtung von fast allen anderen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elementen. Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.ToolBar>, die einen horizontalen <xref:System.Windows.Media.LinearGradientBrush> verwendet, um den Hintergrund mit dem Farbverlauf von links nach rechts zu zeichnen.

![Grafik, die eine Symbolleiste mit einem Farbverlauf von links nach rechts anzeigt.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)

Nachdem Sie die <xref:System.Windows.FlowDirection> auf <xref:System.Windows.FlowDirection.RightToLeft>festgelegt haben, werden nicht nur die Schaltflächen <xref:System.Windows.Controls.ToolBar> von rechts nach links angeordnet, sondern auch der <xref:System.Windows.Media.LinearGradientBrush> die Offsets für den Fluss von rechts nach links ausrichten.

In der folgenden Abbildung wird die Neuausrichtung der <xref:System.Windows.Media.LinearGradientBrush>veranschaulicht.

![Grafik, die eine Symbolleiste mit einem Farbverlauf von rechts nach Links anzeigt.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)

Im folgenden Beispiel wird eine <xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.Controls.ToolBar>gezeichnet. (Um Sie von links nach rechts zu zeichnen, entfernen Sie das <xref:System.Windows.FlowDirection>-Attribut für die <xref:System.Windows.Controls.ToolBar>.

[!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]

<a name="FlowDirectionExceptions"></a>

### <a name="flowdirection-exceptions"></a>FlowDirection-Ausnahmen

Es gibt einige Fälle, in denen sich <xref:System.Windows.FlowDirection> nicht wie erwartet verhält. In diesem Abschnitt werden zwei von diesen Ausnahmen behandelt.

**Image**

Ein-<xref:System.Windows.Controls.Image> das ein Steuerelement darstellt, das ein Bild anzeigt. In XAML kann Sie mit einer <xref:System.Windows.Controls.Image.Source%2A>-Eigenschaft verwendet werden, die den URI (Uniform Resource Identifier) der anzuzeigenden <xref:System.Windows.Controls.Image> definiert.

Im Gegensatz zu anderen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elementen erbt ein <xref:System.Windows.Controls.Image> nicht die <xref:System.Windows.FlowDirection> aus dem Container. Wenn die <xref:System.Windows.FlowDirection> jedoch explizit auf <xref:System.Windows.FlowDirection.RightToLeft>festgelegt ist, wird ein <xref:System.Windows.Controls.Image> horizontal geflippt angezeigt. Dies wird als eine praktische Funktion für Entwickler von bidirektionalem Inhalt implementiert, da in einigen Fällen das horizontale Spiegeln des Bildes den gewünschten Effekt erzeugt.

Die folgende Abbildung zeigt ein geflippte <xref:System.Windows.Controls.Image>.

![Grafik, die ein geflittenes Bild veranschaulicht.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)

Im folgenden Beispiel wird veranschaulicht, dass das <xref:System.Windows.Controls.Image> die <xref:System.Windows.FlowDirection> nicht vom <xref:System.Windows.Controls.StackPanel> erben kann, in dem es enthalten ist.

> [!NOTE]
> Sie benötigen eine Datei namens " **ms_logo. jpg** " auf "C:\". Laufwerk zum Ausführen dieses Beispiels.

[!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]

> [!NOTE]
> In den Download Dateien ist eine **ms_logo. jpg** -Datei enthalten. Der Code geht davon aus, dass die JPG-Datei sich nicht in Ihrem Projekt, sondern an einer beliebigen Stelle auf dem Laufwerk C:\ befindet. Sie kopieren das .jpg aus den Projektdateien auf Ihr Laufwerk C:\ oder ändern den Code, um die Datei im Projekt zu suchen. Zu diesem Zweck `Source="file://c:/ms_logo.jpg"` `Source="ms_logo.jpg"`.

**Pfade**

Zusätzlich zu einem <xref:System.Windows.Controls.Image>ist ein weiteres interessantes Element <xref:System.Windows.Shapes.Path>. Ein Pfad ist ein Objekt, das eine Reihe von miteinander verbundenen Linien und Kurven zeichnen kann. Sie verhält sich ähnlich wie eine <xref:System.Windows.Controls.Image> in Bezug auf die <xref:System.Windows.FlowDirection>. Beispielsweise ist die <xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.FlowDirection> eine horizontale Spiegelung ihrer <xref:System.Windows.FlowDirection.LeftToRight>. Im Gegensatz zu einem <xref:System.Windows.Controls.Image>erbt <xref:System.Windows.Shapes.Path> seine <xref:System.Windows.FlowDirection> aus dem Container, und einer muss ihn nicht explizit angeben.

Im folgenden Beispiel wird ein einfacher Pfeil mit drei Linien gezeichnet. Der erste Pfeil erbt die Richtung des <xref:System.Windows.FlowDirection.RightToLeft> Flusses vom <xref:System.Windows.Controls.StackPanel>, sodass seine Start-und Endpunkte von einem Stamm auf der rechten Seite gemessen werden. Der zweite Pfeil mit einem expliziten <xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.FlowDirection> auch auf der rechten Seite beginnt. Der dritte Pfeil hat jedoch seinen Startstamm auf der linken Seite. Weitere Informationen zum Zeichnen finden Sie unter <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.GeometryGroup>.

[!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]

Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels mit Pfeilen, die mithilfe des `Path`-Elements gezeichnet werden:

![Grafik, die Pfeile veranschaulicht, die mithilfe des Path-Elements gezeichnet werden.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)

Die <xref:System.Windows.Controls.Image> und <xref:System.Windows.Shapes.Path> sind zwei Beispiele dafür, wie [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.FlowDirection>verwendet. Neben dem Anordnen von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elementen in einer bestimmten Richtung innerhalb eines Containers können <xref:System.Windows.FlowDirection> mit Elementen wie <xref:System.Windows.Controls.InkPresenter> verwendet werden, die frei Hand Eingaben auf einer Oberfläche, <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>rendert. Jedes Mal, wenn Sie ein Verhalten von rechts nach Links für Ihre Inhalte benötigen, das das Verhalten von links nach rechts imitiert (oder umgekehrt), bietet [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] diese Funktion.

<a name="NumberSubstitution"></a>

## <a name="number-substitution"></a>Ersetzen von Zahlen

In der Vergangenheit hat Windows das Ersetzen von Zahlen unterstützt, indem es die Darstellung verschiedener kultureller Formen für die gleichen Ziffern ermöglicht und dabei den internen Speicher dieser Ziffern in verschiedenen Gebiets Schemas einheitlich gehalten hat, z. b. Wenn Zahlen in ihren bekannte hexadezimal Werte, 0x40, 0x41, werden jedoch entsprechend der ausgewählten Sprache angezeigt.

Dadurch haben Anwendungen die Möglichkeit, numerische Werte zu verarbeiten, ohne Sie von einer Sprache in eine andere konvertieren zu müssen. ein Benutzer kann z. b. ein Microsoft Excel-Arbeitsblatt in einem lokalisierten arabischen Fenster öffnen und die in Arabisch formatierten Zahlen anzeigen, aber in einem Die Europäische Version von Windows und die Darstellung der gleichen Zahlen in der Europäischen Darstellung. Dies ist auch für andere Symbole, wie z.B. Kommas als Trennzeichen und das Prozentsatzsymbol notwendig, da sie normalerweise Zahlen in einem Dokument begleiten.

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] führt diese Tradition fort und fügt weitere Unterstützung für diese Funktion hinzu, die mehreren Benutzern die Steuerung darüber ermöglicht, wann und wie die Ersetzung verwendet wird. Diese Funktion ist für jede Sprache konzipiert, da sie besonders für bidirektionalen Inhalt nützlich ist, bei dem die Strukturierung von Ziffern für eine bestimmte Sprache in der Regel eine Herausforderung für die Entwickler der Anwendung darstellt, da eine Anwendung aufgrund der verschiedenen Kulturen möglicherweise weiter ausgeführt wird.

Die Kern Eigenschaft, die steuert, wie die Zahlen Ersetzung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funktioniert, ist die <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>-Abhängigkeits Eigenschaft. Die <xref:System.Windows.Media.NumberSubstitution>-Klasse gibt an, wie Zahlen im Text angezeigt werden sollen. Er verfügt über drei öffentliche Eigenschaften, die sein Verhalten definieren. Im folgenden finden Sie eine Zusammenfassung der einzelnen Eigenschaften:

**CultureSource:**

Diese Eigenschaft gibt an, wie die Kultur für Zahlen bestimmt wird. Er nimmt einen von drei <xref:System.Windows.Media.NumberCultureSource> Enumerationswerten an.

- Override: die Zahlen Kultur ist die <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> Eigenschaft.

- Text: Die Kultur der Zahl, ist die Kultur der Textausführung. In Markup wäre dies `xml:lang`oder sein Alias `Language` Eigenschaft (<xref:System.Windows.FrameworkElement.Language%2A> oder <xref:System.Windows.FrameworkContentElement.Language%2A>). Außerdem handelt es sich um den Standardwert für Klassen, die von <xref:System.Windows.FrameworkContentElement>abgeleitet werden. Diese Klassen umfassen <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> usw.

- Benutzer: Die Kultur der Zahl, ist die Kultur des aktuellen Threads. Diese Eigenschaft ist die Standardeinstellung für alle Unterklassen von <xref:System.Windows.FrameworkElement> z. b. <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> und <xref:System.Windows.Controls.TextBlock>.

**CultureOverride**:

Die <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A>-Eigenschaft wird nur verwendet, wenn die <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A>-Eigenschaft auf <xref:System.Windows.Media.NumberCultureSource.Override> festgelegt ist und andernfalls ignoriert wird. Es gibt die Kultur der Zahl an. Der Wert `null`, der Standardwert, wird als en-US interpretiert.

**Ersetzung**:

Diese Eigenschaft gibt den Typ der zu ersetzenden Zahl an. Sie nimmt einen der folgenden <xref:System.Windows.Media.NumberSubstitutionMethod> Enumerationswerte an:

- <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: die Ersetzungs Methode wird basierend auf der <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType>-Eigenschaft der Zahlen Kultur bestimmt. Dies ist der Standardwert.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Wenn die Zahlen Kultur eine arabische oder eine persische Kultur ist, gibt Sie an, dass die Ziffern vom Kontext abhängen.

- <xref:System.Windows.Media.NumberSubstitutionMethod.European>: Zahlen werden immer als europäische Ziffern gerendert.

- <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: Zahlen werden mithilfe der nationalen Ziffern für die Zahlen Kultur gerendert, wie vom <xref:System.Globalization.CultureInfo.NumberFormat%2A>der Kultur angegeben.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: Zahlen werden mithilfe der herkömmlichen Ziffern für die Zahlen Kultur gerendert. In den meisten Kulturen ist dies identisch mit <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>. <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> führt jedoch zu lateinischen Ziffern für einige arabische Kulturen, wohingegen dieser Wert arabische Ziffern für alle arabischen Kulturen zur Folge hat.

Was bedeuten diese Werte für einen Entwickler von bidirektionalem Inhalt? In den meisten Fällen muss der Entwickler möglicherweise nur <xref:System.Windows.FlowDirection> und die Sprache der einzelnen tex[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente definieren, z. b. `Language="ar-SA"`, und die <xref:System.Windows.Media.NumberSubstitution> Logik kümmert sich um die Anzeige der Zahlen entsprechend der richtigen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Das folgende Beispiel veranschaulicht die Verwendung von arabischen und englischen Zahlen in einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendung, die in einer arabischen Version von Windows ausgeführt wird.

[!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]

Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels, wenn Sie in einer arabischen Version von Windows mit den angezeigten arabischen und englischen Zahlen ausführen:

![Grafik, die arabische und englische Zahlen zeigt.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)

In diesem Fall war die <xref:System.Windows.FlowDirection> wichtig, da die <xref:System.Windows.FlowDirection> auf <xref:System.Windows.FlowDirection.LeftToRight> stattdessen die europäischen Ziffern zurückgegeben hätte. In den folgenden Abschnitten wird erläutert, wie eine einheitliche Anzeige von Ziffern im gesamten Dokument möglich ist. Wenn dieses Beispiel in einem arabischen Windows nicht ausgeführt wird, werden alle Ziffern als europäische Ziffern angezeigt.

**Definieren von Ersetzungsregeln**

In einer realen Anwendung müssen Sie die Sprache programmgesteuert festlegen. Sie möchten beispielsweise festlegen, dass das `xml:lang`-Attribut mit dem identisch ist, das vom System [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]verwendet wird, oder die Sprache je nach Anwendungs Zustand ändern.

Wenn Sie Änderungen auf der Grundlage des Anwendungs Zustands vornehmen möchten, verwenden Sie andere Funktionen, die von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bereitgestellt werden.

Legen Sie zunächst den `NumberSubstitution.CultureSource="Text"`der Anwendungs Komponente fest. Wenn Sie diese Einstellung verwenden, stellen Sie sicher, dass die Einstellungen nicht aus der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für Textelemente stammen, deren Standardwert "User" ist, z. b. <xref:System.Windows.Controls.TextBlock>.

Beispiel:

```xaml
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

Legen Sie im C# entsprechenden Code die `Language`-Eigenschaft fest, z. b. auf `"ar-SA"`.

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

Wenn Sie die `Language`-Eigenschaft auf die Benutzeroberflächen Sprache des aktuellen Benutzers festlegen müssen, verwenden Sie den folgenden Code.

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> stellt die aktuelle Kultur dar, die vom aktuellen Thread zur Laufzeit verwendet wird.

Das abschließende XAML-Beispiel sollte in etwa wie im folgenden Beispiel aussehen.

[!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]

Das abschließende C# Beispiel sollte in etwa wie folgt aussehen.

[!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]

In der folgenden Abbildung wird gezeigt, wie das Fenster für beide Programmiersprachen aussieht und wie arabische Zahlen angezeigt werden:

![Grafik, in der arabische Zahlen angezeigt werden.](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)

**Mithilfe der Ersetzungseigenschaft**

Die Art und Weise der Zahlen Ersetzung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] hängt sowohl von der Sprache des Text Elements als auch von der <xref:System.Windows.FlowDirection>ab. Wenn die <xref:System.Windows.FlowDirection> von links nach rechts ist, werden die europäischen Ziffern gerendert. Wenn jedoch der arabische Text vorangestellt ist, oder wenn die Sprache auf "ar" festgelegt ist und die <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection.RightToLeft>ist, werden stattdessen arabische Ziffern gerendert.

In einigen Fällen möchten Sie jedoch eine einheitliche Anwendung, zum Beispiel mit europäischen Ziffern für alle Benutzer erstellen. Oder arabische Ziffern in <xref:System.Windows.Documents.Table> Zellen mit einem bestimmten <xref:System.Windows.Style>. Eine einfache Möglichkeit hierfür ist die Verwendung der <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>-Eigenschaft.

Im folgenden Beispiel wird für den ersten <xref:System.Windows.Controls.TextBlock> die <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>-Eigenschaft nicht festgelegt, sodass der Algorithmus wie erwartet arabische Ziffern anzeigt. Im zweiten <xref:System.Windows.Controls.TextBlock>wird die Ersetzung jedoch auf das europäisch festgelegt, das die Standard Ersetzung für arabische Zahlen überschreibt, und die europäischen Ziffern werden angezeigt.

[!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
