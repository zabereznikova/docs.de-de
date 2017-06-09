---
title: "RelativeSource-Markuperweiterung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RelativeSource"
helpviewer_keywords: 
  - "RelativeSource-Markuperweiterungen"
  - "XAML, RelativeSource-Markuperweiterung"
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# RelativeSource-Markuperweiterung
Gibt die Eigenschaften einer <xref:System.Windows.Data.RelativeSource>\-Bindungsquelle an, die innerhalb einer [Bindung als Markuperweiterung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) oder beim Festlegen der <xref:System.Windows.Data.Binding.RelativeSource%2A>\-Eigenschaft eines in XAML eingerichteten <xref:System.Windows.Data.Binding>\-Elements verwendet werden soll.  
  
## Verwendung von XAML\-Attributen  
  
```  
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>  
```  
  
## XAML\-Attributverwendung \(geschachtelt innerhalb der Bindungserweiterung\)  
  
```  
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>  
```  
  
## Verwendung von XAML\-Objektelementen  
  
```  
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource Mode="modeEnumValue"/>  
  </Binding.RelativeSource>  
</Binding>  
- or   
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource  
      Mode="FindAncestor"  
      AncestorType="{x:Type typeName}"  
      AncestorLevel="intLevel"  
    />  
  </Binding.RelativeSource>  
</Binding>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`modeEnumValue`|Eine der folgenden:<br /><br /> -   Das Zeichenfolgentoken `Self`; entspricht einer <xref:System.Windows.Data.RelativeSource>, die mit einer auf <xref:System.Windows.Data.RelativeSourceMode> festgelegten Eigenschaft <xref:System.Windows.Data.RelativeSource.Mode%2A> erstellt wurde.<br />-   Das Zeichenfolgentoken `TemplatedParent`; entspricht einer <xref:System.Windows.Data.RelativeSource>, die mit einer auf <xref:System.Windows.Data.RelativeSourceMode> festgelegten Eigenschaft <xref:System.Windows.Data.RelativeSource.Mode%2A> erstellt wurde.<br />-   Das Zeichenfolgentoken `PreviousData`; entspricht einer <xref:System.Windows.Data.RelativeSource>, die mit einer auf <xref:System.Windows.Data.RelativeSourceMode> festgelegten Eigenschaft <xref:System.Windows.Data.RelativeSource.Mode%2A> erstellt wurde.<br />-   Weitere Informationen über den `FindAncestor`\-Modus finden Sie unten.|  
|`FindAncestor`|Die Tokenzeichenfolge `FindAncestor`.  Bei Verwendung dieses Tokens wird ein Modus aktiviert, in dem eine `RelativeSource` einen Vorgängertyp und optional eine Vorgängerebene angibt.  Dies entspricht einer <xref:System.Windows.Data.RelativeSource>, die mit einer auf <xref:System.Windows.Data.RelativeSourceMode> festgelegten <xref:System.Windows.Data.RelativeSource.Mode%2A>\-Eigenschaft erstellt wurde.|  
|`typeName`|Erforderlich für `FindAncestor`\-Modus.  Der Name eines Typs, der die <xref:System.Windows.Data.RelativeSource.AncestorType%2A>\-Eigenschaft auffüllt.|  
|`intLevel`|Optional für `FindAncestor`\-Modus.  Eine Vorgängerebene \(ausgewertet bezüglich der übergeordneten Richtung in der logischen Struktur\).|  
  
## Hinweise  
 `{RelativeSource TemplatedParent}`\-Bindungsverwendungen sind eine wichtige Technik für ein größeres Konzept der Trennung von Benutzeroberfläche und Logik eines Steuerelements.  Dies ermöglicht die Bindung aus der Vorlagendefinition mit dem vorlagenbasierten übergeordneten Element \(der Laufzeitobjektinstanz, in der die Vorlage angewendet wird\).  In diesem Fall ist [TemplateBinding\-Markuperweiterung](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) tatsächlich eine Kurznotation für den folgenden Bindungsausdruck: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.  Die Verwendung von `TemplateBinding` oder `{RelativeSource TemplatedParent}` ist jeweils nur innerhalb der XAML relevant, die eine Vorlage definiert.  Weitere Informationen finden Sie unter [TemplateBinding\-Markuperweiterung](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)  
  
 `{RelativeSource FindAncestor}` wird hauptsächlich in Steuerelementvorlagen oder vorhersagbaren unabhängigen Benutzeroberflächenzusammensetzungen für Fälle verwendet, in denen ein Steuerelement immer in einer visuellen Struktur eines bestimmten Vorgängertyps erwartet wird.  Beispielsweise können Elemente eines Elementsteuerelements `FindAncestor`\-Verwendungen zum Binden an Eigenschaften des übergeordneten Vorgängers des Elementsteuerelements verwenden.  Oder Elemente, die Teil der Steuerelementzusammensetzung in einer Vorlage sind, können `FindAncestor`\-Bindungen mit übergeordneten Elemente in derselben Kompositionsstruktur verwenden.  
  
 In der Objektelementsyntax für den `FindAncestor`\-Modus, wie in den XAML\-Syntaxabschnitten dargestellt, wird die zweite Objektelementsyntax speziell für den `FindAncestor`\-Modus verwendet.  Der `FindAncestor`\-Modus erfordert einen <xref:System.Windows.Data.RelativeSource.AncestorType%2A>\-Wert.  Sie müssen <xref:System.Windows.Data.RelativeSource.AncestorType%2A> als Attribut festlegen, unter Verwendung eines [x:Type\-Markuperweiterung](../../../../docs/framework/xaml-services/x-type-markup-extension.md)\-Verweises auf den Vorgängertyp, nach dem gesucht werden soll.  Der <xref:System.Windows.Data.RelativeSource.AncestorType%2A>\-Wert wird verwendet, wenn die Bindungsanforderung zur Laufzeit verarbeitet wird.  
  
 Im `FindAncestor`\-Modus kann die optionale Eigenschaft <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> dazu beitragen, die Vorgängersuche in den Fällen eindeutig zu machen, in denen eventuell mehr als ein Vorgänger dieses Typs in der Elementstruktur vorhanden ist.  
  
 Weitere Informationen zur Verwendung des `FindAncestor`\-Modus finden Sie unter <xref:System.Windows.Data.RelativeSource>.  
  
 `{RelativeSource Self}` ist für Szenarien nützlich, in denen eine Eigenschaft einer Instanz vom Wert einer anderen Eigenschaft derselben Instanz abhängen soll und noch kein allgemeines Abhängigkeitseigenschaftenverhältnis \(beispielsweise Koersion\) zwischen diesen beiden Eigenschaften vorhanden ist.  Obwohl es selten vorkommt, dass für zwei Eigenschaften eines Objekts die Werte buchstäblich identisch \(und vom gleichen Typ\) sind, können Sie einen `Converter`\-Parameter auch auf eine Bindung mit `{RelativeSource Self}` anwenden, und mit dem Konverter zwischen Quell\- und Zieltypen konvertieren.  Ein anderes Szenario für `{RelativeSource Self}` ist Teil von <xref:System.Windows.MultiDataTrigger>.  
  
 Beispielsweise definiert der folgende XAML\-Code ein <xref:System.Windows.Shapes.Rectangle>\-Element so, dass unabhängig davon, welcher Wert für <xref:System.Windows.FrameworkElement.Width%2A> eingegeben wird, <xref:System.Windows.Shapes.Rectangle> immer ein Quadrat ist: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`  
  
 `{RelativeSource PreviousData}` ist entweder in Datenvorlagen oder in Fällen hilfreich, in denen Bindungen eine Auflistung als Datenquelle verwenden.  Sie können `{RelativeSource PreviousData}` verwenden, um Beziehungen zwischen angrenzenden Datenelementen in der Auflistung hervorzuheben.  Eine verwandte Methode besteht darin, eine <xref:System.Windows.Data.MultiBinding> zwischen dem aktuellen und vorherigen Element in der Datenquelle herzustellen und mit einem Konverter für diese Bindung die Differenz zwischen den beiden Elementen und deren Eigenschaften zu ermitteln.  
  
 Im folgenden Beispiel zeigt der erste <xref:System.Windows.Controls.TextBlock> in der Elementvorlage die aktuelle Zahl an.  Die zweite <xref:System.Windows.Controls.TextBlock>\-Bindung ist eine <xref:System.Windows.Data.MultiBinding>, die nominell zwei <xref:System.Windows.Data.Binding>\-Bestandteile besitzt – den aktuellen Datensatz und eine Bindung, die absichtlich den vorherigen Datensatz mithilfe von `{RelativeSource PreviousData}` verwendet.  Anschließend berechnet ein Konverter in der <xref:System.Windows.Data.MultiBinding> den Unterschied und gibt ihn an die Bindung zurück.  
  
```  
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
  
 Das Konzept der Datenbindung wird hier nicht erläutert. Informationen hierzu finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-XAML\-Prozessorimplementierung wird die Handhabung dieser Markuperweiterung durch die <xref:System.Windows.Data.RelativeSource>\-Klasse definiert.  
  
 `RelativeSource` ist eine Markuperweiterung.  Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.  Alle Markuperweiterungen in XAML verwenden die Zeichen `{` und `}` in der Attributsyntax. Dies ist die Konvention, durch die ein XAML\-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss.  Weitere Informationen finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Siehe auch  
 <xref:System.Windows.Data.Binding>   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Übersicht über Bindungsdeklarationen](../../../../docs/framework/wpf/data/binding-declarations-overview.md)   
 [x:Type\-Markuperweiterung](../../../../docs/framework/xaml-services/x-type-markup-extension.md)