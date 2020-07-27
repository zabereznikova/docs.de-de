---
title: RelativeSource-Markuperweiterung
description: Gibt Eigenschaften einer RelativeSource-Bindungs Quelle innerhalb einer Bindungs Markup Erweiterung an oder wenn die RelativeSource-Eigenschaft einer Bindung in XAML festgelegt wird.
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 2da702d23413651a85b45404e088f6708546cc25
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165936"
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="94d44-103">RelativeSource-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="94d44-103">RelativeSource MarkupExtension</span></span>

<span data-ttu-id="94d44-104">Gibt Eigenschaften einer <xref:System.Windows.Data.RelativeSource> Bindungs Quelle an, die innerhalb einer [Bindungs Markup Erweiterung](binding-markup-extension.md)verwendet werden sollen, oder, wenn die- <xref:System.Windows.Data.Binding.RelativeSource%2A> Eigenschaft eines <xref:System.Windows.Data.Binding> in XAML eingerichteten-Elements festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="94d44-104">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="94d44-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="94d44-105">XAML Attribute Usage</span></span>

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" ... />
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="94d44-106">XAML-Attributverwendung (geschachtelt innerhalb der Bindungserweiterung)</span><span class="sxs-lookup"><span data-stu-id="94d44-106">XAML Attribute Usage (nested within Binding extension)</span></span>

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" ... />
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="94d44-107">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="94d44-107">XAML Object Element Usage</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

<span data-ttu-id="94d44-108">Oder</span><span class="sxs-lookup"><span data-stu-id="94d44-108">-or-</span></span>

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

## <a name="xaml-values"></a><span data-ttu-id="94d44-109">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="94d44-109">XAML Values</span></span>

