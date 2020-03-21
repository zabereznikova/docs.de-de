---
title: XAML- und benutzerdefinierte Klassen
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes in XAML [WPF]
- XAML [WPF], custom classes
- classes [WPF], custom classes in XAML
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
ms.openlocfilehash: 4cd0ba7fa03d2578f4477c3ccf53188fbbea2dbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186261"
---
# <a name="xaml-and-custom-classes-for-wpf"></a>XAML- und benutzerdefinierte Klassen für WPF
XAML, wie in CLR-Frameworks (Common Language Runtime) implementiert, unterstützt die Möglichkeit, eine benutzerdefinierte Klasse oder Struktur in jeder CLR-Sprache (Common Language Runtime) zu definieren und dann mithilfe von XAML-Markup auf diese Klasse zuzugreifen. Sie können eine Mischung aus [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Typen und ihren benutzerdefinierten Typen innerhalb derselben Markupdatei verwenden. Die übliche Vorgehensweise hierbei ist, Ihren benutzerdefinierten Typen ein XAML-Namespace-Präfix zuzuordnen. Dieses Thema beschreibt die Anforderungen, die eine benutzerdefinierte Klasse erfüllen muss, um als XAML-Element verwendet werden zu können.  

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
 Strukturen, die Sie als benutzerdefinierte Typen definieren, können [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] immer in XAML in erstellt werden. Dies liegt daran, dass die CLR-Compiler implizit einen parameterlosen Konstruktor für eine Struktur erstellen, die alle Eigenschaftswerte auf ihre Standardwerte initialisiert. In einigen Fällen sind für Strukturen das standardmäßige Konstruktionsverhalten und/oder die Verwendung als Objektelement nicht ratsam. Möglicherweise sollen die Struktur und ihre befüllten Werte konzeptionell als Einheit fungieren, wobei die enthaltenen Werte möglicherweise sich gegenseitig ausschließende Interpretationen haben und daher keiner ihrer Eigenschaften ein Wert zugewiesen werden kann. Ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Beispiel für eine <xref:System.Windows.GridLength>solche Struktur ist . Im Allgemeinen sollten solche Strukturen einen Typkonverter implementieren, sodass die Werte in Attributform ausgedrückt werden können, mit String-Konventionen, welche die verschiedenen Interpretationen oder Modi der Strukturwerte erstellen. Die Struktur sollte auch ähnliches Verhalten für die Codekonstruktion über einen nicht parameterlosen Konstruktor verfügbar machen.  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>
## <a name="requirements-for-properties-of-a-custom-class-as-xaml-attributes"></a>Anforderungen an Eigenschaften einer benutzerdefinierten Klasse als XAML-Attribute  
 Eigenschaften müssen auf einen Nebenwerttyp (z. B. einen Primitivtyp) verweisen oder eine Klasse für den Typ verwenden, der entweder über einen parameterlosen Konstruktor oder einen dedizierten Typkonverter verfügt, auf den ein XAML-Prozessor zugreifen kann. In der CLR XAML-Implementierung finden XAML-Prozessoren solche Konverter entweder über die <xref:System.ComponentModel.TypeConverterAttribute> native Unterstützung für Sprachprimitive oder durch die Anwendung eines Typs oder Members in Sicherungstypdefinitionen.  
  
 Alternativ kann die Eigenschaft auf einen abstrakten Klassentyp oder eine Schnittstelle verweisen. Bei abstrakten Klassen oder Schnittstellen wird bei der XAML-Analyse erwartet, dass der Eigenschaftswert mit praktischen Klasseninstanzen befüllt sein muss, die die Schnittstelle implementieren, oder Instanzen von Typen, die von der abstrakten Klasse abgeleitet sind.  
  
 Eigenschaften können für eine abstrakte Klasse deklariert werden, können jedoch nur in praktischen Klassen festgelegt werden, die von der abstrakten Klasse abgeleitet sind. Dies liegt daran, dass das Erstellen des Objektelements für die Klasse überhaupt einen öffentlichen parameterlosen Konstruktor für die Klasse erfordert.  
  
### <a name="typeconverter-enabled-attribute-syntax"></a>TypeConverter-fähige Attributsyntax  
 Wenn Sie einen dedizierten, mit Attributen versehenen Typkonverter auf Klassenebene bereitstellen, wird durch die angewendete Typumwandlung Attributsyntax für jede Eigenschaft ermöglicht, die diesen Typ instanziieren muss. Ein Typkonverter aktiviert die Verwendung von Objektelementen des Typs nicht. Nur das Vorhandensein eines parameterlosen Konstruktors für diesen Typ ermöglicht die Verwendung von Objektelementen. Aus diesem Grund sind Eigenschaften, für die ein Typkonverter aktiviert ist, im Allgemeinen nicht in Eigenschaftensyntax verwendbar, es sei denn, der Typ selbst unterstützt ebenfalls Objektelementsyntax. Die Ausnahme ist, wenn Sie eine Eigenschaftenelement-Syntax angeben, das Eigenschaftenelement jedoch eine Zeichenfolge enthält. Diese Verwendung ist im Wesentlichen mit einer Attributsyntaxverwendung vergleichbar, und eine solche Verwendung ist nicht üblich, es sei denn, es besteht eine notwendigkeit, den Attributwert robuster mit Leerraum zu verarbeiten. Nachfolgend sehen sie z.B. ein Eigenschaftenelement, das eine Zeichenfolge akzeptiert, und das dazugehörige Äquivalent in Attributsyntax:  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 Beispiele für Eigenschaften, bei denen Attributsyntax zulässig ist, aber die Eigenschaftenelementsyntax, die <xref:System.Windows.Input.Cursor> ein Objektelement enthält, über XAML nicht zulässig ist, sind verschiedene Eigenschaften, die den Typ annehmen. Die <xref:System.Windows.Input.Cursor> Klasse verfügt über <xref:System.Windows.Input.CursorConverter>einen dedizierten Typkonverter , macht <xref:System.Windows.FrameworkElement.Cursor%2A> jedoch keinen parameterlosen Konstruktor verfügbar, <xref:System.Windows.Input.Cursor> sodass die Eigenschaft nur über Attributsyntax festgelegt werden kann, obwohl der tatsächliche Typ ein Verweistyp ist.  
  
### <a name="per-property-type-converters"></a>Typkonverter auf Eigenschaftenebene  
 Alternativ kann die Eigenschaft selbst auf der Eigenschaftenebene einen Typkonverter deklarieren. Dies ermöglicht eine "Minisprache", die Objekte des Typs der Eigenschaft inline instanziiert, indem <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> eingehende Zeichenfolgenwerte des Attributs als Eingabe für einen Vorgang basierend auf dem entsprechenden Typ verarbeitet werden. Dies erfolgt in der Regel, um einen zweckmäßigen Accessor bereitzustellen und nicht als alleiniges Mittel zum Festlegen einer Eigenschaft in XAML. Es ist jedoch auch möglich, Typkonverter für Attribute zu verwenden, bei denen Sie vorhandene CLR-Typen verwenden möchten, die weder einen parameterlosen Konstruktor noch einen attributierten Typkonverter bereitstellen. Beispiele für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die API sind <xref:System.Globalization.CultureInfo> bestimmte Eigenschaften, die den Typ annehmen. In diesem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Fall wurde der vorhandene <xref:System.Globalization.CultureInfo> Microsoft .NET Framework-Typ verwendet, um Kompatibilitäts- und <xref:System.Globalization.CultureInfo> Migrationsszenarien, die in früheren Versionen von Frameworks verwendet wurden, besser zu adressieren, aber der Typ unterstützte nicht die erforderlichen Konstruktoren oder Typkonvertierungen auf Typebene, um direkt als XAML-Eigenschaftswert verwendet zu werden.  
  
 Wenn Sie eine Eigenschaft verfügbar machen, die in XAML Verwendung findet, insbesondere dann, wenn Sie Autor eines Steuerelements sind, sollten Sie unbedingt die Eigenschaft durch eine Abhängigkeitseigenschaft unterstützen. Dies gilt insbesondere, wenn [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Sie die vorhandene Implementierung des XAML-Prozessors verwenden, da Sie die Leistung durch die Verwendung <xref:System.Windows.DependencyProperty> von Backing verbessern können. Eine Abhängigkeitseigenschaft wird für Ihre Eigenschaft Funktionen des Eigenschaftensystems verfügbar machen, die Benutzer von einer XAML-zugänglichen Eigenschaft erwarten. Zu diesen Funktionen gehören z.B. Animationen, Datenbindungen und die Unterstützung von Stilen. Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md) und [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md).  
  
### <a name="writing-and-attributing-a-type-converter"></a>Schreiben und Attribuieren eines Typkonverters  
 Gelegentlich müssen Sie eine <xref:System.ComponentModel.TypeConverter> benutzerdefinierte abgeleitete Klasse schreiben, um eine Typkonvertierung für Ihren Eigenschaftstyp bereitzustellen. Anweisungen zum Ableiten und Erstellen eines Typkonverters, der XAML-Verwendungen <xref:System.ComponentModel.TypeConverterAttribute>unterstützen kann, und zum Anwenden der finden Sie unter [TypeConverters und XAML](typeconverters-and-xaml.md).  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>
## <a name="requirements-for-xaml-event-handler-attribute-syntax-on-events-of-a-custom-class"></a>Anforderungen an die Attributsyntax für XAML-Ereignishandler bei Ereignissen einer Benutzerdefinierten Klasse  
 Um als CLR-Ereignis verwendet zu werden, muss das Ereignis als öffentliches Ereignis für eine Klasse verfügbar gemacht werden, die einen parameterlosen Konstruktor unterstützt, oder als abstrakte Klasse, auf die auf das Ereignis für abgeleitete Klassen zugegriffen werden kann. Um bequem als geroutetes Ereignis verwendet zu werden, `add` sollte `remove` Ihr CLR-Ereignis explizite Methoden implementieren, die Handler für <xref:System.Windows.UIElement.AddHandler%2A> <xref:System.Windows.UIElement.RemoveHandler%2A> die CLR-Ereignissignatur hinzufügen und entfernen und diese Handler an die und Methoden weiterleiten. Diese Methoden fügen die Handler zum Routingereignis-Handlerspeicher auf der Instanz, der das Ereignis zugeordnet ist, hinzu oder entfernen sie.  
  
> [!NOTE]
> Es ist möglich, Handler direkt für <xref:System.Windows.UIElement.AddHandler%2A>geroutete Ereignisse mithilfe von zu registrieren und bewusst kein CLR-Ereignis zu definieren, das das routingierte Ereignis verfügbar macht. Davon wird im Allgemeinen abgeraten, da das Ereignis in diesem Fall keine XAML-Attributsyntax zum Anhängen von Handlern ermöglicht, und die resultierende Klasse eine weniger transparente XAML-Ansicht der Möglichkeiten dieses Typs bieten wird.  
  
<a name="Collection_Properties"></a>
## <a name="writing-collection-properties"></a>Schreiben von Auflistungseigenschaften  
 Eigenschaften, die einen Auflistungstyp annehmen, haben eine XAML-Syntax, die Ihnen ermöglicht, Objekte anzugeben, die der Auflistung hinzugefügt werden. Diese Syntax hat zwei interessante Features.  
  
- Das Objekt, das das Auflistungsobjekt darstellt, muss nicht in Objektelementsyntax angegeben werden. Dieses Auflistungstyps ist implizit dann vorhanden, wenn Sie eine Eigenschaft in XAML angeben, die einen Auflistungstyp annimmt.  
  
- Untergeordnete Elemente der Auflistungseigenschaft im Markup werden so verarbeitet, dass sie Mitglieder der Auflistung werden. Normalerweise erfolgt der Codezugriff auf die Mitglieder einer Auflistung über Listen- bzw. Wörterbuch-Methoden wie z.B. `Add`, oder über einen Indexer. XAML-Syntax unterstützt jedoch weder Methoden noch Indexer (Ausnahme: XAML 2009 kann Methoden unterstützen, aber die Verwendungen von XAML 2009 schränkt die Verwendungsmöglichkeiten mit WPF ein; siehe [XAML 2009-Sprachfunktionen](../../../desktop-wpf/xaml-services/xaml-2009-language-features.md)). Auflistungen sind offensichtlich eine durchaus übliche Anforderung beim Erstellen einer Struktur von Elementen, und Sie benötigen eine Methode zum Befüllen dieser Auflistungen im deklarativen XAML-Code. Aus diesem Grund werden untergeordnete Elemente einer Auflistungseigenschaft verarbeitet, indem sie der Auflistung hinzugefügt werden, die dem Typwert der Auflistungseigenschaft entspricht.  
  
 Die Implementierung von .NET Framework-XAML-Diensten und somit der WPF XAML-Prozessor verwenden die folgende Definition für eine Auflistungseigenschaft. Die Eigenschaftentyp der Eigenschaft muss einen der folgenden implementieren:  
  
- Implementierung von <xref:System.Collections.IList>  
  
- Implementiert <xref:System.Collections.IDictionary> oder das generische<xref:System.Collections.Generic.IDictionary%602>Äquivalent ( ).  
  
- Leitet von <xref:System.Array> (weitere Informationen zu Arrays in XAML finden Sie unter [x:Array Markup Extension](../../../desktop-wpf/xaml-services/xarray-markup-extension.md).)  
  
- Implementiert <xref:System.Windows.Markup.IAddChild> (eine Schnittstelle, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]die durch definiert ist).  
  
 Jeder dieser Typen in CLR verfügt über eine `Add`-Methode, die vom XAML-Prozessor verwendet wird, um der zugrunde liegenden Auflistung bei der Erstellung des Objektdiagramms Elemente hinzuzufügen.  
  
