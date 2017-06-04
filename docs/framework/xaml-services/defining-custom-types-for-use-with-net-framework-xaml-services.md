---
title: "Defining Custom Types for Use with .NET Framework XAML Services | Microsoft Docs"
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
  - "defining custom types [XAML Services]"
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
caps.latest.revision: 11
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 11
---
# Defining Custom Types for Use with .NET Framework XAML Services
Zum Definieren von benutzerdefinierten Typen, die Geschäftsobjekte oder Typen ohne Abhängigkeit von bestimmten Frameworks sind, stehen einige bewährte Methoden für XAML zur Verfügung.  Wenn Sie diesen Vorgehensweisen folgen, können .NET Framework\-XAML\-Dienste und die zugehörigen XAML\-Reader und XAML\-Writer die XAML\-Eigenschaften des Typs ermitteln und in einem XAML\-Knotenstream, der das XAML\-Typsystem verwendet, korrekt darstellen.  In diesem Thema werden bewährte Methoden für Typdefinitionen, Memberdefinitionen und das CLR\-Attributieren von Typen oder Membern beschrieben.  
  
## Konstruktormuster und Typdefinitionen für XAML  
 Eine benutzerdefinierte Klasse muss die folgenden Anforderungen erfüllen, um als Objektelement in XAML instanziiert werden zu können:  
  
-   Die benutzerdefinierte Klasse muss öffentlich sein und einen standardmäßigen \(parameterlosen\) öffentlichen Standardkonstruktor verfügbar machen.  \(Hinweise zu Strukturen finden Sie im folgendem Abschnitt.\)  
  
