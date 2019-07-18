---
title: RelativeSource-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: a6a7d615a3a54fbc75bb86b295fdf80433a31dc5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053495"
---
# <a name="relativesource-markupextension"></a>RelativeSource-Markuperweiterung

Gibt die Eigenschaften einer <xref:System.Windows.Data.RelativeSource> -Bindungsquelle an verwendet werden, eine [-Markuperweiterung](binding-markup-extension.md), oder beim Festlegen der <xref:System.Windows.Data.Binding.RelativeSource%2A> Eigenschaft eine <xref:System.Windows.Data.Binding> Element in XAML eingerichteten.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a>XAML-Attributverwendung (geschachtelt innerhalb der Bindungserweiterung)

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>
```

## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

- oder - 

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource
      Mode="FindAncestor"
      AncestorType="{x:Type typeName}"
      AncestorLevel="intLevel"
    />
  </Binding.RelativeSource>
</Binding>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`modeEnumValue`|Eine der folgenden:<br /><br /> -Das Zeichenfolgentoken, das `Self`; entspricht einer <xref:System.Windows.Data.RelativeSource> wie bei erstellt seine <xref:System.Windows.Data.RelativeSource.Mode%2A> -Eigenschaftensatz auf <xref:System.Windows.Data.RelativeSourceMode.Self>.<br />-Das Zeichenfolgentoken, das `TemplatedParent`; entspricht einer <xref:System.Windows.Data.RelativeSource> wie bei erstellt seine <xref:System.Windows.Data.RelativeSource.Mode%2A> -Eigenschaftensatz auf <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.<br />-Das Zeichenfolgentoken, das `PreviousData`; entspricht einer <xref:System.Windows.Data.RelativeSource> wie bei erstellt seine <xref:System.Windows.Data.RelativeSource.Mode%2A> -Eigenschaftensatz auf <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.<br />-Informationen finden Sie unten auf `FindAncestor` Modus.|
|`FindAncestor`|Die Tokenzeichenfolge `FindAncestor`. Bei Verwendung dieses Tokens wird ein Modus aktiviert, in dem eine `RelativeSource` einen Vorgängertyp und optional eine Vorgängerebene angibt. Dies entspricht einer <xref:System.Windows.Data.RelativeSource>, die mit einer auf <xref:System.Windows.Data.RelativeSource.Mode%2A> festgelegten <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>-Eigenschaft erstellt wurde.|
|`typeName`|Erforderlich für `FindAncestor`-Modus. Der Name eines Typs, der die <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Eigenschaft auffüllt.|
|`intLevel`|Optional für `FindAncestor`-Modus. Eine Vorgängerebene (ausgewertet bezüglich der übergeordneten Richtung in der logischen Struktur).|

## <a name="remarks"></a>Hinweise

`{RelativeSource TemplatedParent}` -Bindungsverwendungen sind eine wichtige Technik, die ein größeres Konzept der Trennung von Benutzeroberfläche und Logik eines Steuerelements behandelt. Dies ermöglicht die Bindung aus der Vorlagendefinition mit dem vorlagenbasierten übergeordneten Element (der Laufzeitobjektinstanz, in der die Vorlage angewendet wird). Für diesen Fall die [TemplateBinding-Markuperweiterung](templatebinding-markup-extension.md) ist tatsächlich eine Kurznotation für den folgenden Bindungsausdruck: `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding` oder `{RelativeSource TemplatedParent}` Verwendungen nur relevant, in das XAML, die eine Vorlage definiert sind. Weitere Informationen finden Sie unter [TemplateBinding-Markuperweiterung](templatebinding-markup-extension.md)

`{RelativeSource FindAncestor}` wird hauptsächlich in Steuerelementvorlagen oder vorhersagbaren unabhängigen benutzeroberflächenzusammensetzungen, für Fälle verwendet, wo ein Steuerelement immer in eine visuelle Struktur eines bestimmten vorgängertyps erwartet wird. Beispielsweise können Elemente eines Elementsteuerelements `FindAncestor`-Verwendungen zum Binden an Eigenschaften des übergeordneten Vorgängers des Elementsteuerelements verwenden. Oder Elemente, die Teil der Steuerelementzusammensetzung in einer Vorlage sind, können `FindAncestor`-Bindungen mit übergeordneten Elemente in derselben Kompositionsstruktur verwenden.

In der Objektelementsyntax für den `FindAncestor`-Modus, wie in den XAML-Syntaxabschnitten dargestellt, wird die zweite Objektelementsyntax speziell für den `FindAncestor`-Modus verwendet. Der `FindAncestor`-Modus erfordert einen <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Wert. Sie müssen festlegen, <xref:System.Windows.Data.RelativeSource.AncestorType%2A> als ein Attribut mit einem [X: Type-Markuperweiterung](../../xaml-services/x-type-markup-extension.md) Verweis auf den Typ des übergeordneten Elements, suchen Sie nach. Der <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Wert wird verwendet, wenn die Bindungsanforderung zur Laufzeit verarbeitet wird.

Im `FindAncestor`-Modus kann die optionale Eigenschaft <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> dazu beitragen, die Vorgängersuche in den Fällen eindeutig zu machen, in denen eventuell mehr als ein Vorgänger dieses Typs in der Elementstruktur vorhanden ist.

Weitere Informationen zur Verwendung des `FindAncestor`-Modus finden Sie unter <xref:System.Windows.Data.RelativeSource>.

`{RelativeSource Self}` eignet sich für Szenarien, in denen eine Eigenschaft einer Instanz bereits auf dem Wert einer anderen Eigenschaft derselben Instanz, und kein allgemeines Abhängigkeitseigenschaftenverhältnis (beispielsweise Koersion) abhängen sollte zwischen diesen beiden Eigenschaften vorhanden. Obwohl es selten, dass zwei Eigenschaften auf ein Objekt vorhanden sein, so, dass die Werte buchstäblich identisch (und werden genauso wie eingegeben), können Sie auch eine `Converter` Parameter, um eine Bindung mit `{RelativeSource Self}`, und mit dem Konverter zum Konvertieren zwischen Quelle und Zieltypen. Ein weiteres Szenario für `{RelativeSource Self}` ist als Teil einer <xref:System.Windows.MultiDataTrigger>.

Beispielsweise definiert der folgende XAML-Code ein <xref:System.Windows.Shapes.Rectangle>-Element so, dass unabhängig davon, welcher Wert für <xref:System.Windows.FrameworkElement.Width%2A> eingegeben wird, <xref:System.Windows.Shapes.Rectangle> immer ein Quadrat ist: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`

