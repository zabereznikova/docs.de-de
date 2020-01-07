---
title: RelativeSource-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 15fdc9d093bb3efb4ea4cef5d4cdfa8474042f12
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559745"
---
# <a name="relativesource-markupextension"></a>RelativeSource-Markuperweiterung

Gibt Eigenschaften einer <xref:System.Windows.Data.RelativeSource> Bindungs Quelle an, die innerhalb einer [Bindungs Markup Erweiterung](binding-markup-extension.md)verwendet werden sollen, oder, wenn die <xref:System.Windows.Data.Binding.RelativeSource%2A>-Eigenschaft eines <xref:System.Windows.Data.Binding> Elements festgelegt wird, das in XAML festgelegt wurde.

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

\- oder -

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
|`modeEnumValue`|Eine der folgenden Komponenten:<br /><br /> -Das Zeichen folgen Token `Self`; entspricht einer <xref:System.Windows.Data.RelativeSource>, die erstellt wird, wobei die <xref:System.Windows.Data.RelativeSource.Mode%2A>-Eigenschaft auf <xref:System.Windows.Data.RelativeSourceMode.Self>festgelegt ist.<br />-Das Zeichen folgen Token `TemplatedParent`; entspricht einer <xref:System.Windows.Data.RelativeSource>, die erstellt wird, wobei die <xref:System.Windows.Data.RelativeSource.Mode%2A>-Eigenschaft auf <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>festgelegt ist.<br />-Das Zeichen folgen Token `PreviousData`; entspricht einer <xref:System.Windows.Data.RelativeSource>, die erstellt wird, wobei die <xref:System.Windows.Data.RelativeSource.Mode%2A>-Eigenschaft auf <xref:System.Windows.Data.RelativeSourceMode.PreviousData>festgelegt ist.<br />-Weitere Informationen zum `FindAncestor` Modus finden Sie unten.|
|`FindAncestor`|Die Tokenzeichenfolge `FindAncestor`. Bei Verwendung dieses Tokens wird ein Modus aktiviert, in dem eine `RelativeSource` einen Vorgängertyp und optional eine Vorgängerebene angibt. Dies entspricht einer <xref:System.Windows.Data.RelativeSource>, die mit einer auf <xref:System.Windows.Data.RelativeSource.Mode%2A> festgelegten <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>-Eigenschaft erstellt wurde.|
|`typeName`|Erforderlich für `FindAncestor`-Modus. Der Name eines Typs, der die <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Eigenschaft auffüllt.|
|`intLevel`|Optional für `FindAncestor`-Modus. Eine Vorgängerebene (ausgewertet bezüglich der übergeordneten Richtung in der logischen Struktur).|

## <a name="remarks"></a>Hinweise

`{RelativeSource TemplatedParent}` Bindungs Verwendungen sind eine wichtige Technik, die ein größeres Konzept der Trennung der Benutzeroberfläche eines Steuer Elements und der Logik eines Steuer Elements adressiert. Dies ermöglicht die Bindung aus der Vorlagendefinition mit dem vorlagenbasierten übergeordneten Element (der Laufzeitobjektinstanz, in der die Vorlage angewendet wird). In diesem Fall ist die [TemplateBinding-Markup Erweiterung](templatebinding-markup-extension.md) tatsächlich eine Kurzform für den folgenden Bindungs Ausdruck: `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding`-oder `{RelativeSource TemplatedParent}` Verwendungen sind sowohl innerhalb des XAML-Codes, der eine Vorlage definiert, nicht relevant. Weitere Informationen finden Sie unter [TemplateBinding-Markup Erweiterung](templatebinding-markup-extension.md).

`{RelativeSource FindAncestor}` wird hauptsächlich in Steuerelement Vorlagen oder vorhersagbaren eigenständigen UI-Kompositionen verwendet, in Fällen, in denen ein Steuerelement immer in einer visuellen Struktur eines bestimmten Vorgänger Typs zu erwarten ist. Beispielsweise können Elemente eines Elementsteuerelements `FindAncestor`-Verwendungen zum Binden an Eigenschaften des übergeordneten Vorgängers des Elementsteuerelements verwenden. Oder Elemente, die Teil der Steuerelementzusammensetzung in einer Vorlage sind, können `FindAncestor`-Bindungen mit übergeordneten Elemente in derselben Kompositionsstruktur verwenden.