-   Die benutzerdefinierte Klasse darf keine geschachtelte Klasse sein.  Durch den zusätzlichen "Punkt" im Pfad für den vollständigen Namen wird die Klassennamespace\-Division mehrdeutig und beeinträchtigt andere XAML\-Funktionen, z. B. angefügte Eigenschaften.  
  
 Wenn ein Objekt als Objektelement instanziiert werden kann, kann das erstellte Objekt die Eigenschaftenelementform beliebiger Eigenschaften ausfüllen, die das Objekt als zugrundeliegenden Typ akzeptieren.  
  
 Sie können immer noch Objektwerte für Typen bereitstellen, die diese Kriterien nicht erfüllen, sofern Sie einen Wertkonverter aktivieren.  Weitere Informationen finden Sie unter [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
### Strukturen  
 Strukturen können immer in XAML durch CLR\-Definition erstellt werden.  Dies liegt daran, dass ein CLR\-Compiler implizit einen Standardkonstruktor für eine Struktur erstellt.  Dieser Konstruktor initialisiert alle Eigenschaftswerte mit ihren Standardwerten.  
  
 In einigen Fällen ist das Standardkonstruktionsverhalten für eine Struktur nicht wünschenswert.  Das könnte daran liegen, dass die Struktur dazu gedacht ist, Werte auszufüllen und als Union zu funktionieren.  Bei der Verwendung als Union können die enthaltenen Werte über sich gegenseitig ausschließende Interpretationen verfügen, wodurch keine der Eigenschaften festgelegt werden kann.  Ein Beispiel für so eine Struktur im WPF\-Vokabular ist <xref:System.Windows.GridLength>.  Diese Strukturen sollten einen Typkonverter so implementieren, dass die Werte anhand von Zeichenfolgenkonventionen, die die verschiedenen Interpretationen oder Modi der Strukturwerte erstellen, in Attributform ausgedrückt werden können.  Die Struktur sollte auch ähnliches Verhalten durch einen nicht standardmäßigen Konstruktor für die Codekonstruktion verfügbar machen.  
  
### Schnittstellen  
 Schnittstellen können als zugrundeliegende Typen von Membern verwendet werden.  Das XAML\-Typsystem überprüft die zuweisbare Liste, und erwartet, dass das als Wert bereitgestellte Objekt der Schnittstelle zugewiesen werden kann.  Es gibt kein Konzept dafür, wie die Schnittstelle als XAML\-Typ dargestellt werden muss, so lange der relevante zuweisbare Typ die XAML\-Konstruktionsanforderungen unterstützt.  
  
### Factorymethode  
 Factorymethoden sind eine XAML 2009\-Funktion.  Sie ändern das XAML\-Prinzip, gemäß dem Objekte über Standardkonstruktoren verfügen müssen.  Factorymethoden werden nicht in diesem Thema dokumentiert.  Weitere Informationen finden Sie unter [x:FactoryMethod Directive](../../../docs/framework/xaml-services/x-factorymethod-directive.md).  
  
## Enumerationen  
 Enumerationen weisen systemeigenes XAML\-Typkonvertierungsverhalten auf.  Konstante in XAML angegebene Enumerationsnamen werden gegen den zugrundeliegenden Enumerationstyp aufgelöst und geben den Enumerationswert an einen XAML\-Objektwriter zurück.  
  
 XAML unterstützt flagähnliche Verwendung für Enumerationen, auf die <xref:System.FlagsAttribute> angewendet wird.  Weitere Informationen finden Sie unter [Ausführliche Erläuterung der XAML\-Syntax](../../../ocs/framework/wpf/advanced/xaml-syntax-in-detail.md).  \([Ausführliche Erläuterung der XAML\-Syntax](../../../ocs/framework/wpf/advanced/xaml-syntax-in-detail.md) wird für die WPF\-Zielgruppe geschrieben, aber die meisten der Informationen in diesem Thema sind für XAML relevant, das für ein bestimmtes implementierendes Framework nicht spezifisch ist.\)  
  
## Memberdefinitionen  
 Typen können Member für die XAML\-Verwendung definieren.  Typen, die Member definieren, können in XAML verwendbar sein, auch wenn der bestimmte Typ nicht in XAML verwendbar ist.  Dies ist aufgrund der CLR\-Vererbung möglich.  So lange ein Typ, der den Member erbt, XAML\-Verwendung als Typ unterstützt und der Member XAML\-Verwendung für seinen zugrunde liegenden Typ unterstützt oder eine systemeigene XAML\-Syntax für diesen Typ verfügbar ist, ist der Member in XAML verwendbar.  
  
### Eigenschaften  
 Wenn Sie Eigenschaften mithilfe der typischen CLR\-`get`\- und `set`\-Accessormuster und der entsprechenden Schlüsselwörter für die Sprache als öffentliche CLR\-Eigenschaft definieren, kann das XAML\-Typsystem die Eigenschaft als Member mit entsprechenden Informationen für <xref:System.Xaml.XamlMember>\-Eigenschaften dokumentieren, z. B. <xref:System.Xaml.XamlMember.IsReadPublic%2A> und <xref:System.Xaml.XamlMember.IsWritePublic%2A>.  
  
 Bestimmte Eigenschaften können eine Textsyntax aktivieren, indem <xref:System.ComponentModel.TypeConverterAttribute> angewendet wird.  Weitere Informationen finden Sie unter [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 In Ermangelung einer Textsyntax oder systemeigenen XAML\-Konvertierung und ohne weitere Dereferenzierung, z. B. eine Markuperweiterungssyntax, muss der Eigenschaftstyp \(<xref:System.Xaml.XamlMember.TargetType%2A> im XAML\-Typsystem\) in der Lage sein, eine Instanz durch das Behandeln des Zieltyps als CLR\-Typ an einen XAML\-Objektwriter zurückzugeben.  
  
 Bei Verwendung von XAML 2009 kann [x:Reference Markup Extension](../../../docs/framework/xaml-services/x-reference-markup-extension.md) zum Bereitstellen von Werten verwendet werden, wenn die obigen Voraussetzungen nicht erfüllt werden. Dies ist jedoch eher ein Syntaxproblem als ein Typdefinitionsproblem.  
  
### Ereignisse  
 Wenn Sie Ereignisse als öffentliches CLR\-Ereignis definieren, kann das XAML\-Typsystem das Ereignis als Member melden, wobei <xref:System.Xaml.XamlMember.IsEvent%2A> auf `true` festgelegt ist.  Die Verknüpfung des Ereignishandlers ist keine Funktion der .NET Framework\-XAML\-Dienste. Hierfür sind bestimmte Frameworks und Implementierungen vorhanden.  
  
### Methoden  
 Der Inlinecode für Methoden ist keine standardmäßige\-XAML\-Funktion.  In den meisten Fällen versehen Sie keine Methodenmember in XAML direkt mit Verweisen, und die Methoden sollen in XAML lediglich Unterstützung für bestimmte XAML\-Muster bieten.  [x:FactoryMethod Directive](../../../docs/framework/xaml-services/x-factorymethod-directive.md) ist eine Ausnahme.  
  
### Felder  
 CLR\-Entwurfsrichtlinien vermeiden nicht statische Felder.  Auf Werte für statische Felder kann nur über [x:Static Markup Extension](../../../docs/framework/xaml-services/x-static-markup-extension.md) zugegriffen werden. In diesem Fall sind zum Verfügbarmachen eines Felds für [x:Static](../../../docs/framework/xaml-services/x-static-markup-extension.md)\-Verwendungen keine besonderen Einstellungen in der CLR\-Definition erforderlich.  
  
## Anfügbare Member  
 Anfügbare Member werden in XAML durch ein Accessormethodenmuster für einen definierenden Typ verfügbar gemacht.  Der definierende Typ selbst muss als Objekt nicht in XAML verwendbar sein.  Ein allgemeines Muster besteht vielmehr darin, eine Dienstklasse zu deklarieren, die die anfügbaren Member besitzt und das zugehörige Verhalten implementiert, jedoch nicht für andere Funktionen wie z. B. eine Benutzeroberflächendarstellung dient.  Für die folgenden Abschnitte stellt der Platzhalter *PropertyName* den Namen des anfügbaren Members dar.  Der Name muss in [XamlName\-Grammatik](../../../docs/framework/xaml-services/xamlname-grammar.md) gültig sein.  
  
 Seien Sie bei Namenskonflikten zwischen diesen Mustern und anderen Methoden eines Typs vorsichtig.  Wenn ein Member vorhanden ist, der einem der beiden Muster entspricht, kann er von einem XAML\-Prozessor als anfügbarer Memberverwendungspfad interpretiert werden, auch wenn das nicht die Absicht war.  
  
#### Der GetPropertyName\-Accessor  
 Die Signatur für den `Get`*PropertyName*\-Accessor muss wie folgt lauten:  
  
 `public static object Get` *PropertyName* `(object`  `target` `)`  
  
-   Das `target`\-Objekt kann in der Implementierung als spezifischerer Typ angegeben werden.  Sie können dies zur Bewertung des anfügbaren Members verwenden. Bei Verwendung außerhalb des beabsichtigten Bereichs werden ungültige Umwandlungsausnahmen ausgelöst, die anschließend durch einen XAML\-Analysefehler angezeigt werden.  Der Parametername `target` ist keine Voraussetzung, wird aber in den meisten Implementierungen der `target`\-Konvention genannt.  
  
-   Der Rückgabewert kann in der Implementierung als spezifischerer Typ angegeben werden.  
  
 Zur Unterstützung einer <xref:System.ComponentModel.TypeConverter>\-fähigen Textsyntax für die Attributverwendung des anfügbaren Members wenden Sie <xref:System.ComponentModel.TypeConverterAttribute> auf den `Get`*PropertyName*\-Accessor an.  Die Anwendung von `get` anstelle von `set` scheint möglicherweise unkonventionell. Diese Konvention kann jedoch das Konzept von schreibgeschützten anfügbaren und serialisierbaren Membern unterstützen, was in Designerszenarien hilfreich ist.  
  
#### Der SetPropertyName\-Accessor  
 Die Signatur für den Set*PropertyName*\-Accessor muss wie folgt lauten:  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
-   Das `target`\-Objekt kann als spezifischerer Typ in der Implementierung angegeben werden. Hierbei gelten die gleiche Logik und die gleichen Folgen wie im vorherigen Abschnitt beschrieben.  
  
-   Das `value`\-Objekt kann in der Implementierung als spezifischerer Typ angegeben werden.  
  
 Der Wert für diese Methode ist die Eingabe von der XAML\-Verwendung, in der Regel in Attributform.  In der Attributform muss Wertkonverterunterstützung für eine Textsyntax vorliegen, und die Attribute werden dem `Get`*PropertyName*\-Accessor zugeordnet.  
  
### Anfügbare Memberspeicher  
 Die Accessormethoden reichen in der Regel nicht aus, um anfügbare Memberwerte in einem Objektdiagramm einzufügen oder Werte aus dem Objektdiagramm abzurufen und korrekt zu serialisieren.  Um diese Funktion bereitzustellen, müssen die `target`\-Objekte in den vorherigen Accessorsignaturen in der Lage sein, Werte zu speichern.  Der Speichermechanismus muss mit dem Prinzip vereinbar sein, dass der Member Zielen zugeordnet werden kann, in denen der anfügbare Member nicht in der Memberliste enthalten ist.  .NET Framework\-XAML\-Dienste stellen über die <xref:System.Xaml.IAttachedPropertyStore>\- und <xref:System.Xaml.AttachablePropertyServices>\-APIs eine Implementierungstechnik für anfügbare Memberspeicher bereit.  <xref:System.Xaml.IAttachedPropertyStore> wird von den XAML\-Writern verwendet, um die Speicherungsimplementierung zu erkennen, und sollte für den Typ implementiert werden, der das `target` der Accessoren ist.  Die statischen <xref:System.Xaml.AttachablePropertyServices>\-APIs werden im Textkörper der Accessoren verwendet und verweisen anhand der <xref:System.Xaml.AttachableMemberIdentifier> auf den anfügbaren Member.  
  
## XAML\-bezogene CLR\-Attribute  
 Das ordnungsgemäße Zuordnen von Typen, Membern und Assemblys ist wichtig, damit .NET Framework\-XAML\-Diensten XAML\-Typsysteminformationen gemeldet werden können.  Dies ist relevant, wenn die Typen in XAML\-Systemen verwendet werden sollen, die direkt auf XAML\-Readern und XAML\-Writern von .NET Framework\-XAML\-Diensten basieren, oder Sie ein Framework mit XAML definieren bzw. verwenden, das auf diesen XAML\-Readern und XAML\-Writern basiert.  
  
 Eine Auflistung aller XAML\-bezogener Attribute, die für die XAML\-Unterstützung benutzerdefinierter Typen relevant sind, finden Sie unter [XAML\-Related CLR Attributes for Custom Types and Libraries](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## Verwendung  
 Die Verwendung benutzerdefinierter Typen erfordert, dass der Markupautor ein Präfix für die Assembly und den CLR\-Namespace zuordnen muss, die den benutzerdefinierten Typ enthalten.  Diese Prozedur wird in diesem Thema nicht behandelt.  
  
## Zugriffsebene  
 XAML bietet die Möglichkeit, Typen mit einer `internal`\-Zugriffsebene zu laden und zu instanziieren.  Diese Funktion wird bereitgestellt, damit in Benutzercode eigene Typen definiert und diese Klassen anschließend in Markup instanziiert werden können, das zum gleichen Benutzercodebereich gehört.  
  
 Ein WPF\-Beispiel hierfür ist die Definition eines <xref:System.Windows.Controls.UserControl> in Benutzercode, das eine Möglichkeit zum Umgestalten eines Benutzeroberflächenverhaltens bereitstellen, aber nicht Teil eines Erweiterungsmechanismus sein soll, der durch Deklarieren der unterstützenden Klasse mit `public`\-Zugriffsebene impliziert werden könnte.  Ein solches <xref:System.Windows.Controls.UserControl> kann mit `internal`\-Zugriff deklariert werden, wenn der Unterstützungscode in der Assembly kompiliert wird, in der als XAML\-Typ auf ihn verwiesen wird.  
  
 Für eine Anwendung, die XAML mit voller Vertrauenswürdigkeit lädt und <xref:System.Xaml.XamlObjectWriter> verwendet, ist das Laden von Klassen mit `internal`\-Zugriffsebene immer möglich.  
  
 Für eine Anwendung, die XAML mit teilweiser Vertrauenswürdigkeit lädt, können Sie die Zugriffsebeneneigenschaften mithilfe der <xref:System.Xaml.Permissions.XamlAccessLevel>\-API steuern.  Zudem müssen Verzögerungsmechanismen \(z. B. das WPF\-Vorlagensystem\) in der Lage sein, Zugriffsebenenberechtigungen zu verteilen und die möglichen Laufzeitauswertungen beizubehalten. Dies wird intern durch Übergeben der <xref:System.Xaml.Permissions.XamlAccessLevel>\-Informationen behandelt.  
  
### WPF\-Implementierung  
 WPF\-XAML verwendet ein Zugriffsmodell mit teilweiser Vertrauenswürdigkeit, bei dem der Zugriff für die Assembly, die die BAML\-Quelle ist, auf <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> beschränkt wird, wenn BAML mit teilweiser Vertrauenswürdigkeit geladen wird.  Zur Verzögerung verwendet WPF <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=fullName> als Mechanismus zum Übergeben der Zugriffsebeneninformationen.  
  
 In der WPF\-XAML\-Terminologie ist ein *interner Typ* ein Typ, der in der Assembly definiert ist, die auch das verweisende XAML enthält.  Ein solcher Typ kann über einen XAML\-Namespace zugeordnet werden, in dem der "assembly\="\-Teil einer Zuordnung bewusst weggelassen wird, z. B. `xmlns:local="clr-namespace:WPFApplication1"`.  Wenn BAML auf einen internen Typ verweist und dieser Typ die `internal`\-Zugriffsebene aufweist, wird dadurch eine `GeneratedInternalTypeHelper`\-Klasse für die Assembly generiert.  Wenn Sie `GeneratedInternalTypeHelper` umgehen möchten, müssen Sie entweder die `public`\-Zugriffsebene verwenden oder die relevante Klasse in eine separate Assembly umgestalten und diese als abhängige Assembly festlegen.  
  
## Siehe auch  
 [XAML\-Related CLR Attributes for Custom Types and Libraries](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)   
 [XAML Services](../../../docs/framework/xaml-services/index.md)