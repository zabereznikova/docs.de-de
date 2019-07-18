---
title: Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: fea5c656cf5e793ca0717cf3ef60016128a942be
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617298"
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten
Beim Definieren von benutzerdefinierten Typen, die Geschäftsobjekte sind oder sind Typen, die nicht über eine Abhängigkeit auf bestimmten Frameworks verfügen, gibt es einige bewährten Methoden für XAML, die Sie ausführen können. Wenn Sie diese Vorgehensweisen ausführen, können .NET Framework-XAML-Dienste und die XAML-Readern und XAML-Writer die XAML-Eigenschaften des Typs ermitteln und geben sie entsprechende Darstellung in einem XAML-Knotenstream verwenden das XAML-Typsystem. Dieses Thema beschreibt bewährte Methoden für die Typdefinitionen, die Memberdefinitionen und CLR-Attributieren von Typen oder Member.  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Konstruktormuster und Typdefinitionen für XAML  
 Um als Objektelement in XAML instanziiert werden, muss eine benutzerdefinierte Klasse die folgenden Anforderungen erfüllen:  
  
- Die benutzerdefinierte Klasse muss öffentlich sein und einen (parameterlosen) öffentlichen Standardkonstruktor verfügbar machen. (Hinweise zu Strukturen finden Sie im folgenden Abschnitt.)  
  
