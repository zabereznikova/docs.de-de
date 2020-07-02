---
title: Übersicht über Bindungsdeklarationen
description: Erfahren Sie, wie Sie eine Bindung in XAML für die Anwendungsentwicklung in Windows Presentation Foundation (WPF) deklarieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- markup extensions [WPF]
- data binding [WPF], declarations
- object element syntax [WPF]
- binding data [WPF], declarations
- syntax [WPF], object elements
- binding declarations [WPF]
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
ms.openlocfilehash: 8d4943de0cacb5fe0b5a0c37a5a68f15243ad528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619636"
---
# <a name="binding-declarations-overview"></a>Übersicht über Bindungsdeklarationen

In diesem Thema werden die verschiedenen Möglichkeiten zum Deklarieren einer Bindung erläutert.

<a name="Prereq"></a>

## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie dieses Thema lesen, ist es wichtig, dass Sie mit dem Konzept und der Verwendung von Markuperweiterungen vertraut sind. Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](../advanced/markup-extensions-and-wpf-xaml.md).

In diesem Thema werden keinen Datenbindungskonzepte behandelt. Eine Erörterung der Datenbindungskonzepte finden Sie in der [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

<a name="BindinginXAML"></a>

## <a name="declaring-a-binding-in-xaml"></a>Deklarieren einer Bindung in XAML

In diesem Abschnitt wird das Deklarieren einer Bindung in XAML erläutert.

<a name="MarkupExtensionSyntax"></a>

### <a name="markup-extension-usage"></a>Verwendung von Markuperweiterungen

<xref:System.Windows.Data.Binding> ist eine Markuperweiterung. Wenn Sie die Bindungserweiterung zum Deklarieren einer Bindung verwenden, besteht die Deklaration aus einer Reihe von Klauseln, die dem `Binding`-Schlüsselwort folgen und durch Kommas (,) getrennt sind. Die Klauseln in der Bindungsdeklaration können in beliebiger Reihenfolge aufgeführt sein, und es gibt zahlreiche mögliche Kombinationen. Die-Klauseln sind *Name*- = *Wert* -Paare, wobei *Name* der Name der <xref:System.Windows.Data.Binding> Eigenschaft und *value* der Wert ist, den Sie für die Eigenschaft festlegen.

Wenn Bindungsdeklarationszeichenfolgen im Markup erstellt werden, müssen sie an die entsprechende Abhängigkeitseigenschaft eines Zielobjekts angefügt werden. Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> -Eigenschaft mithilfe der Bindungs Erweiterung gebunden wird und die-Eigenschaft und die-Eigenschaft angegeben werden <xref:System.Windows.Data.Binding.Source%2A> <xref:System.Windows.Data.Binding.Path%2A> .

[!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#L37-L37)]

Auf diese Weise können Sie die meisten Eigenschaften der <xref:System.Windows.Data.Binding> Klasse angeben. Weitere Informationen zur Bindungs Erweiterung sowie eine Liste der Eigenschaften, die <xref:System.Windows.Data.Binding> nicht mit der Bindungs Erweiterung festgelegt werden können, finden Sie in der Übersicht über die [Bindungs Markup Erweiterung](../advanced/binding-markup-extension.md) .

<a name="ObjectElementSyntax"></a>

### <a name="object-element-syntax"></a>Objektelementsyntax

Die Objektelementsyntax stellt eine Alternative zur Erstellung der Bindungsdeklaration dar. In den meisten Fällen gibt es keinen besonderen Vorteil der Verwendung der Markuperweiterung gegenüber der Objektelementsyntax. In den Fällen, in denen die Markuperweiterung das von Ihnen verwendete Szenario jedoch nicht unterstützt (wenn der Eigenschaftswert zum Beispiel keine Zeichenfolge ist und keine Typkonvertierung hierfür vorhanden ist), müssen Sie die Objektelementsyntax verwenden.

Nachfolgend ist ein Beispiel für die Verwendung der Objektelementsyntax und der Markuperweiterung aufgeführt:

[!code-xaml[BindConversionMarkup#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]

Im Beispiel wird die- <xref:System.Windows.Controls.TextBlock.Foreground%2A> Eigenschaft gebunden, indem eine Bindung mithilfe der Erweiterungs Syntax deklariert wird. Die Bindungs Deklaration für die- <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft verwendet die Objekt Element Syntax.

Weitere Informationen zu den unterschiedlichen Begriffen finden Sie unter [Ausführliche Erläuterung der XAML-Syntax](../advanced/xaml-syntax-in-detail.md).

<a name="MBandPB"></a>

### <a name="multibinding-and-prioritybinding"></a>MultiBinding und PriorityBinding

<xref:System.Windows.Data.MultiBinding>und <xref:System.Windows.Data.PriorityBinding> unterstützen die XAML-Erweiterungs Syntax nicht. Daher müssen Sie die Objekt Element Syntax verwenden, wenn Sie eine <xref:System.Windows.Data.MultiBinding> oder eine <xref:System.Windows.Data.PriorityBinding> in XAML deklarieren.

<a name="BindinginCode"></a>

## <a name="creating-a-binding-in-code"></a>Erstellen einer Bindung in Code

Eine andere Möglichkeit, eine Bindung anzugeben, besteht darin, Eigenschaften direkt für ein- <xref:System.Windows.Data.Binding> Objekt im Code festzulegen. Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Data.Binding> -Objekt erstellt und die Eigenschaften im Code angegeben werden.  In diesem Beispiel `TheConverter` ist ein Objekt, das die- <xref:System.Windows.Data.IValueConverter> Schnittstelle implementiert.

[!code-csharp[BindConversion#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
[!code-vb[BindConversion#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]

Wenn das Objekt, das Sie binden, ein <xref:System.Windows.FrameworkElement> oder ein ist, <xref:System.Windows.FrameworkContentElement> können Sie die- `SetBinding` Methode für das-Objekt direkt anstelle von verwenden <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> . Ein Beispiel finden Sie unter [Erstellen einer Bindung in Code](how-to-create-a-binding-in-code.md).

<a name="Path_Syntax"></a>

## <a name="binding-path-syntax"></a>Bindungspfadsyntax

Verwenden Sie die- <xref:System.Windows.Data.Binding.Path%2A> Eigenschaft, um den Quellwert anzugeben, an den Sie binden möchten:

- Im einfachsten Fall <xref:System.Windows.Data.Binding.Path%2A> ist der Eigenschafts Wert der Name der Eigenschaft des Quell Objekts, das für die Bindung verwendet werden soll, z `Path=PropertyName` . b..

- Unter Eigenschaften einer Eigenschaft können mit einer ähnlichen Syntax wie in c# angegeben werden. So legt zum Beispiel die Klausel `Path=ShoppingCart.Order` die Bindung für die untergeordnete `Order`-Eigenschaft des Objekts oder die `ShoppingCart`-Eigenschaft fest.

- Um eine angefügte Eigenschaft zu binden, schließen Sie die angefügte Eigenschaft in Klammern ein. Um z. b. an die angefügte-Eigenschaft zu binden <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> , ist die Syntax `Path=(DockPanel.Dock)` .

- Indexer einer Eigenschaft können durch eckige Klammern nach dem Namen der indizierten Eigenschaft angegeben werden. So legt zum Beispiel die `Path=ShoppingCart[0]`-Klausel die Bindung auf den Index fest, der der Art und Weise entspricht, wie die interne Indizierung der Eigenschaft das Zeichenfolgenliteral „0“ handhabt. Geschachtelte Indexer werden ebenfalls unterstützt.

- Indexer und untergeordnete Eigenschaften können in einer `Path`-Klausel kombiniert werden, z. B. `Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`.

- Indexer können mehrere durch Kommata (,) getrennte Indexer-Parameter aufweisen. Der Typ der einzelnen Parameter kann in Klammern angegeben werden. Sie können beispielsweise über `Path="[(sys:Int32)42,(sys:Int32)24]"` verfügen, wobei `sys` dem `System`-Namespace zugeordnet ist.

- Wenn die Quelle eine Auflistungsansicht darstellt, kann das aktuelle Element mit einem Schrägstrich (/) angegeben werden. Beispielsweise legt die Klausel `Path=/` die Bindung auf das aktuelle Element in der Ansicht fest. Wenn die Quelle eine Auflistung darstellt, gibt diese Syntax das aktuelle Element der Standardauflistungsansicht an.

- Eigenschaftennamen und Schrägstriche können kombiniert werden, um Eigenschaften zu durchlaufen, die Auflistungen darstellen. Beispielsweise gibt `Path=/Offices/ManagerName` das aktuelle Element der Quellauflistung an, die eine `Offices`-Eigenschaft enthält, bei der es sich ebenfalls um eine Auflistung handelt. Bei dem aktuellen Element handelt es sich um ein Objekt, das eine `ManagerName`-Eigenschaft enthält.

- Optional kann ein Pfad mit einem Punkt (.) für die Bindung an die aktuelle Quelle verwendet werden. `Text="{Binding}"` entspricht beispielsweise `Text="{Binding Path=.}"`.

### <a name="escaping-mechanism"></a>Mechanismus zum Verwenden von Escapezeichen

- In Indexern ([ ]) dient das Caretzeichen (^) als Escapezeichen für das nächste Zeichen.

- Wenn Sie <xref:System.Windows.Data.Binding.Path%2A> in XAML festlegen, müssen Sie auch eine Escapezeichen (mit XML-Entitäten) für bestimmte Sonderzeichen in der XML-Sprachdefinition verwenden:

  - Verwenden Sie `&amp;`, um das Zeichen „&“ mit Escapezeichen zu versehen.

  - Verwenden Sie `&gt;`, um das Endtag „>“ mit Escapezeichen zu versehen.

- Darüber hinaus müssen Sie, wenn Sie die gesamte Bindung in einem Attribut mit der Markuperweiterungssyntax beschreiben, Zeichen (mit einem umgekehrten Schrägstrich \\) mit Escapezeichen zu versehen, die speziell vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Markuperweiterungsparser verwendet werden:

  - Der umgekehrte Schrägstrich (\\) ist das eigentliche Escapezeichen.

  - Das Gleichheitszeichen (=) trennt den Eigenschaftennamen vom Eigenschaftswert.

  - Ein Komma (,) trennt Eigenschaften.

  - Die rechte geschweifte Klammer (}) gibt das Ende einer Markuperweiterung an.

<a name="Default"></a>

## <a name="default-behaviors"></a>Standardverhalten

Das Standardverhalten ist das wie folgt angegebene Verhalten, wenn nicht anders in der Deklaration angegeben.

- Es wird ein Standardkonverter erstellt, der versucht, eine Typkonvertierung zwischen dem Wert der Bindungsquelle und dem Wert des Bindungsziels durchzuführen. Wenn keine Konvertierung durchgeführt werden kann, gibt der Standardkonverter `null` zurück.

- Wenn Sie nicht festlegen <xref:System.Windows.Data.Binding.ConverterCulture%2A> , verwendet die Bindungs-Engine die- `Language` Eigenschaft des Bindungs Zielobjekts. In XAML ist der Standardwert „en-US“, oder der Wert wird vom Stammelement (oder einem beliebigen Element) der Seite übernommen, wenn ein Element explizit festgelegt wurde.

- Solange die Bindung bereits über einen Datenkontext verfügt (z. B. den übernommenen Datenkontext eines übergeordneten Elements) und das von diesem Kontext zurückgegebene Element oder die Auflistung für die Bindung geeignet ist, ohne dass eine weitere Pfadänderung notwendig ist, kann eine Bindung auch über keine Klauseln verfügen: `{Binding}`. Dies ist häufig der Fall, wenn eine Bindung für die Datenformatierung festgelegt wird, wobei die Bindung auf eine Auflistung angewendet wird. Weitere Informationen finden Sie im Abschnitt „Als Bindungsquelle verwendete ganze Objekte“ in der [Übersicht über Bindungsquellen](binding-sources-overview.md).

- Der Standardwert <xref:System.Windows.Data.Binding.Mode%2A> variiert je nach Abhängigkeits Eigenschaft, die gebunden wird, zwischen unidirektionaler und bidirektional. Sie können den Bindungsmodus immer explizit deklarieren, um sicherzustellen, dass die Bindung das gewünschte Verhalten aufweist. Im Allgemeinen werden von Benutzern bearbeitbare Steuerelement Eigenschaften, z. b. <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> und, standardmäßig bidirektionale <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType> Bindungen, wohingegen die meisten anderen Eigenschaften standardmäßig unidirektionale Bindungen haben.

- Der Standard <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert variiert <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> je nach <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> der gebundenen Abhängigkeits Eigenschaft auch zwischen und. Der Standardwert für die meisten Abhängigkeitseigenschaften ist <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, während die <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>-Eigenschaft den Standardwert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> aufweist.

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Artikel zu Vorgehensweisen](data-binding-how-to-topics.md)
- [Datenbindung](../advanced/optimizing-performance-data-binding.md)
- [XAML-Syntax von PropertyPath](../advanced/propertypath-xaml-syntax.md)
