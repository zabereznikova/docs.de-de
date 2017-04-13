---
title: "x:Name Directive | Microsoft Docs"
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
  - "x:Name"
  - "xName"
  - "Name"
helpviewer_keywords: 
  - "x:Name attribute [XAML Services]"
  - "XAML [XAML Services], x:Name attribute"
  - "Name attribute in XAML [XAML Services]"
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
caps.latest.revision: 27
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 27
---
# x:Name Directive
Identifiziert eindeutig XAML\-definierte Elemente in einem XAML\-Namescope.  XAML\-Namescopes und ihre Eindeutigkeitsmodelle können auf die instanziierten Objekte angewendet werden, wenn Frameworks APIs oder Implementierungsverhalten bereitstellen, die während der Laufzeit auf das XAML\-erstellte Objektdiagramm zugreifen.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object x:Name="XAMLNameValue".../>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`XAMLNameValue`|Eine Zeichenfolge, die den Einschränkungen der [XamlName\-Grammatik](../../../docs/framework/xaml-services/xamlname-grammar.md) entspricht.|  
  
## Hinweise  
 Nachdem `x:Name` auf das Sicherungsprogrammiermodell eines Frameworks angewendet wurde, entspricht der Name der Variablen, die einen von einem Konstruktor zurückgegebenen Objektverweis oder eine Instanz enthält.  
  
 Der Wert des Verbrauchs einer `x:Name`\-Direktive muss eindeutig innerhalb eines XAML\-Namescope sein.  Standardmäßig wird der primäre XAML\-Namescope bei Verwendung durch die .NET Framework\-XAML\-Dienste\-API am XAML\-Stammelement einer einzelnen XAML\-Produktion definiert und enthält die Elemente in dieser XAML\-Produktion.  Zusätzliche diskrete XAML\-Namensbereiche, die innerhalb einer einzelnen XAML\-Produktion auftreten können, können von Frameworks definiert werden, um bestimmte Szenarios zu behandeln.  Beispielsweise werden in WPF neue XAML\-Namescopes von jeder ebenfalls für diese XAML\-Erstellung definierten Vorlage definiert und erstellt.  Weitere Informationen zu XAML\-Namescopes \(geschrieben für WPF, aber relevant für viele XAML\-Namescope\-Konzepte\) finden Sie unter [WPF\-XAML\-Namescopes](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 `x:Name` sollte meist nicht in Situationen übernommen werden, die auch `x:Key` verwenden.  XAML\-Implementierungen von bestimmten vorhandenen Frameworks haben Ersetzungskonzepte zwischen `x:Key` und `x:Name` eingeführt, aber das ist keine empfohlene Vorgehensweise.  Beim Behandeln von Name\-\/Schlüssel\-Informationen wie z. B. <xref:System.Windows.Markup.INameScope> oder <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute> unterstützt .NET Framework\-XAML\-Dienst keine solchen Ersetzungskonzepte.  
  
 Regeln für die Zulassung von `x:Name` sowie der Namenseindeutigkeitserzwingung werden potenziell von bestimmten implementierenden Frameworks definiert.  Damit sie jedoch mit .NET Framework\-XAML\-Diensten verwendbar sind, sollten die Frameworkdefinitionen der XAML\-Namescope\-Eindeutigkeit mit der Definition der <xref:System.Windows.Markup.INameScope>\-Informationen in dieser Dokumentation konsistent sein und dieselben Regeln in Bezug darauf verwenden, wo die Informationen übernommen werden.  Beispielswiese unterteilt die [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]\-Implementierung verschiedene Markupelemente in separate <xref:System.Windows.NameScope>\-Bereiche, z. B. Ressourcenwörterbücher, die von der XAML auf Seitenebene erstellte logische Elementstruktur, Vorlagen und anderen Inhalt, und setzt dann die Eindeutigkeit des XAML\-Namens innerhalb jeder dieser XAML\-Namescopes durch.  
  
 Für benutzerdefinierte Typen mit XAML\-Serien\-Objektwriter der .NET Framework\-XAML\-Dienste, kann eine Eigenschaft erstellt oder geändert werden, die `x:Name` einem Typ zugeordnet.  Definieren Sie dieses Verhalten, indem Sie auf den Namen der Eigenschaft verweisen, die <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> im Typdefinitionscode zugeordnet werden soll.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> ist ein Attribut auf Typebene.  
  
 Mit .NET Framework XAML\-Diensten, kann die Unterstützungslogik für XAML\-Namescope\-Unterstützung auf eine frameworkneutrale Weise definiert werden, indem die <xref:System.Windows.Markup.INameScope>\-Schnittstelle implementiert wird.  
  
## Hinweise zur WPF\-Verwendung  
 In der Standardbuildkonfiguration für eine [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung, die XAML, partielle Klassen und Code\-Behind verwendet, wird der angegebene `x:Name` zum Namen eines Felds, das im zugrunde liegende Code erstellt wird, wenn [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] von einer Buildaufgabe zur Markupkompilierung verarbeitet wird, und das Feld einen Verweis auf das Objekt enthält. Standardmäßig ist das erstellte Feld intern.  Sie können den Feldzugriff ändern, indem Sie das [x:FieldModifier\-Attribut](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md) angeben.  In WPF und Silverlight gilt die Reihenfolge, dass die Markupkompilierung das Feld in einer partiellen Klasse definiert und benennt, der Wert anfänglich jedoch leer ist.  Anschließend wird eine generierte Methode mit dem Namen `InitializeComponent` aus dem Klassenkonstruktor aufgerufen.  `InitializeComponent` besteht aus `FindName`\-Aufrufen mithilfe aller `x:Name`\-Werte, die im XAML\-definierten Teil der partiellen Klasse als Eingabezeichenfolgen vorhanden sind.  Die Rückgabewerte werden dann auf den Feldverweis mit demselben Namen zugewiesen, um die Feldwerte mit Objekten zu füllen, die beim XAML\-Analysieren erstellt wurden.  Die Ausführung von `InitializeComponent` ermöglicht es, direkt auf das Laufzeitobjektdiagramm mit `x:Name`\/Feldname zu verweisen, anstatt `FindName` immer dann explizit aufrufen zu müssen, wenn Sie einen Verweis auf ein XAML\-definiertes Objekt benötigen.  
  
 Für eine WPF\-Anwendung, die die [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]\-Ziele verwendet und XAML\-Dateien mit `Page`\-Buildvorgang enthält, wird während der Kompilierung eine separate Verweiseigenschaft erstellt. Diese Eigenschaft fügt das `WithEvents`\-Schlüsselwort allen Elementen hinzu, die über einen `x:Name` verfügen, um die `Handles`\-Syntax für Ereignishandlerdelegaten zu unterstützen.  Diese Eigenschaft ist immer öffentlich.  Weitere Informationen finden Sie unter [Visual Basic\- und WPF\-Ereignisbehandlung](../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 `x:Name` wird vom WPF\-XAML\-Prozessor verwendet, um einen Namen in einem XAML\-Namescope zur Ladezeit zu registrieren, auch für Fälle, in denen die Seite nicht von Buildvorgängen kompiliertes Markup darstellt \(z. B. Loose XAML eines Ressourcenwörterbuchs\).  Ein Grund für dieses Verhalten liegt darin, dass der `x:Name` ggf. für die <xref:System.Windows.Data.Binding.ElementName%2A>\-Bindung benötigt wird.  Ausführlichere Informationen finden Sie unter [Übersicht über Datenbindung](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Wie zuvor erwähnt, sollte `x:Name` \(oder `Name`\) nicht in Situationen übernommen werden, die auch `x:Key` verwenden.  [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> hat das spezielle Verhalten, sich selbst als XAML\-Namensbereich zu definieren, gibt aber für <xref:System.Windows.Markup.INameScope>\-APIs "Nicht implementiert" zurück, um dieses Verhalten zu erzwingen.  Wenn der WPF\-XAML\-Parser `Name` oder `x:Name` in einem XAML\-definierten <xref:System.Windows.ResourceDictionary> feststellt, wird der Name keinem XAML\-Namescope hinzugefügt.  Der Versuch, diesen Namen in einem XAML\-Namescope und `FindName`\-Methoden zu suchen, gibt keine gültige Ergebnisse zurück.  
  
### x:Name und Name  
 Viele WPF\-Anwendungsszenarien sind in der Lage, jegliche Verwendung des `x:Name`\-Attributs zu verhindern, da die `Name`\-Abhängigkeitseigenschaft, die im standardmäßigen XAML\-Namespace für mehrere der wichtigen Basisklassen wie <xref:System.Windows.FrameworkElement> und <xref:System.Windows.FrameworkContentElement> angegeben ist, denselben Zweck erfüllt.  Es gibt noch einige allgemeine XAML\- und WPF\-Szenarien, in denen Codezugriff auf ein Element ohne `Name`\-Eigenschaft auf Frameworkebene wichtig ist.  Zum Beispiel unterstützten bestimmte Animations\- und Storyboard\-Unterstützungsklassen keine `Name`\-Eigenschaft. Auf diese muss jedoch häufig in Code verwiesen werden, um die Animation zu steuern.  Sie sollten `x:Name` als Attribut für in XAML erstellte Zeitachsen und Transformationen angeben, wenn Sie auf diese später in Code verweisen möchten.  
  
 Wenn <xref:System.Windows.FrameworkElement.Name%2A> als Eigenschaft eines Elements in der Klasse verfügbar ist, können <xref:System.Windows.FrameworkElement.Name%2A> und `x:Name` austauschbar als Attribute verwendet werden, aber es tritt eine Analyseausnahme auf, wenn beide für ein und dasselbe Element angegeben werden.  Wenn das XAML kompiliertes Markup ist, tritt die Ausnahme bei der Markupkompilierung auf, andernfalls tritt sie beim Laden auf.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> kann mithilfe der XAML\-Attributsyntax und im Code mithilfe von <xref:System.Windows.DependencyObject.SetValue%2A> festgelegt werden. Beachten Sie jedoch, dass das Festlegen der <xref:System.Windows.FrameworkElement.Name%2A>\-Eigenschaft im Code in den meisten Fällen nicht dazu führt, dass der repräsentative Feldverweis im XAML\-Namensbereich erstellt wird, wenn XAML bereits geladen ist.  Statt zu versuchen, <xref:System.Windows.FrameworkElement.Name%2A> in Code festzulegen, verwenden Sie die <xref:System.Windows.NameScope>\-Methoden aus dem Code für den entsprechenden Namensbereich.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> kann auch mit Eigenschaftenelementsyntax mit innerem Text festgelegt werden, aber das ist unüblich.  Im Gegensatz dazu kann `x:Name` nicht in der XAML\-Eigenschaftenelementsyntax oder in Code mit <xref:System.Windows.DependencyObject.SetValue%2A> verwendet werden. Er kann nur mithilfe der Attributsyntax in Objekten festgelegt werden, weil es sich um eine Direktive handelt.  
  
## Silverlight\-Verwendungshinweise  
 `x:Name` für Silverlight wird separat dokumentiert.  Weitere Informationen finden Sie unter [Sprachfeatures des XAML\-Namespace \(x:\)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## Siehe auch  
 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=fullName>   
 <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=fullName>   
 [Strukturen in WPF](../../../docs/framework/wpf/advanced/trees-in-wpf.md)