`{RelativeSource PreviousData}` eignet sich entweder in Datenvorlagen oder in Fällen, in denen Bindungen eine Auflistung als Datenquelle verwenden. Sie können `{RelativeSource PreviousData}` um Beziehungen zwischen angrenzenden Datenelementen in der Auflistung hervorzuheben. Eine verwandte Methode besteht darin, eine <xref:System.Windows.Data.MultiBinding> zwischen dem aktuellen und vorherigen Element in der Datenquelle herzustellen und mit einem Konverter für diese Bindung die Differenz zwischen den beiden Elementen und deren Eigenschaften zu ermitteln.

Im folgenden Beispiel zeigt der erste <xref:System.Windows.Controls.TextBlock> in der Elementvorlage die aktuelle Zahl an. Die zweite <xref:System.Windows.Controls.TextBlock> Bindung ist eine <xref:System.Windows.Data.MultiBinding> , die nominell zwei <xref:System.Windows.Data.Binding> Betriebsfunktionen: der aktuelle Datensatz ein, und eine Bindung, die absichtlich den vorherigen Datensatz verwendet, indem `{RelativeSource PreviousData}`. Anschließend berechnet ein Konverter in der <xref:System.Windows.Data.MultiBinding> den Unterschied und gibt ihn an die Bindung zurück.

```xml
<ListBox Name="fibolist">
    <ListBox.ItemTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding}"/>
            <TextBlock>, difference = </TextBlock>
                <TextBlock>
                    <TextBlock.Text>
                        <MultiBinding Converter="{StaticResource DiffConverter}">
                            <Binding/>
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>
                        </MultiBinding>
                    </TextBlock.Text>
                </TextBlock>
            </StackPanel>
        </DataTemplate>
    </ListBox.ItemTemplate>
```

Finden Sie mit der Datenbindung ein Konzept ist hier nicht erläutert [Übersicht über die Datenbindung](../data/data-binding-overview.md).

In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-prozessorimplementierung wird die Handhabung dieser Markuperweiterung wird definiert, indem die <xref:System.Windows.Data.RelativeSource> Klasse.

`RelativeSource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in der Attributsyntax, dies ist die Konvention mit dem ein XAML-Prozessor erkannt wird, dass das Attribut von eine Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.Binding>
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Übersicht über Bindungsdeklarationen](../data/binding-declarations-overview.md)
- [x:Type-Markuperweiterung](../../xaml-services/x-type-markup-extension.md)
