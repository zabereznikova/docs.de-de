---
title: Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: 7437add6795c1bb7f8a59807ebfc51dc2d0f987f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972024"
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten
Wenn Sie benutzerdefinierte Typen definieren, bei denen es sich um Geschäftsobjekte handelt oder es sich um Typen handelt, die keine Abhängigkeit von bestimmten Frameworks aufweisen, gibt es bestimmte bewährte Methoden für XAML, denen Sie folgen können. Wenn Sie diese Vorgehensweisen befolgen, können .NET Framework XAML-Dienste und Ihre XAML-Reader und XAML-Writer die XAML-Merkmale Ihres Typs ermitteln und ihr eine geeignete Darstellung in einem XAML-knotenstream mithilfe des XAML-Typsystems zur Verfügung stellen. In diesem Thema werden bewährte Methoden für Typdefinitionen, Element Definitionen und CLR-Attributierung von Typen oder Membern beschrieben.  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Konstruktormuster und Typdefinitionen für XAML  
 Eine benutzerdefinierte Klasse muss die folgenden Anforderungen erfüllen, damit Sie als Objekt Element in XAML instanziiert werden kann:  
  
- Die benutzerdefinierte Klasse muss öffentlich sein und muss einen Parameter losen öffentlichen Konstruktor verfügbar machen. (Hinweise zu Strukturen finden Sie im folgenden Abschnitt.)  
  
