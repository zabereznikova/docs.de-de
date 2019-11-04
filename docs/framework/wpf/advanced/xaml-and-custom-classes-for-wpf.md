---
title: XAML- und benutzerdefinierte Klassen für WPF
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes in XAML [WPF]
- XAML [WPF], custom classes
- classes [WPF], custom classes in XAML
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
ms.openlocfilehash: b573137b8d96565776d4b31f7ae8e5cc0b203a21
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459457"
---
# <a name="xaml-and-custom-classes-for-wpf"></a>XAML- und benutzerdefinierte Klassen für WPF
XAML wird in Common Language Runtime (CLR)-Frameworks implementiert und unterstützt die Möglichkeit, eine benutzerdefinierte Klasse oder Struktur in jeder beliebigen Common Language Runtime (CLR)-Sprache zu definieren und dann mithilfe von XAML-Markup auf diese Klasse zuzugreifen. Sie können eine Mischung aus [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Typen und ihren benutzerdefinierten Typen innerhalb derselben Markupdatei verwenden. Die übliche Vorgehensweise hierbei ist, Ihren benutzerdefinierten Typen ein XAML-Namespace-Präfix zuzuordnen. Dieses Thema beschreibt die Anforderungen, die eine benutzerdefinierte Klasse erfüllen muss, um als XAML-Element verwendet werden zu können.  

<a name="Custom_Classes_in_Applications_vs__in_Assemblies"></a>   
## <a name="custom-classes-in-applications-or-assemblies"></a>Benutzerdefinierte Klassen in Anwendungen oder Assemblys  
 Benutzerdefinierte Klassen, die in XAML verwendet werden, können auf zwei verschiedene Arten definiert werden: im CodeBehind oder in anderem Code, der die primäre [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendung erzeugt, oder als Klasse in einer separaten Assembly, z.B. einer ausführbare Datei oder einer als Klassenbibliothek verwendeten DLL. Jeder dieser Ansätze hat bestimmte Vor- und Nachteile.  
  
- Der Vorteil der Erstellung einer Klassenbibliothek ist, dass alle diese benutzerdefinierten Klassen über viele verschiedene mögliche Anwendungen gemeinsam genutzt werden können. Eine separate Bibliothek gibt Ihnen auch mehr Kontrolle über die Versionierung von Anwendungen und vereinfacht das Erstellen einer Klasse, in denen die gewünschten Klasse als Stammelement auf einer XAML-Seite verwendet wird.  
  
- Der Vorteil bei der Definition der benutzerdefinierten Klassen in der Anwendung ist, dass diese Technik relativ schlank ist und Probleme bei Bereitstellung und Tests minimiert, die auftreten, wenn Sie separate Assemblys zusätzlich zur ausführbaren Hauptdatei der Anwendung einführen.  
  
- Egal, ob sie in derselben oder einer anderen Assembly definiert sind: benutzerdefinierte Klassen benötigen eine Zuordnung zwischen dem CLR-Namespace und dem XML-Namespace, um in XAML als Elemente verwendet werden zu können. Siehe [XAML-Namespaces und Namespacezuordnung für WPF-XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="Requirements_for_a_Custom_Class_as_a_XAML_Element"></a>   
## <a name="requirements-for-a-custom-class-as-a-xaml-element"></a>Anforderungen an benutzerdefinierten Klassen als XAML-Elemente  
 Um als Objektelement instanziiert werden zu können, muss die Klasse die folgenden Anforderungen erfüllen:  
  
- Ihre benutzerdefinierte Klasse muss öffentlich sein und über einen parameterlosen öffentlichen Standardkonstruktor verfügen. (Hinweise zu Strukturen finden Sie im folgenden Abschnitt.)  
  
- Die benutzerdefinierte Klasse darf keine geschachtelte Klasse sein. Geschachtelte Klassen und der "Punkt" in ihrer allgemeinen CLR-Notation verursachen Konflikte mit anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]- und/oder XAML-Funktionen wie z.B. angefügten Eigenschaften.  
  
 Ihre Objektdefinition ermöglicht nicht nur die Verwendung von Objektelement-Syntax, sondern auch von Eigenschaftenelement-Syntax für alle öffentlichen Eigenschaften, die dieses Objekt als Werttyp haben. Dies liegt darin begründet, dass das Objekt jetzt als Objektelement instanziiert werden kann und somit den Eigenschaftenelementwert einer solchen Eigenschaft befüllen kann.  
  
### <a name="structures"></a>Strukturen  
 Strukturen, die Sie als benutzerdefinierte Typen definieren, können in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] immer in XAML erstellt werden. Dies liegt daran, dass die CLR-Compiler implizit einen Parameter losen Konstruktor für eine Struktur erstellen, die alle Eigenschaftswerte mit ihren Standardwerten initialisiert. In einigen Fällen sind für Strukturen das standardmäßige Konstruktionsverhalten und/oder die Verwendung als Objektelement nicht ratsam. Möglicherweise sollen die Struktur und ihre befüllten Werte konzeptionell als Einheit fungieren, wobei die enthaltenen Werte möglicherweise sich gegenseitig ausschließende Interpretationen haben und daher keiner ihrer Eigenschaften ein Wert zugewiesen werden kann. Ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Beispiel für eine solche Struktur ist <xref:System.Windows.GridLength>. Im Allgemeinen sollten solche Strukturen einen Typkonverter implementieren, sodass die Werte in Attributform ausgedrückt werden können, mit String-Konventionen, welche die verschiedenen Interpretationen oder Modi der Strukturwerte erstellen. Die Struktur sollte auch ähnliches Verhalten für die Code Erstellung durch einen nicht parameterlosen Konstruktor verfügbar machen.  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>   
## <a name="requirements-for-properties-of-a-custom-class-as-xaml-attributes"></a>Anforderungen an Eigenschaften einer benutzerdefinierten Klasse als XAML-Attribute  
 Eigenschaften müssen auf einen durch einen Werttyp (z. b. ein primitiv) verweisen oder eine Klasse für den Typ verwenden, die entweder einen Parameter losen Konstruktor oder einen dedizierten Typkonverter hat, auf den ein XAML-Prozessor zugreifen kann. In der CLR-XAML-Implementierung finden XAML-Prozessoren solche Konverter entweder durch systemeigene Unterstützung für sprach Primitive oder durch die Anwendung von <xref:System.ComponentModel.TypeConverterAttribute> auf einen Typ oder Member in den Sicherungstyp Definitionen.  
  
 Alternativ kann die Eigenschaft auf einen abstrakten Klassentyp oder eine Schnittstelle verweisen. Bei abstrakten Klassen oder Schnittstellen wird bei der XAML-Analyse erwartet, dass der Eigenschaftswert mit praktischen Klasseninstanzen befüllt sein muss, die die Schnittstelle implementieren, oder Instanzen von Typen, die von der abstrakten Klasse abgeleitet sind.  
  
 Eigenschaften können für eine abstrakte Klasse deklariert werden, können jedoch nur in praktischen Klassen festgelegt werden, die von der abstrakten Klasse abgeleitet sind. Dies liegt daran, dass das Erstellen des Object-Elements für die-Klasse überhaupt einen öffentlichen Parameter losen Konstruktor für die-Klasse erfordert.  
  
### <a name="typeconverter-enabled-attribute-syntax"></a>TypeConverter-fähige Attributsyntax  
 Wenn Sie einen dedizierten, mit Attributen versehenen Typkonverter auf Klassenebene bereitstellen, wird durch die angewendete Typumwandlung Attributsyntax für jede Eigenschaft ermöglicht, die diesen Typ instanziieren muss. Ein Typkonverter ermöglicht keine Objekt Element Verwendung des Typs. nur das vorhanden sein eines Parameter losen Konstruktors für diesen Typ ermöglicht die Verwendung von Objekt Elementen. Aus diesem Grund sind Eigenschaften, für die ein Typkonverter aktiviert ist, im Allgemeinen nicht in Eigenschaftensyntax verwendbar, es sei denn, der Typ selbst unterstützt ebenfalls Objektelementsyntax. Die Ausnahme ist, wenn Sie eine Eigenschaftenelement-Syntax angeben, das Eigenschaftenelement jedoch eine Zeichenfolge enthält. Diese Verwendung entspricht im Wesentlichen der Verwendung einer Attribut Syntax, und eine solche Verwendung ist nicht üblich, es sei denn, es ist eine robustere Leerraum Behandlung des Attribut Werts erforderlich. Nachfolgend sehen sie z.B. ein Eigenschaftenelement, das eine Zeichenfolge akzeptiert, und das dazugehörige Äquivalent in Attributsyntax:  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 Beispiele für Eigenschaften, bei denen die Attribut Syntax zulässig ist, aber die Eigenschafts Element Syntax, die ein Objekt Element enthält, nicht durch XAML zulässig ist, sind verschiedene Eigenschaften, die den <xref:System.Windows.Input.Cursor> Typ annehmen. Die <xref:System.Windows.Input.Cursor>-Klasse verfügt über einen dedizierten Typkonverter <xref:System.Windows.Input.CursorConverter>, macht aber keinen Parameter losen Konstruktor verfügbar, sodass die <xref:System.Windows.FrameworkElement.Cursor%2A>-Eigenschaft nur über die Attribut Syntax festgelegt werden kann, obwohl der tatsächliche <xref:System.Windows.Input.Cursor> Typ ein Verweistyp ist.  
  
### <a name="per-property-type-converters"></a>Typkonverter auf Eigenschaftenebene  
 Alternativ kann die Eigenschaft selbst auf der Eigenschaftenebene einen Typkonverter deklarieren. Dadurch wird eine "Mini Sprache" aktiviert, die Objekte des Typs der Eigenschaft inline instanziiert, indem die eingehenden Zeichen folgen Werte des Attributs als Eingabe für einen <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> Vorgang auf der Grundlage des entsprechenden Typs verarbeitet werden. Dies erfolgt in der Regel, um einen zweckmäßigen Accessor bereitzustellen und nicht als alleiniges Mittel zum Festlegen einer Eigenschaft in XAML. Es ist jedoch auch möglich, Typkonverter für Attribute zu verwenden, bei denen Sie vorhandene CLR-Typen verwenden möchten, die keinen Parameter losen Konstruktor oder einen attributierten Typkonverter bereitstellen. Beispiele aus der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-API sind bestimmte Eigenschaften, die den <xref:System.Globalization.CultureInfo>-Typ annehmen. In diesem Fall wurde [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das vorhandene Microsoft .NET Framework <xref:System.Globalization.CultureInfo> Type verwendet, um Kompatibilitäts-und Migrationsszenarien besser zu behandeln, die in früheren Versionen von Frameworks verwendet wurden, aber der <xref:System.Globalization.CultureInfo> Typ unterstützte die erforderlichen Konstruktoren nicht. Typkonvertierung auf Typebene, um direkt als XAML-Eigenschafts Wert verwendet werden zu können.  
  
 Wenn Sie eine Eigenschaft verfügbar machen, die in XAML Verwendung findet, insbesondere dann, wenn Sie Autor eines Steuerelements sind, sollten Sie unbedingt die Eigenschaft durch eine Abhängigkeitseigenschaft unterstützen. Dies trifft vor allem dann zu, wenn Sie die vorhandene [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Implementierung des XAML-Prozessors verwenden, da Sie die Leistung mithilfe <xref:System.Windows.DependencyProperty>-Unterstützung verbessern können. Eine Abhängigkeitseigenschaft wird für Ihre Eigenschaft Funktionen des Eigenschaftensystems verfügbar machen, die Benutzer von einer XAML-zugänglichen Eigenschaft erwarten. Zu diesen Funktionen gehören z.B. Animationen, Datenbindungen und die Unterstützung von Stilen. Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md) und [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md).  
  
### <a name="writing-and-attributing-a-type-converter"></a>Schreiben und Attribuieren eines Typkonverters  
 Gelegentlich müssen Sie eine benutzerdefinierte <xref:System.ComponentModel.TypeConverter> abgeleitete Klasse schreiben, um eine Typkonvertierung für Ihren Eigenschaftentyp bereitzustellen. Anweisungen zum Ableiten von und zum Erstellen eines Typkonverters, der XAML-Verwendungen unterstützen kann, sowie zum Anwenden des <xref:System.ComponentModel.TypeConverterAttribute>finden Sie unter [TypeConverter und XAML](typeconverters-and-xaml.md).  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>   
## <a name="requirements-for-xaml-event-handler-attribute-syntax-on-events-of-a-custom-class"></a>Anforderungen an die Attributsyntax für XAML-Ereignishandler bei Ereignissen einer Benutzerdefinierten Klasse  
 Um als CLR-Ereignis verwendet werden zu können, muss das Ereignis als öffentliches Ereignis für eine Klasse verfügbar gemacht werden, die einen Parameter losen Konstruktor unterstützt, oder für eine abstrakte Klasse, bei der auf das Ereignis in abgeleiteten Klassen zugegriffen werden kann. Um bequem als Routing Ereignis verwendet werden zu können, sollte das CLR-Ereignis explizite `add`-und `remove`-Methoden implementieren, die Handler für die CLR-Ereignis Signatur hinzufügen und entfernen und diese Handler an die <xref:System.Windows.UIElement.AddHandler%2A>-und <xref:System.Windows.UIElement.RemoveHandler%2A>-Methoden weiterleiten. Diese Methoden fügen die Handler zum Routingereignis-Handlerspeicher auf der Instanz, der das Ereignis zugeordnet ist, hinzu oder entfernen sie.  
  
> [!NOTE]
> Es ist möglich, Handler für Routing Ereignisse mithilfe von <xref:System.Windows.UIElement.AddHandler%2A>direkt zu registrieren und absichtlich kein CLR-Ereignis zu definieren, das das Routing Ereignis verfügbar macht. Davon wird im Allgemeinen abgeraten, da das Ereignis in diesem Fall keine XAML-Attributsyntax zum Anhängen von Handlern ermöglicht, und die resultierende Klasse eine weniger transparente XAML-Ansicht der Möglichkeiten dieses Typs bieten wird.  
  
<a name="Collection_Properties"></a>   
## <a name="writing-collection-properties"></a>Schreiben von Auflistungseigenschaften  
 Eigenschaften, die einen Auflistungstyp annehmen, haben eine XAML-Syntax, die Ihnen ermöglicht, Objekte anzugeben, die der Auflistung hinzugefügt werden. Diese Syntax hat zwei interessante Features.  
  
- Das Objekt, das das Auflistungsobjekt darstellt, muss nicht in Objektelementsyntax angegeben werden. Dieses Auflistungstyps ist implizit dann vorhanden, wenn Sie eine Eigenschaft in XAML angeben, die einen Auflistungstyp annimmt.  
  
- Untergeordnete Elemente der Auflistungseigenschaft im Markup werden so verarbeitet, dass sie Mitglieder der Auflistung werden. Normalerweise erfolgt der Codezugriff auf die Mitglieder einer Auflistung über Listen- bzw. Wörterbuch-Methoden wie z.B. `Add`, oder über einen Indexer. XAML-Syntax unterstützt jedoch weder Methoden noch Indexer (Ausnahme: XAML 2009 kann Methoden unterstützen, aber die Verwendungen von XAML 2009 schränkt die Verwendungsmöglichkeiten mit WPF ein; siehe [XAML 2009-Sprachfunktionen](../../xaml-services/xaml-2009-language-features.md)). Auflistungen sind offensichtlich eine durchaus übliche Anforderung beim Erstellen einer Struktur von Elementen, und Sie benötigen eine Methode zum Befüllen dieser Auflistungen im deklarativen XAML-Code. Aus diesem Grund werden untergeordnete Elemente einer Auflistungseigenschaft verarbeitet, indem sie der Auflistung hinzugefügt werden, die dem Typwert der Auflistungseigenschaft entspricht.  
  
 Die Implementierung von .NET Framework-XAML-Diensten und somit der WPF XAML-Prozessor verwenden die folgende Definition für eine Auflistungseigenschaft. Die Eigenschaftentyp der Eigenschaft muss einen der folgenden implementieren:  
  
- Implementiert <xref:System.Collections.IList>.  
  
- Implementiert <xref:System.Collections.IDictionary> oder das generische Äquivalent (<xref:System.Collections.Generic.IDictionary%602>).  
  
- Wird von <xref:System.Array> abgeleitet (Weitere Informationen zu Arrays in XAML finden Sie unter [x:Array-Markup Erweiterung](../../xaml-services/x-array-markup-extension.md).)  
  
- Implementiert <xref:System.Windows.Markup.IAddChild> (eine durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]definierte Schnittstelle).  
  
 Jeder dieser Typen in CLR verfügt über eine `Add`-Methode, die vom XAML-Prozessor verwendet wird, um der zugrunde liegenden Auflistung bei der Erstellung des Objektdiagramms Elemente hinzuzufügen.  
  
> [!NOTE]
> Die generischen `List` und `Dictionary` Schnittstellen (<xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IDictionary%602>) werden nicht für die Sammlungs Erkennung durch den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Prozessor unterstützt. Allerdings können Sie die <xref:System.Collections.Generic.List%601>-Klasse als Basisklasse verwenden, da Sie <xref:System.Collections.IList> direkt implementiert oder als Basisklasse <xref:System.Collections.Generic.Dictionary%602>, da Sie <xref:System.Collections.IDictionary> direkt implementiert.  
  
 Wenn Sie eine Eigenschaft, die eine Auflistung annimmt, deklarieren, sollten Sie sorgfältig darauf achten, wie dieser Eigenschaftswert in neuen Instanzen des Typs initialisiert wird. Wenn Sie die Eigenschaft nicht als Abhängigkeitseigenschaft implementieren, ist es angebracht, der Eigenschaft ein unterstützendes Feld zuzuweisen, das den Typkonstruktor der Auflistung aufruft. Wenn die Eigenschaft eine Abhängigkeitseigenschaft ist, müssen Sie die Auflistungseigenschaft als Teil des standardmäßigen Typkonstruktors initialisieren. Der Grund dafür ist, dass eine Abhängigkeitseigenschaft ihren Standardwert aus Metadaten übernimmt, und Sie in der Regel nicht möchten, dass der Anfangswert einer Auflistungseigenschaft eine statische, gemeinsam genutzte Auflistung ist. Es sollte eine Auflistungsinstanz pro enthaltender Typinstanz geben. Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md).  
  
 Sie können für Ihre Auflistungseigenschaft einen benutzerdefinierten Auflistungstyp implementieren. Aufgrund der impliziten Behandlung von Sammlungs Eigenschaften muss der benutzerdefinierte Auflistungstyp keinen Parameter losen Konstruktor bereitstellen, um implizit in XAML verwendet werden zu können. Sie können jedoch optional einen Parameter losen Konstruktor für den Auflistungstyp angeben. Dies ist eine durchaus ratsame Praxis. Wenn Sie keinen Parameter losen Konstruktor bereitstellen, können Sie die Auflistung nicht explizit als Objekt Element deklarieren. Einige Markupautoren sehen die explizite Auflistung möglicherweise als guten und zu bevorzugenden Markupstil. Außerdem kann ein Parameter loser Konstruktor die Initialisierungs Anforderungen vereinfachen, wenn Sie neue Objekte erstellen, die Ihren Auflistungstyp als Eigenschafts Wert verwenden.  
  