|||
|-|-|
|`modeEnumValue`|<span data-ttu-id="94d44-110">Einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="94d44-110">One of the following:</span></span><br /><br /> <span data-ttu-id="94d44-111">-Das Zeichen folgen Token `Self` . entspricht einem, das erstellt wird, <xref:System.Windows.Data.RelativeSource> wobei die- <xref:System.Windows.Data.RelativeSource.Mode%2A> Eigenschaft auf festgelegt ist <xref:System.Windows.Data.RelativeSourceMode.Self> .</span><span class="sxs-lookup"><span data-stu-id="94d44-111">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="94d44-112">-Das Zeichen folgen Token `TemplatedParent` . entspricht einem, das erstellt wird, <xref:System.Windows.Data.RelativeSource> wobei die- <xref:System.Windows.Data.RelativeSource.Mode%2A> Eigenschaft auf festgelegt ist <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent> .</span><span class="sxs-lookup"><span data-stu-id="94d44-112">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="94d44-113">-Das Zeichen folgen Token `PreviousData` . entspricht einem, das erstellt wird, <xref:System.Windows.Data.RelativeSource> wobei die- <xref:System.Windows.Data.RelativeSource.Mode%2A> Eigenschaft auf festgelegt ist <xref:System.Windows.Data.RelativeSourceMode.PreviousData> .</span><span class="sxs-lookup"><span data-stu-id="94d44-113">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="94d44-114">-Weitere Informationen zum-Modus finden Sie unten `FindAncestor` .</span><span class="sxs-lookup"><span data-stu-id="94d44-114">-   See below for information on `FindAncestor` mode.</span></span>|
|`FindAncestor`|<span data-ttu-id="94d44-115">Die Tokenzeichenfolge `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="94d44-115">The string token `FindAncestor`.</span></span> <span data-ttu-id="94d44-116">Bei Verwendung dieses Tokens wird ein Modus aktiviert, in dem eine `RelativeSource` einen Vorgängertyp und optional eine Vorgängerebene angibt.</span><span class="sxs-lookup"><span data-stu-id="94d44-116">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="94d44-117">Dies entspricht einer <xref:System.Windows.Data.RelativeSource>, die mit einer auf <xref:System.Windows.Data.RelativeSource.Mode%2A> festgelegten <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>-Eigenschaft erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="94d44-117">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|
|`typeName`|<span data-ttu-id="94d44-118">Erforderlich für `FindAncestor`-Modus.</span><span class="sxs-lookup"><span data-stu-id="94d44-118">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="94d44-119">Der Name eines Typs, der die <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Eigenschaft auffüllt.</span><span class="sxs-lookup"><span data-stu-id="94d44-119">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|
|`intLevel`|<span data-ttu-id="94d44-120">Optional für `FindAncestor`-Modus.</span><span class="sxs-lookup"><span data-stu-id="94d44-120">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="94d44-121">Eine Vorgängerebene (ausgewertet bezüglich der übergeordneten Richtung in der logischen Struktur).</span><span class="sxs-lookup"><span data-stu-id="94d44-121">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|

## <a name="remarks"></a><span data-ttu-id="94d44-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="94d44-122">Remarks</span></span>

<span data-ttu-id="94d44-123">`{RelativeSource TemplatedParent}`Bindungs Verwendungen sind eine wichtige Technik, die ein größeres Konzept der Trennung der Benutzeroberfläche eines Steuer Elements und der Logik eines Steuer Elements adressiert.</span><span class="sxs-lookup"><span data-stu-id="94d44-123">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="94d44-124">Dies ermöglicht die Bindung aus der Vorlagendefinition mit dem vorlagenbasierten übergeordneten Element (der Laufzeitobjektinstanz, in der die Vorlage angewendet wird).</span><span class="sxs-lookup"><span data-stu-id="94d44-124">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="94d44-125">In diesem Fall ist die [TemplateBinding-Markup Erweiterung](templatebinding-markup-extension.md) tatsächlich eine Kurzform für den folgenden Bindungs Ausdruck: `{Binding RelativeSource={RelativeSource TemplatedParent}}` .</span><span class="sxs-lookup"><span data-stu-id="94d44-125">For this case, the [TemplateBinding Markup Extension](templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="94d44-126">`TemplateBinding`die-oder- `{RelativeSource TemplatedParent}` Verwendungen sind sowohl innerhalb des XAML-Codes, der eine Vorlage definiert, nur relevant.</span><span class="sxs-lookup"><span data-stu-id="94d44-126">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="94d44-127">Weitere Informationen finden Sie unter [TemplateBinding-Markup Erweiterung](templatebinding-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="94d44-127">For more information, see [TemplateBinding Markup Extension](templatebinding-markup-extension.md).</span></span>

<span data-ttu-id="94d44-128">`{RelativeSource FindAncestor}`wird hauptsächlich in Steuerelement Vorlagen oder vorhersagbaren eigenständigen UI-Kompositionen verwendet, in Fällen, in denen ein Steuerelement immer in einer visuellen Struktur eines bestimmten Vorgänger Typs zu erwarten ist.</span><span class="sxs-lookup"><span data-stu-id="94d44-128">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="94d44-129">Beispielsweise können Elemente eines Elementsteuerelements `FindAncestor`-Verwendungen zum Binden an Eigenschaften des übergeordneten Vorgängers des Elementsteuerelements verwenden.</span><span class="sxs-lookup"><span data-stu-id="94d44-129">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="94d44-130">Oder Elemente, die Teil der Steuerelementzusammensetzung in einer Vorlage sind, können `FindAncestor`-Bindungen mit übergeordneten Elemente in derselben Kompositionsstruktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="94d44-130">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>

<span data-ttu-id="94d44-131">In der Objektelementsyntax für den `FindAncestor`-Modus, wie in den XAML-Syntaxabschnitten dargestellt, wird die zweite Objektelementsyntax speziell für den `FindAncestor`-Modus verwendet.</span><span class="sxs-lookup"><span data-stu-id="94d44-131">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="94d44-132">Der `FindAncestor`-Modus erfordert einen <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Wert.</span><span class="sxs-lookup"><span data-stu-id="94d44-132">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="94d44-133">Sie müssen <xref:System.Windows.Data.RelativeSource.AncestorType%2A> als Attribut festlegen, indem Sie [einen x:Type-Markup Erweiterungs](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) Verweis auf den Typ des übergeordneten Elements festlegen, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="94d44-133">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="94d44-134">Der <xref:System.Windows.Data.RelativeSource.AncestorType%2A>-Wert wird verwendet, wenn die Bindungsanforderung zur Laufzeit verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="94d44-134">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>

<span data-ttu-id="94d44-135">Im `FindAncestor`-Modus kann die optionale Eigenschaft <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> dazu beitragen, die Vorgängersuche in den Fällen eindeutig zu machen, in denen eventuell mehr als ein Vorgänger dieses Typs in der Elementstruktur vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="94d44-135">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>

<span data-ttu-id="94d44-136">Weitere Informationen zur Verwendung des `FindAncestor`-Modus finden Sie unter <xref:System.Windows.Data.RelativeSource>.</span><span class="sxs-lookup"><span data-stu-id="94d44-136">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>

<span data-ttu-id="94d44-137">`{RelativeSource Self}`ist nützlich für Szenarien, in denen eine Eigenschaft einer Instanz von dem Wert einer anderen Eigenschaft derselben Instanz abhängen sollte und keine allgemeine Beziehung der Abhängigkeits Eigenschaft (z. b. Umwandlung) zwischen diesen beiden Eigenschaften vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="94d44-137">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="94d44-138">Obwohl es selten vorkommt, dass zwei Eigenschaften für ein Objekt vorhanden sind, sodass die Werte buchstäblich identisch sind (und identisch typisiert sind), können Sie auch einen `Converter` Parameter auf eine Bindung anwenden, die über verfügt, `{RelativeSource Self}` und den Konverter verwenden, um zwischen Quell-und Zieltyp zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="94d44-138">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="94d44-139">Ein anderes Szenario für `{RelativeSource Self}` ist als Teil von <xref:System.Windows.MultiDataTrigger> .</span><span class="sxs-lookup"><span data-stu-id="94d44-139">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>

<span data-ttu-id="94d44-140">Beispielsweise definiert der folgende XAML-Code ein <xref:System.Windows.Shapes.Rectangle>-Element so, dass unabhängig davon, welcher Wert für <xref:System.Windows.FrameworkElement.Width%2A> eingegeben wird, <xref:System.Windows.Shapes.Rectangle> immer ein Quadrat ist: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span><span class="sxs-lookup"><span data-stu-id="94d44-140">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>

<span data-ttu-id="94d44-141">`{RelativeSource PreviousData}`ist entweder in Datenvorlagen oder in Fällen nützlich, in denen Bindungen eine Auflistung als Datenquelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="94d44-141">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="94d44-142">Sie können verwenden `{RelativeSource PreviousData}` , um Beziehungen zwischen benachbarten Datenelementen in der Auflistung hervorzuheben.</span><span class="sxs-lookup"><span data-stu-id="94d44-142">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="94d44-143">Eine verwandte Methode besteht darin, eine <xref:System.Windows.Data.MultiBinding> zwischen dem aktuellen und vorherigen Element in der Datenquelle herzustellen und mit einem Konverter für diese Bindung die Differenz zwischen den beiden Elementen und deren Eigenschaften zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="94d44-143">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>

<span data-ttu-id="94d44-144">Im folgenden Beispiel zeigt der erste <xref:System.Windows.Controls.TextBlock> in der Elementvorlage die aktuelle Zahl an.</span><span class="sxs-lookup"><span data-stu-id="94d44-144">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="94d44-145">Die zweite <xref:System.Windows.Controls.TextBlock> Bindung ist eine <xref:System.Windows.Data.MultiBinding> , die nominale zwei <xref:System.Windows.Data.Binding> Bestandteile hat: der aktuelle Datensatz und eine Bindung, die den vorherigen Daten Satz absichtlich mithilfe von verwendet `{RelativeSource PreviousData}` .</span><span class="sxs-lookup"><span data-stu-id="94d44-145">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> constituents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="94d44-146">Anschließend berechnet ein Konverter in der <xref:System.Windows.Data.MultiBinding> den Unterschied und gibt ihn an die Bindung zurück.</span><span class="sxs-lookup"><span data-stu-id="94d44-146">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>

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
</ListBox>
```

