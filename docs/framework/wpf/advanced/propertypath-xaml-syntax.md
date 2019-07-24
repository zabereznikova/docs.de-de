---
title: XAML-Syntax von PropertyPath
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: deebdb690a6ba831730701de2608089af2d6bdfd
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401657"
---
# <a name="propertypath-xaml-syntax"></a>XAML-Syntax von PropertyPath

Das <xref:System.Windows.PropertyPath> -Objekt unterstützt eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] komplexe Inline Syntax zum Festlegen verschiedener Eigenschaften, <xref:System.Windows.PropertyPath> die den-Typ als Wert annehmen. In diesem Thema wird <xref:System.Windows.PropertyPath> die Syntax beschrieben, die für die Bindungs-und Animations Syntax verwendet wird.

<a name="where"></a>

## <a name="where-propertypath-is-used"></a>Verwendung von PropertyPath

<xref:System.Windows.PropertyPath>ist ein gängiges Objekt, das in mehreren [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Features verwendet wird. Trotz der allgemeinen <xref:System.Windows.PropertyPath> Verwendung von, um Eigenschafts Pfadinformationen zu übermitteln, variieren die Verwendungen für jeden Funktionsbereich, in dem <xref:System.Windows.PropertyPath> als Typ verwendet wird. Daher ist es praktischer, die Syntaxen pro Funktion zu dokumentieren.

In erster Linie <xref:System.Windows.PropertyPath>verwendet, um Objektmodell Pfade zum Durchlaufen der Eigenschaften einer Objektdaten Quelle zu beschreiben und den Zielpfad für gezielte Animationen zu beschreiben. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]

Einige Stil-und Vorlagen Eigenschaften, <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> wie z. b., verwenden einen qualifizierten Eigenschaftsnamen, der einem <xref:System.Windows.PropertyPath>sehr ähnlich ist Dies ist jedoch nicht der Fall <xref:System.Windows.PropertyPath>, da es sich um einen qualifizierten *Besitzer handelt.* die Verwendung des Eigenschaften Zeichen folgen Formats, das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vom WPF-Prozessor in Kombination <xref:System.Windows.DependencyProperty>mit dem Typkonverter für aktiviert wird.

<a name="databinding_s"></a>

## <a name="propertypath-for-objects-in-data-binding"></a>PropertyPath für Objekte in der Datenbindung

Datenbindung ist eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktion, bei der Sie an den Zielwert einer beliebigen Abhängigkeitseigenschaft binden können. Allerdings muss die Quelle einer solchen Datenbindung keine Abhängigkeitseigenschaft sein. Es kann sich um einen beliebigen Eigenschaftstyp handeln, der vom Anwendungsdatenanbieter erkannt wird. Eigenschafts Pfade werden insbesondere für das <xref:System.Windows.Data.ObjectDataProvider>verwendet, das zum Abrufen von Bindungs Quellen von Common Language Runtime (CLR)-Objekten und deren Eigenschaften verwendet wird.