<a name="XAMLCONtent"></a>   
## <a name="declaring-xaml-content-properties"></a>Deklarieren von XAML-Inhaltseigenschaften  
 Die XAML-Sprache definiert das Konzept einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Inhaltseigenschaft. Jede Klasse, die in Objektsyntax verwendet werden kann, hat genau eine XAML-Inhaltseigenschaft. Um eine Eigenschaft als XAML-Inhalts Eigenschaft für die Klasse zu deklarieren, wenden Sie die <xref:System.Windows.Markup.ContentPropertyAttribute> als Teil der Klassendefinition an. Geben Sie den Namen der vorgesehenen XAML-Inhalts Eigenschaft als <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A> im Attribut an. Die-Eigenschaft wird als Zeichenfolge anhand des Namens angegeben, nicht als reflektionskonstrukt, wie z. b. <xref:System.Reflection.PropertyInfo>.  
  
 Sie können eine Auflistungseigenschaft als XAML-Inhaltseigenschaft angeben. Dies führt zu einer Verwendung dieser Eigenschaft, bei der das Objektelement ein oder mehrere untergeordnete Elemente ohne dazwischenliegende Auflistungs-Objektelemente oder Eigenschaftenelement-Tags haben kann. Diese Elemente werden dann als Wert für die XAML-Inhaltseigenschaft behandelt und der unterstützenden Auflistungsinstanz hinzugefügt.  
  
 Einige vorhandene XAML-Inhaltseigenschaften verwenden den Eigenschaftentyp `Object`. Dies ermöglicht eine XAML-Inhalts Eigenschaft, die primitive Werte annehmen kann, z. b. eine <xref:System.String>, und einen einzelnen Verweis Objektwert annimmt. Befolgen Sie dieses Modell, ist Ihr Typ sowohl für die Typbestimmung als auch für die Behandlung der möglichen Typen zuständig. Der typische Grund für einen <xref:System.Object> Inhaltstyp besteht darin, sowohl eine einfache Möglichkeit zum Hinzufügen von Objekt Inhalten als Zeichenfolge (die eine standardmäßige Präsentations Behandlung empfängt) als auch eine erweiterte Methode zum Hinzufügen von Objekt Inhalten zu unterstützen, die eine nicht standardmäßige Präsentation angibt, oder Weitere Daten.  
  
<a name="Serializing"></a>   
## <a name="serializing-xaml"></a>Serialisieren von XAML  
 Für bestimmte Szenarios, z.B. Wenn Sie Autor eines Steuerelements sind, möchten Sie möglicherweise auch sicherstellen, dass jede Objektdarstellung, die in XAML instanziiert werden kann, auch wieder zurück in das entsprechende XAML-Markup serialisiert werden kann. Serialisierungsanforderungen werden in diesem Thema nicht beschrieben. Informationen hierzu finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md) und [Elementstruktur und Serialisierung](element-tree-and-serialization.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
- [Übersicht über Basiselemente](base-elements-overview.md)
- [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md)
