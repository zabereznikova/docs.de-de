---
title: "XAML- und benutzerdefinierte Klassen f&#252;r WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Klassen, Benutzerdefinierte Klassen in XAML"
  - "Benutzerdefinierte Klassen in XAML"
  - "XAML, Benutzerdefinierte Klassen"
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# XAML- und benutzerdefinierte Klassen f&#252;r WPF
XAML, wie in [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Frameworks implementiert bietet die Möglichkeit, eine benutzerdefinierte Klasse oder Struktur in einer beliebigen Sprache [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] definieren und diese Klasse greift dann mithilfe des XAML\-Markups.  Sie können eine Mischung aus [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-definierten Typen und den benutzerdefinierten Typen innerhalb derselben Markupdatei verwenden, in der Regel durch die Zuordnung der benutzerdefinierten Typen zu einem XAML\-Namespace\-Präfix.  In diesem Thema werden die Anforderungen, die eine benutzerdefinierte Klasse erfüllen muss, um als XAML\-Element verwendbar sein.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Custom_Classes_in_Applications_vs__in_Assemblies"></a>   
## Benutzerdefinierte Klassen in Anwendungen oder Assemblys  
 Benutzerdefinierte Klassen, die in XAML verwendet werden, können auf zwei verschiedene Arten definiert sind: in Code\-Behind oder anderen Code, der die primäre [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendung erzeugt oder als Klasse in einer separaten Assembly als eine ausführbare Datei oder eine DLL verwendet als Klassenbibliothek.  Jeder dieser Ansätze hat bestimmte Vor\- und Nachteile.  
  
-   Der Vorteil beim Erstellen einer Klassenbibliothek besteht darin, dass benutzerdefinierte Klassen dieser Art von vielen verschiedenen Anwendungen gemeinsam genutzt werden können.  Eine separate Bibliothek stellt außerdem Versionsproblemen von Anwendungen leichter zu steuern und vereinfacht das Erstellen einer Klasse, in der die vorgesehene Verwendung von Klassen als Stammelement für eine XAML\-Seite ist.  
  
-   Der Vorteil beim Definieren der benutzerdefinierten Klassen in der Anwendung besteht darin, dass dieses Verfahren relativ einfach ist und die Bereitstellungs\- und Testprobleme minimiert, die auftreten können, wenn Sie neben der primären ausführbaren Anwendungsdatei noch separate Assemblys verwenden.  
  
-   Ob definiert in derselben oder in einer anderen Assembly, benutzerdefinierte Klassen zwischen CLR\-Namespace und XML\-Namespace zugeordnet werden müssen, damit sie in XAML als Elemente verwendet werden soll.  Weitere Informationen finden Sie unter [XAML\-Namespaces und Namespacezuordnung für WPF\-XAML](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="Requirements_for_a_Custom_Class_as_a_XAML_Element"></a>   
## Anforderungen für eine benutzerdefinierte Klasse als XAML\-Element  
 Ihre Klasse muss die folgenden Anforderungen erfüllen, um als Objektelement instanziiert werden zu können:  
  
-   Die benutzerdefinierte Klasse muss öffentlich sein und einen \(parameterlosen\) öffentlichen Standardkonstruktor unterstützen.  \(Hinweise zu Strukturen finden Sie im folgendem Abschnitt.\)  
  
-   Die benutzerdefinierte Klasse darf keine geschachtelte Klasse sein.  Geschachtelte Klassen und der "Punkt" in ihrer allgemeinen CLR\-Verwendungssyntax beeinträchtigen andere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\- und\/oder XAML\-Funktionen, wie z. B. angefügte Eigenschaften.  
  
 Die Objektdefinition aktiviert nicht nur die Objektelementsyntax, sondern auch die Eigenschaftenelementsyntax für alle anderen öffentlichen Eigenschaften, die das Objekt als Werttyp verwenden.  Der Grund dafür ist, dass das Objekt jetzt als Objektelement instanziiert werden und den Eigenschaftenelementwert einer Eigenschaft dieser Art füllen kann.  
  
### Strukturen  
 Strukturen, die Sie definieren, wie benutzerdefinierte Typen sind immer in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in XAML erstellt werden soll. Dies liegt daran, dass die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Compiler einen Standardkonstruktor implizit für eine Struktur erstellen, die alle Eigenschaftswerte mit ihren Standardwerten initialisiert.  In einigen Fällen ist das Standardkonstruktionsverhalten und\/oder die Objektelementverwendung für eine Struktur nicht wünschenswert.  Dies kann darauf zurückzuführen sein, dass die Struktur Werte und Funktionen konzeptuell als eine Einheit füllen soll, wobei die enthaltenen Werte sich gegenseitig ausschließende Interpretationen aufweisen und deshalb eine seiner Eigenschaften festgelegt werden kann.  Ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Beispiel für eine solche Struktur ist <xref:System.Windows.GridLength>.  Im Allgemeinen sollten diese Strukturen einen Typkonverter so implementieren, dass die Werte mithilfe von Zeichenfolgenkonventionen, die die verschiedenen Interpretationen oder Modi der Strukturwerte erstellen, in Attributform ausgedrückt werden können.  Die Struktur sollte auch ähnliches Verhalten durch einen nicht standardmäßigen Konstruktor für die Codekonstruktion verfügbar machen.  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>   
## Anforderungen für Eigenschaften einer benutzerdefinierten Klasse als XAML\-Attribute  
 Eigenschaften müssen auf einen Pro\-Wert\-Typ \(z. B. ein "Primitive"\) verweisen oder eine Klasse für einen Typ verwenden, der  entweder über einen Standardkonstruktor oder einen dedizierten Typkonverter verfügt, auf den ein XAML\-Prozessor zugreifen kann.  In der CLR\-XAML\-Implementierung finden XAML\-Prozessoren diese Konverter durch die systemeigene Unterstützung für Sprachprimitiven oder durch Anwenden von <xref:System.ComponentModel.TypeConverterAttribute> auf einen Typ oder ein Member in unterstützenden Typdefinitionen.  
  
 Alternativ dazu kann die Eigenschaft auch auf einen abstrakten Klassentyp oder eine Schnittstelle verweisen.  Bei abstrakten Klassen oder Schnittstellen besteht für XAML\-Analysen die Anforderung, dass der Eigenschaftswert mit Instanzen von praktischen Klassen gefüllt wird, die die Schnittstelle implementieren, oder mit Typinstanzen, die von der abstrakten Klasse abgeleitet sind.  
  
 Eigenschaften können in einer abstrakten Klasse deklariert werden, aber nur in praktischen Klassen festgelegt werden, die sich von der abstrakten Klasse ableiten.  Das liegt daran, dass die Erstellung des Objektelements für die Klasse einen öffentlichen Standardkonstruktor erfordert.  
  
### Attributsyntax mit Typkonverteraktivierung  
 Wenn Sie auf Klassenebene einen dedizierten Typkonverter mit Attributen bereitstellen, aktiviert die angewendete Typkonvertierung die Attributsyntax für alle Eigenschaften, die diesen Typ instanziieren müssen.  Ein Typkonverter aktiviert keine Objektelementnutzung des Typs. Die Objektelementnutzung wird nur durch das Vorhandensein eines Standardkonstruktors für diesen Typ aktiviert.  Aus diesem Grund können Eigenschaften mit Typkonverteraktivierung in der Eigenschaftensyntax im Allgemeinen nicht verwendet werden, es sei denn, der Typ selbst unterstützt ebenfalls die Objektelementsyntax.  Eine Ausnahme hierbei ist, dass Sie eine Eigenschaftenelementsyntax angeben können, wobei das Eigenschaftenelement jedoch eine Zeichenfolge enthält.  Dies ist im Wesentlichen äquivalent zur Nutzung der Attributsyntax. Diese Art der Nutzung ist nicht gängig, es sei denn, für den Attributwert ist eine stabilere Verarbeitung von Leerräumen erforderlich.  Die Beispiele unten zeigen z. B. ein Eigenschaftenelement, das eine Zeichenfolge verwendet, sowie die äquivalente Nutzung eines Attributs:  
  
 [!code-xml[XamlOvwSupport#GoofyTCPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xml[XamlOvwSupport#GoofyTCPE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 Beispiele für Eigenschaften, bei denen die Attributsyntax zulässig ist, aber der Eigenschaftenelementsyntax, die ein Objektelement enthält, wird durch XAML sind verschiedene Eigenschaften nicht zugelassen, die den <xref:System.Windows.Input.Cursor>\-Typ annehmen.  Die <xref:System.Windows.Input.Cursor>\-Klasse verfügt über den dedizierten Typkonverter <xref:System.Windows.Input.CursorConverter>, legt jedoch keinen Standardkonstruktor offen. Die <xref:System.Windows.FrameworkElement.Cursor%2A>\-Eigenschaft kann also nur per Attributsyntax festgelegt werden, auch wenn es sich beim eigentlichen <xref:System.Windows.Input.Cursor>\-Typ um einen Referenztyp handelt.  
  
### Typkonverter pro Eigenschaft  
 Alternativ dazu kann die Eigenschaft selbst auf der Eigenschaftenebene einen Typkonverter deklarieren.  Auf diese Weise wird eine "Minisprache" ermöglicht, die Objekte vom Typ der Eigenschaft inline instanziiert, indem eingehende Zeichenfolgenwerte des Attributs basierend auf dem entsprechenden Typ als Eingabe für einen <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>\-Vorgang verarbeitet werden.  In der Regel verwenden einen Accessor für die Bereitstellung und nicht als einzige Möglichkeit zum Festlegen einer Eigenschaft in XAML zu aktivieren.  Sie können jedoch auch Typkonverter für Attribute verwenden, für die Sie vorhandene [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Typen nutzen möchten, die keinen Standardkonstruktor oder einen Typkonverter mit Attributen bereitstellen.  Beispiele für vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] APIs sind bestimmte Eigenschaften, die den <xref:System.Globalization.CultureInfo>\-Typ annehmen.  In diesem Fall verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorhandenen Typ[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] <xref:System.Globalization.CultureInfo> , um Adressen kompatibilitäts\- und ein Szenarios zu verbessern, die in früheren Versionen des Frameworks verwendet wurden, aber der <xref:System.Globalization.CultureInfo> unterstützten Typ nicht über die erforderlichen Konstruktoren oder auf Typebene die Typkonvertierung als XAML\-Eigenschaftswert verwendbar sein soll.  
  
 Beim Offenlegen einer Eigenschaft, die per XAML verwendet werden kann, sollten Sie es besonders als Entwickler von Steuerelementen stets ernsthaft in Erwägung ziehen, die Eigenschaft mithilfe einer Abhängigkeitseigenschaft zu unterstützen.  Dies gilt insbesondere, wenn Sie die vorhandene [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Implementierung des XAML\-Prozessors verwenden, da die Leistung verbessern, indem Sie <xref:System.Windows.DependencyProperty> Zurückziehen verwenden.  Eine Abhängigkeitseigenschaft legt Eigenschaftensystemfunktionen für die Eigenschaft offen, die Benutzer von einer per XAML zugänglichen Eigenschaft erwarten.  Dies schließt Funktionen wie Animation, Datenbindung und Unterstützung von Stilen ein.  Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) und [Laden von XAML und Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md).  
  
### Schreiben eines Typkonverters und Hinzufügen von Attributen  
 Sie werden gelegentlich eine benutzerdefinierte abgeleitete <xref:System.ComponentModel.TypeConverter>\-Klasse schreiben müssen, um für Ihren Eigenschaftentyp eine Typkonvertierung bereitzustellen.  Anweisungen zur Ableitung von einem Typkonverter und zur Erstellung eines Typkonverters, der die XAML\-Verwendung unterstützt, sowie zur Anwendung des <xref:System.ComponentModel.TypeConverterAttribute> finden Sie unter [TypeConverter und XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>   
## Anforderungen für XAML\-Ereignishandler\-Attributsyntax von Ereignissen einer benutzerdefinierten Klasse  
 Um als [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignis verwendet werden zu können, muss das Ereignis als öffentliches Ereignis einer Klasse offengelegt werden, die einen Standardkonstruktor unterstützt, oder einer abstrakten Klasse, bei der auf das Ereignis über abgeleitete Klassen zugegriffen werden kann.  Um das Ereignis auf benutzerfreundliche Weise als [Routingereignis](GTMT) verwenden zu können, muss Ihr [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignis explizite `add`\- und `remove`\-Methoden implementieren. Diese Methoden fügen der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignissignatur Handler hinzu, entfernen diese und leiten sie an die Methoden <xref:System.Windows.UIElement.AddHandler%2A> und <xref:System.Windows.UIElement.RemoveHandler%2A> weiter.  Die Methoden fügen die Handler dem Routingereignis\-Handlerspeicher der Instanz hinzu \(bzw. entfernen diese daraus\), der das Ereignis zugeordnet ist.  
  
> [!NOTE]
>  Sie können Handler für Routingereignisse direkt registrieren, indem Sie das <xref:System.Windows.UIElement.AddHandler%2A>\-Ereignis verwenden, und um absichtlich kein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignis zu definieren, das das [Routingereignis](GTMT) offenlegt.  Dies ist im Allgemeinen nicht ratsam, da das XAML\-Attribut Ereignis nicht Syntax für das Anfügen von Handlern aktiviert und die resultierende Klasse eine weniger transparente der XAML\-Ansicht der Funktionen dieses Typs bereitstellt.  
  
<a name="Collection_Properties"></a>   
## Schreiben von Auflistungseigenschaften  
 Eigenschaften, die einen Auflistungstyp verwenden, verfügen über eine XAML\-Syntax, mit der Sie Objekte angeben können, die der Auflistung hinzugefügt werden.  Diese Syntax weist zwei interessante Funktionen auf.  
  
-   Sie müssen das Objekt, das das Auflistungsobjekt darstellt, in der Objektelementsyntax nicht angeben.  Dieser Auflistungstyp ist jeweils implizit vorhanden, wenn Sie eine Eigenschaft in XAML angeben, die einen Auflistungstyp verwendet.  
  
-   Untergeordnete Elemente der Auflistungseigenschaft im Markup werden verarbeitet, um zu Membern der Auflistung zu werden.  Normalerweise wird der Codezugriff auf die Member einer Auflistung mithilfe von Listen\-\/Wörterbuchmethoden  wie `Add` oder unter Verwendung eines Indexers durchgeführt.  Aber XAML\-Syntax unterstützt keine Methoden oder Indexer \(Ausnahme: XAML 2009 kann Methoden unterstützen, jedoch mit XAML 2009 schränkt die mögliche WPF\-Verwendung ein. Weitere Informationen finden Sie unter [XAML 2009\-Sprachfunktionen](../../../../docs/framework/xaml-services/xaml-2009-language-features.md)\).  Auflistungen sind bekanntermaßen eine häufige Anforderung an die Erstellung einer Struktur von Elementen, und Sie müssen diese Auflistungen mithilfe von deklarativen XAML\-Daten füllen.  Aus diesem Grund werden untergeordnete Elemente einer Auflistungseigenschaft verarbeitet, indem sie der Auflistung hinzugefügt werden, bei der es sich um den Typwert der Auflistungseigenschaft handelt.  
  
 Die .NET Framework\-XAML\-Dienst\-Implementierung und somit der WPF\-XAML\-Prozessor verwenden, was die folgende Definition für eine Auflistungseigenschaft bildet.  Der Eigenschaftentyp der Eigenschaft muss einen der folgenden Typen implementieren:  
  
-   Implementierung von <xref:System.Collections.IList>  
  
-   Implementierung von <xref:System.Collections.IDictionary> oder der generischen Entsprechung \(<xref:System.Collections.Generic.IDictionary%602>\).  
  
-   Wird von <xref:System.Array> \(Weitere Informationen zu Arrays in XAML finden Sie unter [x:Array\-Markuperweiterung](../../../../docs/framework/xaml-services/x-array-markup-extension.md)\).  
  
-   Implementierung von <xref:System.Windows.Markup.IAddChild> \(eine von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definierte Schnittstelle\).  
  
 Jeder dieser Typen in der CLR verfügt über eine `Add`\-Methode, die vom XAML\-Prozessor verwendet wird, um Elemente der zugrunde liegenden Auflistung hinzuzufügen, falls das Objektdiagramm erstellt.  
  
> [!NOTE]
>  Generische `List` und die `Dictionary`\-Schnittstellen \(<xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IDictionary%602>\) werden für die Auflistungserkennung nicht vom Prozessor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML unterstützt.  Sie können jedoch als Basisklasse die <xref:System.Collections.Generic.List%601>\-Klasse verwenden, da sie <xref:System.Collections.IList> direkt implementiert, bzw. die <xref:System.Collections.Generic.Dictionary%602>\-Klasse, da diese <xref:System.Collections.IDictionary> direkt implementiert.  
  
 Beim Deklarieren einer Eigenschaft, die eine Auflistung verwendet, sollten Sie sorgfältig darauf achten, wie der Eigenschaftswert in neuen Instanzen des Typs initialisiert wird.  Wenn Sie die Eigenschaft nicht als Abhängigkeitseigenschaft implementieren, ist es ratsam, dass die Eigenschaft ein Unterstützungsfeld verwendet, das den Auflistungstypkonstruktor aufruft.  Wenn es sich bei der Eigenschaft um eine Abhängigkeitseigenschaft handelt, kann es erforderlich sein, die Auflistungseigenschaft als Teil des standardmäßigen Typkonstruktors zu initialisieren.  Dies hängt damit zusammen, dass eine Abhängigkeitseigenschaft ihren Standardwert aus Metadaten übernimmt und Sie in der Regel nicht möchten, dass der Anfangswert einer Auflistungseigenschaft eine statische, freigegebene Auflistung ist.  Pro enthaltender Typinstanz sollte eine Auflistungsinstanz vorhanden sein.  Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
 Sie können für Ihre Auflistungseigenschaft einen benutzerdefinierten Auflistungstyp implementieren.  Aufgrund der impliziten Behandlung der Auflistungseigenschaft muss der benutzerdefinierte Auflistungstyp keinen Standardkonstruktor bereitstellen, um implizit in XAML verwendet werden zu können.  Sie können für den Auflistungstyp jedoch optional einen Standardkonstruktor bereitstellen.  Dies kann ein lohnenswertes Verfahren sein.  Sofern Sie keinen Standardkonstruktor bereitstellen, können Sie die Auflistung nicht explizit als Objektelement deklarieren.  Einige Entwickler, die Markup verwenden, bevorzugen aus Gründen des Markupstils ggf. explizite Auflistungen.  Außerdem kann ein Standardkonstruktor die Initialisierungsanforderungen vereinfachen, wenn Sie neue Objekte erstellen, die Ihren Auflistungstyp als Eigenschaftswert verwenden.  
  
<a name="XAMLCONtent"></a>   
## Deklarieren von XAML\-Inhaltseigenschaften  
 Die XAML\-Sprache definiert das Konzept einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Inhaltseigenschaft.  Jede Klasse, die in der Objektsyntax verwendet werden kann, kann über genau eine XAML\-Inhaltseigenschaft verfügen.  Um eine Eigenschaft als XAML\-Inhaltseigenschaft Ihrer Klasse zu deklarieren, wenden Sie das <xref:System.Windows.Markup.ContentPropertyAttribute> als Teil der Klassendefinition an.  Geben Sie den Namen der gewünschten XAML\-Inhaltseigenschaft im Attribut als <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A> an.  Die Eigenschaft wird als Zeichenfolge anhand des Namens, nicht als Reflektions konstrukt wie<xref:System.Reflection.PropertyInfo>angegeben.  
  
 Sie können eine Auflistungseigenschaft als XAML\-Inhaltseigenschaft angeben.  Dies führt zur Verwendung dieser Eigenschaft, wobei das Objektelement über ein oder mehrere untergeordnete Elemente verfügen kann, ohne dass dazwischen stehende Auflistungsobjektelemente oder Eigenschaftenelementtags erforderlich sind.  Diese Elemente werden dann als Wert für die XAML\-Inhaltseigenschaft behandelt und der unterstützenden Auflistungsinstanz hinzugefügt.  
  
 Einige vorhandene Eigenschaften des XAML\-Inhalts verwenden den Eigenschaftentyp aus `Object`.  Auf diese Weise wird eine XAML\-Inhaltseigenschaft aktiviert, die primitive Werte wie <xref:System.String> sowie einen einzelnen Verweisobjektwert verwenden kann.  Wenn Sie dieses Modell anwenden, ist Ihr Typ für die Typermittlung und die Behandlung der möglichen Typen zuständig.  Ein häufiger Grund für die Verwendung eines <xref:System.Object>\-Inhaltstyps ist die gleichzeitige Unterstützung eines einfachen Verfahrens zum Hinzufügen von Objektinhalt als Zeichenfolge \(die standardmäßig dargestellt wird\) und eines erweiterten Verfahrens zum Hinzufügen von Objektinhalt, bei dem eine andere Darstellungsart als die Standarddarstellung oder zusätzliche Daten angegeben werden.  
  
<a name="Serializing"></a>   
## Serialisieren von XAML  
 Für bestimmte Szenarien, z. B., wenn Sie ein Steuerelementautor können, sollten Sie außerdem sicherstellen, dass jede Objektdarstellung, die in XAML instanziiert werden kann, an dem entsprechenden XAML\-Markup außerdem serialisiert werden kann.  Die Serialisierungsanforderungen sind in diesem Thema nicht beschrieben.  Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md) und [Elementstruktur und Serialisierung](../../../../docs/framework/wpf/advanced/element-tree-and-serialization.md).  
  
## Siehe auch  
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [Laden von XAML und Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)