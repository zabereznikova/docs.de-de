---
title: XAML- und benutzerdefinierte Klassen für WPF
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes in XAML [WPF]
- XAML [WPF], custom classes
- classes [WPF], custom classes in XAML
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
ms.openlocfilehash: a1de1ee80d1f88b0c0a7adfb75b96353b6861d97
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371891"
---
# <a name="xaml-and-custom-classes-for-wpf"></a>XAML- und benutzerdefinierte Klassen für WPF
Die Implementierung von XAML in [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Frameworks unterstützt die Möglichkeit zum Definieren einer benutzerdefinierten Klasse oder Struktur in einer beliebigen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Sprache und den anschließenden Zugriff auf diese Klasse unter Verwendung von XAML-Markup. Sie können eine Mischung aus [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Typen und ihren benutzerdefinierten Typen innerhalb derselben Markupdatei verwenden. Die übliche Vorgehensweise hierbei ist, Ihren benutzerdefinierten Typen ein XAML-Namespace-Präfix zuzuordnen. Dieses Thema beschreibt die Anforderungen, die eine benutzerdefinierte Klasse erfüllen muss, um als XAML-Element verwendet werden zu können.  
  
 
  
<a name="Custom_Classes_in_Applications_vs__in_Assemblies"></a>   
## <a name="custom-classes-in-applications-or-assemblies"></a>Benutzerdefinierte Klassen in Anwendungen oder Assemblys  
 Benutzerdefinierte Klassen, die in XAML verwendet werden, können auf zwei verschiedene Arten definiert werden: im CodeBehind oder in anderem Code, der die primäre [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendung erzeugt, oder als Klasse in einer separaten Assembly, z.B. einer ausführbare Datei oder einer als Klassenbibliothek verwendeten DLL. Jeder dieser Ansätze hat bestimmte Vor- und Nachteile.  
  
-   Der Vorteil der Erstellung einer Klassenbibliothek ist, dass alle diese benutzerdefinierten Klassen über viele verschiedene mögliche Anwendungen gemeinsam genutzt werden können. Eine separate Bibliothek gibt Ihnen auch mehr Kontrolle über die Versionierung von Anwendungen und vereinfacht das Erstellen einer Klasse, in denen die gewünschten Klasse als Stammelement auf einer XAML-Seite verwendet wird.  
  
-   Der Vorteil bei der Definition der benutzerdefinierten Klassen in der Anwendung ist, dass diese Technik relativ schlank ist und Probleme bei Bereitstellung und Tests minimiert, die auftreten, wenn Sie separate Assemblys zusätzlich zur ausführbaren Hauptdatei der Anwendung einführen.  
  
-   Egal, ob sie in derselben oder einer anderen Assembly definiert sind: benutzerdefinierte Klassen benötigen eine Zuordnung zwischen dem CLR-Namespace und dem XML-Namespace, um in XAML als Elemente verwendet werden zu können. Siehe [XAML-Namespaces und Namespacezuordnung für WPF-XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="Requirements_for_a_Custom_Class_as_a_XAML_Element"></a>   
## <a name="requirements-for-a-custom-class-as-a-xaml-element"></a>Anforderungen an benutzerdefinierten Klassen als XAML-Elemente  
 Um als Objektelement instanziiert werden zu können, muss die Klasse die folgenden Anforderungen erfüllen:  
  
-   Ihre benutzerdefinierte Klasse muss öffentlich sein und über einen parameterlosen öffentlichen Standardkonstruktor verfügen. (Hinweise zu Strukturen finden Sie im folgenden Abschnitt.)  
  
-   Die benutzerdefinierte Klasse darf keine geschachtelte Klasse sein. Geschachtelte Klassen und der "Punkt" in ihrer allgemeinen CLR-Notation verursachen Konflikte mit anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]- und/oder XAML-Funktionen wie z.B. angefügten Eigenschaften.  
  
 Ihre Objektdefinition ermöglicht nicht nur die Verwendung von Objektelement-Syntax, sondern auch von Eigenschaftenelement-Syntax für alle öffentlichen Eigenschaften, die dieses Objekt als Werttyp haben. Dies liegt darin begründet, dass das Objekt jetzt als Objektelement instanziiert werden kann und somit den Eigenschaftenelementwert einer solchen Eigenschaft befüllen kann.  
  
### <a name="structures"></a>Strukturen  
 Strukturen, die Sie als benutzerdefinierte Typen definieren, können immer in XAML in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erstellt werden. Grund hierfür ist, dass die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Compiler implizit einen Standardkonstruktor für Strukturen erstellen, die alle Eigenschaftswerte mit ihren Standardwerten initialisieren. In einigen Fällen sind für Strukturen das standardmäßige Konstruktionsverhalten und/oder die Verwendung als Objektelement nicht ratsam. Möglicherweise sollen die Struktur und ihre befüllten Werte konzeptionell als Einheit fungieren, wobei die enthaltenen Werte möglicherweise sich gegenseitig ausschließende Interpretationen haben und daher keiner ihrer Eigenschaften ein Wert zugewiesen werden kann. Ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Beispiel einer solchen Struktur wird <xref:System.Windows.GridLength>. Im Allgemeinen sollten solche Strukturen einen Typkonverter implementieren, sodass die Werte in Attributform ausgedrückt werden können, mit String-Konventionen, welche die verschiedenen Interpretationen oder Modi der Strukturwerte erstellen. Die Struktur sollte über einen nicht standardmäßigen Konstruktor ein ähnliches Verhalten auch für die Codekonstruktion verfügbar machen.  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>   
## <a name="requirements-for-properties-of-a-custom-class-as-xaml-attributes"></a>Anforderungen an Eigenschaften einer benutzerdefinierten Klasse als XAML-Attribute  
 Eigenschaften müssen einen Werttypen referenzieren (z.B. einen primitiven Typen) oder eine Klasse verwenden, die entweder einen Standardkonstruktor oder einen Typkonverter besitzt, auf den ein XAML-Prozessor zugreifen kann. In der CLR XAML-Implementierung finden XAML-Prozessoren entweder diese Konverter durch native Unterstützung für Sprachprimitive, oder durch Anwenden von <xref:System.ComponentModel.TypeConverterAttribute> auf einen Typ oder Member in unterstützenden Typdefinitionen.  
  
 Alternativ kann die Eigenschaft auf einen abstrakten Klassentyp oder eine Schnittstelle verweisen. Bei abstrakten Klassen oder Schnittstellen wird bei der XAML-Analyse erwartet, dass der Eigenschaftswert mit praktischen Klasseninstanzen befüllt sein muss, die die Schnittstelle implementieren, oder Instanzen von Typen, die von der abstrakten Klasse abgeleitet sind.  
  
 Eigenschaften können für eine abstrakte Klasse deklariert werden, können jedoch nur in praktischen Klassen festgelegt werden, die von der abstrakten Klasse abgeleitet sind. Dies liegt daran, dass für das Erstellen eines Objektelements dieser Klasse ein öffentlicher Standardkonstruktor für diese Klasse Grundvoraussetzung ist.  
  
### <a name="typeconverter-enabled-attribute-syntax"></a>TypeConverter-fähige Attributsyntax  
 Wenn Sie einen dedizierten, mit Attributen versehenen Typkonverter auf Klassenebene bereitstellen, wird durch die angewendete Typumwandlung Attributsyntax für jede Eigenschaft ermöglicht, die diesen Typ instanziieren muss. Ein Typkonverter ermöglicht keine Objektelementverwendung des Typs; nur das Vorhandensein eines Standardkonstruktors für diesen Typ ermöglicht Objektelementverwendung. Aus diesem Grund sind Eigenschaften, für die ein Typkonverter aktiviert ist, im Allgemeinen nicht in Eigenschaftensyntax verwendbar, es sei denn, der Typ selbst unterstützt ebenfalls Objektelementsyntax. Die Ausnahme ist, wenn Sie eine Eigenschaftenelement-Syntax angeben, das Eigenschaftenelement jedoch eine Zeichenfolge enthält. Diese Verwendung ist Wesentlichen äquivalent zur Nutzung der Attributsyntax, und eine solche Verwendung ist nicht üblich, es sei denn, besteht die Notwendigkeit für eine robustere Behandlung von Leerzeichen von den Wert des Attributs. Nachfolgend sehen sie z.B. ein Eigenschaftenelement, das eine Zeichenfolge akzeptiert, und das dazugehörige Äquivalent in Attributsyntax:  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 Beispiele für Eigenschaften, die Attributsyntax zulässig ist jedoch Eigenschaftenelement-Syntax, die ein Objektelement enthält ist nicht zulässig, über die XAML, sind verschiedene Eigenschaften, verwenden die <xref:System.Windows.Input.Cursor> Typ. Die <xref:System.Windows.Input.Cursor> -Klasse verfügt über einen Typkonverter <xref:System.Windows.Input.CursorConverter>, aber nicht über einen Standardkonstruktor verfügbar macht also die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft kann nur festgelegt werden über die Attributsyntax, obwohl die tatsächliche <xref:System.Windows.Input.Cursor> Typ ein Verweistyp ist.  
  
### <a name="per-property-type-converters"></a>Typkonverter auf Eigenschaftenebene  
 Alternativ kann die Eigenschaft selbst auf der Eigenschaftenebene einen Typkonverter deklarieren. Dies ermöglicht eine "Minisprache", die Objekte vom Typ der Eigenschaft Inline instanziiert, indem eingehende Zeichenfolgenwerte des Attributs als Eingabe für eine <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> Vorgang basierend auf den entsprechenden Typ. Dies erfolgt in der Regel, um einen zweckmäßigen Accessor bereitzustellen und nicht als alleiniges Mittel zum Festlegen einer Eigenschaft in XAML. Es ist jedoch auch möglich, Typkonverter für Attribute dort einzusetzen, wo Sie vorhandene [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Typen verwenden möchten, die entweder keinen Standardkonstruktor oder keinen attribuierten Typkonverter bereitstellen. Beispiele aus der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -API sind bestimmte Eigenschaften mit den <xref:System.Globalization.CultureInfo> Typ. In diesem Fall [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet das bestehende Microsoft .NET Framework <xref:System.Globalization.CultureInfo> Typ für eine bessere Kompatibilität und Migration von Szenarien, die in früheren Versionen des Frameworks verwendet wurden, aber die <xref:System.Globalization.CultureInfo> Typ nicht die erforderlichen Konstruktoren oder auf Typebene typkonvertierung als Eigenschaftswert XAML direkt verwendet werden kann.  
  
 Wenn Sie eine Eigenschaft verfügbar machen, die in XAML Verwendung findet, insbesondere dann, wenn Sie Autor eines Steuerelements sind, sollten Sie unbedingt die Eigenschaft durch eine Abhängigkeitseigenschaft unterstützen. Dies ist vor allem dann, wenn die vorhandene [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Implementierung der XAML-Prozessor, da Sie mithilfe von verbessern können <xref:System.Windows.DependencyProperty> sichern. Eine Abhängigkeitseigenschaft wird für Ihre Eigenschaft Funktionen des Eigenschaftensystems verfügbar machen, die Benutzer von einer XAML-zugänglichen Eigenschaft erwarten. Zu diesen Funktionen gehören z.B. Animationen, Datenbindungen und die Unterstützung von Stilen. Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md) und [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md).  
  
### <a name="writing-and-attributing-a-type-converter"></a>Schreiben und Attribuieren eines Typkonverters  
 Sie gelegentlich benötigen zum Schreiben einer benutzerdefinierten <xref:System.ComponentModel.TypeConverter> abgeleitete Klasse, um die typkonvertierung für Ihren Eigenschaftstyp bereitzustellen. Anweisungen zum Ableiten und erstellen einen Typkonverter, die XAML-Verwendungen unterstützen kann, und Anwenden der <xref:System.ComponentModel.TypeConverterAttribute>, finden Sie unter [TypeConverter und XAML](typeconverters-and-xaml.md).  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>   
## <a name="requirements-for-xaml-event-handler-attribute-syntax-on-events-of-a-custom-class"></a>Anforderungen an die Attributsyntax für XAML-Ereignishandler bei Ereignissen einer Benutzerdefinierten Klasse  
 Damit ein Ereignis als [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Ereignis verwendet werden kann, muss es als öffentliches Ereignis einer Klasse verfügbar gemacht werden, die einen Standardkonstruktor unterstützt, oder einer abstrakten Klasse, in der auf das Ereignis über abgeleitete Klassen zugegriffen werden kann. Um einfache Art als Routingereignis, verwendet werden Ihre [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Ereignis sollten explizit implementieren `add` und `remove` -Methoden, die hinzufügen und Entfernen von Ereignishandlern für die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Ereignissignatur und dann diese Handler an das <xref:System.Windows.UIElement.AddHandler%2A>und <xref:System.Windows.UIElement.RemoveHandler%2A> Methoden. Diese Methoden fügen die Handler zum Routingereignis-Handlerspeicher auf der Instanz, der das Ereignis zugeordnet ist, hinzu oder entfernen sie.  
  
> [!NOTE]
>  Es ist möglich, registrieren Sie Handler für Routingereignisse mithilfe direkt <xref:System.Windows.UIElement.AddHandler%2A>, und absichtlich kein definieren eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] -Ereignis, das das Routingereignis verfügbar macht. Davon wird im Allgemeinen abgeraten, da das Ereignis in diesem Fall keine XAML-Attributsyntax zum Anhängen von Handlern ermöglicht, und die resultierende Klasse eine weniger transparente XAML-Ansicht der Möglichkeiten dieses Typs bieten wird.  
  
<a name="Collection_Properties"></a>   
## <a name="writing-collection-properties"></a>Schreiben von Auflistungseigenschaften  
 Eigenschaften, die einen Auflistungstyp annehmen, haben eine XAML-Syntax, die Ihnen ermöglicht, Objekte anzugeben, die der Auflistung hinzugefügt werden. Diese Syntax hat zwei interessante Features.  
  
-   Das Objekt, das das Auflistungsobjekt darstellt, muss nicht in Objektelementsyntax angegeben werden. Dieses Auflistungstyps ist implizit dann vorhanden, wenn Sie eine Eigenschaft in XAML angeben, die einen Auflistungstyp annimmt.  
  
-   Untergeordnete Elemente der Auflistungseigenschaft im Markup werden so verarbeitet, dass sie Mitglieder der Auflistung werden. Normalerweise erfolgt der Codezugriff auf die Mitglieder einer Auflistung über Listen- bzw. Wörterbuch-Methoden wie z.B. `Add`, oder über einen Indexer. XAML-Syntax unterstützt jedoch keine Methoden noch Indexer (Ausnahme: XAML 2009 kann Methoden unterstützen, jedoch mit XAML 2009 schränkt die möglichen Verwendungen von WPF. finden Sie unter [XAML 2009-Sprachfunktionen](../../xaml-services/xaml-2009-language-features.md)). Auflistungen sind offensichtlich eine durchaus übliche Anforderung beim Erstellen einer Struktur von Elementen, und Sie benötigen eine Methode zum Befüllen dieser Auflistungen im deklarativen XAML-Code. Aus diesem Grund werden untergeordnete Elemente einer Auflistungseigenschaft verarbeitet, indem sie der Auflistung hinzugefügt werden, die dem Typwert der Auflistungseigenschaft entspricht.  
  
 Die Implementierung von .NET Framework-XAML-Diensten und somit der WPF XAML-Prozessor verwenden die folgende Definition für eine Auflistungseigenschaft. Die Eigenschaftentyp der Eigenschaft muss einen der folgenden implementieren:  
  
-   Implementiert <xref:System.Collections.IList>.  
  
-   Implementiert <xref:System.Collections.IDictionary> oder das generische Äquivalent (<xref:System.Collections.Generic.IDictionary%602>).  
  
-   Leitet sich von <xref:System.Array> (Weitere Informationen zu Arrays in XAML finden Sie unter [X: Array Markup Extension](../../xaml-services/x-array-markup-extension.md).)  
  
-   Implementiert <xref:System.Windows.Markup.IAddChild> (eine Schnittstelle definiert, indem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]).  
  
 Jeder dieser Typen in CLR verfügt über eine `Add`-Methode, die vom XAML-Prozessor verwendet wird, um der zugrunde liegenden Auflistung bei der Erstellung des Objektdiagramms Elemente hinzuzufügen.  
  
> [!NOTE]
>  Die generische `List` und `Dictionary` Schnittstellen (<xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IDictionary%602>) werden nicht unterstützt, für die auflistungserkennung durch den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Prozessor. Allerdings können Sie die <xref:System.Collections.Generic.List%601> Klasse als Basisklasse verwendet, da er implementiert <xref:System.Collections.IList> direkt oder <xref:System.Collections.Generic.Dictionary%602> als Basisklasse, da er implementiert <xref:System.Collections.IDictionary> direkt.  
  
 Wenn Sie eine Eigenschaft, die eine Auflistung annimmt, deklarieren, sollten Sie sorgfältig darauf achten, wie dieser Eigenschaftswert in neuen Instanzen des Typs initialisiert wird. Wenn Sie die Eigenschaft nicht als Abhängigkeitseigenschaft implementieren, ist es angebracht, der Eigenschaft ein unterstützendes Feld zuzuweisen, das den Typkonstruktor der Auflistung aufruft. Wenn die Eigenschaft eine Abhängigkeitseigenschaft ist, müssen Sie die Auflistungseigenschaft als Teil des standardmäßigen Typkonstruktors initialisieren. Der Grund dafür ist, dass eine Abhängigkeitseigenschaft ihren Standardwert aus Metadaten übernimmt, und Sie in der Regel nicht möchten, dass der Anfangswert einer Auflistungseigenschaft eine statische, gemeinsam genutzte Auflistung ist. Es sollte eine Auflistungsinstanz pro enthaltender Typinstanz geben. Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md).  
  
 Sie können für Ihre Auflistungseigenschaft einen benutzerdefinierten Auflistungstyp implementieren. Aufgrund der impliziten Behandlung der Auflistungseigenschaft muss der benutzerdefinierte Auflistungstyp keinen Standardkonstruktor bereitstellen, um implizit in XAML verwendet werden zu können. Allerdings können Sie für den Auflistungstyp optional einen Standardkonstruktor bereitstellen. Dies ist eine durchaus ratsame Praxis. Solange Sie keinen Standardkonstruktor bereitstellen, können Sie die Auflistung nicht explizit als Element deklarieren. Einige Markupautoren sehen die explizite Auflistung möglicherweise als guten und zu bevorzugenden Markupstil. Darüber hinaus kann ein Standardkonstruktor die Initialisierungsanforderungen vereinfachen, wenn Sie neue Objekte erstellen, die Ihren Auflistungstyp als Eigenschaftswert verwenden.  
  
<a name="XAMLCONtent"></a>   
## <a name="declaring-xaml-content-properties"></a>Deklarieren von XAML-Inhaltseigenschaften  
 Die XAML-Sprache definiert das Konzept einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Inhaltseigenschaft. Jede Klasse, die in Objektsyntax verwendet werden kann, hat genau eine XAML-Inhaltseigenschaft. Um eine Eigenschaft, die XAML-Inhaltseigenschaft für die Klasse zu deklarieren, wenden die <xref:System.Windows.Markup.ContentPropertyAttribute> als Teil der Definition der Klasse. Geben Sie den Namen der gewünschten XAML Inhaltseigenschaft als die <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A> im Attribut. Die Eigenschaft angegeben wird als Zeichenfolge den Namen nicht als Konstrukt Reflektion z. B. <xref:System.Reflection.PropertyInfo>.  
  
 Sie können eine Auflistungseigenschaft als XAML-Inhaltseigenschaft angeben. Dies führt zu einer Verwendung dieser Eigenschaft, bei der das Objektelement ein oder mehrere untergeordnete Elemente ohne dazwischenliegende Auflistungs-Objektelemente oder Eigenschaftenelement-Tags haben kann. Diese Elemente werden dann als Wert für die XAML-Inhaltseigenschaft behandelt und der unterstützenden Auflistungsinstanz hinzugefügt.  
  
 Einige vorhandene XAML-Inhaltseigenschaften verwenden den Eigenschaftentyp `Object`. Dies ermöglicht eine XAML-Inhalt, die primitive können Eigenschaftswerte wie z. B. eine <xref:System.String> sowie einen einzelnen Verweisobjektwert. Befolgen Sie dieses Modell, ist Ihr Typ sowohl für die Typbestimmung als auch für die Behandlung der möglichen Typen zuständig. Der Hauptgrund für eine <xref:System.Object> Content Typ ist zur Unterstützung von sowohl eine einfache Möglichkeit des Hinzufügens von Objektinhalten als Zeichenfolge (die eine standardmäßige WPF-Behandlung erhält) oder eine fortgeschrittene Möglichkeit zum Hinzufügen von Objekt-Inhalt, der angibt, eine nicht standardmäßige Präsentation oder zusätzliche Daten.  
  
<a name="Serializing"></a>   
## <a name="serializing-xaml"></a>Serialisieren von XAML  
 Für bestimmte Szenarios, z.B. Wenn Sie Autor eines Steuerelements sind, möchten Sie möglicherweise auch sicherstellen, dass jede Objektdarstellung, die in XAML instanziiert werden kann, auch wieder zurück in das entsprechende XAML-Markup serialisiert werden kann. Serialisierungsanforderungen werden in diesem Thema nicht beschrieben. Informationen hierzu finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md) und [Elementstruktur und Serialisierung](element-tree-and-serialization.md).  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
- [Übersicht über Basiselemente](base-elements-overview.md)
- [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md)