<span data-ttu-id="94d44-147">Die Beschreibung der Datenbindung als Konzept wird hier nicht behandelt. Informationen hierzu finden Sie unter [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="94d44-147">Describing data binding as a concept is not covered here, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="94d44-148">In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Prozessor Implementierung wird die Handhabung dieser Markup Erweiterung durch die- <xref:System.Windows.Data.RelativeSource> Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="94d44-148">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>

<span data-ttu-id="94d44-149">`RelativeSource` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="94d44-149">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="94d44-150">Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="94d44-150">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="94d44-151">Alle Markup Erweiterungen in XAML verwenden die `{` `}` Zeichen und in der Attribut Syntax. dabei handelt es sich um die Konvention, mit der ein XAML-Prozessor erkennt, dass das Attribut von einer Markup Erweiterung verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="94d44-151">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="94d44-152">Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="94d44-152">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="94d44-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94d44-153">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="94d44-154">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="94d44-154">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="94d44-155">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="94d44-155">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="94d44-156">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="94d44-156">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="94d44-157">Übersicht über die Datenbindung</span><span class="sxs-lookup"><span data-stu-id="94d44-157">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="94d44-158">Übersicht über Bindungsdeklarationen</span><span class="sxs-lookup"><span data-stu-id="94d44-158">Binding Declarations Overview</span></span>](../data/binding-declarations-overview.md)
- [<span data-ttu-id="94d44-159">x:typmarkup Erweiterung</span><span class="sxs-lookup"><span data-stu-id="94d44-159">x:Type Markup Extension</span></span>](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
