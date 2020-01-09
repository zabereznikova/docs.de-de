---
title: XAML-Syntax von PropertyPath
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: 17c8982a66960626a5d049fa2da90f5f2d995d14
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559767"
---
# <a name="propertypath-xaml-syntax"></a>XAML-Syntax von PropertyPath

Das <xref:System.Windows.PropertyPath>-Objekt unterstützt eine komplexe Inline [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Syntax zum Festlegen verschiedener Eigenschaften, die den <xref:System.Windows.PropertyPath> Typ als Wert annehmen. In diesem Thema wird die <xref:System.Windows.PropertyPath> Syntax beschrieben, die auf Bindungs-und Animations Syntax angewendet wird.

<a name="where"></a>

## <a name="where-propertypath-is-used"></a>Verwendung von PropertyPath

<xref:System.Windows.PropertyPath> ist ein gängiges Objekt, das in mehreren [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Features verwendet wird. Trotz der Verwendung der allgemeinen <xref:System.Windows.PropertyPath>, um Eigenschafts Pfadinformationen zu übermitteln, unterscheiden sich die Verwendungen für jeden Funktionsbereich, in dem <xref:System.Windows.PropertyPath> als Typ verwendet wird. Daher ist es praktischer, die Syntaxen pro Funktion zu dokumentieren.

In erster Linie verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.PropertyPath>, um Objektmodell Pfade zum Durchlaufen der Eigenschaften einer Objektdaten Quelle zu beschreiben und den Zielpfad für gezielte Animationen zu beschreiben.

Einige Stil-und Vorlagen Eigenschaften, z. b. <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType>, nehmen einen qualifizierten Eigenschaftsnamen an, der einer <xref:System.Windows.PropertyPath>sehr ähnlich ist. Aber dies ist kein echter <xref:System.Windows.PropertyPath>. Stattdessen handelt es sich um einen qualifizierten Besitzer. die Verwendung des *Eigenschafts* Zeichen folgen Formats, das vom WPF-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor in Verbindung mit dem Typkonverter für <xref:System.Windows.DependencyProperty>aktiviert wird.

<a name="databinding_s"></a>

## <a name="propertypath-for-objects-in-data-binding"></a>PropertyPath für Objekte in der Datenbindung

Datenbindung ist eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktion, bei der Sie an den Zielwert einer beliebigen Abhängigkeitseigenschaft binden können. Allerdings muss die Quelle einer solchen Datenbindung keine Abhängigkeitseigenschaft sein. Es kann sich um einen beliebigen Eigenschaftstyp handeln, der vom Anwendungsdatenanbieter erkannt wird. Eigenschafts Pfade werden insbesondere für das <xref:System.Windows.Data.ObjectDataProvider>verwendet, das zum Abrufen von Bindungs Quellen von Common Language Runtime (CLR)-Objekten und deren Eigenschaften verwendet wird.

Beachten Sie, dass die Datenbindung an XML <xref:System.Windows.PropertyPath>nicht verwendet, da Sie im <xref:System.Windows.Data.Binding>nicht <xref:System.Windows.Data.Binding.Path%2A> verwendet. Verwenden Sie stattdessen <xref:System.Windows.Data.Binding.XPath%2A>, und geben Sie eine gültige XPath-Syntax in der XML-Dokumentobjektmodell (DOM) der Daten an. <xref:System.Windows.Data.Binding.XPath%2A> wird auch als Zeichenfolge angegeben, aber hier nicht dokumentiert. Weitere Informationen finden [Sie unterbinden an XML-Daten mithilfe von XmlDataProvider und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).

Für das Verständnis von Eigenschaftspfaden in der Datenbindung ist es wichtig zu wissen, dass Sie einen individuellen Eigenschaftswert als Ziel für die Bindung festlegen oder stattdessen Bindung zu Zieleigenschaften herstellen können, die Listen oder Auflistungen verwenden. Wenn Sie Auflistungen binden, beispielsweise eine <xref:System.Windows.Controls.ListBox> binden, die abhängig von der Anzahl der Datenelemente in der Auflistung erweitert werden, sollte der Eigenschafts Pfad auf das Auflistungs Objekt und nicht auf einzelne Auflistungs Elemente verweisen. Das Daten Bindungs Modul passt die als Datenquelle verwendete Auflistung automatisch an den Typ des Bindungs Ziels an, was zu einem Verhalten führt, z. b. zum Auffüllen einer <xref:System.Windows.Controls.ListBox> mit einem Element Array.

<a name="singlecurrent"></a>

### <a name="single-property-on-the-immediate-object-as-data-context"></a>Einzelne Eigenschaft auf dem unmittelbaren Objekt als Datenkontext

```xml
<Binding Path="propertyName" .../>
```

*propertyName* muss in den Namen einer Eigenschaft aufgelöst werden, die im aktuellen <xref:System.Windows.FrameworkElement.DataContext%2A> für eine <xref:System.Windows.Data.Binding.Path%2A> Verwendung ist. Wenn die Bindung die Quelle aktualisiert, müssen für diese Eigenschaft Schreib- und Leseberechtigungen festgelegt sein, und das Quellobjekt muss geändert werden können.

<a name="singleindex"></a>

### <a name="single-indexer-on-the-immediate-object-as-data-context"></a>Einzelner Indexer auf dem unmittelbaren Objekt als Datenkontext

```xml
<Binding Path="[key]" .../>
```

`key` muss der eingegebene Index zu einem Wörterbuch oder einer Hashtabelle oder der ganzzahlige Index eines Arrays sein. Zudem muss der Wert des Schlüssels ein Typ sein, der direkt an die Eigenschaft, auf die er angewendet wird, gebunden werden kann. Beispielsweise kann eine Hash Tabelle, die Zeichen folgen Schlüssel und Zeichen folgen Werte enthält, auf diese Weise zum Binden an Text für eine <xref:System.Windows.Controls.TextBox>verwendet werden. Wenn der Schlüssel auf eine Auflistung oder einen Unterindex verweist, können Sie mit dieser Syntax eine Bindung zu einer Zielauflistungseigenschaft herstellen. Andernfalls müssen Sie mithilfe einer Syntax wie `<Binding Path="[key].propertyName" .../>` auf eine bestimmte Eigenschaft verweisen.

Sie können falls erforderlich den Typ des Index angeben. Ausführliche Informationen zu diesem Aspekt eines indizierten Eigenschafts Pfads finden Sie unter <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.

<a name="multipleindirect"></a>

### <a name="multiple-property-indirect-property-targeting"></a>Mehrere Eigenschaften (indirekte Eigenschaftsziele)

```xml
<Binding Path="propertyName.propertyName2" .../>
```

`propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die der aktuelle <xref:System.Windows.FrameworkElement.DataContext%2A>ist. Bei den Pfadeigenschaften `propertyName` und `propertyName2` kann es sich um alle Eigenschaften handeln, die in einer Beziehung vorhanden sind, wobei `propertyName2` eine Eigenschaft in dem Typ ist, der dem Wert von `propertyName` entspricht.

<a name="singleattached"></a>

### <a name="single-property-attached-or-otherwise-type-qualified"></a>Einzelne angefügte oder anderweitig typqualifizierte Eigenschaft

```xml
<object property="(ownerType.propertyName)" .../>
```

Die Klammern geben an, dass diese Eigenschaft in einer <xref:System.Windows.PropertyPath> mit einer Teilqualifikation erstellt werden soll. Es kann ein XML-Namespace verwendet werden, um den Typ mit einer entsprechenden Zuordnung zu suchen. Der `ownerType` durchsucht die Typen, auf die ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Zugriff hat, über die <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Deklarationen in den einzelnen Assemblys. In den meisten Anwendungen ist dem `http://schemas.microsoft.com/winfx/2006/xaml/presentation`-Namespace der XML-Standardnamespace zugeordnet. Ein Präfix ist daher normalerweise nur für benutzerdefinierte Typen oder andere Typen erforderlich, die sich anderweitig außerhalb dieses Namespace befinden.  `propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die im `ownerType`-Objekt vorhanden ist. Diese Syntax wird in der Regel für einen der folgenden Fälle verwendet:

- Der Pfad wird in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] angegeben, d.h. in einem Stil oder einer Vorlage, die keinen spezifischen Zieltyp aufweist. Eine qualifizierte Verwendung ist normalerweise in anderen Fällen als diesem nicht zulässig, da in Fällen ohne Stil bzw. Vorlage die Eigenschaft in einer Instanz anstatt in einem Typ enthalten ist.

- Die Eigenschaft ist eine angefügte Eigenschaft.

- Sie binden an eine statische Eigenschaft.

Zur Verwendung als Storyboard-Ziel muss die als `propertyName` angegebene Eigenschaft <xref:System.Windows.DependencyProperty>sein.

<a name="sourcetraversal"></a>

### <a name="source-traversal-binding-to-hierarchies-of-collections"></a>Quellendurchlauf (Binden an Auflistungshierarchien)

```xml
<object Path="propertyName/propertyNameX" .../>
```

Das Zeichen / in dieser Syntax ermöglicht die Navigation in einem hierarchischen Datenquellenobjekt. In der Hierarchie werden mehrere Schritte mit aufeinanderfolgenden Schrägstrichen (/) unterstützt. Der Quellendurchlauf kennzeichnet die Zeigerposition des aktuellen Datensatzes, welche durch die Synchronisation der Daten mit der Benutzeroberfläche der Ansicht ermittelt wird. Weitere Informationen zum Binden mit hierarchischen Datenquellenobjekten und zur Bedeutung des Zeigers für den aktuellen Datensatz in der Datenbindung finden Sie unter [Verwenden des Master-Detail-Musters mit hierarchischen Daten](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) und [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

> [!NOTE]
> Oberflächlich betrachtet, ähnelt diese Syntax XPath. Ein echter XPath-Ausdruck für die Bindung an eine XML-Datenquelle wird nicht als <xref:System.Windows.Data.Binding.Path%2A> Wert verwendet und sollte stattdessen für die sich gegenseitig ausschließende <xref:System.Windows.Data.Binding.XPath%2A>-Eigenschaft verwendet werden.

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

In der Standardeinstellung werden die Indexerwerte durch Verwendung der Eigenschaften des zugrunde liegenden Objekts eingegeben. Sie können falls erforderlich den Typ des Index angeben. Ausführliche Informationen zum Eingeben der Indexer finden Sie unter <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.

<a name="mixing"></a>

### <a name="mixing-syntaxes"></a>Kombinieren von Syntaxen

Jede der oben angegebenen Syntaxen kann mit einer anderen Syntax kombiniert werden. Im folgenden Beispiel wird ein Eigenschafts Pfad zu der Farbe eines bestimmten x, y einer `ColorGrid` Eigenschaft erstellt, die ein Pixelraster Array von <xref:System.Windows.Media.SolidColorBrush> Objekten enthält:

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

Der Werttyp oder die zu animierende Eigenschaft muss entweder ein <xref:System.Windows.Freezable> oder ein primitiver Typ sein. Die Eigenschaft, die den Pfad startet, muss in den Namen einer Abhängigkeits Eigenschaft aufgelöst werden, die für den angegebenen <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Typ vorhanden ist.

Um das Klonen zum Animieren einer <xref:System.Windows.Freezable> zu unterstützen, die bereits eingefroren ist, muss das durch <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> angegebene Objekt eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitete Klasse sein.

<a name="singlestepanim"></a>

### <a name="single-property-on-the-target-object"></a>Einzelne Eigenschaft auf dem Zielobjekt

```xml
<animation Storyboard.TargetProperty="propertyName" .../>
```

`propertyName` muss in den Namen einer Abhängigkeits Eigenschaft aufgelöst werden, die für den angegebenen <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Typ vorhanden ist.

<a name="indirectanim"></a>

### <a name="indirect-property-targeting"></a>Indirekte Eigenschaftsziele

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>
```

`propertyName` muss eine Eigenschaft sein, die entweder ein <xref:System.Windows.Freezable> Werttyp oder ein primitiv ist, das für den angegebenen <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Typ vorhanden ist.

`propertyName2` muss der Name einer Abhängigkeitseigenschaft sein, die auf dem Objekt vorhanden ist, das dem Wert von `propertyName` entspricht. Anders ausgedrückt: `propertyName2` müssen als eine Abhängigkeits Eigenschaft für den Typ vorhanden sein, der die `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>ist.

Die indirekte Verwendung von Animationen als Ziel ist aufgrund der angewendeten Stile und Vorlagen erforderlich. Um eine Animation als Ziel festzustellen, benötigen Sie eine <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> für ein Zielobjekt, und dieser Name wird von [x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) oder <xref:System.Windows.FrameworkElement.Name%2A>festgelegt. Vorlagen- und Stilelemente können zwar ebenfalls Namen haben, aber diese Namen sind nur innerhalb des Namescope des Stils bzw. der Vorlage gültig. (Wenn Vorlagen und Stile den gleichen Namescope wie das Anwendungsmarkup verwenden würden, wären die Namen nicht eindeutig. Die Stile und Vorlagen werden buchstäblich zwischen Instanzen gemeinsam genutzt und würden doppelte Namen erhalten.) Wenn die einzelnen Eigenschaften eines Elements, das Sie möglicherweise animieren möchten, von einem Stil oder einer Vorlage stammen, müssen Sie mit einer benannten Element Instanz beginnen, die nicht aus einer Stilvorlage stammt, und dann auf die visuelle Struktur des Stils oder der Vorlage abzielen, um die Eigenschaft zu empfangen. Sie möchten animieren.

Die <xref:System.Windows.Controls.Panel.Background%2A>-Eigenschaft einer <xref:System.Windows.Controls.Panel> ist beispielsweise eine komplette <xref:System.Windows.Media.Brush> (tatsächlich ein <xref:System.Windows.Media.SolidColorBrush>), die aus einer Designvorlage stammt. Um eine <xref:System.Windows.Media.Brush> vollständig zu animieren, muss eine BrushAnimation (wahrscheinlich eine für jeden <xref:System.Windows.Media.Brush> Typ) vorhanden sein, und es ist kein solcher Typ vorhanden. Um einen Pinsel zu animieren, animieren Sie stattdessen die Eigenschaften eines bestimmten <xref:System.Windows.Media.Brush> Typs. Sie müssen von <xref:System.Windows.Media.SolidColorBrush> zu seiner <xref:System.Windows.Media.SolidColorBrush.Color%2A> gelangen, um eine <xref:System.Windows.Media.Animation.ColorAnimation> dort anzuwenden. Der Eigenschaftspfad für dieses Beispiel wäre `Background.Color`.

<a name="attachedanim"></a>

### <a name="attached-properties"></a>Angefügte Eigenschaften

```xml
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>
```

Die Klammern geben an, dass diese Eigenschaft in einer <xref:System.Windows.PropertyPath> mit einer Teilqualifikation erstellt werden soll. Es kann ein XML-Namespace verwendet werden, um nach dem Typ zu suchen. Der `ownerType` durchsucht die Typen, auf die ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Zugriff hat, über die <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Deklarationen in den einzelnen Assemblys. In den meisten Anwendungen ist dem `http://schemas.microsoft.com/winfx/2006/xaml/presentation`-Namespace der XML-Standardnamespace zugeordnet. Ein Präfix ist daher normalerweise nur für benutzerdefinierte Typen oder andere Typen erforderlich, die sich anderweitig außerhalb dieses Namespace befinden. `propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die im `ownerType`-Objekt vorhanden ist. Die als `propertyName` angegebene Eigenschaft muss ein <xref:System.Windows.DependencyProperty>sein. (Alle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] angefügten Eigenschaften werden als Abhängigkeitseigenschaften implementiert, weshalb dies nur bei benutzerdefinierten, angefügten Eigenschaften relevant ist.)

<a name="indexanim"></a>

### <a name="indexers"></a>Indexer

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>
```

Ein Indexer wird von den meisten Abhängigkeits Eigenschaften oder <xref:System.Windows.Freezable> Typen nicht unterstützt. Indexer können deshalb in einem Animationspfad nur an einer Zwischenposition zwischen der Eigenschaft, mit der die Kette am benannten Ziel beginnt, und gegebenenfalls der animierten Eigenschaft verwendet werden. In der dargestellten Syntax ist dies `propertyName2`. Beispielsweise kann eine Indexer-Verwendung erforderlich sein, wenn die zwischen Eigenschaft eine Auflistung wie <xref:System.Windows.Media.TransformGroup>in einem Eigenschafts Pfad wie `RenderTransform.Children[1].Angle`ist.

<a name="ppincode"></a>

## <a name="propertypath-in-code"></a>PropertyPath im Code

Die Code Verwendung für <xref:System.Windows.PropertyPath>, einschließlich der Vorgehensweise zum Erstellen einer <xref:System.Windows.PropertyPath>, ist im Referenz Thema für <xref:System.Windows.PropertyPath>dokumentiert.

Im Allgemeinen ist <xref:System.Windows.PropertyPath> für die Verwendung von zwei verschiedenen Konstruktoren konzipiert, eine für die Bindungs Verwendungen und die einfachste Animations Verwendungen und eine für die komplexe Animations Verwendungen. Verwenden Sie die <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> Signatur für Bindungs Verwendungen, bei denen das Objekt eine Zeichenfolge ist. Verwenden Sie die <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> Signatur für Animations Pfade mit einem Schritt, bei denen es sich bei dem Objekt um einen <xref:System.Windows.DependencyProperty>handelt. Verwenden Sie die <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> Signatur für komplexe Animationen. Dieser zweite Konstruktor verwendet eine Tokenzeichenfolge für den ersten Parameter und ein Array von Objekten, die Positionen in der Tokenzeichenfolge füllen, um eine Eigenschaftspfadbeziehung zu definieren.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.PropertyPath>
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md)
