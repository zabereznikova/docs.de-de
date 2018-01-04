---
title: XAML-Syntax von PropertyPath
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9778094eb098d1e119ef4ef0c25dd022130a11ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="propertypath-xaml-syntax"></a>XAML-Syntax von PropertyPath
Die <xref:System.Windows.PropertyPath> Objekt unterstützt eine komplexe [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Syntax zum Festlegen verschiedener Eigenschaften, die <xref:System.Windows.PropertyPath> Typ als ihren Wert. Dieses Thema zeigt die <xref:System.Windows.PropertyPath> Syntax, um die Syntax der Bindung und der Animation angewendet.  
    
  
<a name="where"></a>   
## <a name="where-propertypath-is-used"></a>Verwendung von PropertyPath  
 <xref:System.Windows.PropertyPath>ist ein allgemeines Objekt, das in mehreren verwendet wird [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Funktionen. Das allgemeine <xref:System.Windows.PropertyPath> um Informationen zu vermitteln, die Markuperweiterungsverwendungen für jeden Funktionsbereich, in denen <xref:System.Windows.PropertyPath> dient als ein Typ unterscheiden. Daher ist es praktischer, die Syntaxen pro Funktion zu dokumentieren.  
  
 In erster Linie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet <xref:System.Windows.PropertyPath> Objektmodells Pfade zum Traversieren der Eigenschaften einer Objektdatenquelle beschreiben und den Zielpfad für zielgerichtete Animationen beschreiben.  
  
 Einige Eigenschaften Stil und einem Vorlage wie z. B. <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> haben einen qualifizierten Eigenschaftennamen, die oberflächlich ähnelt einer <xref:System.Windows.PropertyPath>. Dies ist jedoch keine echten <xref:System.Windows.PropertyPath>; stattdessen wird ein qualifizierter *owner.property* Zeichenfolge Format Nutzungsarten, die aktiviert ist, indem der WPF [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor in Kombination mit den Typkonverter für <xref:System.Windows.DependencyProperty>.  
  
<a name="databinding_s"></a>   
## <a name="propertypath-for-objects-in-data-binding"></a>PropertyPath für Objekte in der Datenbindung  
 Datenbindung ist eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktion, bei der Sie an den Zielwert einer beliebigen Abhängigkeitseigenschaft binden können. Allerdings muss die Quelle einer solchen Datenbindung keine Abhängigkeitseigenschaft sein. Es kann sich um einen beliebigen Eigenschaftstyp handeln, der vom Anwendungsdatenanbieter erkannt wird. Eigenschaftspfade werden vor allem verwendet, für die <xref:System.Windows.Data.ObjectDataProvider>, dient zum Abrufen von Bindungsquellen aus [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekte und ihre Eigenschaften.  
  
 Beachten Sie, um die Datenbindung [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] verwendet keine <xref:System.Windows.PropertyPath>, da sie nicht verwendet <xref:System.Windows.Data.Binding.Path%2A> in der <xref:System.Windows.Data.Binding>. Verwenden Sie stattdessen <xref:System.Windows.Data.Binding.XPath%2A> , und geben Sie gültigen XPath-Syntax in der [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] der Daten. <xref:System.Windows.Data.Binding.XPath%2A>wird auch als Zeichenfolge angegeben, jedoch wird hier nicht dokumentiert; finden Sie unter [Binden mit XML-Daten mithilfe einer XMLDataProvider und XPath-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Für das Verständnis von Eigenschaftspfaden in der Datenbindung ist es wichtig zu wissen, dass Sie einen individuellen Eigenschaftswert als Ziel für die Bindung festlegen oder stattdessen Bindung zu Zieleigenschaften herstellen können, die Listen oder Auflistungen verwenden. Wenn Sie Sammlungen binden, z. B. Binden einer <xref:System.Windows.Controls.ListBox> , die erweitert, je nachdem, wie viele Datenelemente in der Auflistung werden und dann Ihre Eigenschaftspfad sollte das Auflistungsobjekt, nicht für die einzelnen Sammelelemente verweisen. Das Datenbindungsmodul entspricht die Auflistung verwendet werden, wie die Daten automatisch in den Typ der Bindungsziel Datenquelle Verhalten wie z. B. das Auffüllen einer <xref:System.Windows.Controls.ListBox> mit einem Array von Elementen.  
  
<a name="singlecurrent"></a>   
### <a name="single-property-on-the-immediate-object-as-data-context"></a>Einzelne Eigenschaft auf dem unmittelbaren Objekt als Datenkontext  
  
```xml  
<Binding Path="propertyName" .../>  
```  
  
 *PropertyName* muss den Namen einer Eigenschaft zu sein, die in der aktuellen auflösen <xref:System.Windows.FrameworkElement.DataContext%2A> für eine <xref:System.Windows.Data.Binding.Path%2A> Verwendung. Wenn die Bindung die Quelle aktualisiert, müssen für diese Eigenschaft Schreib- und Leseberechtigungen festgelegt sein, und das Quellobjekt muss geändert werden können.  
  
<a name="singleindex"></a>   
### <a name="single-indexer-on-the-immediate-object-as-data-context"></a>Einzelner Indexer auf dem unmittelbaren Objekt als Datenkontext  
  
```xml  
<Binding Path="[key]" .../>  
```  
  
 `key` muss der eingegebene Index zu einem Wörterbuch oder einer Hashtabelle oder der ganzzahlige Index eines Arrays sein. Zudem muss der Wert des Schlüssels ein Typ sein, der direkt an die Eigenschaft, auf die er angewendet wird, gebunden werden kann. Z. B. eine Hashtabelle, das Zeichenfolgenschlüssel und Zeichenfolgenwerte enthält kann auf diese Weise für die in Text für die Bindung verwendet ein <xref:System.Windows.Controls.TextBox>. Wenn der Schlüssel auf eine Auflistung oder einen Unterindex verweist, können Sie mit dieser Syntax eine Bindung zu einer Zielauflistungseigenschaft herstellen. Andernfalls müssen Sie mithilfe einer Syntax wie `<Binding Path="[``key``].``propertyName``" .../>` auf eine bestimmte Eigenschaft verweisen.  
  
 Sie können falls erforderlich den Typ des Index angeben. Weitere Informationen zu diesem Aspekt eines Pfads indizierte Eigenschaft finden Sie unter <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.  
  
<a name="multipleindirect"></a>   
### <a name="multiple-property-indirect-property-targeting"></a>Mehrere Eigenschaften (indirekte Eigenschaftsziele)  
  
```xml  
<Binding Path="propertyName.propertyName2" .../>  
```  
  
 `propertyName`muss in den Namen einer Eigenschaft zu sein, die die aktuelle aufgelöst <xref:System.Windows.FrameworkElement.DataContext%2A>. Bei den Pfadeigenschaften `propertyName` und `propertyName2` kann es sich um alle Eigenschaften handeln, die in einer Beziehung vorhanden sind, wobei `propertyName2` eine Eigenschaft in dem Typ ist, der dem Wert von `propertyName` entspricht.  
  
<a name="singleattached"></a>   
### <a name="single-property-attached-or-otherwise-type-qualified"></a>Einzelne angefügte oder anderweitig typqualifizierte Eigenschaft  
  
```xml  
<object property="(ownerType.propertyName)" .../>  
```  
  
 Die Klammern geben an, die diese Eigenschaft in einer <xref:System.Windows.PropertyPath> teilweise Modulmember erstellt werden soll. Es kann ein XML-Namespace verwendet werden, um den Typ mit einer entsprechenden Zuordnung zu suchen. Die `ownerType` sucht Typen, die eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor verfügt über Zugriff auf, bis die <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Deklarationen in den jeweiligen Assemblys. In den meisten Anwendungen ist dem [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]-Namespace der XML-Standardnamespace zugeordnet. Ein Präfix ist daher normalerweise nur für benutzerdefinierte Typen oder andere Typen erforderlich, die sich anderweitig außerhalb dieses Namespace befinden.  `propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die im `ownerType`-Objekt vorhanden ist. Diese Syntax wird in der Regel für einen der folgenden Fälle verwendet:  
  
-   Der Pfad wird in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] angegeben, d.h. in einem Stil oder einer Vorlage, die keinen spezifischen Zieltyp aufweist. Eine qualifizierte Verwendung ist normalerweise in anderen Fällen als diesem nicht zulässig, da in Fällen ohne Stil bzw. Vorlage die Eigenschaft in einer Instanz anstatt in einem Typ enthalten ist.  
  
-   Die Eigenschaft ist eine angefügte Eigenschaft.  
  
-   Sie binden an eine statische Eigenschaft.  
  
 Für die Verwendung als Storyboardziel, die Eigenschaft angegeben, als `propertyName` muss eine <xref:System.Windows.DependencyProperty>.  
  
<a name="sourcetraversal"></a>   
### <a name="source-traversal-binding-to-hierarchies-of-collections"></a>Quellendurchlauf (Binden an Auflistungshierarchien)  
  
```xml  
<object Path="propertyName/propertyNameX" .../>  
```  
  
 Das Zeichen / in dieser Syntax ermöglicht die Navigation in einem hierarchischen Datenquellenobjekt. In der Hierarchie werden mehrere Schritte mit aufeinanderfolgenden Schrägstrichen (/) unterstützt. Der Quellendurchlauf kennzeichnet die Zeigerposition des aktuellen Datensatzes, welche durch die Synchronisation der Daten mit der Benutzeroberfläche der Ansicht ermittelt wird. Weitere Informationen zum Binden mit hierarchischen Datenquellenobjekten und zur Bedeutung des Zeigers für den aktuellen Datensatz in der Datenbindung finden Sie unter [Verwenden des Master-Detail-Musters mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) und [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
> [!NOTE]
>  Auf den ersten Blick ähnelt diese Syntax [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]. Eine "true" [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] Ausdruck für die Bindung an eine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] -Datenquelle dient nicht als eine <xref:System.Windows.Data.Binding.Path%2A> -Wert und sollte stattdessen verwendet werden, für die sich gegenseitig ausschließende <xref:System.Windows.Data.Binding.XPath%2A> Eigenschaft.  
  
### <a name="collection-views"></a>Auflistungsansichten  
 Stellen Sie dem Namen der Auflistungsansicht das Hashzeichen (`#`) voran, um auf eine benannte Auflistungsansicht zu verweisen.  
  
### <a name="current-record-pointer"></a>Zeiger auf den aktuellen Datensatz  
 Beginnen Sie die Pfadzeichenfolge mit einem Schrägstrich (`/`), um für eine Auflistungsansicht oder ein Master-Detail-Datenbindungsszenario auf den Zeiger für den aktuellen Datensatz zu verweisen. Ein beliebiger Pfad nach dem Schrägstrich wird ab dem Zeiger auf den aktuellen Datensatz durchlaufen.  
  
### <a name="multiple-indexers"></a>Mehrere Indexer  
  
```  
<object Path="[index1,index2...]" .../>  
or  
<object Path="propertyName[index,index2...]" .../>  
```  
  
 Wenn ein bestimmtes Objekt mehrere Indexer unterstützt, können diese Indexer in der richtigen Reihenfolge angegeben werden, ähnlich wie ein Array, das auf Syntax verweist. Bei diesem Objekt kann es sich entweder um den aktuellen Kontext oder um den Wert einer Eigenschaft handeln, die ein Objekt mit mehreren Indizes enthält.  
  
 In der Standardeinstellung werden die Indexerwerte durch Verwendung der Eigenschaften des zugrunde liegenden Objekts eingegeben. Sie können falls erforderlich den Typ des Index angeben. Weitere Informationen zum Eingeben der Indexer finden Sie unter <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.  
  
<a name="mixing"></a>   
### <a name="mixing-syntaxes"></a>Kombinieren von Syntaxen  
 Jede der oben angegebenen Syntaxen kann mit einer anderen Syntax kombiniert werden. Beispielsweise ist im folgenden ein Beispiel, das einen Eigenschaftenpfad mit der Farbe auf einem bestimmten x-und y erstellt eine `ColorGrid` Eigenschaft, die ein Array des Pixel-Raster von enthält <xref:System.Windows.Media.SolidColorBrush> Objekte:  
  
```xml  
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" .../>  
```  
  
### <a name="escapes-for-property-path-strings"></a>Escapezeichen für Eigenschaftspfadzeichenfolgen  
 Bei bestimmten Geschäftsobjekten kann es vorkommen, dass die Eigenschaftspfadzeichenfolge eine Escapesequenz erfordert, um ordnungsgemäß analysiert werden zu können. Der Bedarf an Escapezeichen sollte gering sein, da viele dieser Zeichen ähnliche Benennungsinteraktionsprobleme in Sprachen aufweisen, die normalerweise verwendet werden würden, um das Geschäftsobjekt zu definieren.  
  
-   In Indexern ([ ]) dient das Caretzeichen (^) als Escapezeichen für das nächste Zeichen.  
  
-   Sie müssen bestimmte Zeichen (mit XML-Entitäten), die für die XML-Sprachdefinition von besonderer Bedeutung sind, mit Escapezeichen versehen. Verwenden Sie `&`, um das Zeichen „&“ mit Escapezeichen zu versehen. Verwenden Sie `>`, um das Endtag „>“ mit Escapezeichen zu versehen.  
  
-   Sie müssen Escapezeichen (mit dem umgekehrten Schrägstrich `\`) zu Zeichen hinzufügen, die für das WPF-XAML-Parserverhalten beim Verarbeiten einer Markuperweiterung von besonderer Bedeutung sind.  
  
    -   Der umgekehrte Schrägstrich (`\`) ist das eigentliche Escapezeichen.  
  
    -   Das Gleichheitszeichen (`=`) trennt den Eigenschaftsnamen vom Eigenschaftswert.  
  
    -   Das Komma (`,`) trennt Eigenschaften.  
  
    -   Die rechte geschweifte Klammer (`}`) gibt das Ende einer Markuperweiterung an.  
  
> [!NOTE]
>  Technisch gesehen funktionieren diese Escapezeichen auch für einen Storyboardeigenschaftspfad, aber da Sie normalerweise Objektmodelle für vorhandene WPF-Objekte durchlaufen, sollten Escapezeichen unnötig sein.  
  
<a name="databinding_sa"></a>   
## <a name="propertypath-for-animation-targets"></a>PropertyPath für Animationsziele  
 Die Zieleigenschaft einer Animation muss eine Abhängigkeitseigenschaft, die entweder akzeptiert eine <xref:System.Windows.Freezable> oder einen primitiven Typ. Die Zieleigenschaft für einen Typ und gegebenenfalls die animierte Eigenschaft können sich jedoch auf unterschiedlichen Objekten befinden. Bei Animationen wird ein Eigenschaftspfad verwendet, um die Verbindung zwischen der Eigenschaft des benannten Animationszielobjekts und der Eigenschaft der gewünschten Zielanimation zu definieren. Hierzu werden die Objekteigenschaftsbeziehungen in den Eigenschaftswerten durchlaufen.  
  
<a name="general"></a>   
### <a name="general-object-property-considerations-for-animations"></a>Allgemeine Überlegungen zu Objekteigenschaften für Animationen  
 Weitere Informationen zu Animationskonzepten im Allgemeinen finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) und [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Der Werttyp oder der zu animierenden Eigenschaft muss entweder eine <xref:System.Windows.Freezable> Typ oder ein primitiver Wert. Die Eigenschaft, die den Pfad beginnt, muss in den Namen einer Abhängigkeitseigenschaft sein, auf dem angegebenen aufgelöst werden <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Typ.  
  
 Um das Klonen für die Animation unterstützt eine <xref:System.Windows.Freezable> , die bereits gesperrt ist, das vom angegebenen Objekt <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> muss ein <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitete Klasse.  
  
<a name="singlestepanim"></a>   
### <a name="single-property-on-the-target-object"></a>Einzelne Eigenschaft auf dem Zielobjekt  
  
```xml  
<animation Storyboard.TargetProperty="propertyName" .../>  
```  
  
 `propertyName`muss in den Namen einer Abhängigkeitseigenschaft sein, auf dem angegebenen aufgelöst <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Typ.  
  
<a name="indirectanim"></a>   
### <a name="indirect-property-targeting"></a>Indirekte Eigenschaftsziele  
  
```xml  
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>  
```  
  
 `propertyName`muss eine Eigenschaft, die entweder eine <xref:System.Windows.Freezable> Werttyp oder ein primitiver, die auf dem angegebenen vorhanden ist <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Typ.  
  
 `propertyName2` muss der Name einer Abhängigkeitseigenschaft sein, die auf dem Objekt vorhanden ist, das dem Wert von `propertyName` entspricht. Das heißt, `propertyName2` muss vorhanden sein, als Abhängigkeitseigenschaft des Typs, der die `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>.  
  
 Die indirekte Verwendung von Animationen als Ziel ist aufgrund der angewendeten Stile und Vorlagen erforderlich. Um eine Animation abzielen möchten, müssen Sie eine <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> ein Zielobjekt, und diesem Namen wird hergestellt [X: Name](../../../../docs/framework/xaml-services/x-name-directive.md) oder <xref:System.Windows.FrameworkElement.Name%2A>. Vorlagen- und Stilelemente können zwar ebenfalls Namen haben, aber diese Namen sind nur innerhalb des Namescope des Stils bzw. der Vorlage gültig. (Wenn Vorlagen und Stile den gleichen Namescope wie das Anwendungsmarkup verwenden würden, wären die Namen nicht eindeutig. Die Stile und Vorlagen würden dann von verschiedenen Instanzen gleichzeitig verwendet werden und würden doppelte Namen weitergeben.) Wenn die spezifischen Eigenschaften eines zu animierenden Elements aus einem Stil oder einer Vorlage stammen, müssen Sie daher mit einer benannten Elementinstanz beginnen, die nicht aus der Formatvorlage stammt, und dann als Ziel die visuelle Struktur des Stils oder der Vorlage angeben, um zu der Eigenschaft zu gelangen, die Sie animieren möchten.  
  
 Z. B. die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft eine <xref:System.Windows.Controls.Panel> ein vollständiges <xref:System.Windows.Media.Brush> (tatsächlich ein <xref:System.Windows.Media.SolidColorBrush>), die aus einer Designvorlage stammt. Zum Animieren einer <xref:System.Windows.Media.Brush> vollständig, benötigen Sie eine BrushAnimation, (wahrscheinlich eine für jede <xref:System.Windows.Media.Brush> Typ) und kein solcher Typ vorhanden ist. Einen Pinsel, Sie stattdessen animieren Eigenschaften eines bestimmten <xref:System.Windows.Media.Brush> Typ. Müssen Sie zum Abrufen von <xref:System.Windows.Media.SolidColorBrush> auf seine <xref:System.Windows.Media.SolidColorBrush.Color%2A> anzuwendende eine <xref:System.Windows.Media.Animation.ColorAnimation> vorhanden. Der Eigenschaftspfad für dieses Beispiel wäre `Background.Color`.  
  
<a name="attachedanim"></a>   
### <a name="attached-properties"></a>Angefügte Eigenschaften  
  
```xml  
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>  
```  
  
 Die Klammern geben an, die diese Eigenschaft in einer <xref:System.Windows.PropertyPath> teilweise Modulmember erstellt werden soll. Es kann ein XML-Namespace verwendet werden, um nach dem Typ zu suchen. Die `ownerType` sucht Typen, die eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor verfügt über Zugriff auf, bis die <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Deklarationen in den jeweiligen Assemblys. In den meisten Anwendungen ist dem [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]-Namespace der XML-Standardnamespace zugeordnet. Ein Präfix ist daher normalerweise nur für benutzerdefinierte Typen oder andere Typen erforderlich, die sich anderweitig außerhalb dieses Namespace befinden. `propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die im `ownerType`-Objekt vorhanden ist. Als die angegebene Eigenschaft `propertyName` muss eine <xref:System.Windows.DependencyProperty>. (Alle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] angefügten Eigenschaften werden als Abhängigkeitseigenschaften implementiert, weshalb dies nur bei benutzerdefinierten, angefügten Eigenschaften relevant ist.)  
  
<a name="indexanim"></a>   
### <a name="indexers"></a>Indexer  
  
```xml  
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>  
```  
  
 Die meisten Abhängigkeitseigenschaften oder <xref:System.Windows.Freezable> Typen einen Indexer nicht unterstützt. Indexer können deshalb in einem Animationspfad nur an einer Zwischenposition zwischen der Eigenschaft, mit der die Kette am benannten Ziel beginnt, und gegebenenfalls der animierten Eigenschaft verwendet werden. In der dargestellten Syntax ist dies `propertyName2`. Z. B. möglicherweise die Verwendung als Indexer erforderlich, wenn die intermediate-Eigenschaft eine Auflistung wie z. B. <xref:System.Windows.Media.TransformGroup>, in einem Eigenschaftenpfad, z. B. `RenderTransform.Children[1].Angle`.  
  
<a name="ppincode"></a>   
## <a name="propertypath-in-code"></a>PropertyPath im Code  
 Verwendung von Code für <xref:System.Windows.PropertyPath>, einschließlich Informationen zum Erstellen einer <xref:System.Windows.PropertyPath>, finden Sie im Referenzthema für <xref:System.Windows.PropertyPath>.  
  
 Im allgemeinen <xref:System.Windows.PropertyPath> zwei verschiedene Konstruktoren, für die Bindung Verwendungen und die einfachsten Verwendungsmöglichkeiten der Animation und eine für die komplexe Animation Verwendungen verwenden soll. Verwenden der <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> Signatur zum Binden von Verwendungen, in dem das Objekt eine Zeichenfolge ist. Verwenden der <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> Signatur für die einstufige Animationspfade werden, in dem das Objekt ist eine <xref:System.Windows.DependencyProperty>. Verwenden der <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> Signatur für komplexe Animationen. Dieser zweite Konstruktor verwendet eine Tokenzeichenfolge für den ersten Parameter und ein Array von Objekten, die Positionen in der Tokenzeichenfolge füllen, um eine Eigenschaftspfadbeziehung zu definieren.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.PropertyPath>  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
