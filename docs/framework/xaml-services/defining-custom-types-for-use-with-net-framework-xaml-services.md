---
title: "Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
caps.latest.revision: 
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c7cce479c7c7a5f6c7112f08f1e15f3bc7e4d366
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten
Wenn Sie definieren benutzerdefinierter Typen, die Geschäftsobjekte oder Typen, die keine Abhängigkeit auf bestimmten Frameworks sind, stehen bestimmte bewährten Methoden für XAML, die Sie befolgen können. Wenn Sie diese Methoden befolgen, können .NET Framework-XAML-Dienste und die XAML-Readern und XAML-Writern die Verwendung von XAML-Eigenschaften des Typs ermitteln und geben sie entsprechende Darstellung in einem XAML-Knotenstream mit XAML-Typsystem. Dieses Thema beschreibt bewährte Methoden für Typdefinitionen, Memberdefinitionen und CLR-Typen oder Member Attributierung.  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Konstruktormuster und Typdefinitionen für XAML  
 Um als Objektelement in XAML instanziiert werden, muss eine benutzerdefinierte Klasse die folgenden Anforderungen erfüllen:  
  
-   Die benutzerdefinierte Klasse muss öffentlich sein und einen (parameterlosen) öffentlichen Standardkonstruktor verfügbar machen. (Hinweise zu Strukturen finden Sie im folgenden Abschnitt.)  
  