- Die benutzerdefinierte Klasse darf keine nicht-Klasse sein. Durch den zusätzlichen "Punkt" im Pfad des vollständigen Namens ist die Division der Klasse "Namespace" mehrdeutig, und es werden andere XAML-Funktionen wie z. b. angefügte Eigenschaften beeinträchtigt.  
  
 Wenn ein Objekt als Objekt Element instanziiert werden kann, kann das erstellte Objekt das Eigenschafts Element Formular aller Eigenschaften ausfüllen, die das Objekt als zugrunde liegenden Typ annehmen.  
  
 Sie können weiterhin Objektwerte für Typen bereitstellen, die diese Kriterien nicht erfüllen, wenn Sie einen Wert Konverter aktivieren. Weitere Informationen finden Sie unter [Typkonverter und Markup Erweiterungen für XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
### <a name="structures"></a>Strukturen  
 Strukturen können in XAML nach CLR-Definition erstellt werden. Dies liegt daran, dass ein CLR-Compiler implizit einen Parameter losen Konstruktor für eine Struktur erstellt. Dieser Konstruktor initialisiert alle Eigenschaftswerte mit ihren Standardwerten.  
  
 In einigen Fällen ist das standardmäßige Konstruktions Verhalten für eine Struktur nicht wünschenswert. Dies kann daran liegen, dass die-Struktur zum Auffüllen von Werten und zum Konzept der Funktionsweise als Union vorgesehen ist. Als Union können die enthaltenen Werte sich gegenseitig ausschließende Interpretationen befinden, sodass keine ihrer Eigenschaften festgelegt werden kann. Ein Beispiel für eine solche Struktur im WPF-Vokabular ist <xref:System.Windows.GridLength>. Diese Strukturen sollten einen Typkonverter implementieren, damit die Werte in Attribut Form mithilfe von Zeichen folgen Konventionen ausgedrückt werden können, die die verschiedenen Interpretationen oder Modi der Struktur Werte erstellen. Die Struktur sollte auch ähnliches Verhalten für die Code Erstellung durch einen nicht parameterlosen Konstruktor verfügbar machen.  
  
### <a name="interfaces"></a>Schnittstellen  
 Schnittstellen können als zugrunde liegende Typen von Membern verwendet werden. Das XAML-Typsystem überprüft die Zuweisungs Liste und erwartet, dass das Objekt, das als-Wert bereitgestellt wird, der-Schnittstelle zugewiesen werden kann. Es gibt kein Konzept, wie die Schnittstelle als XAML-Typ dargestellt werden muss, solange ein relevanter zustellbaren Typ die XAML-Konstruktionsanforderungen unterstützt.  
  
### <a name="factory-methods"></a>Factorymethoden  
 Factorymethoden sind ein XAML 2009-Feature. Sie ändern das XAML-Prinzip, dass Objekte Parameter lose Konstruktoren aufweisen müssen. Factorymethoden werden in diesem Thema nicht dokumentiert. Siehe [x:factorymethod-Direktive](x-factorymethod-directive.md).  
  
## <a name="enumerations"></a>Enumerationen  
 Enumerationen haben ein System eigenes XAML-Typkonvertierungs Verhalten. In XAML angegebene enumerationskonstantennamen werden für den zugrunde liegenden Enumerationstyp aufgelöst und geben den Enumerationswert an einen XAML-objektwriter zurück.  
  
 XAML unterstützt die Verwendung von Flags für Enumerationen mit angewendeten <xref:System.FlagsAttribute>. Weitere Informationen finden Sie [in der XAML-Syntax im Detail](../wpf/advanced/xaml-syntax-in-detail.md). (Die[XAML-Syntax wird im Detail](../wpf/advanced/xaml-syntax-in-detail.md) für die WPF-Zielgruppe geschrieben, aber die meisten Informationen in diesem Thema sind für XAML relevant, das nicht spezifisch für ein bestimmtes implementierungsframework ist.)  
  
## <a name="member-definitions"></a>Element Definitionen  
 Typen können Member für die XAML-Verwendung definieren. Typen, die Member definieren, die XAML-verwendbar sind, auch wenn dieser bestimmte Typ nicht XAML-verwendbar ist. Dies ist aufgrund der CLR-Vererbung möglich. Solange ein Typ, der den Member erbt, die XAML-Verwendung als Typ unterstützt, und der Member die XAML-Verwendung für den zugrunde liegenden Typ unterstützt oder eine systemeigene XAML-Syntax verfügbar ist, ist dieser Member XAML-verwendbar.  
  
### <a name="properties"></a>Eigenschaften  
 Wenn Sie Eigenschaften als öffentliche CLR-Eigenschaft mit den typischen CLR-`get` und `set` accessormustern und sprach geeigneter Key-Formulierung definieren, kann das XAML-Typsystem die Eigenschaft als Member mit den entsprechenden Informationen für <xref:System.Xaml.XamlMember> Eigenschaften, z. b. <xref:System.Xaml.XamlMember.IsReadPublic%2A> und <xref:System.Xaml.XamlMember.IsWritePublic%2A>, melden.  
  
 Bestimmte Eigenschaften können eine Text Syntax durch Anwenden von <xref:System.ComponentModel.TypeConverterAttribute>aktivieren. Weitere Informationen finden Sie unter [Typkonverter und Markup Erweiterungen für XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
 Wenn keine Text Syntax oder systemeigene XAML-Konvertierung vorhanden ist und keine weitere Dereferenzierung (z. b. eine Markup Erweiterungs Verwendung) vorhanden ist, muss der Typ einer Eigenschaft (<xref:System.Xaml.XamlMember.TargetType%2A> im XAML-Typsystem) in der Lage sein, eine Instanz an einen XAML-objektwriter zurückzugeben, indem der Zieltyp als CLR-Typ behandelt wird.  
  
 Wenn Sie XAML 2009 verwenden, kann die [x:Reference-Markup Erweiterung](x-reference-markup-extension.md) verwendet werden, um Werte bereitzustellen, wenn die vorherigen Überlegungen nicht erfüllt sind. Dies ist jedoch eher ein Verwendungs Problem als ein typdefinitions Problem.  
  
### <a name="events"></a>Ereignisse  
 Wenn Sie Ereignisse als öffentliches CLR-Ereignis definieren, kann das XAML-Typsystem das Ereignis als Member mit <xref:System.Xaml.XamlMember.IsEvent%2A> als `true`melden. Das Verknüpfen von Ereignis Handlern liegt nicht innerhalb des Bereichs .NET Framework Funktionen der XAML-Dienste. Dies gilt für bestimmte Frameworks und Implementierungen.  
  
### <a name="methods"></a>Methoden  
 Inline Code für Methoden ist keine XAML-Standardfunktion. In den meisten Fällen verweisen Sie nicht direkt auf Methoden Elemente aus XAML, und die Rolle von Methoden in XAML besteht nur darin, die Unterstützung für bestimmte XAML-Muster bereitzustellen. die [x:factorymethod-Direktive](x-factorymethod-directive.md) ist eine Ausnahme.  
  
### <a name="fields"></a>Felder  
 Die CLR-Entwurfs Richtlinien verhindern nicht statische Felder. Für statische Felder können Sie nur über die [x:statische Markup Erweiterung](x-static-markup-extension.md)auf statische Feldwerte zugreifen. in diesem Fall werden Sie in der CLR-Definition nichts Besonderes tun, um ein Feld für [x:static](x-static-markup-extension.md) -Verwendungen verfügbar zu machen.  
  
## <a name="attachable-members"></a>Anfügbare Member  
 Anfügbare Member werden für XAML über ein Accessor-Methoden Muster für einen definierenden Typ verfügbar gemacht. Der definierende Typ selbst muss nicht XAML-verwendbar als Objekt sein. Tatsächlich ist es ein gängiges Muster, eine Dienstklasse zu deklarieren, deren Rolle dem anfügbaren Member angehören und das zugehörige Verhalten implementiert, aber keine andere Funktion, wie z. b. eine Benutzeroberflächen Darstellung, bereitstellt. In den folgenden Abschnitten stellt der Platzhalter *propertyName* den Namen Ihres anfügbaren Members dar. Dieser Name muss in der [XamlName-Grammatik](xamlname-grammar.md)gültig sein.  
  
 Seien Sie vorsichtig bei Namenskollisionen zwischen diesen Mustern und anderen Methoden eines Typs. Wenn ein Member vorhanden ist, der mit einem der Muster übereinstimmt, kann er als anfügbare Element Verwendungs Pfad von einem XAML-Prozessor interpretiert werden, auch wenn dies nicht beabsichtigt war.  
  
#### <a name="the-getpropertyname-accessor"></a>Der GetPropertyName-Accessor  
 Die Signatur für den Accessoren `Get`*PropertyName* muss Folgende sein:  
  
 `public static object Get` *PropertyName* `(object`  `target` `)`  
  
- Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Sie können dies verwenden, um die Verwendung Ihres anfügbaren Members festzustellen. für Verwendungen außerhalb des vorgesehenen Bereichs werden ungültige Umwandlungs Ausnahmen ausgelöst, die dann durch einen XAML-Analysefehler angezeigt werden. Der Parameter Name `target` ist keine Voraussetzung, wird jedoch in den meisten Implementierungen `target` by-Konvention benannt.  
  
- Der Rückgabewert kann als spezifischerer Typ in Ihrer Implementierung angegeben werden.  
  
 Um eine <xref:System.ComponentModel.TypeConverter> aktivierte Text Syntax für die Attribut Verwendung des anfügbaren Members zu unterstützen, wenden Sie <xref:System.ComponentModel.TypeConverterAttribute> auf den `Get`*propertyName* -Accessor an. Die Anwendung auf die `get` statt auf die `set` erscheint möglicherweise nicht intuitiv. Diese Konvention kann jedoch das Konzept Schreib geschützter anfügbarer Member unterstützen, die serialisierbar sind, was in Designer Szenarios nützlich ist.  
  
#### <a name="the-setpropertyname-accessor"></a>Der SetPropertyName-Accessor  
 Die Signatur für den Set*propertyName* -Accessor muss wie folgt lauten:  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
- Das `target`-Objekt kann in der-Implementierung als spezifischeren Typ angegeben werden, und zwar mit der gleichen Logik und den Folgen, wie im vorherigen Abschnitt beschrieben.  
  
- Das `value`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden.  
  
 Beachten Sie, dass der Wert für diese Methode die Eingabe aus der XAML-Verwendung ist, in der Regel in Attribut Form. Aus dem Attribut Formular muss die Unterstützung von Wert Konvertern für eine Text Syntax und das Attribut für den `Get`*propertyName* -Accessor sein.  
  
### <a name="attachable-member-stores"></a>Anfügbare Member Stores  
 Die Accessormethoden reichen in der Regel nicht aus, um ein Mittel zum Platzieren von anfügbaren Element Werten in einem Objekt Diagramm oder zum Abrufen von Werten aus dem Objekt Diagramm und zum ordnungsgemäßen Serialisieren der Werte bereitzustellen. Um diese Funktionalität bereitzustellen, müssen die `target` Objekte in den vorherigen Accessor-Signaturen in der Lage sein, Werte zu speichern. Der Speichermechanismus sollte mit dem anfügbaren Member-Prinzip konsistent sein, dass der Member an Ziele anfügbar ist, wo sich der anfügbare Member nicht in der Liste der Mitglieder befindet. .NET Framework XAML-Dienste stellen eine Implementierungs Technik für anfügbare Element Speicher über die APIs <xref:System.Xaml.IAttachedPropertyStore> und <xref:System.Xaml.AttachablePropertyServices>bereit. <xref:System.Xaml.IAttachedPropertyStore> wird von den XAML-Writern zum Ermitteln der Speicher Implementierung verwendet und sollte für den Typ implementiert werden, der die `target` der Accessoren ist. Die statischen <xref:System.Xaml.AttachablePropertyServices>-APIs werden innerhalb des Texts der Accessoren verwendet und verweisen auf den anfügbaren Member durch seine <xref:System.Xaml.AttachableMemberIdentifier>.  
  
## <a name="xaml-related-clr-attributes"></a>XAML-bezogene CLR-Attribute  
 Das ordnungsgemäße Zuweisen von Typen, Membern und Assemblys ist wichtig, um XAML-typsysteminformationen an .NET Framework XAML-Dienste zu melden. Dies ist relevant, wenn Sie beabsichtigen, ihre Typen mit XAML-Systemen zu verwenden, die direkt auf .NET Framework XAML-Readern und XAML-Writern von XAML-Diensten basieren, oder wenn Sie ein XAML-basiertes Framework definieren oder verwenden, das auf diesen XAML-Readern und XAML-Writern basiert.  
  
 Eine Auflistung der einzelnen XAML-bezogenen Attribute, die für die XAML-Unterstützung der benutzerdefinierten Typen relevant sind, finden Sie unter [XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken](xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="usage"></a>Verwendung  
 Die Verwendung benutzerdefinierter Typen erfordert, dass der Markup Autor ein Präfix für die Assembly und den CLR-Namespace zuordnen muss, die den benutzerdefinierten Typ enthalten. Dieses Verfahren ist in diesem Thema nicht dokumentiert.  
  
## <a name="access-level"></a>Zugriffsebene  
 Mit XAML können Typen geladen und instanziiert werden, die über eine `internal` Zugriffsebene verfügen. Diese Funktion wird bereitgestellt, damit Benutzercode eigene Typen definieren und diese Klassen aus Markup instanziieren kann, das auch Teil desselben Benutzercode Bereichs ist.  
  
 Ein Beispiel für WPF ist, wenn Benutzercode eine <xref:System.Windows.Controls.UserControl> definiert, die als Möglichkeit zum Umgestalten eines UI-Verhaltens gedacht ist, aber nicht als Teil eines möglichen Erweiterungsmechanismus, der möglicherweise durch Deklarieren der unterstützenden Klasse mit `public` Zugriffsebene impliziert wird. Eine solche <xref:System.Windows.Controls.UserControl> kann mit `internal` Access deklariert werden, wenn der Unterstützungs Code in dieselbe Assembly kompiliert wird, aus der er als XAML-Typ referenziert wird.  
  
 Für eine Anwendung, die XAML unter voller Vertrauenswürdigkeit lädt und <xref:System.Xaml.XamlObjectWriter>verwendet, ist das Laden von Klassen mit `internal` Zugriffsebene immer aktiviert.  
  
 Für eine Anwendung, die XAML mit teilweiser Vertrauenswürdigkeit lädt, können Sie die Eigenschaften der Zugriffsebene mithilfe der <xref:System.Xaml.Permissions.XamlAccessLevel>-API steuern. Außerdem müssen zurückstellungs Mechanismen (z. b. das WPF-Vorlagen System) in der Lage sein, alle Zugriffsebenen-Berechtigungen weiterzugeben und Sie für die Evaluierungs Versionen der Laufzeit zu erhalten. Dies wird intern durch übergeben der <xref:System.Xaml.Permissions.XamlAccessLevel> Informationen gehandhabt.  
  
### <a name="wpf-implementation"></a>WPF-Implementierung  
 WPF-XAML verwendet ein teilweise vertrauenswürdiges Zugriffs Modell, bei dem BAML unter teilweiser Vertrauenswürdigkeit geladen wird. der Zugriff ist auf <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> für die Assembly beschränkt, die die BAML-Quelle ist. Bei der Verzögerung verwendet WPF <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> als Mechanismus zum übergeben der Informationen zur Zugriffsebene.  
  
 In der WPF-XAML-Terminologie ist ein *interner Typ* ein Typ, der durch dieselbe Assembly definiert wird, die auch die verweisende XAML enthält. Ein solcher Typ kann über einen XAML-Namespace zugeordnet werden, der den Assembly =-Teil einer Zuordnung absichtlich auslässt, z. b. `xmlns:local="clr-namespace:WPFApplication1"`.  Wenn BAML auf einen internen Typ verweist und dieser Typ über `internal` Zugriffsebene verfügt, generiert dies eine `GeneratedInternalTypeHelper` Klasse für die Assembly. Wenn Sie `GeneratedInternalTypeHelper`vermeiden möchten, müssen Sie entweder `public` Zugriffsebene verwenden, oder Sie müssen die relevante Klasse in eine separate Assembly einbeziehen und diese Assembly abhängig machen.  
  
## <a name="see-also"></a>Siehe auch

- [XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken](xaml-related-clr-attributes-for-custom-types-and-libraries.md)
- [XAML Services](index.md) (XAML-Dienste)
