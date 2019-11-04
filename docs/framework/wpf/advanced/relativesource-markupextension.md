---
title: RelativeSource-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 28f3aa500014b768bd07723511613a42df8689aa
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458773"
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="e5200-102">RelativeSource-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="e5200-102">RelativeSource MarkupExtension</span></span>

<span data-ttu-id="e5200-103">Gibt Eigenschaften einer <xref:System.Windows.Data.RelativeSource> Bindungs Quelle an, die innerhalb einer [Bindungs Markup Erweiterung](binding-markup-extension.md)verwendet werden sollen, oder, wenn die <xref:System.Windows.Data.Binding.RelativeSource%2A>-Eigenschaft eines <xref:System.Windows.Data.Binding> Elements festgelegt wird, das in XAML festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="e5200-103">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="e5200-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="e5200-104">XAML Attribute Usage</span></span>

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="e5200-105">XAML-Attributverwendung (geschachtelt innerhalb der Bindungserweiterung)</span><span class="sxs-lookup"><span data-stu-id="e5200-105">XAML Attribute Usage (nested within Binding extension)</span></span>

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="e5200-106">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="e5200-106">XAML Object Element Usage</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

<span data-ttu-id="e5200-107">- oder -</span><span class="sxs-lookup"><span data-stu-id="e5200-107">-or-</span></span>

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

## <a name="xaml-values"></a><span data-ttu-id="e5200-108">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="e5200-108">XAML Values</span></span>