-   Die benutzerdefinierte Klasse darf nicht auf eine geschachtelte Klasse sein. Die zusätzlichen "Punkt" im Pfad voller Name Klassennamespace Division mehrdeutig ist, und verursacht einen Konflikt mit anderen XAML-Funktionen, z. B. angefügte Eigenschaften.  
  
 Ein Objekt als Objektelement instanziiert werden kann, kann das erstellte Objekt Element das Eigenschaftenformular des beliebiger Eigenschaften vollständig aufgefüllt, die das Objekt als deren zugrunde liegenden Typs akzeptieren.  
  
 Sie können immer noch Objektwerte für Typen, die diese Kriterien nicht erfüllen bereitstellen, wenn Sie einen Wertkonverter aktivieren. Weitere Informationen finden Sie unter [Typkonverter und Markuperweiterungen für XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
### <a name="structures"></a>Strukturen  
 Strukturen sind immer in XAML durch CLR-Definition erstellt werden können. Dies ist, da ein CLR-Compiler implizit einen Standardkonstruktor für eine Struktur erstellt. Dieser Konstruktor initialisiert alle Eigenschaftswerte auf ihre Standardwerte.  
  
 In einigen Fällen ist das Standardverhalten für die Konstruktion für eine Struktur nicht wünschenswert. Dies kann sein, da die Struktur vorgesehen ist, Werte und die Funktion grundsätzlich als Union zu füllen. Als Union die enthaltenen Werte über sich gegenseitig ausschließende Interpretationen verfügen, und daher keine Eigenschaften festgelegt werden. Ein Beispiel einer solchen Struktur im WPF-Vokabular ist <xref:System.Windows.GridLength>. Solche Strukturen sollten einen Typkonverter implementieren, damit, dass die Werte können in Attributform, ausgedrückt werden mithilfe von Zeichenfolgenkonventionen, die die verschiedenen Interpretationen oder Modi der Strukturwerte zu erstellen. Die Struktur sollte über einen nicht standardmäßigen Konstruktor ein ähnliches Verhalten auch für die Codekonstruktion verfügbar machen.  
  
### <a name="interfaces"></a>Schnittstellen  
 Schnittstellen können als zugrunde liegende Typen von Elementen verwendet werden. Das XAML-Typsystem überprüft die zuweisbare Liste und erwartet, dass das Objekt, das als Wert angegeben wird, auf die Schnittstelle zugewiesen werden kann. Es ist kein Konzept wie die Schnittstelle als einen XAML-Typ dargestellt werden sollen, solange ein relevanten zugeordnet werden kann die Verwendung von XAML-Konstruktion-Anforderungen unterstützt.  
  
### <a name="factory-methods"></a>Factorymethoden  
 Factorymethoden sind eine XAML 2009-Funktion. Sie ändern das XAML-Prinzip, dass Objekte über Standardkonstruktoren verfügen müssen. Factorymethoden werden nicht in diesem Thema dokumentiert. Finden Sie unter [X: FactoryMethod-Direktive](../../../docs/framework/xaml-services/x-factorymethod-directive.md).  
  
## <a name="enumerations"></a>Enumerationen  
 Enumerationen haben systemeigene Typkonvertierungsverhalten XAML. Enumeration Konstantennamen in XAML angegeben werden für den zugrunde liegenden Enumerationstyp aufgelöst, und den Enumerationswert für eine XAML-Objektwriter zurückzugeben.  
  
 XAML unterstützt eine Flags-Stil-Verwendung für Enumerationen mit <xref:System.FlagsAttribute> angewendet. Weitere Informationen finden Sie unter [XAML-Syntax im Detail](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md). ([XAML-Syntax im Detail](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md) geschrieben wird, die WPF-Zielgruppe, aber die meisten der Informationen in diesem Thema ist relevant für XAML, die nicht spezifisch für ein bestimmtes implementierende Framework ist.)  
  
## <a name="member-definitions"></a>Elementdefinitionen  
 Typen können für die Verwendung von XAML-Member definieren. Es ist möglich, dass Typen, die Elemente zu, die XAML-verwendbar sind definieren, auch wenn diese bestimmte Art nicht XAML verwendbar ist. Dies ist aufgrund von CLR-Vererbung möglich. So lange ein Typ, der das Element erbt unterstützt die Verwendung von XAML als einen Typ und das Element unterstützt die Verwendung von XAML-Verwendung für den zugrunde liegenden Typ oder verfügt über eine systemeigene XAML-Syntax, die verfügbar sind, ist diese Member XAML verwendet werden kann.  
  
### <a name="properties"></a>Eigenschaften  
 Wenn Sie die Eigenschaften als öffentliche CLR-Eigenschaft unter Verwendung der typischen CLR definieren `get` und `set` Accessor Muster und sprachspezifischen Keywording, XAML-Typsystem kann gemeldet werden, für die Eigenschaft als ein Element mit dem entsprechenden Informationen bereitgestellt <xref:System.Xaml.XamlMember> Eigenschaften, z. B. <xref:System.Xaml.XamlMember.IsReadPublic%2A> und <xref:System.Xaml.XamlMember.IsWritePublic%2A>.  
  
 Bestimmte Eigenschaften können eine Textsyntax aktivieren, durch Anwenden von <xref:System.ComponentModel.TypeConverterAttribute>. Weitere Informationen finden Sie unter [Typkonverter und Markuperweiterungen für XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 In Ermangelung einer Textsyntax oder systemeigenen XAML-Konvertierung und ohne weitere Dereferenzierung, z. B. eine Markuperweiterungsverwendung, die den Typ einer Eigenschaft (<xref:System.Xaml.XamlMember.TargetType%2A> in der XAML-Typsystem) muss in der Lage, eine Instanz für eine XAML-Objektwriter zurückzugeben, indem zum Behandeln von t Arget Typ als CLR-Typ.  
  
 Wenn XAML 2009 verwendet wird, [X: Reference-Markuperweiterung](../../../docs/framework/xaml-services/x-reference-markup-extension.md) können verwendet werden, um Werte bereitzustellen, wenn die vorausgegangenen Ausführungen nicht erfüllt werden; dies ist jedoch mehr als ein Typ Definition Problem ein Problem beim Ressourceneinsatz.  
  
### <a name="events"></a>Ereignisse  
 Wenn Sie Ereignisse als öffentliches CLR-Ereignis definieren, kann das XAML-Typsystem als ein Element mit dem das Ereignis melden <xref:System.Xaml.XamlMember.IsEvent%2A> als `true`. Die Ereignishandler Verkabelung ist nicht innerhalb des Bereichs von .NET Framework XAML Services-Funktionen. Dies ist die Implementierung und spezifische Frameworks links ausgerichtet.  
  
### <a name="methods"></a>Methoden  
 Inlinecode für Methoden ist nicht standardmäßig XAML-Funktion. In den meisten Fällen Sie nicht direkt auf verweisen Methodenmember aus XAML und die Rolle der Methoden in XAML wird nur für bestimmte XAML-Muster unterstützen. [X: FactoryMethod-Direktive](../../../docs/framework/xaml-services/x-factorymethod-directive.md) ist eine Ausnahme.  
  
### <a name="fields"></a>Felder  
 CLR-Entwurfsrichtlinien vermeiden nicht statische Felder. Für statische Felder, die Sie Werte für statische Felder zugreifen können nur über [X: statische Markuperweiterung](../../../docs/framework/xaml-services/x-static-markup-extension.md); in diesem Fall Sie sind nicht auf diese Weise nichts Besonderes in der CLR-Definition für ein Feld verfügbar machen [X: Static](../../../docs/framework/xaml-services/x-static-markup-extension.md) Verwendungen.  
  
## <a name="attachable-members"></a>Anfügbare Member  
 Anfügbare Member werden in XAML über einen Accessor-Methode Muster für einen definierenden Typ verfügbar gemacht. Der definierende Typ selbst muss nicht als Objekt XAML verwendet werden kann. Ein allgemeines Muster ist eine Dienstklasse deklarieren, dessen Rolle, anfügbaren Members besitzen und das zugehörige Verhalten implementiert, aber keine anderen Funktion z. B. eine Benutzeroberflächendarstellung dienen. Für die folgenden Abschnitte, die Platzhalter *PropertyName* den Namen des anfügbaren Members darstellt. Dieser Name muss in gültig sein der [XamlName-Grammatik](../../../docs/framework/xaml-services/xamlname-grammar.md).  
  
 Seien Sie vorsichtig, der Namenskonflikte zwischen diesen Mustern und anderen Methoden eines Typs. Wenn ein Element vorhanden, das einem Muster entspricht ist, kann es als Pfad einer anfügbaren Members-Verwendung durch einen XAML-Prozessor interpretiert werden, auch wenn Ihre Absicht nicht ausgeführt wurde.  
  
#### <a name="the-getpropertyname-accessor"></a>Der Accessor GetPropertyName-Methode  
 Die Signatur für den Accessoren `Get`*PropertyName* muss Folgende sein:  
  
 `public static object Get` *PropertyName* `(object`  `target` `)`  
  
-   Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Dadurch können Sie die Verwendung des anfügbaren Members Bereich; Verwendungen außerhalb des beabsichtigten Bereichs löst Ausnahmen für ungültige Umwandlung, die dann von einem XAML-Analysefehler angefügt sind. Der Name des Parameters `target` ist nicht erforderlich, aber ist mit dem Namen `target` gemäß der Konvention in den meisten Implementierungen.  
  
-   Der Rückgabewert kann als spezifischerer Typ in Ihrer Implementierung angegeben werden.  
  
 Zur Unterstützung einer <xref:System.ComponentModel.TypeConverter> aktiviert Textsyntax für die Attributverwendung des anfügbaren Members, gelten <xref:System.ComponentModel.TypeConverterAttribute> auf die `Get` *PropertyName* Accessor. Anwenden auf die `get` statt der `set` mag unkonventionell; allerdings kann diese Konvention unterstützen das Konzept des nur-Lese anfügbare Member, die serialisierbar sind, ist die Designer-Szenarien nützlich.  
  
#### <a name="the-setpropertyname-accessor"></a>Der SetPropertyName Accessor  
 Die Signatur für den Satz*PropertyName* Accessor muss:  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
-   Die `target` Objekt kann als einen spezifischeren Typ in der Implementierung, mit derselben Logik und die Konsequenzen angegeben werden, wie im vorherigen Abschnitt beschrieben.  
  
-   Das `value`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden.  
  
 Denken Sie daran, dass der Wert für diese Methode die Eingabe aus der XAML-Verwendung in der Regel in Attributform stammen. In Attributform müssen Wert Konverter-Unterstützung für die eine Textsyntax vorhanden sein, und Sie Attribut auf die `Get` *PropertyName* Accessor.  
  
### <a name="attachable-member-stores"></a>Anfügbare Member speichert  
 Die Zugriffsmethoden sind in der Regel nicht ausreichend, um bieten eine Möglichkeit zum anfügbaren Members-Werte in einem Objektdiagramm zu platzieren oder zum Abrufen von Werten aus dem Objektdiagramm und korrekt zu serialisieren. Zum Bereitstellen dieser Funktionalität der `target` Objekte in den vorherigen Accessorsignaturen müssen zum Speichern von Werten in der Lage sein. Speichermechanismus sollte mit dem Prinzip des anfügbaren Members entsprechen, die die Member Zielen handelt, in denen anfügbaren Members nicht in der Liste der Member ist. .NET Framework XAML Services stellt eine Implementierung, die auch für anfügbaren Members über die APIs speichert <xref:System.Xaml.IAttachedPropertyStore> und <xref:System.Xaml.AttachablePropertyServices>. <xref:System.Xaml.IAttachedPropertyStore>wird durch die Verwendung von XAML-Writer verwendet, um die Implementierung zu ermitteln und implementiert werden sollte, für den Typ, der die `target` Accessor. Die statische <xref:System.Xaml.AttachablePropertyServices> APIs werden verwendet, im Text der Zugriffsmethoden und verweisen auf anfügbaren Members von seiner <xref:System.Xaml.AttachableMemberIdentifier>.  
  
## <a name="xaml-related-clr-attributes"></a>XAML-bezogene CLR-Attributen  
 Attributierung ordnungsgemäß Ihre Typen, Member und Assemblys ist wichtig, in der Reihenfolge nach der Verwendung von XAML-System Typinformationen für .NET Framework XAML Services-Bericht. Dies ist relevant, wenn Sie beabsichtigen, Ihre Typen für die Verwendung mit Verwendung von XAML-Systemen, die direkt auf .NET Framework XAML Services XAML-Readern und XAML-Writer basieren, oder wenn Sie definieren, oder verwenden ein XAML-Writern Framework, das auf die XAML-Readern und XAML-Writern basiert.  
  
 Eine Liste der einzelnen XAML-bezogene Attribute, die für die Verwendung von XAML-Unterstützung benutzerdefinierter Typen relevant sind, finden Sie unter [XAML-Related CLR-Attribute für benutzerdefinierte Typen und Bibliotheken](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="usage"></a>Verwendung  
 Verwendung von benutzerdefinierten Typen erfordert, dass der Markupautor zuordnen muss ein Präfix für die Assembly und die CLR-Namespace, die den benutzerdefinierten Typ enthalten. Dieses Verfahren ist nicht in diesem Thema dokumentiert.  
  
## <a name="access-level"></a>Zugriffsebene  
 XAML bietet eine Möglichkeit zum Laden und Instanziieren von Typen, die über eine `internal` Zugriffsebene. Diese Funktion wird bereitgestellt, sodass Benutzercode eigenen Typen definieren kann, und klicken Sie dann Instanziieren dieser Klassen von Markup, das auch Teil des gleichen Bereiches Benutzer Code ist.  
  
 Ein Beispiel aus WPF ist immer, wenn Benutzercode definiert eine <xref:System.Windows.Controls.UserControl> , dient als eine Möglichkeit zum Umgestalten einer Verhalten der Benutzeroberfläche, aber nicht als Teil eines Erweiterungsmechanismus, die impliziert werden könnte, indem Sie deklarieren die unterstützende Klasse mit `public` Zugriffsebene. Solche eine <xref:System.Windows.Controls.UserControl> können deklariert werden, mit `internal` zugreifen, wenn die zugrunde liegende Code in derselben Assembly kompiliert wird, aus dem es als einen XAML-Typ verweist.  
  
 Für eine Anwendung, die XAML mit voller Vertrauenswürdigkeit lädt und verwendet <xref:System.Xaml.XamlObjectWriter>, Laden von Klassen mit `internal` Zugriffsebene ist immer aktiviert.  
  
 Für eine Anwendung, die XAML unter teilweiser Vertrauenswürdigkeit lädt, können Sie steuern die Zugriffsmerkmale Ebene über der <xref:System.Xaml.Permissions.XamlAccessLevel> API. Verzögerungsmechanismen (z. B. das WPF-vorlagensystem) muss darüber hinaus können keine Zugriffsberechtigungen Ebene weitergegeben, und erhalten diese für die letztendliche zur Laufzeit auswertungen; Dies wird intern behandelt, durch das Übergeben der <xref:System.Xaml.Permissions.XamlAccessLevel> Informationen.  
  
### <a name="wpf-implementation"></a>WPF-Implementierung  
 WPF XAML verwendet ein teilweise vertrauenswürdigen Zugriffsmodell, in dem Wenn BAML unter teilweiser Vertrauenswürdigkeit geladen wird, ist der Zugriff auf eingeschränkte <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> für die Assembly, die die BAML-Quelle ist. Für Deferral, WPF verwendet <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> als Mechanismus für die Weitergabe von Informationen der Zugriff.  
  
 In der Terminologie von WPF XAML eine *internen Typ* ist ein Typ, der von der gleichen Assembly definiert ist, auch das verweisende XAML enthält. Ein solchen Typs zugeordnet werden kann, durch einen XAML-Namespace, der die Assembly bewusst ausgelassen = Teil einer Zuordnung, z. B. `xmlns:local="clr-namespace:WPFApplication1"`.  Wenn BAML einen internen Typ verweist und Typ verfügt über `internal` Zugriffsebene Dies generiert eine `GeneratedInternalTypeHelper` Klasse für die Assembly. Wenn Sie vermeiden möchten `GeneratedInternalTypeHelper`, entweder müssen Sie verwenden `public` Zugriffsebene verlagern Sie die relevante Klasse in einer separaten Assembly und müssen diese Assembly abhängig machen.  
  
## <a name="see-also"></a>Siehe auch  
 [XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)  
 [XAML Services](../../../docs/framework/xaml-services/index.md) (XAML-Dienste)