> [!NOTE]
> Die `List` generischen `Dictionary` Schnittstellen<xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IDictionary%602>( und ) werden für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Sammlungserkennung durch den XAML-Prozessor nicht unterstützt. Sie können <xref:System.Collections.Generic.List%601> die Klasse jedoch als Basisklasse verwenden, da sie <xref:System.Collections.IList> direkt oder <xref:System.Collections.Generic.Dictionary%602> als <xref:System.Collections.IDictionary> Basisklasse implementiert wird, da sie direkt implementiert wird.  
  
 Wenn Sie eine Eigenschaft, die eine Auflistung annimmt, deklarieren, sollten Sie sorgfältig darauf achten, wie dieser Eigenschaftswert in neuen Instanzen des Typs initialisiert wird. Wenn Sie die Eigenschaft nicht als Abhängigkeitseigenschaft implementieren, ist es angebracht, der Eigenschaft ein unterstützendes Feld zuzuweisen, das den Typkonstruktor der Auflistung aufruft. Wenn die Eigenschaft eine Abhängigkeitseigenschaft ist, müssen Sie die Auflistungseigenschaft als Teil des standardmäßigen Typkonstruktors initialisieren. Der Grund dafür ist, dass eine Abhängigkeitseigenschaft ihren Standardwert aus Metadaten übernimmt, und Sie in der Regel nicht möchten, dass der Anfangswert einer Auflistungseigenschaft eine statische, gemeinsam genutzte Auflistung ist. Es sollte eine Auflistungsinstanz pro enthaltender Typinstanz geben. Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md).  
  
 Sie können für Ihre Auflistungseigenschaft einen benutzerdefinierten Auflistungstyp implementieren. Aufgrund der impliziten Auflistungseigenschaftsbehandlung muss der benutzerdefinierte Auflistungstyp keinen parameterlosen Konstruktor bereitstellen, um implizit in XAML verwendet zu werden. Sie können jedoch optional einen parameterlosen Konstruktor für den Auflistungstyp bereitstellen. Dies ist eine durchaus ratsame Praxis. Wenn Sie keinen parameterlosen Konstruktor bereitstellen, können Sie die Auflistung nicht explizit als Objektelement deklarieren. Einige Markupautoren sehen die explizite Auflistung möglicherweise als guten und zu bevorzugenden Markupstil. Außerdem kann ein parameterloser Konstruktor die Initialisierungsanforderungen vereinfachen, wenn Sie neue Objekte erstellen, die Ihren Auflistungstyp als Eigenschaftswert verwenden.  
  
