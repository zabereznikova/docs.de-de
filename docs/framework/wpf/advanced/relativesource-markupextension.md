---
title: RelativeSource-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 77caa7c84f63f90ae83df5685f93ba6d18f7436f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548265"
---
# <a name="relativesource-markupextension"></a>RelativeSource-Markuperweiterung
Gibt die Eigenschaften einer <xref:System.Windows.Data.RelativeSource> Bindungsquelle in verwendet werden eine [-Markuperweiterung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md), oder beim Festlegen der <xref:System.Windows.Data.Binding.RelativeSource%2A> Eigenschaft ein <xref:System.Windows.Data.Binding> Element hergestellt, die in XAML.  
  
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
- or   
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
|`modeEnumValue`|Eine der folgenden:<br /><br /> -Das Zeichenfolgentoken, das `Self`; entspricht einem <xref:System.Windows.Data.RelativeSource> mit erstellt seine <xref:System.Windows.Data.RelativeSource.Mode%2A> -Eigenschaftensatz auf <xref:System.Windows.Data.RelativeSourceMode.Self>.<br />-Das Zeichenfolgentoken, das `TemplatedParent`; entspricht einem <xref:System.Windows.Data.RelativeSource> mit erstellt seine <xref:System.Windows.Data.RelativeSource.Mode%2A> -Eigenschaftensatz auf <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.<br />-Das Zeichenfolgentoken, das `PreviousData`; entspricht einem <xref:System.Windows.Data.RelativeSource> mit erstellt seine <xref:System.Windows.Data.RelativeSource.Mode%2A> -Eigenschaftensatz auf <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.<br />-Informationen finden Sie unten auf `FindAncestor` Modus.|  
|`FindAncestor`|Die Tokenzeichenfolge `FindAncestor`. Bei Verwendung dieses Tokens wird ein Modus aktiviert, in dem eine `RelativeSource` einen Vorgängertyp und optional eine Vorgängerebene angibt. Dies entspricht einer <xref:System.Windows.Data.RelativeSource>, die mit einer auf <xref:System.Windows.Data.RelativeSource.Mode%2A> festgelegten <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>-Eigenschaft erstellt wurde.|  
|`typeName`|Erforderlich für `FindAncestor`-Modus. Der Name eines Typs, der die <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Eigenschaft auffüllt.|  
|`intLevel`|Optional für `FindAncestor`-Modus. Eine Vorgängerebene (ausgewertet bezüglich der übergeordneten Richtung in der logischen Struktur).|  
  
