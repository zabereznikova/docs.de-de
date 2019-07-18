---
title: XAML-Syntax von PropertyPath
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: 5dc8fc8c43e43691c46ad84379fe2bcb23987667
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67660797"
---
# <a name="propertypath-xaml-syntax"></a>XAML-Syntax von PropertyPath

Die <xref:System.Windows.PropertyPath> Objekt unterstützt eine komplexe [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Syntax für das Festlegen verschiedener Eigenschaften, die annehmen der <xref:System.Windows.PropertyPath> -Typ als Wert. Dieses Thema dokumentiert die <xref:System.Windows.PropertyPath> Syntax auf die Bindungs- und animationssyntax Syntaxen angewendet.

<a name="where"></a>

## <a name="where-propertypath-is-used"></a>Verwendung von PropertyPath

<xref:System.Windows.PropertyPath> ist ein allgemeines Objekt, das in mehreren verwendet wird [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Funktionen. Obwohl das allgemeine <xref:System.Windows.PropertyPath> um Informationen zu vermitteln, die Verwendungen für jeden Funktionsbereich, in denen <xref:System.Windows.PropertyPath> wird verwendet, wie ein Typ variieren. Daher ist es praktischer, die Syntaxen pro Funktion zu dokumentieren.

In erster Linie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet <xref:System.Windows.PropertyPath> um Objektmodellpfade zum Durchlaufen der Eigenschaften einer Objektdatenquelle zu beschreiben und den Zielpfad für zielgerichtete Animationen anzugeben.

Einige Stil- und Vorlageneigenschaften wie z. B. <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> nehmen einen qualifizierten Eigenschaftsnamen, die ersten Blick ähnelt einem <xref:System.Windows.PropertyPath>. Dies ist jedoch keiner echten <xref:System.Windows.PropertyPath>; er stellt vielmehr eine qualifizierte *owner.property* Zeichenfolgenformats, die durch den WPF-aktiviert ist [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Prozessor in Kombination mit den Typkonverter für <xref:System.Windows.DependencyProperty>.

<a name="databinding_s"></a>

## <a name="propertypath-for-objects-in-data-binding"></a>PropertyPath für Objekte in der Datenbindung

Datenbindung ist eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktion, bei der Sie an den Zielwert einer beliebigen Abhängigkeitseigenschaft binden können. Allerdings muss die Quelle einer solchen Datenbindung keine Abhängigkeitseigenschaft sein. Es kann sich um einen beliebigen Eigenschaftstyp handeln, der vom Anwendungsdatenanbieter erkannt wird. Eigenschaftspfade werden vor allem verwendet, für die <xref:System.Windows.Data.ObjectDataProvider>, dient zum Abrufen von Bindungsquellen aus [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekte und deren Eigenschaften.

Beachten Sie, dass die Datenbindung zu [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] verwendet keine <xref:System.Windows.PropertyPath>, da sie nicht verwendet <xref:System.Windows.Data.Binding.Path%2A> in die <xref:System.Windows.Data.Binding>. Verwenden Sie stattdessen <xref:System.Windows.Data.Binding.XPath%2A> , und geben Sie gültigen XPath-Syntax der [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] der Daten. <xref:System.Windows.Data.Binding.XPath%2A> wird auch als Zeichenfolge angegeben, aber hier nicht dokumentiert; finden Sie unter [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).

Für das Verständnis von Eigenschaftspfaden in der Datenbindung ist es wichtig zu wissen, dass Sie einen individuellen Eigenschaftswert als Ziel für die Bindung festlegen oder stattdessen Bindung zu Zieleigenschaften herstellen können, die Listen oder Auflistungen verwenden. Wenn Sie Auflistungen binden, z. B. die Bindung einer <xref:System.Windows.Controls.ListBox> , die abhängig von der Anzahl von Datenelementen in der Auflistung erweitert, und klicken Sie dann der Eigenschaftspfad sollten die Collection-Objekt, das nicht auf einzelne Auflistungselemente verweisen. Der Datenbindungs-Engine entspricht die Auflistung verwendet, wie die Daten automatisch in den Typ des Bindungsziels Verhalten Source wie das Auffüllen einer <xref:System.Windows.Controls.ListBox> mit einem Elementarray.

<a name="singlecurrent"></a>

### <a name="single-property-on-the-immediate-object-as-data-context"></a>Einzelne Eigenschaft auf dem unmittelbaren Objekt als Datenkontext

```xml
<Binding Path="propertyName" .../>
```

*PropertyName* muss aufgelöst werden, werden den Namen einer Eigenschaft, die in der aktuellen <xref:System.Windows.FrameworkElement.DataContext%2A> für eine <xref:System.Windows.Data.Binding.Path%2A> Nutzung. Wenn die Bindung die Quelle aktualisiert, müssen für diese Eigenschaft Schreib- und Leseberechtigungen festgelegt sein, und das Quellobjekt muss geändert werden können.

<a name="singleindex"></a>

### <a name="single-indexer-on-the-immediate-object-as-data-context"></a>Einzelner Indexer auf dem unmittelbaren Objekt als Datenkontext

```xml
<Binding Path="[key]" .../>
```

`key` muss der eingegebene Index zu einem Wörterbuch oder einer Hashtabelle oder der ganzzahlige Index eines Arrays sein. Zudem muss der Wert des Schlüssels ein Typ sein, der direkt an die Eigenschaft, auf die er angewendet wird, gebunden werden kann. Beispielsweise eine Hashtabelle mit Zeichenfolgenschlüsseln und Zeichenfolgenwerten kann verwendet werden auf diese Weise zum Binden an den Text für ein <xref:System.Windows.Controls.TextBox>. Wenn der Schlüssel auf eine Auflistung oder einen Unterindex verweist, können Sie mit dieser Syntax eine Bindung zu einer Zielauflistungseigenschaft herstellen. Andernfalls müssen Sie mithilfe einer Syntax wie `<Binding Path="[key].propertyName" .../>` auf eine bestimmte Eigenschaft verweisen.

Sie können falls erforderlich den Typ des Index angeben. Weitere Informationen zu diesem Aspekt eines indizierten eigenschaftspfads finden Sie unter <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.

<a name="multipleindirect"></a>

### <a name="multiple-property-indirect-property-targeting"></a>Mehrere Eigenschaften (indirekte Eigenschaftsziele)

```xml
<Binding Path="propertyName.propertyName2" .../>
```

`propertyName` muss in den Namen einer Eigenschaft zu sein, die der aktuelle aufgelöst <xref:System.Windows.FrameworkElement.DataContext%2A>. Bei den Pfadeigenschaften `propertyName` und `propertyName2` kann es sich um alle Eigenschaften handeln, die in einer Beziehung vorhanden sind, wobei `propertyName2` eine Eigenschaft in dem Typ ist, der dem Wert von `propertyName` entspricht.

<a name="singleattached"></a>

### <a name="single-property-attached-or-otherwise-type-qualified"></a>Einzelne angefügte oder anderweitig typqualifizierte Eigenschaft

```xml
<object property="(ownerType.propertyName)" .../>
```

Die Klammern zeigen an, die diese Eigenschaft in einem <xref:System.Windows.PropertyPath> mit einer partiellen Qualifikation erstellt werden sollten. Es kann ein XML-Namespace verwendet werden, um den Typ mit einer entsprechenden Zuordnung zu suchen. Die `ownerType` sucht Typen, die eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Prozessor zugreifen kann, bis die <xref:System.Windows.Markup.XmlnsDefinitionAttribute> -Deklarationen in jeder Assembly. In den meisten Anwendungen ist dem [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]-Namespace der XML-Standardnamespace zugeordnet. Ein Präfix ist daher normalerweise nur für benutzerdefinierte Typen oder andere Typen erforderlich, die sich anderweitig außerhalb dieses Namespace befinden.  `propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die im `ownerType`-Objekt vorhanden ist. Diese Syntax wird in der Regel für einen der folgenden Fälle verwendet:

- Der Pfad wird in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] angegeben, d.h. in einem Stil oder einer Vorlage, die keinen spezifischen Zieltyp aufweist. Eine qualifizierte Verwendung ist normalerweise in anderen Fällen als diesem nicht zulässig, da in Fällen ohne Stil bzw. Vorlage die Eigenschaft in einer Instanz anstatt in einem Typ enthalten ist.

- Die Eigenschaft ist eine angefügte Eigenschaft.

- Sie binden an eine statische Eigenschaft.

Für die Verwendung als Storyboardziel, die Eigenschaft angegeben, als `propertyName` muss eine <xref:System.Windows.DependencyProperty>.

<a name="sourcetraversal"></a>

### <a name="source-traversal-binding-to-hierarchies-of-collections"></a>Quellendurchlauf (Binden an Auflistungshierarchien)

```xml
<object Path="propertyName/propertyNameX" .../>
```

Das Zeichen / in dieser Syntax ermöglicht die Navigation in einem hierarchischen Datenquellenobjekt. In der Hierarchie werden mehrere Schritte mit aufeinanderfolgenden Schrägstrichen (/) unterstützt. Der Quellendurchlauf kennzeichnet die Zeigerposition des aktuellen Datensatzes, welche durch die Synchronisation der Daten mit der Benutzeroberfläche der Ansicht ermittelt wird. Weitere Informationen zum Binden mit hierarchischen Datenquellenobjekten und zur Bedeutung des Zeigers für den aktuellen Datensatz in der Datenbindung finden Sie unter [Verwenden des Master-Detail-Musters mit hierarchischen Daten](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) und [Übersicht über die Datenbindung](../data/data-binding-overview.md).

> [!NOTE]
> Auf den ersten Blick ähnelt diese Syntax [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]. Eine echte [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] Ausdruck für die Bindung an eine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] -Datenquelle dient nicht als eine <xref:System.Windows.Data.Binding.Path%2A> Wert ein, und sollte stattdessen verwendet werden, für die sich gegenseitig ausschließende <xref:System.Windows.Data.Binding.XPath%2A> Eigenschaft.

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

In der Standardeinstellung werden die Indexerwerte durch Verwendung der Eigenschaften des zugrunde liegenden Objekts eingegeben. Sie können falls erforderlich den Typ des Index angeben. Weitere Informationen zum Eingeben der Indexer finden Sie unter <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.

<a name="mixing"></a>

### <a name="mixing-syntaxes"></a>Kombinieren von Syntaxen

Jede der oben angegebenen Syntaxen kann mit einer anderen Syntax kombiniert werden. Folgendes ist z. B. ein Beispiel, das ein Eigenschaftenpfad, der die Farbe an einem bestimmten X, y-Wert der erstellt eine `ColorGrid` Eigenschaft, die ein Pixelrasterarray von enthält <xref:System.Windows.Media.SolidColorBrush> Objekte:

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

Die Zieleigenschaft einer Animation muss eine Abhängigkeitseigenschaft, die entweder akzeptiert eine <xref:System.Windows.Freezable> oder einen primitiven Typ. Die Zieleigenschaft für einen Typ und gegebenenfalls die animierte Eigenschaft können sich jedoch auf unterschiedlichen Objekten befinden. Bei Animationen wird ein Eigenschaftspfad verwendet, um die Verbindung zwischen der Eigenschaft des benannten Animationszielobjekts und der Eigenschaft der gewünschten Zielanimation zu definieren. Hierzu werden die Objekteigenschaftsbeziehungen in den Eigenschaftswerten durchlaufen.

<a name="general"></a>

### <a name="general-object-property-considerations-for-animations"></a>Allgemeine Überlegungen zu Objekteigenschaften für Animationen

Weitere Informationen zu Animationskonzepten im Allgemeinen finden Sie unter [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md) und [Übersicht über Animationen](../graphics-multimedia/animation-overview.md).

Der Werttyp oder die animierte Eigenschaft muss entweder eine <xref:System.Windows.Freezable> Typ oder ein primitiver Wert. Die Eigenschaft, die der Pfad beginnt muss in den Namen einer Abhängigkeitseigenschaft, die für den angegebenen vorhanden ist, werden aufgelöst <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Typ.

Um das Klonen für die Animation unterstützt eine <xref:System.Windows.Freezable> , die bereits gesperrt ist, das Objekt anhand des <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> muss eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitete Klasse.

<a name="singlestepanim"></a>

### <a name="single-property-on-the-target-object"></a>Einzelne Eigenschaft auf dem Zielobjekt

```xml
<animation Storyboard.TargetProperty="propertyName" .../>
```

`propertyName` muss in den Namen einer Abhängigkeitseigenschaft, die für den angegebenen vorhanden ist, werden aufgelöst <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Typ.

<a name="indirectanim"></a>

### <a name="indirect-property-targeting"></a>Indirekte Eigenschaftsziele

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>
```

`propertyName` muss eine Eigenschaft, die entweder eine <xref:System.Windows.Freezable> Werttyp oder ein primitiver Typ, der in der angegebenen vorhanden ist <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Typ.

`propertyName2` muss der Name einer Abhängigkeitseigenschaft sein, die auf dem Objekt vorhanden ist, das dem Wert von `propertyName` entspricht. Das heißt, `propertyName2` muss vorhanden sein, als Abhängigkeitseigenschaft des Typs, der die `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>.

Die indirekte Verwendung von Animationen als Ziel ist aufgrund der angewendeten Stile und Vorlagen erforderlich. Um eine Animation als Ziel verwenden, müssen Sie eine <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> ein Zielobjekt, und diesem-Name wird hergestellt, indem [X: Name](../../xaml-services/x-name-directive.md) oder <xref:System.Windows.FrameworkElement.Name%2A>. Vorlagen- und Stilelemente können zwar ebenfalls Namen haben, aber diese Namen sind nur innerhalb des Namescope des Stils bzw. der Vorlage gültig. (Wenn Vorlagen und Stile den gleichen Namescope wie das Anwendungsmarkup verwenden würden, wären die Namen nicht eindeutig. Die Stile und Vorlagen würden dann von verschiedenen Instanzen gleichzeitig verwendet werden und würden doppelte Namen weitergeben.) Wenn die spezifischen Eigenschaften eines zu animierenden Elements aus einem Stil oder einer Vorlage stammen, müssen Sie daher mit einer benannten Elementinstanz beginnen, die nicht aus der Formatvorlage stammt, und dann als Ziel die visuelle Struktur des Stils oder der Vorlage angeben, um zu der Eigenschaft zu gelangen, die Sie animieren möchten.

Z. B. die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft eine <xref:System.Windows.Controls.Panel> ist eine vollständige <xref:System.Windows.Media.Brush> (eigentlich um ein <xref:System.Windows.Media.SolidColorBrush>), die aus einer Designvorlage stammt. Zum Animieren einer <xref:System.Windows.Media.Brush> vollständig, es müssten Sie eine BrushAnimation, (wahrscheinlich einen für jede <xref:System.Windows.Media.Brush> Typ) und kein solcher Typ vorhanden ist. Um einen Pinsel zu animieren, animieren Sie stattdessen Eigenschaften eines bestimmten <xref:System.Windows.Media.Brush> Typ. Müssen Sie zum Abrufen von <xref:System.Windows.Media.SolidColorBrush> auf seine <xref:System.Windows.Media.SolidColorBrush.Color%2A> anzuwendende eine <xref:System.Windows.Media.Animation.ColorAnimation> vorhanden. Der Eigenschaftspfad für dieses Beispiel wäre `Background.Color`.

<a name="attachedanim"></a>

### <a name="attached-properties"></a>Angefügte Eigenschaften

```xml
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>
```

Die Klammern zeigen an, die diese Eigenschaft in einem <xref:System.Windows.PropertyPath> mit einer partiellen Qualifikation erstellt werden sollten. Es kann ein XML-Namespace verwendet werden, um nach dem Typ zu suchen. Die `ownerType` sucht Typen, die eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Prozessor zugreifen kann, bis die <xref:System.Windows.Markup.XmlnsDefinitionAttribute> -Deklarationen in jeder Assembly. In den meisten Anwendungen ist dem [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]-Namespace der XML-Standardnamespace zugeordnet. Ein Präfix ist daher normalerweise nur für benutzerdefinierte Typen oder andere Typen erforderlich, die sich anderweitig außerhalb dieses Namespace befinden. `propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die im `ownerType`-Objekt vorhanden ist. Als die angegebene Eigenschaft `propertyName` muss eine <xref:System.Windows.DependencyProperty>. (Alle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] angefügten Eigenschaften werden als Abhängigkeitseigenschaften implementiert, weshalb dies nur bei benutzerdefinierten, angefügten Eigenschaften relevant ist.)

<a name="indexanim"></a>

### <a name="indexers"></a>Indexer

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>
```

Die meisten Abhängigkeitseigenschaften oder <xref:System.Windows.Freezable> unterstützen keine Indexer. Indexer können deshalb in einem Animationspfad nur an einer Zwischenposition zwischen der Eigenschaft, mit der die Kette am benannten Ziel beginnt, und gegebenenfalls der animierten Eigenschaft verwendet werden. In der dargestellten Syntax ist dies `propertyName2`. Z. B. ein Indexer kann beispielsweise erforderlich sein, wenn die Zwischeneigenschaft eine Auflistung, z. B. ist <xref:System.Windows.Media.TransformGroup>, in einem Eigenschaftspfad wie z. B. `RenderTransform.Children[1].Angle`.

<a name="ppincode"></a>

## <a name="propertypath-in-code"></a>PropertyPath im Code

Verwendung von Code für <xref:System.Windows.PropertyPath>, einschließlich Informationen zum Erstellen einer <xref:System.Windows.PropertyPath>, finden Sie im Referenzthema für <xref:System.Windows.PropertyPath>.

Im allgemeinen <xref:System.Windows.PropertyPath> zwei verschiedenen Konstruktoren, für die Bindungsverwendungen und einfache Animationen und einer für komplexe Animationen verwenden soll. Verwenden der <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> Signatur für Bindungsverwendungen, wenn das Objekt eine Zeichenfolge. Verwenden der <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> Signatur für Animationspfade, wobei das Objekt ist ein <xref:System.Windows.DependencyProperty>. Verwenden der <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> -Signatur für komplexe Animationen. Dieser zweite Konstruktor verwendet eine Tokenzeichenfolge für den ersten Parameter und ein Array von Objekten, die Positionen in der Tokenzeichenfolge füllen, um eine Eigenschaftspfadbeziehung zu definieren.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.PropertyPath>
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md)
