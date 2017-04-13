---
title: "XAML-Syntax von PropertyPath | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PropertyPath-Objekt"
  - "XAML, PropertyPath-Objekt"
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# XAML-Syntax von PropertyPath
Das <xref:System.Windows.PropertyPath>\-Objekt unterstützt eine komplexe [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Inlinesyntax, mit der verschiedene Eigenschaften festgelegt werden können, die den <xref:System.Windows.PropertyPath>\-Typ als Wert verwenden.  In diesem Thema wird die <xref:System.Windows.PropertyPath>\-Syntax und deren Anwendung auf Bindungs\- und Animationssyntax dargestellt.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="where"></a>   
## Verwendung von PropertyPath  
 <xref:System.Windows.PropertyPath> ist ein allgemeines Objekt, das in verschiedenen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Features verwendet wird.  Das allgemeine <xref:System.Windows.PropertyPath>\-Objekt wird zum Vermitteln von Informationen zu dem Eigenschaftenpfad genutzt. Die Verwendung in den einzelnen Featurebereichen, in denen <xref:System.Windows.PropertyPath> als Typ eingesetzt wird, variiert jedoch.  Die Syntax wird daher nach Funktionen unterteilt dokumentiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet <xref:System.Windows.PropertyPath> hauptsächlich, um Objektmodellpfade zum Traversieren der Eigenschaften einer Objektdatenquelle anzugeben und um den Zielpfad für zielgerichtete Animationen anzugeben.  
  
 Einige Format\- und Vorlageneigenschaften, z. B. <xref:System.Windows.Setter.Property%2A?displayProperty=fullName>, haben einen qualifizierten Eigenschaftennamen, der auf den ersten Blick einem <xref:System.Windows.PropertyPath> ähnelt.  Hierbei handelt es sich jedoch nicht um einen echten <xref:System.Windows.PropertyPath>, sondern um eine qualifizierte Verwendung des *Besitzer.Eigenschaft*\-Zeichenfolgenformats, das vom [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-WPF\-Prozessor in Kombination mit dem Typkonverter für <xref:System.Windows.DependencyProperty> aktiviert wird.  
  
<a name="databinding_s"></a>   
## PropertyPath für Objekte in einer Datenbindung  
 Die Datenbindung ist ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Feature, durch das Sie eine Bindung zu dem Zielwert einer beliebigen [Abhängigkeitseigenschaft](GTMT) herstellen können.  Die Quelle einer solchen Datenbindung muss jedoch keine [Abhängigkeitseigenschaft](GTMT) sein. Es kann sich auch um einen anderen Eigenschaftentyp handeln, der vom Anwendungsdatenanbieter erkannt wird.  Eigenschaftenpfade werden vor allem für den <xref:System.Windows.Data.ObjectDataProvider> verwendet, der zum Abrufen von Bindungsquellen aus [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Objekten und von zugehörigen Eigenschaften genutzt wird.  
  
 Beachten Sie, dass die Datenbindung mit [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] <xref:System.Windows.PropertyPath> nicht verwendet, da <xref:System.Windows.Data.Binding.Path%2A> in <xref:System.Windows.Data.Binding> nicht genutzt wird.  Stattdessen verwenden Sie die <xref:System.Windows.Data.Binding.XPath%2A>\-Eigenschaft, und Sie geben gültige XPath\-Syntax in den [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] der Daten an.  <xref:System.Windows.Data.Binding.XPath%2A> wird auch als Zeichenfolge angegeben, aber wird nicht hier dokumentiert; sehen Sie [Binden an XML\-Daten mithilfe von XMLDataProvider und XPath\-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Um Eigenschaftenpfade in der Datenbindung zu verstehen, müssen Sie wissen, dass Sie einen individuellen Eigenschaftswert als Ziel für die Bindung festlegen können. Alternativ können Sie eine Bindung zu Zieleigenschaften herstellen, die Listen oder Auflistungen übernehmen.  Wenn Sie Auflistungen binden und z. B. eine <xref:System.Windows.Controls.ListBox> binden, die abhängig von der Anzahl der Datenelemente in der Auflistung erweitert wird, sollte der Eigenschaftenpfad auf das Auflistungsobjekt verweisen und nicht auf einzelne Auflistungselemente.  Das Datenbindungsmodul ordnet die als Datenquelle verwendeten Auflistungen automatisch dem Typ des Bindungsziels zu und hat ein ähnliches Verhalten wie beim Eingeben eines Elementarrays in eine <xref:System.Windows.Controls.ListBox> zur Folge.  
  
<a name="singlecurrent"></a>   
### Einzelne Eigenschaft auf dem unmittelbaren Objekt als Datenkontext  
  
```  
<Binding Path="propertyName" .../>  
```  
  
 *propertyName* muss in den Namen einer Eigenschaft aufgelöst werden, die im aktuellen <xref:System.Windows.FrameworkElement.DataContext%2A> für eine <xref:System.Windows.Data.Binding.Path%2A>\-Verwendung enthalten ist.  Wenn die Bindung die Quelle aktualisiert, müssen für diese Eigenschaft Schreib\- und Leseberechtigungen festgelegt sein, und das Quellobjekt muss geändert werden können.  
  
<a name="singleindex"></a>   
### Einzelner Indexer auf dem unmittelbaren Objekt als Datenkontext  
  
```  
<Binding Path="[key]" .../>  
```  
  
 `key` muss der eingegebene Index zu einem Wörterbuch oder einer Hashtabelle oder der ganzzahlige Index eines Arrays sein.  Zudem muss der Wert des Schlüssels einem Typ entsprechen, der direkt an die Eigenschaft, auf die er angewendet wird, gebunden werden kann.  Eine Hashtabelle mit Zeichenfolgenschlüsseln und Zeichenfolgenwerten kann beispielsweise auf diese Art verwendet werden, um eine Bindung zu Text für ein <xref:System.Windows.Controls.TextBox> herzustellen.  Verweist der Schlüssel auf eine Auflistung oder einen Unterindex, können Sie mit dieser Syntax eine Bindung zu einer Zielauflistungseigenschaft herstellen.  Andernfalls müssen Sie mithilfe einer Syntax wie `<Binding Path="[``key``].``propertyName``" .../>` auf eine bestimmte Eigenschaft verweisen.  
  
 Sie können bei Bedarf den Typ des Indexes angeben.  Weitere Informationen zu diesem Aspekt eines indizierten Eigenschaftenpfads finden Sie unter <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>.  
  
<a name="multipleindirect"></a>   
### Mehrere Eigenschaften \(indirekte Eigenschaftenverwendung\)  
  
```  
<Binding Path="propertyName.propertyName2" .../>  
```  
  
 `propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die dem aktuellen <xref:System.Windows.FrameworkElement.DataContext%2A> entspricht.  Für die Pfadeigenschaften `propertyName` und `propertyName2` können alle Eigenschaften in einer Beziehung verwendet werden, wobei `propertyName2` eine Eigenschaft in dem Typ ist, der dem Wert von `propertyName` entspricht.  
  
<a name="singleattached"></a>   
### Einzelne Eigenschaft, angefügt oder anderweitig typqualifiziert  
  
```  
<object property="(ownerType.propertyName)" .../>  
```  
  
 Die Klammern kennzeichnen, dass diese Eigenschaft in einem <xref:System.Windows.PropertyPath> mit einer Teilqualifikation erstellt werden sollte.  Es kann ein XML\-Namespace verwendet werden, um den Typ mit einer entsprechenden Zuordnung zu suchen.  Der `ownerType` sucht Typen, auf die ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor zugreifen kann, mithilfe der <xref:System.Windows.Markup.XmlnsDefinitionAttribute>\-Deklarationen in jeder Assembly.  In den meisten Anwendungen ist dem [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]\-Namespace ein standardmäßiger XML\-Namespace zugeordnet. Ein Präfix ist daher normalerweise nur für benutzerdefinierte Typen oder andere Typen erforderlich, die sich andernfalls außerhalb dieses Namespaces befinden würden.  `propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die in `ownerType` existiert.  Diese Syntax wird zumeist in einem der folgenden Fälle verwendet:  
  
-   Dieser Pfad wird in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] angegeben, d. h. in einem Format oder einer Vorlage, die keinen spezifischen Zieltyp aufweist.  Eine qualifizierte Verwendung ist normalerweise in anderen Fällen als diesem nicht zulässig, da in Fällen ohne Format bzw. Vorlage die Eigenschaft in einer Instanz anstatt in einem Typ enthalten ist.  
  
-   Die Eigenschaft ist eine angefügte Eigenschaft.  
  
-   Sie binden an eine statische Eigenschaft.  
  
 Für die Verwendung als Storyboardziel muss die als `propertyName` angegebene Eigenschaft eine <xref:System.Windows.DependencyProperty> sein.  
  
<a name="sourcetraversal"></a>   
### Quellentraversal \(Binden an Auflistungshierarchien\)  
  
```  
<object Path="propertyName/propertyNameX" .../>  
```  
  
 Das Zeichen \/ in dieser Syntax ermöglicht die Navigation in einem hierarchischen Datenquellenobjekt. In der Hierarchie werden mehrere Schritte mit aufeinander folgenden Schrägstrichen \(\/\) unterstützt.  Das Quellentraversal kennzeichnet die Zeigerposition des aktuellen Datensatzes, welche durch die Synchronisation der Daten mit der Benutzeroberfläche der Ansicht ermittelt wird.  Weitere Informationen zum Binden mit hierarchischen Datenquellenobjekten und zu der Bedeutung des Zeigers für den aktuellen Datensatz in der Datenbindung finden Sie unter [Verwenden des Master\-\/Detailmusters mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) oder [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
> [!NOTE]
>  Auf den ersten Blick ähnelt diese Syntax [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)].  Ein echter [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]\-Ausdruck für das Binden an eine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Datenquelle wird jedoch nicht als <xref:System.Windows.Data.Binding.Path%2A>\-Wert verwendet. Er sollte stattdessen für die sich ausschließende <xref:System.Windows.Data.Binding.XPath%2A>\-Eigenschaft verwendet werden.  
  
### Auflistungsansichten  
 Um auf eine benannte Auflistungsansicht zu verweisen, stellen Sie dem Auflistungsansichtsnamen das Hashzeichen \(`#`\) voran.  
  
### Zeiger auf den aktuellen Datensatz  
 Um für eine Auflistungsansicht auf den Zeiger auf den aktuellen Datensatz oder Master\-Detaildatenbindungsszenario zu verweisen, beginnen Sie die Pfadzeichenfolge mit einem Schrägstrich \(`/`\).  Ein beliebiger Pfad nach dem Schrägstrich wird ab dem Zeiger auf den aktuellen Datensatz durchlaufen.  
  
### Mehrere Indexer  
  
```  
<object Path="[index1,index2...]" .../>  
or  
<object Path="propertyName[index,index2...]" .../>  
```  
  
 Wenn ein bestimmtes Objekt mehrere Indexer unterstützt, können diese in der richtigen Reihenfolge angegeben werden, ähnlich wie ein auf Syntax verweisendes Array.  Bei dem betreffenden Objekt handelt es sich entweder um den aktuellen Kontext oder um den Wert einer Eigenschaft, die ein Objekt mit mehreren Indizes enthält.  
  
 Standardmäßig werden die Indexerwerte eingegeben, indem die Eigenschaften des zugrunde liegenden Objekts verwendet werden.  Sie können bei Bedarf den Typ des Indexes angeben.  Weitere Informationen zum Eingeben der Indexer finden Sie unter <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>.  
  
<a name="mixing"></a>   
### Kombinieren von Syntax  
 Jede oben angegebene Syntax kann mit anderer Syntax kombiniert werden.  Im folgenden Beispiel wird beispielsweise ein Eigenschaftenpfad zu der Farbe an einem bestimmten XY\-Punkt einer `ColorGrid`\-Eigenschaft erstellt, die ein Pixelrasterarray von <xref:System.Windows.Media.SolidColorBrush>\-Objekten enthält:  
  
```  
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" .../>  
```  
  
### Escapes für Eigenschaftenpfadzeichenfolgen  
 Bei bestimmten Geschäftsobjekten könnten Sie auf einen Fall stoßen, in dem die Eigenschaftenpfadzeichenfolge eine Escapesequenz erfordert, um ordnungsgemäß analysiert werden zu können.  Die Anforderung für Escapezeichen sollte selten sein, da viele dieser Zeichen ähnliche Benennungsinteraktionsprobleme in Sprachen aufweisen, die in der Regel verwendet werden würden, um das Geschäftsobjekt zu definieren.  
  
-   In Indexern \(\[ \]\) Indexern dient das Caretzeichen \(^\) als Ecsapezeichen für das nächste Zeichen.  
  
-   Sie müssen bestimmte Zeichen \(mit XML\-Entitäten\), die in der XML\-Sprachdefinitionen eine besondere Bedeutung haben, mit Escapezeichen versehen.  Verwenden Sie `&`, um das Zeichen "&" mit Escapezeichen zu versehen.  Verwenden Sie `>`, um das Endtag "\>" mit Escapezeichen zu versehen.  
  
-   Sie müssen Escapezeichen \(mit dem umgekehrten Schrägstrich `\`\) zu Zeichen hinzufügen, die für das WPF XAML\-Parserverhalten beim Verarbeiten einer Markuperweiterung eine besondere Bedeutung haben.  
  
    -   Der umgekehrte Schrägstrich \(`\`\) ist das eigentliche Escapezeichen.  
  
    -   Das Gleichheitszeichen \(`=`\) trennt den Eigenschaftennamen vom Eigenschaftswert.  
  
    -   Mit einem Komma \(`,`\) werden Eigenschaften getrennt.  
  
    -   Die rechte geschweifte Klammer \(`}`\) gibt das Ende einer Markuperweiterung an.  
  
> [!NOTE]
>  Praktisch funktionieren diese Escapes auch für einen Storyboardeigenschaftenpfad, aber Sie durchlaufen normalerweise Objektmodelle für vorhandene WPF\-Objekte, und Escapezeichen sollten unnötig sein.  
  
<a name="databinding_sa"></a>   
## PropertyPath für Animationsziele  
 Die Zieleigenschaft einer Animation muss eine [Abhängigkeitseigenschaft](GTMT) sein, die einen <xref:System.Windows.Freezable>\-Typ oder einen primitiven Typ aufweist.  Die Zieleigenschaft für einen Typ und die ggf. animierte Eigenschaft können sich jedoch auf unterschiedlichen Objekten befinden.  Bei Animationen wird ein Eigenschaftenpfad verwendet, um die Verbindung zwischen der Eigenschaft des benannten Animationszielobjekts und der Eigenschaft der gewünschten Zielanimation zu definieren. Hierzu werden die Objekt\-\/Eigenschaftenbeziehungen in den Eigenschaftswerten durchlaufen.  
  
<a name="general"></a>   
### Allgemeine Überlegungen zu Objekten\/Eigenschaften für Animationen  
 Weitere Informationen zu Animationskonzepten im Allgemeinen finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) und [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Der Werttyp oder die animierte Eigenschaft muss ein <xref:System.Windows.Freezable>\-Typ oder primitiver Typ sein.  Die Eigenschaft, die den Pfad beginnt, muss in den Namen einer [Abhängigkeitseigenschaft](GTMT) aufgelöst werden, die in dem angegebenen <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>\-Typ vorhanden ist.  
  
 Um das Klonen für die Animation eines <xref:System.Windows.Freezable>\-Typs zu unterstützen, der bereits gesperrt ist, muss das durch <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> angegebene Objekt eine abgeleitete <xref:System.Windows.FrameworkElement>\- oder <xref:System.Windows.FrameworkContentElement>\-Klasse sein.  
  
<a name="singlestepanim"></a>   
### Einzelne Eigenschaft auf dem Zielobjekt  
  
```  
<animation Storyboard.TargetProperty="propertyName" .../>  
```  
  
 `propertyName` muss in den Namen einer [Abhängigkeitseigenschaft](GTMT) aufgelöst werden, die in dem angegebenen <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>\-Typ vorhanden ist.  
  
<a name="indirectanim"></a>   
### Indirekte Eigenschaftenverwendung  
  
```  
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>  
```  
  
 `propertyName` muss eine Eigenschaft sein, die entweder ein <xref:System.Windows.Freezable>\-Werttyp oder ein primitiver Werttyp ist, der in dem angegebenen <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>\-Typ vorhanden ist.  
  
 `propertyName2` muss dem Namen einer [Abhängigkeitseigenschaft](GTMT) entsprechen, die in dem Objekt vorhanden ist, das den Wert von `propertyName` angibt.  Mit anderen Worten, `propertyName2` muss als Abhängigkeitseigenschaft des Typs vorhanden sein, der den `propertyName`<xref:System.Windows.DependencyProperty.PropertyType%2A> kennzeichnet.  
  
 Die indirekte Verwendung von Animationen ist aufgrund der angewendeten Formate und Vorlagen erforderlich.  Um eine Animation zu verwenden, benötigen Sie einen <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> auf einem Zielobjekt. Dieser Name wird durch [x:Name](../../../../docs/framework/xaml-services/x-name-directive.md) oder <xref:System.Windows.FrameworkElement.Name%2A> festgelegt.  Vorlagen\- und Formatelemente können zwar ebenfalls Namen aufweisen, diese sind jedoch nur innerhalb des Namescope für das Format bzw. die Vorlage gültig.  \(Wenn Vorlagen und Formate den gleichen Namescope wie Anwendungsmarkup verwenden würden, wären die Namen nicht eindeutig.  Die Formate und Vorlagen würden dann von verschiedenen Instanzen gleichzeitig verwendet und doppelte Namen weitergeben.\) Wenn die spezifischen Eigenschaften eines zu animierenden Elements aus einem Format oder einer Vorlage stammen, müssen Sie daher mit einer benannten Elementinstanz beginnen, die nicht aus der Formatvorlage stammt. Geben Sie dann als Ziel die visuelle Struktur des Formats oder der Vorlage an, um die Eigenschaft zu kennzeichnen, die Sie animieren möchten.  
  
 Beispiel: Die <xref:System.Windows.Controls.Panel.Background%2A>\-Eigenschaft eines <xref:System.Windows.Controls.Panel> ist ein vollständiger <xref:System.Windows.Media.Brush> \(um genau zu sein ein <xref:System.Windows.Media.SolidColorBrush>\), der aus einer Designvorlage stammt.  Um einen <xref:System.Windows.Media.Brush> vollständig zu animieren, benötigen Sie eine BrushAnimation \(zumeist eine für jeden <xref:System.Windows.Media.Brush>\-Typ\), ein solcher Typ ist jedoch nicht vorhanden.  Sie animieren daher statt des Pinsels die Eigenschaften eines bestimmten <xref:System.Windows.Media.Brush>\-Typs.  Sie müssen von dem <xref:System.Windows.Media.SolidColorBrush> zu der entsprechenden <xref:System.Windows.Media.SolidColorBrush.Color%2A> gelangen, um auf diese eine <xref:System.Windows.Media.Animation.ColorAnimation> anzuwenden.  Der Eigenschaftenpfad für dieses Beispiel wäre `Background.Color`.  
  
<a name="attachedanim"></a>   
### Angefügte Eigenschaften  
  
```  
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>  
```  
  
 Die Klammern kennzeichnen, dass diese Eigenschaft in einem <xref:System.Windows.PropertyPath> mit einer Teilqualifikation erstellt werden sollte.  Es kann ein XML\-Namespace verwendet werden, um den Typ zu suchen.  Der `ownerType` sucht Typen, auf die ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor zugreifen kann, mithilfe der <xref:System.Windows.Markup.XmlnsDefinitionAttribute>\-Deklarationen in jeder Assembly.  In den meisten Anwendungen ist dem [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]\-Namespace ein standardmäßiger XML\-Namespace zugeordnet. Ein Präfix ist daher normalerweise nur für benutzerdefinierte Typen oder andere Typen erforderlich, die sich andernfalls außerhalb dieses Namespaces befinden würden.  `propertyName` muss in den Namen einer Eigenschaft aufgelöst werden, die in `ownerType` existiert.  Die als `propertyName` angegebene Eigenschaft muss eine <xref:System.Windows.DependencyProperty> sein.  \(Alle angefügten Eigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden als Abhängigkeitseigenschaften implementiert. Diese Frage ist daher nur für benutzerdefinierte, angefügte Eigenschaften relevant.\)  
  
<a name="indexanim"></a>   
### Indexer  
  
```  
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>  
```  
  
 Die meisten Abhängigkeitseigenschaften oder <xref:System.Windows.Freezable>\-Typen unterstützen keinen Indexer.  Indexer können daher in einem Animationspfad nur an einer Zwischenposition zwischen der Eigenschaft, mit der die Kette am benannten Ziel beginnt, und der ggf. animierten Eigenschaft verwendet werden.  In der dargestellten Syntax ist dies `propertyName2`.  Ein Indexer kann beispielsweise erforderlich sein, wenn die Zwischeneigenschaft eine Auflistung, z. B. <xref:System.Windows.Media.TransformGroup>, in einem Eigenschaftenpfad wie `RenderTransform.Children[1].Angle` ist.  
  
<a name="ppincode"></a>   
## PropertyPath im Code  
 Die Verwendung von Code für <xref:System.Windows.PropertyPath>, einschließlich Angaben zur Erstellung eines <xref:System.Windows.PropertyPath>, ist im Referenzthema für <xref:System.Windows.PropertyPath> dokumentiert.  
  
 In der Regel verwendet <xref:System.Windows.PropertyPath> zwei unterschiedliche Konstruktoren, einen für die Verwendung von Bindungen und einfachen Animationen und einen für die Verwendung komplexer Animationen.  Verwenden Sie die <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29>\-Signatur für Bindungsverwendungen, wenn das Objekt eine Zeichenfolge ist.  Verwenden Sie die <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29>\-Signatur für Animationspfade mit einem Schritt, wenn das Objekt eine <xref:System.Windows.DependencyProperty> ist.  Verwenden Sie die [PropertyPath\(String, Object\<xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29>\-Signatur für komplexe Animationen.  Der zuletzt genannte Konstruktor nutzt eine Tokenzeichenfolge für den ersten Parameter und ein Array mit Objekten, die die Positionen in der Tokenzeichenfolge füllen, um eine Eigenschaftenpfadbeziehung zu definieren.  
  
## Siehe auch  
 <xref:System.Windows.PropertyPath>   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)