|||
|-|-|
|`modeEnumValue`|<span data-ttu-id="e5200-109">Eine der folgenden:</span><span class="sxs-lookup"><span data-stu-id="e5200-109">One of the following:</span></span><br /><br /> <span data-ttu-id="e5200-110">-Das Zeichen folgen Token `Self`; entspricht einer <xref:System.Windows.Data.RelativeSource>, die erstellt wird, wobei die <xref:System.Windows.Data.RelativeSource.Mode%2A>-Eigenschaft auf <xref:System.Windows.Data.RelativeSourceMode.Self>festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e5200-110">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="e5200-111">-Das Zeichen folgen Token `TemplatedParent`; entspricht einer <xref:System.Windows.Data.RelativeSource>, die erstellt wird, wobei die <xref:System.Windows.Data.RelativeSource.Mode%2A>-Eigenschaft auf <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e5200-111">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="e5200-112">-Das Zeichen folgen Token `PreviousData`; entspricht einer <xref:System.Windows.Data.RelativeSource>, die erstellt wird, wobei die <xref:System.Windows.Data.RelativeSource.Mode%2A>-Eigenschaft auf <xref:System.Windows.Data.RelativeSourceMode.PreviousData>festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e5200-112">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="e5200-113">-Weitere Informationen zum `FindAncestor` Modus finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="e5200-113">-   See below for information on `FindAncestor` mode.</span></span>|
|`FindAncestor`|<span data-ttu-id="e5200-114">Die Tokenzeichenfolge `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="e5200-114">The string token `FindAncestor`.</span></span> <span data-ttu-id="e5200-115">Bei Verwendung dieses Tokens wird ein Modus aktiviert, in dem eine `RelativeSource` einen Vorgängertyp und optional eine Vorgängerebene angibt.</span><span class="sxs-lookup"><span data-stu-id="e5200-115">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="e5200-116">Dies entspricht einer <xref:System.Windows.Data.RelativeSource>, die mit einer auf <xref:System.Windows.Data.RelativeSource.Mode%2A> festgelegten <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>-Eigenschaft erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e5200-116">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|
|`typeName`|<span data-ttu-id="e5200-117">Erforderlich für `FindAncestor`-Modus.</span><span class="sxs-lookup"><span data-stu-id="e5200-117">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="e5200-118">Der Name eines Typs, der die <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Eigenschaft auffüllt.</span><span class="sxs-lookup"><span data-stu-id="e5200-118">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|
|`intLevel`|<span data-ttu-id="e5200-119">Optional für `FindAncestor`-Modus.</span><span class="sxs-lookup"><span data-stu-id="e5200-119">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="e5200-120">Eine Vorgängerebene (ausgewertet bezüglich der übergeordneten Richtung in der logischen Struktur).</span><span class="sxs-lookup"><span data-stu-id="e5200-120">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|

## <a name="remarks"></a><span data-ttu-id="e5200-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5200-121">Remarks</span></span>

<span data-ttu-id="e5200-122">`{RelativeSource TemplatedParent}` Bindungs Verwendungen sind eine wichtige Technik, die ein größeres Konzept der Trennung der Benutzeroberfläche eines Steuer Elements und der Logik eines Steuer Elements adressiert.</span><span class="sxs-lookup"><span data-stu-id="e5200-122">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="e5200-123">Dies ermöglicht die Bindung aus der Vorlagendefinition mit dem vorlagenbasierten übergeordneten Element (der Laufzeitobjektinstanz, in der die Vorlage angewendet wird).</span><span class="sxs-lookup"><span data-stu-id="e5200-123">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="e5200-124">In diesem Fall ist die [TemplateBinding-Markup Erweiterung](templatebinding-markup-extension.md) tatsächlich eine Kurzform für den folgenden Bindungs Ausdruck: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span><span class="sxs-lookup"><span data-stu-id="e5200-124">For this case, the [TemplateBinding Markup Extension](templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="e5200-125">`TemplateBinding`-oder `{RelativeSource TemplatedParent}` Verwendungen sind sowohl innerhalb des XAML-Codes, der eine Vorlage definiert, nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="e5200-125">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="e5200-126">Weitere Informationen finden Sie unter [TemplateBinding-Markup Erweiterung](templatebinding-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="e5200-126">For more information, see [TemplateBinding Markup Extension](templatebinding-markup-extension.md).</span></span>

<span data-ttu-id="e5200-127">`{RelativeSource FindAncestor}` wird hauptsächlich in Steuerelement Vorlagen oder vorhersagbaren eigenständigen UI-Kompositionen verwendet, in Fällen, in denen ein Steuerelement immer in einer visuellen Struktur eines bestimmten Vorgänger Typs zu erwarten ist.</span><span class="sxs-lookup"><span data-stu-id="e5200-127">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="e5200-128">Beispielsweise können Elemente eines Elementsteuerelements `FindAncestor`-Verwendungen zum Binden an Eigenschaften des übergeordneten Vorgängers des Elementsteuerelements verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5200-128">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="e5200-129">Oder Elemente, die Teil der Steuerelementzusammensetzung in einer Vorlage sind, können `FindAncestor`-Bindungen mit übergeordneten Elemente in derselben Kompositionsstruktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5200-129">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>

<span data-ttu-id="e5200-130">In der Objektelementsyntax für den `FindAncestor`-Modus, wie in den XAML-Syntaxabschnitten dargestellt, wird die zweite Objektelementsyntax speziell für den `FindAncestor`-Modus verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5200-130">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="e5200-131">Der `FindAncestor`-Modus erfordert einen <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Wert.</span><span class="sxs-lookup"><span data-stu-id="e5200-131">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="e5200-132">Sie müssen <xref:System.Windows.Data.RelativeSource.AncestorType%2A> als Attribut festlegen, indem Sie einen [x:Type-Markup Erweiterungs](../../xaml-services/x-type-markup-extension.md) Verweis auf den Typ des übergeordneten Elements festlegen, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5200-132">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../xaml-services/x-type-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="e5200-133">Der <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Wert wird verwendet, wenn die Bindungsanforderung zur Laufzeit verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="e5200-133">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>

<span data-ttu-id="e5200-134">Im `FindAncestor`-Modus kann die optionale Eigenschaft <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> dazu beitragen, die Vorgängersuche in den Fällen eindeutig zu machen, in denen eventuell mehr als ein Vorgänger dieses Typs in der Elementstruktur vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e5200-134">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>

<span data-ttu-id="e5200-135">Weitere Informationen zur Verwendung des `FindAncestor`-Modus finden Sie unter <xref:System.Windows.Data.RelativeSource>.</span><span class="sxs-lookup"><span data-stu-id="e5200-135">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>

<span data-ttu-id="e5200-136">`{RelativeSource Self}` ist für Szenarien nützlich, in denen eine Eigenschaft einer Instanz von dem Wert einer anderen Eigenschaft derselben Instanz abhängen sollte und keine allgemeine Beziehung der Abhängigkeits Eigenschaft (z. b. Umwandlung) zwischen diesen beiden Eigenschaften vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e5200-136">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="e5200-137">Obwohl es selten vorkommt, dass zwei Eigenschaften für ein Objekt vorhanden sind, sodass die Werte buchstäblich identisch sind (und identisch typisiert sind), können Sie auch einen `Converter` Parameter auf eine Bindung anwenden, die über `{RelativeSource Self}`verfügt, und den Konverter verwenden, um zwischen Quelle und Ziel zu konvertieren. solche.</span><span class="sxs-lookup"><span data-stu-id="e5200-137">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="e5200-138">Ein anderes Szenario für `{RelativeSource Self}` ist als Teil einer <xref:System.Windows.MultiDataTrigger>.</span><span class="sxs-lookup"><span data-stu-id="e5200-138">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>

<span data-ttu-id="e5200-139">Beispielsweise definiert der folgende XAML-Code ein <xref:System.Windows.Shapes.Rectangle>-Element so, dass unabhängig davon, welcher Wert für <xref:System.Windows.FrameworkElement.Width%2A> eingegeben wird, <xref:System.Windows.Shapes.Rectangle> immer ein Quadrat ist: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span><span class="sxs-lookup"><span data-stu-id="e5200-139">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>

<span data-ttu-id="e5200-140">`{RelativeSource PreviousData}` ist entweder in Datenvorlagen oder in Fällen nützlich, in denen Bindungen eine Auflistung als Datenquelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5200-140">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="e5200-141">Mit `{RelativeSource PreviousData}` können Sie Beziehungen zwischen benachbarten Datenelementen in der Auflistung hervorheben.</span><span class="sxs-lookup"><span data-stu-id="e5200-141">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="e5200-142">Eine verwandte Methode besteht darin, eine <xref:System.Windows.Data.MultiBinding> zwischen dem aktuellen und vorherigen Element in der Datenquelle herzustellen und mit einem Konverter für diese Bindung die Differenz zwischen den beiden Elementen und deren Eigenschaften zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e5200-142">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>

<span data-ttu-id="e5200-143">Im folgenden Beispiel zeigt der erste <xref:System.Windows.Controls.TextBlock> in der Elementvorlage die aktuelle Zahl an.</span><span class="sxs-lookup"><span data-stu-id="e5200-143">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="e5200-144">Die zweite <xref:System.Windows.Controls.TextBlock> Bindung ist ein <xref:System.Windows.Data.MultiBinding>, der nominale zwei <xref:System.Windows.Data.Binding>-Bestandteile hat: der aktuelle Datensatz und eine Bindung, die den vorherigen Datensatz absichtlich mithilfe `{RelativeSource PreviousData}`verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5200-144">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> constituents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="e5200-145">Anschließend berechnet ein Konverter in der <xref:System.Windows.Data.MultiBinding> den Unterschied und gibt ihn an die Bindung zurück.</span><span class="sxs-lookup"><span data-stu-id="e5200-145">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>

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

<span data-ttu-id="e5200-146">Die Beschreibung der Datenbindung als Konzept wird hier nicht behandelt. Informationen hierzu finden Sie unter [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e5200-146">Describing data binding as a concept is not covered here, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="e5200-147">In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Prozessor Implementierung wird die Handhabung dieser Markup Erweiterung durch die <xref:System.Windows.Data.RelativeSource>-Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="e5200-147">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>

<span data-ttu-id="e5200-148">`RelativeSource` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="e5200-148">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="e5200-149">Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5200-149">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="e5200-150">Alle Markup Erweiterungen in XAML verwenden die `{`-und `}` Zeichen in der Attribut Syntax. Dies ist die Konvention, mit der ein XAML-Prozessor erkennt, dass das Attribut von einer Markup Erweiterung verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="e5200-150">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="e5200-151">Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="e5200-151">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e5200-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5200-152">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="e5200-153">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="e5200-153">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="e5200-154">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="e5200-154">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="e5200-155">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="e5200-155">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="e5200-156">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="e5200-156">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="e5200-157">Übersicht über Bindungsdeklarationen</span><span class="sxs-lookup"><span data-stu-id="e5200-157">Binding Declarations Overview</span></span>](../data/binding-declarations-overview.md)
- [<span data-ttu-id="e5200-158">x:Type-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="e5200-158">x:Type Markup Extension</span></span>](../../xaml-services/x-type-markup-extension.md)