In der Objektelementsyntax für den `FindAncestor`-Modus, wie in den XAML-Syntaxabschnitten dargestellt, wird die zweite Objektelementsyntax speziell für den `FindAncestor`-Modus verwendet. Der `FindAncestor`-Modus erfordert einen <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Wert. Sie müssen <xref:System.Windows.Data.RelativeSource.AncestorType%2A> als Attribut festlegen, indem Sie einen [x:Type-Markup Erweiterungs](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) Verweis auf den Typ des übergeordneten Elements festlegen, nach dem gesucht werden soll. Der <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Wert wird verwendet, wenn die Bindungsanforderung zur Laufzeit verarbeitet wird.

Im `FindAncestor`-Modus kann die optionale Eigenschaft <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> dazu beitragen, die Vorgängersuche in den Fällen eindeutig zu machen, in denen eventuell mehr als ein Vorgänger dieses Typs in der Elementstruktur vorhanden ist.

Weitere Informationen zur Verwendung des `FindAncestor`-Modus finden Sie unter <xref:System.Windows.Data.RelativeSource>.

`{RelativeSource Self}` ist für Szenarien nützlich, in denen eine Eigenschaft einer Instanz von dem Wert einer anderen Eigenschaft derselben Instanz abhängen sollte und keine allgemeine Beziehung der Abhängigkeits Eigenschaft (z. b. Umwandlung) zwischen diesen beiden Eigenschaften vorhanden ist. Obwohl es selten vorkommt, dass zwei Eigenschaften für ein Objekt vorhanden sind, sodass die Werte buchstäblich identisch sind (und identisch typisiert sind), können Sie auch einen `Converter` Parameter auf eine Bindung anwenden, die über `{RelativeSource Self}`verfügt, und den Konverter verwenden, um zwischen Quell-und Zieltyp zu konvertieren. Ein anderes Szenario für `{RelativeSource Self}` ist als Teil einer <xref:System.Windows.MultiDataTrigger>.

Beispielsweise definiert der folgende XAML-Code ein <xref:System.Windows.Shapes.Rectangle>-Element so, dass unabhängig davon, welcher Wert für <xref:System.Windows.FrameworkElement.Width%2A> eingegeben wird, <xref:System.Windows.Shapes.Rectangle> immer ein Quadrat ist: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`

`{RelativeSource PreviousData}` ist entweder in Datenvorlagen oder in Fällen nützlich, in denen Bindungen eine Auflistung als Datenquelle verwenden. Mit `{RelativeSource PreviousData}` können Sie Beziehungen zwischen benachbarten Datenelementen in der Auflistung hervorheben. Eine verwandte Methode besteht darin, eine <xref:System.Windows.Data.MultiBinding> zwischen dem aktuellen und vorherigen Element in der Datenquelle herzustellen und mit einem Konverter für diese Bindung die Differenz zwischen den beiden Elementen und deren Eigenschaften zu ermitteln.

Im folgenden Beispiel zeigt der erste <xref:System.Windows.Controls.TextBlock> in der Elementvorlage die aktuelle Zahl an. Die zweite <xref:System.Windows.Controls.TextBlock> Bindung ist ein <xref:System.Windows.Data.MultiBinding>, der nominale zwei <xref:System.Windows.Data.Binding>-Bestandteile hat: der aktuelle Datensatz und eine Bindung, die den vorherigen Datensatz absichtlich mithilfe `{RelativeSource PreviousData}`verwendet. Anschließend berechnet ein Konverter in der <xref:System.Windows.Data.MultiBinding> den Unterschied und gibt ihn an die Bindung zurück.

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

Die Beschreibung der Datenbindung als Konzept wird hier nicht behandelt. Informationen hierzu finden Sie unter [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Prozessor Implementierung wird die Handhabung dieser Markup Erweiterung durch die <xref:System.Windows.Data.RelativeSource>-Klasse definiert.

`RelativeSource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markup Erweiterungen in XAML verwenden die `{`-und `}` Zeichen in der Attribut Syntax. Dies ist die Konvention, mit der ein XAML-Prozessor erkennt, dass das Attribut von einer Markup Erweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.Binding>
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Bindungsdeklarationen](../data/binding-declarations-overview.md)
- [x:Type-Markuperweiterung](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