- Die benutzerdefinierte Klasse muss eine geschachtelte Klasse nicht. Die zusätzlichen "Punkt" in den vollständigen Namen Pfad ist die Namespace der Klasse Division mehrdeutig und verursacht einen Konflikt mit anderen XAML-Funktionen wie z.B. angefügten Eigenschaften.  
  
 Wenn ein Objekt als Objektelement instanziiert werden kann, kann das erstellte Objekt der Eigenschaft Element der Eigenschaften Ausfüllen von Formularen, die das Objekt als ihren zugrunde liegenden Typ akzeptieren.  
  
 Sie können weiterhin Objektwerte für Typen, die diese Kriterien nicht erfüllen bereitstellen, wenn Sie einen Wertkonverter aktivieren. Weitere Informationen finden Sie unter [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
### <a name="structures"></a>Strukturen  
 Strukturen sind immer in XAML, CLR-Definition erstellt werden können. Dies ist ein CLR-Compiler implizit einen Standardkonstruktor für eine Struktur erstellt. Dieser Konstruktor initialisiert alle Eigenschaftswerte auf ihre Standardwerte.  
  
 In einigen Fällen ist das Standardverhalten für die Konstruktion für eine Struktur nicht wünschenswert. Dies kann sein, da die Struktur vorgesehen ist, um Werte und Funktionen im Prinzip als Union zu füllen. Als eine Union die enthaltenen Werte möglicherweise sich gegenseitig ausschließende Interpretationen haben und daher keine Eigenschaften festgelegt werden. Ein Beispiel einer solchen Struktur in WPF-Vokabular ist <xref:System.Windows.GridLength>. Diese Strukturen sollte einen Typkonverter implementieren, damit, dass die Werte können in Attributform, ausgedrückt werden mit String-Konventionen, die die verschiedenen Interpretationen oder Modi der Strukturwerte erstellen. Die Struktur sollte über einen nicht standardmäßigen Konstruktor ein ähnliches Verhalten auch für die Codekonstruktion verfügbar machen.  
  
### <a name="interfaces"></a>Schnittstellen  
 Schnittstellen können als zugrunde liegende Typen von Elementen verwendet werden. Das XAML-Typsystem überprüft die Liste zugeordnet werden kann und davon ausgegangen, dass das Objekt, das als Wert angegeben wird, auf die Schnittstelle zugewiesen werden kann. Es gibt kein Konzept wie die Schnittstelle als XAML-Typ angegeben werden muss, solange ein relevanten zugewiesen werden kann die XAML-Konstruktion-Anforderungen unterstützt.  
  
### <a name="factory-methods"></a>Factory-Methoden  
 Factory-Methoden sind eine XAML 2009-Funktion. Sie ändern das XAML-Prinzip, dass Objekte über Standardkonstruktoren verfügen müssen. Factory-Methoden sind nicht in diesem Thema dokumentiert. Finden Sie unter [X: FactoryMethod-Anweisung](x-factorymethod-directive.md).  
  
## <a name="enumerations"></a>Enumerationen  
 Enumerationen, Typkonvertierungsverhalten in XAML native haben. Namen für Aufzählungskonstanten in XAML angegebenen für den zugrunde liegenden Enumerationstyp aufgelöst werden, und den Enumerationswert an einen XAML-Objektwriter zurück.  
  
 XAML unterstützt eine Flags-Stil-Verwendung für Enumerationen mit <xref:System.FlagsAttribute> angewendet. Weitere Informationen finden Sie unter [XAML-Syntax im Detail](../wpf/advanced/xaml-syntax-in-detail.md). ([XAML-Syntax im Detail](../wpf/advanced/xaml-syntax-in-detail.md) geschrieben wird, die WPF-Zielgruppe, aber die meisten der Informationen in diesem Thema ist relevant für XAML, die nicht für ein bestimmtes implementierendes Framework spezifisch ist.)  
  
## <a name="member-definitions"></a>Elementdefinitionen  
 Typen können Mitglieder für die Verwendung von XAML definieren. Es ist möglich, dass Typen, die Elemente zu, die XAML-verwendet werden definieren, auch wenn diese bestimmte Art nicht XAML-verwendbar ist. Dies ist möglich, durch die CLR-Vererbung. Solange eine Art, die das Element erbt XAML-Verwendung als Typ unterstützt und das Element unterstützt die Verwendung der XAML für die zugrunde liegenden Typ oder verfügt über eine native XAML-Syntax zur Verfügung, ist dieser Member XAML-verwendet werden.  
  
### <a name="properties"></a>Eigenschaften  
 Wenn Sie die Eigenschaften als eine öffentliche CLR-Eigenschaft, die mit der typischen CLR definieren `get` und `set` Accessor Muster sprachspezifischen Keywording das XAML-Typsystem kann Berichts und, die Eigenschaft als ein Element mit entsprechenden Informationen für bereitgestellt <xref:System.Xaml.XamlMember> Eigenschaften, z. B. <xref:System.Xaml.XamlMember.IsReadPublic%2A> und <xref:System.Xaml.XamlMember.IsWritePublic%2A>.  
  
 Bestimmte Eigenschaften können eine Textsyntax aktivieren, durch Anwenden von <xref:System.ComponentModel.TypeConverterAttribute>. Weitere Informationen finden Sie unter [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
 In Ermangelung einer Textsyntax oder systemeigenen XAML-Konvertierung und ohne weitere Dereferenzierung, z. B. eine Markuperweiterungsverwendung, der den Typ einer Eigenschaft (<xref:System.Xaml.XamlMember.TargetType%2A> in der XAML-Typsystem) muss in der Lage, eine Instanz einer XAML-Objektwriter wiederherstellen, indem Sie zum Behandeln von t Ziel-Typ als CLR-Typ.  
  
 Wenn Sie XAML 2009 verwendet wird, [X: Reference Markup Extension](x-reference-markup-extension.md) können verwendet werden, um die Werte bereitzustellen, wenn die vorausgegangenen Ausführungen nicht erfüllt werden; dies ist jedoch mehr ein Syntaxproblem als ein Problem der Type-Definition.  
  
### <a name="events"></a>Ereignisse  
 Wenn Sie Ereignisse als öffentliche CLR-Ereignis definieren, kann das XAML-Typsystem als ein Element mit dem das Ereignis melden <xref:System.Xaml.XamlMember.IsEvent%2A> als `true`. Verknüpfen die Ereignishandler ist nicht innerhalb des Bereichs von .NET Framework XAML Services-Funktionen. Dadurch wird die Implementierung und spezifische Frameworks überlassen.  
  
### <a name="methods"></a>Methoden  
 Inline-Code für Methoden ist es sich nicht um eine Standard-XAML-Funktion. In den meisten Fällen Sie nicht direkt auf Mitglieder der Methode aus XAML und die Rolle der Methoden in XAML ist nur für bestimmte XAML-Muster unterstützen. [X: FactoryMethod-Direktive](x-factorymethod-directive.md) ist eine Ausnahme.  
  
### <a name="fields"></a>Felder  
 CLR-Entwurfsrichtlinien Raten von nicht statischen Felder ab. Für statische Felder, die Sie Werte für statische Felder zugreifen können nur über [X: statische Markuperweiterung](x-static-markup-extension.md); in diesem Fall Sie nichts in der CLR-Definition für ein Feld verfügbar zu machen, spezielle [X: Static](x-static-markup-extension.md) Verwendungen.  
  
## <a name="attachable-members"></a>Anfügbare Member  
 Anfügbare Member werden über ein Accessor-Methode Muster für einen definierenden Typ für XAML verfügbar gemacht. Der definierende Typ selbst muss nicht als Objekt XAML verwendet werden kann. In der Tat ein häufiges Muster ist, um eine Dienstklasse zu deklarieren, dessen Rolle, auf die anfügbaren Member und das zugehörige Verhalten implementiert, aber nicht für andere Funktionen wie z. B. eine Darstellung der Benutzeroberfläche zu verarbeiten. Für die folgenden Abschnitte, die Platzhalter *PropertyName* den Namen des anfügbaren Members darstellt. Dieser Name muss in gültig sein der [XamlName-Grammatik](xamlname-grammar.md).  
  
 Seien Sie vorsichtig, Namenskonflikte zwischen diesen Mustern und andere Methoden eines Typs. Wenn ein Element vorhanden, der mit einem der Muster übereinstimmt ist, kann es als ein anfügbarer Member Nutzung Weg von einem XAML-Prozessor interpretiert werden, auch wenn, die nicht Ihrer Absicht war.  
  
#### <a name="the-getpropertyname-accessor"></a>Der Accessor GetPropertyName-Methode  
 Die Signatur für den Accessoren `Get`*PropertyName* muss Folgende sein:  
  
 `public static object Get` *PropertyName* `(object`  `target` `)`  
  
- Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Damit können Sie die Verwendung des anfügbaren Members Bereich; Bei Verwendung außerhalb Ihrer vorgesehene Umfang löst ungültige Umwandlung von Ausnahmen, die dann von einem XAML-Analyse-Fehler angezeigt werden. Der Name des Parameters `target` nicht erforderlich ist, hat aber den Namen `target` gemäß der Konvention in den meisten Implementierungen.  
  
- Der Rückgabewert kann als spezifischerer Typ in Ihrer Implementierung angegeben werden.  
  
 Zur Unterstützung einer <xref:System.ComponentModel.TypeConverter> aktiviert Textsyntax für die Verwendung von Attributen des abzurufenden anfügbaren Members, gelten <xref:System.ComponentModel.TypeConverterAttribute> auf die `Get` *PropertyName* Accessor. Anwenden auf die `get` statt der `set` mag unkonventionell; allerdings kann diese Konvention unterstützen das Konzept von nur-Lese anfügbare Member, die serialisierbar sind, was in Szenarien nützlich ist.  
  
#### <a name="the-setpropertyname-accessor"></a>Der SetPropertyName Accessor  
 Die Signatur für den Satz*PropertyName* Accessor muss:  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
- Die `target` Objekt kann als spezifischerer Typ in Ihrer Implementierung mit derselben Logik und die Konsequenzen angegeben werden, wie im vorherigen Abschnitt beschrieben.  
  
- Das `value`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden.  
  
 Denken Sie daran, dass der Wert für diese Methode die Eingabe aus der XAML-Syntax, in der Regel in Attributform stammen. In Attributform sein Wert Konverter-Unterstützung für eine Textsyntax sind, und Sie auf das die `Get` *PropertyName* Accessor.  
  
### <a name="attachable-member-stores"></a>Anfügbare Member speichert  
 Die Accessor-Methoden sind in der Regel nicht ausreichend, bieten eine Möglichkeit zum anfügbaren Member-Werte in ein Objektdiagramm zu platzieren oder zum Abrufen von Werten aus dem Objektdiagramm und korrekt zu serialisieren. Mit dieser Funktionalität, die `target` Objekte in den oben stehenden Accessorsignaturen müssen zum Speichern von Werten der Lage sein. Der Speichermechanismus sollte mit dem Prinzip des anfügbaren Members entsprechen, die der Member anfügbar ist, um Ziele ist, in dem der anfügbare Member nicht in der Liste ist. .NET Framework-XAML-Dienste bietet eine Implementierung, die auch für anfügbarer Member über die APIs speichert <xref:System.Xaml.IAttachedPropertyStore> und <xref:System.Xaml.AttachablePropertyServices>. <xref:System.Xaml.IAttachedPropertyStore> wird durch die XAML-Writer verwendet, um die Implementierung des Speichers zu ermitteln, und sollte implementiert werden, auf dem Typ, der die `target` der Accessoren. Die statische <xref:System.Xaml.AttachablePropertyServices> APIs innerhalb des Texts der Accessoren verwendet werden, und klicken Sie auf dem anfügbare Member verweisen die <xref:System.Xaml.AttachableMemberIdentifier>.  
  
## <a name="xaml-related-clr-attributes"></a>XAML-bezogene CLR-Attribute  
 Ordnungsgemäße Attributierung Ihre Typen, Member und Assemblys ist wichtig, in der Reihenfolge nach Bericht XAML-Typsysteminformationen für .NET Framework-XAML-Dienste. Dies ist relevant, wenn Sie beabsichtigen, Ihre Typen für die Verwendung mit XAML-Systeme, die direkt auf .NET Framework XAML Services XAML-Readern und XAML-Writern basieren, oder wenn Sie definieren, oder Verwenden eines XAML-Writern-Frameworks, das für diese XAML-Readern und XAML-Writern basiert.  
  
 Eine Liste der einzelnen XAML-bezogene Attribute, die für die XAML-Unterstützung benutzerdefinierter Typen relevant sind, finden Sie unter [XAML-Related CLR-Attribute für benutzerdefinierte Typen und Bibliotheken](xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="usage"></a>Verwendung  
 Verwendung von benutzerdefinierten Typen erfordert, dass der Ersteller des Markups hinzufügt zuordnen muss ein Präfix für die Assembly und die CLR-Namespace, die den benutzerdefinierten Typ enthalten. Dieses Verfahren ist nicht in diesem Thema dokumentiert.  
  
## <a name="access-level"></a>Zugriffsebene  
 XAML bietet eine Möglichkeit zum Laden und Instanziieren von Typen, die eine `internal` Zugriffsebene. Diese Funktion wird bereitgestellt, sodass Benutzercode kann ihre eigenen Typen definieren und diese Klassen von Markup, das ebenfalls den gleichen Code Benutzerbereich gehört die Instanziierung.  
  
 Ein Beispiel aus WPF ist, wenn der Benutzercode definiert eine <xref:System.Windows.Controls.UserControl> , dient als eine Möglichkeit zum Umgestalten einer UI-Verhalten, aber nicht als Teil eines Erweiterungsmechanismus, der impliziert werden kann, indem Sie deklarieren die unterstützende Klasse mit `public` Zugriffsebene. Solche eine <xref:System.Windows.Controls.UserControl> können deklariert werden, mit `internal` zugreifen, wenn der zugrunde liegenden Code in die gleiche Assembly kompiliert wird, von dem es als XAML-Typ verweist.  
  
 Für eine Anwendung, die XAML mit voller Vertrauenswürdigkeit geladen und verwendet <xref:System.Xaml.XamlObjectWriter>, Laden von Klassen mit `internal` Zugriffsebene ist immer aktiviert.  
  
 Für eine Anwendung, die von XAML mit teilweiser Vertrauenswürdigkeit geladen wird, können Sie steuern die Zugriff auf Eigenschaften über die <xref:System.Xaml.Permissions.XamlAccessLevel> API. Darüber hinaus müssen verzögerungsmechanismen (z. B. das System des WPF-Vorlage) möglicherweise weitergegeben werden alle Access-Berechtigungen auf Serverebene und diese für die auswertungen "Eventual" zur Laufzeit beibehalten; Dies wird intern behandelt, durch das Übergeben der <xref:System.Xaml.Permissions.XamlAccessLevel> Informationen.  
  
### <a name="wpf-implementation"></a>WPF-Implementierung  
 WPF XAML verwendet ein Zugriffsmodell für teilweise vertrauenswürdigen, wenn BAML unter teilweiser Vertrauenswürdigkeit geladen wird, ist der Zugriff beschränkt, <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> für die Assembly, die die BAML-Quelle ist. Für das aufschieben, WPF verwendet <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> als Mechanismus zum Übergeben der Zugriff auf Informationen.  
  
 In der Terminologie von WPF XAML ein *interner Typ* ist ein Typ, der von der gleichen Assembly definiert ist, die auch die verweisende XAML enthält. Ein solchen Typ zugeordnet werden kann, bis ein XAML-Namespace, der die Assembly absichtlich ausgelassen = Teil einer Zuordnung, z. B. `xmlns:local="clr-namespace:WPFApplication1"`.  Wenn BAML einen internen Typ verweist und Typ verfügt über `internal` Zugriffsebene generiert eine `GeneratedInternalTypeHelper` -Klasse für die Assembly. Wenn Sie vermeiden möchten `GeneratedInternalTypeHelper`, entweder hierarchieverwaltungstools `public` Zugriffsebene oder berücksichtigen Sie die relevante Klasse in einer separaten Assembly und müssen diese als abhängige Assembly.  
  
## <a name="see-also"></a>Siehe auch

- [XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken](xaml-related-clr-attributes-for-custom-types-and-libraries.md)
- [XAML Services](index.md) (XAML-Dienste)