<a name="XAMLCONtent"></a>
## <a name="declaring-xaml-content-properties"></a>Deklarieren von XAML-Inhaltseigenschaften  
 Die XAML-Sprache definiert das Konzept einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Inhaltseigenschaft. Jede Klasse, die in Objektsyntax verwendet werden kann, hat genau eine XAML-Inhaltseigenschaft. Um eine Eigenschaft als XAML-Inhaltseigenschaft für Ihre <xref:System.Windows.Markup.ContentPropertyAttribute> Klasse zu deklarieren, wenden Sie die als Teil der Klassendefinition an. Geben Sie den Namen der beabsichtigten <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A> XAML-Inhaltseigenschaft als die im Attribut an. Die Eigenschaft wird als Zeichenfolge nach Namen und nicht <xref:System.Reflection.PropertyInfo>als Reflektionskonstrukt wie angegeben.  
  
 Sie können eine Auflistungseigenschaft als XAML-Inhaltseigenschaft angeben. Dies führt zu einer Verwendung dieser Eigenschaft, bei der das Objektelement ein oder mehrere untergeordnete Elemente ohne dazwischenliegende Auflistungs-Objektelemente oder Eigenschaftenelement-Tags haben kann. Diese Elemente werden dann als Wert für die XAML-Inhaltseigenschaft behandelt und der unterstützenden Auflistungsinstanz hinzugefügt.  
  
 Einige vorhandene XAML-Inhaltseigenschaften verwenden den Eigenschaftentyp `Object`. Dadurch wird eine XAML-Inhaltseigenschaft aktiviert, <xref:System.String> die primitive Werte wie einen sowie einen einzelnen Referenzobjektwert annehmen kann. Befolgen Sie dieses Modell, ist Ihr Typ sowohl für die Typbestimmung als auch für die Behandlung der möglichen Typen zuständig. Der typische Grund <xref:System.Object> für einen Inhaltstyp besteht darin, sowohl eine einfache Möglichkeit zum Hinzufügen von Objektinhalt als Zeichenfolge (die eine Standarddarstellungsbehandlung empfängt) als auch eine erweiterte Möglichkeit zum Hinzufügen von Objektinhalt zu unterstützen, das eine nicht standardmäßige Präsentation oder zusätzliche Daten angibt.  
  
<a name="Serializing"></a>
## <a name="serializing-xaml"></a>Serialisieren von XAML  
 Für bestimmte Szenarios, z.B. Wenn Sie Autor eines Steuerelements sind, möchten Sie möglicherweise auch sicherstellen, dass jede Objektdarstellung, die in XAML instanziiert werden kann, auch wieder zurück in das entsprechende XAML-Markup serialisiert werden kann. Serialisierungsanforderungen werden in diesem Thema nicht beschrieben. Informationen hierzu finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md) und [Elementstruktur und Serialisierung](element-tree-and-serialization.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
- [Übersicht über Basiselemente](base-elements-overview.md)
- [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md)