Beachten Sie, dass die [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Datenbindung an <xref:System.Windows.PropertyPath>nicht verwendet, da Sie nicht <xref:System.Windows.Data.Binding.Path%2A> in <xref:System.Windows.Data.Binding>verwendet wird. Verwenden <xref:System.Windows.Data.Binding.XPath%2A> Sie stattdessen, und geben Sie eine gültige XPath- [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] Syntax in der der Daten an. <xref:System.Windows.Data.Binding.XPath%2A>wird auch als Zeichenfolge angegeben, aber hier nicht dokumentiert. Weitere Informationen finden [Sie unterbinden an XML-Daten mithilfe von XmlDataProvider und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).

Für das Verständnis von Eigenschaftspfaden in der Datenbindung ist es wichtig zu wissen, dass Sie einen individuellen Eigenschaftswert als Ziel für die Bindung festlegen oder stattdessen Bindung zu Zieleigenschaften herstellen können, die Listen oder Auflistungen verwenden. Wenn Sie Auflistungen binden, beispielsweise die <xref:System.Windows.Controls.ListBox> Bindung a, die abhängig von der Anzahl der Datenelemente in der Auflistung erweitert wird, sollte der Eigenschafts Pfad auf das Auflistungs Objekt und nicht auf einzelne Auflistungs Elemente verweisen. Das Daten Bindungs Modul passt die Auflistung, die als Datenquelle verwendet wird, automatisch an den Typ des Bindungs Ziels an, was zu einem Verhalten führt, <xref:System.Windows.Controls.ListBox> wie z. b. das Auffüllen eines mit einem Element Array.

<a name="singlecurrent"></a>

### <a name="single-property-on-the-immediate-object-as-data-context"></a>Einzelne Eigenschaft auf dem unmittelbaren Objekt als Datenkontext

```xml
<Binding Path="propertyName" .../>
```

*propertyName* muss in den Namen einer Eigenschaft aufgelöst werden, die in der aktuellen <xref:System.Windows.FrameworkElement.DataContext%2A> für eine <xref:System.Windows.Data.Binding.Path%2A> Verwendung ist. Wenn die Bindung die Quelle aktualisiert, müssen für diese Eigenschaft Schreib- und Leseberechtigungen festgelegt sein, und das Quellobjekt muss geändert werden können.

<a name="singleindex"></a>

### <a name="single-indexer-on-the-immediate-object-as-data-context"></a>Einzelner Indexer auf dem unmittelbaren Objekt als Datenkontext

```xml
<Binding Path="[key]" .../>
```

`key` muss der eingegebene Index zu einem Wörterbuch oder einer Hashtabelle oder der ganzzahlige Index eines Arrays sein. Zudem muss der Wert des Schlüssels ein Typ sein, der direkt an die Eigenschaft, auf die er angewendet wird, gebunden werden kann. Beispielsweise kann eine Hash Tabelle, die Zeichen folgen Schlüssel und Zeichen folgen Werte enthält, auf diese Weise zum Binden an Text <xref:System.Windows.Controls.TextBox>für eine verwendet werden. Wenn der Schlüssel auf eine Auflistung oder einen Unterindex verweist, können Sie mit dieser Syntax eine Bindung zu einer Zielauflistungseigenschaft herstellen. Andernfalls müssen Sie mithilfe einer Syntax wie `<Binding Path="[key].propertyName" .../>` auf eine bestimmte Eigenschaft verweisen.

Sie können falls erforderlich den Typ des Index angeben. Ausführliche Informationen zu diesem Aspekt eines indizierten Eigenschafts Pfads <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>finden Sie unter.

<a name="multipleindirect"></a>

### <a name="multiple-property-indirect-property-targeting"></a>Mehrere Eigenschaften (indirekte Eigenschaftsziele)

```xml
<Binding Path="propertyName.propertyName2" .../>
```

`propertyName`muss in den Namen einer Eigenschaft aufgelöst werden, die der aktuelle <xref:System.Windows.FrameworkElement.DataContext%2A>ist. Bei den Pfadeigenschaften `propertyName` und `propertyName2` kann es sich um alle Eigenschaften handeln, die in einer Beziehung vorhanden sind, wobei `propertyName2` eine Eigenschaft in dem Typ ist, der dem Wert von `propertyName` entspricht.

<a name="singleattached"></a>

### <a name="single-property-attached-or-otherwise-type-qualified"></a>Einzelne angefügte oder anderweitig typqualifizierte Eigenschaft

```xml
<object property="(ownerType.propertyName)" .../>
```

Die Klammern geben an, dass diese Eigenschaft in einem <xref:System.Windows.PropertyPath> mit einer Teilqualifikation erstellt werden soll. Es kann ein XML-Namespace verwendet werden, um den Typ mit einer entsprechenden Zuordnung zu suchen. Die `ownerType` sucht Typen, auf [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] die ein Prozessor Zugriff hat, durch <xref:System.Windows.Markup.XmlnsDefinitionAttribute> die Deklarationen in den einzelnen Assemblys. In den meisten Anwendungen ist dem [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]-Namespace der XML-Standardnamespace zugeordnet. Ein Präfix ist daher normalerweise nur für benutzerdefinierte Typen oder andere Typen erforderlich, die sich anderweitig außerhalb dieses Namespace befinden.  `propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die im `ownerType`-Objekt vorhanden ist. Diese Syntax wird in der Regel für einen der folgenden Fälle verwendet:

- Der Pfad wird in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] angegeben, d.h. in einem Stil oder einer Vorlage, die keinen spezifischen Zieltyp aufweist. Eine qualifizierte Verwendung ist normalerweise in anderen Fällen als diesem nicht zulässig, da in Fällen ohne Stil bzw. Vorlage die Eigenschaft in einer Instanz anstatt in einem Typ enthalten ist.

- Die Eigenschaft ist eine angefügte Eigenschaft.

- Sie binden an eine statische Eigenschaft.

Zur Verwendung als Storyboard-Ziel muss die als `propertyName` angegebene Eigenschaft eine <xref:System.Windows.DependencyProperty>sein.

<a name="sourcetraversal"></a>

### <a name="source-traversal-binding-to-hierarchies-of-collections"></a>Quellendurchlauf (Binden an Auflistungshierarchien)

```xml
<object Path="propertyName/propertyNameX" .../>
```

Das Zeichen / in dieser Syntax ermöglicht die Navigation in einem hierarchischen Datenquellenobjekt. In der Hierarchie werden mehrere Schritte mit aufeinanderfolgenden Schrägstrichen (/) unterstützt. Der Quellendurchlauf kennzeichnet die Zeigerposition des aktuellen Datensatzes, welche durch die Synchronisation der Daten mit der Benutzeroberfläche der Ansicht ermittelt wird. Weitere Informationen zum Binden mit hierarchischen Datenquellenobjekten und zur Bedeutung des Zeigers für den aktuellen Datensatz in der Datenbindung finden Sie unter [Verwenden des Master-Detail-Musters mit hierarchischen Daten](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) und [Übersicht über die Datenbindung](../data/data-binding-overview.md).

> [!NOTE]
> Auf den ersten Blick ähnelt diese Syntax [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]. Ein true [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] -Ausdruck für die Bindung [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] an eine Datenquelle <xref:System.Windows.Data.Binding.Path%2A> wird nicht als Wert verwendet und sollte stattdessen für die sich gegenseitig <xref:System.Windows.Data.Binding.XPath%2A> ausschließende Eigenschaft verwendet werden.

### <a name="collection-views"></a>Auflistungsansichten

Stellen Sie dem Namen der Auflistungsansicht das Hashzeichen (`#`) voran, um auf eine benannte Auflistungsansicht zu verweisen.

### <a name="current-record-pointer"></a>Zeiger auf den aktuellen Datensatz

Beginnen Sie die Pfadzeichenfolge mit einem Schrägstrich (`/`), um für eine Auflistungsansicht oder ein Master-Detail-Datenbindungsszenario auf den Zeiger für den aktuellen Datensatz zu verweisen. Ein beliebiger Pfad nach dem Schrägstrich wird ab dem Zeiger auf den aktuellen Datensatz durchlaufen.

### <a name="multiple-indexers"></a>Mehrere Indexer

```xaml
<object Path="[index1,index2...]" .../>
```

oder

```xaml
<object Path="propertyName[index,index2...]" .../>
```

Wenn ein bestimmtes Objekt mehrere Indexer unterstützt, können diese Indexer in der richtigen Reihenfolge angegeben werden, ähnlich wie ein Array, das auf Syntax verweist. Bei diesem Objekt kann es sich entweder um den aktuellen Kontext oder um den Wert einer Eigenschaft handeln, die ein Objekt mit mehreren Indizes enthält.

In der Standardeinstellung werden die Indexerwerte durch Verwendung der Eigenschaften des zugrunde liegenden Objekts eingegeben. Sie können falls erforderlich den Typ des Index angeben. Weitere Informationen zum Eingeben der Indexer finden <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>Sie unter.

<a name="mixing"></a>

### <a name="mixing-syntaxes"></a>Kombinieren von Syntaxen

Jede der oben angegebenen Syntaxen kann mit einer anderen Syntax kombiniert werden. Im folgenden Beispiel wird ein Eigenschafts Pfad zu der Farbe eines bestimmten x, y `ColorGrid` einer Eigenschaft erstellt, die ein Pixelraster Array von <xref:System.Windows.Media.SolidColorBrush> -Objekten enthält:

```xml
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" .../>
```

### <a name="escapes-for-property-path-strings"></a>Escapezeichen für Eigenschaftspfadzeichenfolgen

Bei bestimmten Geschäftsobjekten kann es vorkommen, dass die Eigenschaftspfadzeichenfolge eine Escapesequenz erfordert, um ordnungsgemäß analysiert werden zu können. Der Bedarf an Escapezeichen sollte gering sein, da viele dieser Zeichen ähnliche Benennungsinteraktionsprobleme in Sprachen aufweisen, die normalerweise verwendet werden würden, um das Geschäftsobjekt zu definieren.

- In Indexern ([ ]) dient das Caretzeichen (^) als Escapezeichen für das nächste Zeichen.

- Sie müssen bestimmte Zeichen (mit XML-Entitäten), die für die XML-Sprachdefinition von besonderer Bedeutung sind, mit Escapezeichen versehen. Verwenden Sie `&`, um das Zeichen „&“ mit Escapezeichen zu versehen. Verwenden Sie `>`, um das Endtag „>“ mit Escapezeichen zu versehen.

- Sie müssen Escapezeichen (mit dem umgekehrten Schrägstrich `\`) zu Zeichen hinzufügen, die für das WPF-XAML-Parserverhalten beim Verarbeiten einer Markuperweiterung von besonderer Bedeutung sind.

  - Der umgekehrte Schrägstrich (`\`) ist das eigentliche Escapezeichen.

  - Das Gleichheitszeichen (`=`) trennt den Eigenschaftsnamen vom Eigenschaftswert.

  - Das Komma (`,`) trennt Eigenschaften.

  - Die rechte geschweifte Klammer (`}`) gibt das Ende einer Markuperweiterung an.

> [!NOTE]
> Technisch gesehen funktionieren diese Escapezeichen auch für einen Storyboardeigenschaftspfad, aber da Sie normalerweise Objektmodelle für vorhandene WPF-Objekte durchlaufen, sollten Escapezeichen unnötig sein.

<a name="databinding_sa"></a>

## <a name="propertypath-for-animation-targets"></a>PropertyPath für Animationsziele

Die Ziel Eigenschaft einer Animation muss eine Abhängigkeits Eigenschaft sein, die entweder einen <xref:System.Windows.Freezable> oder einen primitiven Typ annimmt. Die Zieleigenschaft für einen Typ und gegebenenfalls die animierte Eigenschaft können sich jedoch auf unterschiedlichen Objekten befinden. Bei Animationen wird ein Eigenschaftspfad verwendet, um die Verbindung zwischen der Eigenschaft des benannten Animationszielobjekts und der Eigenschaft der gewünschten Zielanimation zu definieren. Hierzu werden die Objekteigenschaftsbeziehungen in den Eigenschaftswerten durchlaufen.

<a name="general"></a>

### <a name="general-object-property-considerations-for-animations"></a>Allgemeine Überlegungen zu Objekteigenschaften für Animationen

Weitere Informationen zu Animationskonzepten im Allgemeinen finden Sie unter [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md) und [Übersicht über Animationen](../graphics-multimedia/animation-overview.md).

Der Werttyp oder die zu animierende Eigenschaft muss <xref:System.Windows.Freezable> entweder ein Typ oder ein primitiv sein. Die Eigenschaft, die den Pfad startet, muss in den Namen einer Abhängigkeits Eigenschaft aufgelöst werden, die für <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> den angegebenen Typ vorhanden ist.

Um das <xref:System.Windows.Freezable> Klonen zum Animieren eines zu unterstützen, das bereits eingefroren ist, muss das von <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> angegebene Objekt eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitete Klasse sein.

<a name="singlestepanim"></a>

### <a name="single-property-on-the-target-object"></a>Einzelne Eigenschaft auf dem Zielobjekt

```xml
<animation Storyboard.TargetProperty="propertyName" .../>
```

`propertyName`muss in den Namen einer Abhängigkeits Eigenschaft aufgelöst werden, die für den angegebenen <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Typ vorhanden ist.

<a name="indirectanim"></a>

### <a name="indirect-property-targeting"></a>Indirekte Eigenschaftsziele

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>
```

`propertyName`muss eine Eigenschaft sein, bei der es <xref:System.Windows.Freezable> sich entweder um einen Werttyp oder um einen primitiven <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> handelt, der für den angegebenen Typ vorhanden ist.

`propertyName2` muss der Name einer Abhängigkeitseigenschaft sein, die auf dem Objekt vorhanden ist, das dem Wert von `propertyName` entspricht. Anders ausgedrückt, `propertyName2` muss als eine Abhängigkeits Eigenschaft für den Typ vorhanden sein, der `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>ist.

Die indirekte Verwendung von Animationen als Ziel ist aufgrund der angewendeten Stile und Vorlagen erforderlich. Um eine Animation als Ziel festzustellen, benötigen Sie <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> einen für ein Zielobjekt, und dieser Name wird von [x:Name](../../xaml-services/x-name-directive.md) oder <xref:System.Windows.FrameworkElement.Name%2A>festgelegt. Vorlagen- und Stilelemente können zwar ebenfalls Namen haben, aber diese Namen sind nur innerhalb des Namescope des Stils bzw. der Vorlage gültig. (Wenn Vorlagen und Stile den gleichen Namescope wie das Anwendungsmarkup verwenden würden, wären die Namen nicht eindeutig. Die Stile und Vorlagen würden dann von verschiedenen Instanzen gleichzeitig verwendet werden und würden doppelte Namen weitergeben.) Wenn die spezifischen Eigenschaften eines zu animierenden Elements aus einem Stil oder einer Vorlage stammen, müssen Sie daher mit einer benannten Elementinstanz beginnen, die nicht aus der Formatvorlage stammt, und dann als Ziel die visuelle Struktur des Stils oder der Vorlage angeben, um zu der Eigenschaft zu gelangen, die Sie animieren möchten.

Beispielsweise <xref:System.Windows.Controls.Panel> ist die <xref:System.Windows.Controls.Panel.Background%2A> -Eigenschaft eines ein kompletter <xref:System.Windows.Media.Brush> (tatsächlich ein <xref:System.Windows.Media.SolidColorBrush>), der aus einer Designvorlage stammt. Um einen <xref:System.Windows.Media.Brush> vollständig zu animieren, muss eine BrushAnimation (wahrscheinlich eine für jeden <xref:System.Windows.Media.Brush> Typ) vorhanden sein, und es ist kein solcher Typ vorhanden. Um einen Pinsel zu animieren, animieren Sie stattdessen die Eigenschaften eines <xref:System.Windows.Media.Brush> bestimmten Typs. Sie müssen sich von <xref:System.Windows.Media.SolidColorBrush> <xref:System.Windows.Media.SolidColorBrush.Color%2A> zu einem bewegen, um eine <xref:System.Windows.Media.Animation.ColorAnimation> dort anzuwendende. Der Eigenschaftspfad für dieses Beispiel wäre `Background.Color`.

<a name="attachedanim"></a>

### <a name="attached-properties"></a>Angefügte Eigenschaften

```xml
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>
```

Die Klammern geben an, dass diese Eigenschaft in einem <xref:System.Windows.PropertyPath> mit einer Teilqualifikation erstellt werden soll. Es kann ein XML-Namespace verwendet werden, um nach dem Typ zu suchen. Die `ownerType` sucht Typen, auf [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] die ein Prozessor Zugriff hat, durch <xref:System.Windows.Markup.XmlnsDefinitionAttribute> die Deklarationen in den einzelnen Assemblys. In den meisten Anwendungen ist dem [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]-Namespace der XML-Standardnamespace zugeordnet. Ein Präfix ist daher normalerweise nur für benutzerdefinierte Typen oder andere Typen erforderlich, die sich anderweitig außerhalb dieses Namespace befinden. `propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die im `ownerType`-Objekt vorhanden ist. Die als `propertyName` angegebene Eigenschaft muss eine <xref:System.Windows.DependencyProperty>sein. (Alle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] angefügten Eigenschaften werden als Abhängigkeitseigenschaften implementiert, weshalb dies nur bei benutzerdefinierten, angefügten Eigenschaften relevant ist.)