## <a name="remarks"></a>Hinweise  
 `{RelativeSource TemplatedParent}` Bindung Verwendungen handelt es sich um einen Schlüssel Technik, die ein größeres Konzept der Trennung von ein Steuerelement-Benutzeroberfläche und die Logik des Steuerelements behandelt. Dies ermöglicht die Bindung aus der Vorlagendefinition mit dem vorlagenbasierten übergeordneten Element (der Laufzeitobjektinstanz, in der die Vorlage angewendet wird). Für diesen Fall die [TemplateBinding Markuperweiterung](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) ist tatsächlich eine Kurzform für die folgenden Bindungsausdruck: `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding` oder `{RelativeSource TemplatedParent}` Verwendungen nur relevant, in der XAML-Code, der eine Vorlage definiert sind. Weitere Informationen finden Sie unter [TemplateBinding-Markuperweiterung](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)  
  
 `{RelativeSource FindAncestor}` wird hauptsächlich in Steuerelementvorlagen oder vorhersagbare geschlossene UI Kompositionen für Fälle verwendet, in denen ein Steuerelement immer in einer visuellen Struktur eines bestimmten Typs Vorgänger erwartet wird. Beispielsweise können Elemente eines Elementsteuerelements `FindAncestor`-Verwendungen zum Binden an Eigenschaften des übergeordneten Vorgängers des Elementsteuerelements verwenden. Oder Elemente, die Teil der Steuerelementzusammensetzung in einer Vorlage sind, können `FindAncestor`-Bindungen mit übergeordneten Elemente in derselben Kompositionsstruktur verwenden.  
  
 In der Objektelementsyntax für den `FindAncestor`-Modus, wie in den XAML-Syntaxabschnitten dargestellt, wird die zweite Objektelementsyntax speziell für den `FindAncestor`-Modus verwendet. Der `FindAncestor`-Modus erfordert einen <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Wert. Sie müssen festlegen, <xref:System.Windows.Data.RelativeSource.AncestorType%2A> als ein Attribut mit einer [X: Type-Markuperweiterung](../../../../docs/framework/xaml-services/x-type-markup-extension.md) Verweis auf den Typ des übergeordneten Elements für. Der <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Wert wird verwendet, wenn die Bindungsanforderung zur Laufzeit verarbeitet wird.  
  
 Im `FindAncestor`-Modus kann die optionale Eigenschaft <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> dazu beitragen, die Vorgängersuche in den Fällen eindeutig zu machen, in denen eventuell mehr als ein Vorgänger dieses Typs in der Elementstruktur vorhanden ist.  
  
 Weitere Informationen zur Verwendung des `FindAncestor`-Modus finden Sie unter <xref:System.Windows.Data.RelativeSource>.  
  
 `{RelativeSource Self}` eignet sich für Szenarien, in denen eine Eigenschaft einer Instanz hängen vom Wert einer anderen Eigenschaft von der gleichen Instanz und keine allgemeine abhängigkeitsbeziehung des-Eigenschaft (z. B. Koersion) bereits sollte zwischen diesen beiden Eigenschaften vorhanden ist. Zwar selten, dass zwei Eigenschaften auf ein Objekt vorhanden sein, so, dass die Werte identisch sind (und identisch typisiert werden), können Sie auch Anwenden einer `Converter` Parameter einer Bindung, die hat `{RelativeSource Self}`, und verwenden Sie den Konverter zum Konvertieren zwischen Quelle und Zieltypen. Ein weiteres Szenario für `{RelativeSource Self}` ist als Teil einer <xref:System.Windows.MultiDataTrigger>.  
  
 Beispielsweise definiert der folgende XAML-Code ein <xref:System.Windows.Shapes.Rectangle>-Element so, dass unabhängig davon, welcher Wert für <xref:System.Windows.FrameworkElement.Width%2A> eingegeben wird, <xref:System.Windows.Shapes.Rectangle> immer ein Quadrat ist: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`  
  
 `{RelativeSource PreviousData}` ist nützlich, in Datenvorlagen oder in Fällen, in denen Bindungen eine Auflistung als Datenquelle verwenden. Sie können `{RelativeSource PreviousData}` um Beziehungen zwischen angrenzenden Datenelemente in der Auflistung zu markieren. Eine verwandte Methode besteht darin, eine <xref:System.Windows.Data.MultiBinding> zwischen dem aktuellen und vorherigen Element in der Datenquelle herzustellen und mit einem Konverter für diese Bindung die Differenz zwischen den beiden Elementen und deren Eigenschaften zu ermitteln.  
  
 Im folgenden Beispiel zeigt der erste <xref:System.Windows.Controls.TextBlock> in der Elementvorlage die aktuelle Zahl an. Die zweite <xref:System.Windows.Controls.TextBlock> Bindung ist eine <xref:System.Windows.Data.MultiBinding> , die nominell verfügt über zwei <xref:System.Windows.Data.Binding> -Bestandteile besitzt: den aktuellen Datensatz und eine Bindung, den vorherigen Datensatz mit absichtlich verwendet `{RelativeSource PreviousData}`. Anschließend berechnet ein Konverter in der <xref:System.Windows.Data.MultiBinding> den Unterschied und gibt ihn an die Bindung zurück.  
  
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
  
 Binden von Daten beschreiben, wie ein Konzept hier nicht behandelt wird finden Sie unter [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -XAML-Prozessor-Implementierung, die Handhabung für diese Markuperweiterung wird definiert, indem die <xref:System.Windows.Data.RelativeSource> Klasse.  
  
 `RelativeSource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in der Attributsyntax normalerweise wird mit dem ein XAML-Prozessor erkennt, dass das Attribut eine Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Data.Binding>  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Übersicht über Bindungsdeklarationen](../../../../docs/framework/wpf/data/binding-declarations-overview.md)  
 [x:Type-Markuperweiterung](../../../../docs/framework/xaml-services/x-type-markup-extension.md)