<a name="indexanim"></a>

### <a name="indexers"></a>Indexer

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>
```

Ein Indexer wird <xref:System.Windows.Freezable> von den meisten Abhängigkeits Eigenschaften oder-Typen nicht unterstützt. Indexer können deshalb in einem Animationspfad nur an einer Zwischenposition zwischen der Eigenschaft, mit der die Kette am benannten Ziel beginnt, und gegebenenfalls der animierten Eigenschaft verwendet werden. In der dargestellten Syntax ist dies `propertyName2`. Beispielsweise <xref:System.Windows.Media.TransformGroup> `RenderTransform.Children[1].Angle`kann eine Indexer-Verwendung erforderlich sein, wenn die zwischen Eigenschaft eine Auflistung wie ist, z. b. in einem Eigenschafts Pfad, z. b.

<a name="ppincode"></a>

## <a name="propertypath-in-code"></a>PropertyPath im Code

Die Code Verwendung <xref:System.Windows.PropertyPath>für, einschließlich der Vorgehensweise <xref:System.Windows.PropertyPath>zum Erstellen eines, ist im Referenz Thema <xref:System.Windows.PropertyPath>für dokumentiert.

Im allgemeinen <xref:System.Windows.PropertyPath> ist so konzipiert, dass zwei verschiedene Konstruktoren verwendet werden: eine für die Bindungs Verwendungen und die einfachste Animations Verwendungen und eine für die komplexe Animations Verwendungen. Verwenden Sie <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> die Signatur für Bindungs Verwendungen, bei denen das Objekt eine Zeichenfolge ist. Verwenden Sie <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> die Signatur für Animations Pfade mit einem Schritt, bei denen das Objekt <xref:System.Windows.DependencyProperty>ein ist. Verwenden Sie <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> die Signatur für komplexe Animationen. Dieser zweite Konstruktor verwendet eine Tokenzeichenfolge für den ersten Parameter und ein Array von Objekten, die Positionen in der Tokenzeichenfolge füllen, um eine Eigenschaftspfadbeziehung zu definieren.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.PropertyPath>
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md)
