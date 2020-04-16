---
title: Definieren benutzerdefinierter Typen für die Verwendung in .NET-XAML-Diensten
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: ff7e4229450e801a6d618c5141efde8cdcbef03d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433073"
---
# <a name="define-custom-types-for-use-with-net-xaml-services"></a>Definieren benutzerdefinierter Typen für die Verwendung mit .NET XAML Services

Wenn Sie benutzerdefinierte Typen definieren, die Geschäftsobjekte oder Typen sind, die nicht von bestimmten Frameworks abhängig sind, gibt es bestimmte bewährte Methoden für XAML, die Sie befolgen können. Wenn Sie diese Vorgehensweisen befolgen, können .NET XAML Services und seine XAML-Reader und XAML-Writer die XAML-Eigenschaften Ihres Typs ermitteln und ihn mithilfe des XAML-Typsystems in einem XAML-Knotenstream entsprechend darstellungen. In diesem Thema werden bewährte Methoden für Typdefinitionen, Memberdefinitionen und CLR-Zuordnungen von Typen oder Membern beschrieben.

## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Konstruktormuster und Typdefinitionen für XAML

Um als Objektelement in XAML instanziiert zu werden, muss eine benutzerdefinierte Klasse die folgenden Anforderungen erfüllen:

- Die benutzerdefinierte Klasse muss öffentlich sein und einen parameterlosen öffentlichen Konstruktor verfügbar machen. (Hinweise zu Strukturen finden Sie im folgenden Abschnitt.)

- Die benutzerdefinierte Klasse darf keine geschachtelte Klasse sein. Der zusätzliche "Punkt" im Vollständigennamenpfad macht die Klassennamespace-Division mehrdeutig und stört andere XAML-Features, z. B. angefügte Eigenschaften.
Wenn ein Objekt als Objektelement instanziiert werden kann, kann das erstellte Objekt das Eigenschaftselementformular aller Eigenschaften ausfüllen, die das Objekt als zugrunde liegenden Typ annehmen.

Sie können weiterhin Objektwerte für Typen bereitstellen, die diese Kriterien nicht erfüllen, wenn Sie einen Wertkonverter aktivieren. Weitere Informationen finden Sie unter [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions.md).

### <a name="structures"></a>Strukturen

Strukturen können immer in XAML nach CLR-Definition erstellt werden. Dies liegt daran, dass ein CLR-Compiler implizit einen parameterlosen Konstruktor für eine Struktur erstellt. Dieser Konstruktor initialisiert alle Eigenschaftswerte auf ihre Standardwerte.

In einigen Fällen ist das Standardmäßige Konstruktionsverhalten für eine Struktur nicht wünschenswert. Dies kann daran liegen, dass die Struktur dazu bestimmt ist, Werte zu füllen und konzeptionell als Union zu fungieren. Als Union können die enthaltenen Werte sich gegenseitig ausschließende Interpretationen haben, und daher ist keine ihrer Eigenschaften setzbar. Ein Beispiel für eine solche Struktur <xref:System.Windows.GridLength>im WPF-Vokabular ist . Solche Strukturen sollten einen Typkonverter implementieren, damit die Werte in Attributform ausgedrückt werden können, indem Zeichenfolgenkonventionen verwendet werden, die die unterschiedlichen Interpretationen oder Modi der Strukturwerte erstellen. Die Struktur sollte auch ähnliches Verhalten für die Codekonstruktion über einen nicht parameterlosen Konstruktor verfügbar machen.

### <a name="interfaces"></a>Schnittstellen

Schnittstellen können als zugrunde liegende Elementtypen verwendet werden. Das XAML-Typsystem überprüft die zuweisbare Liste und erwartet, dass das Objekt, das als Wert bereitgestellt wird, der Schnittstelle zugewiesen werden kann. Es gibt kein Konzept, wie die Schnittstelle als XAML-Typ dargestellt werden muss, solange ein relevanter zuweisbarer Typ die XAML-Konstruktionsanforderungen unterstützt.

### <a name="factory-methods"></a>Fabrikmethoden

Werksmethoden sind ein XAML 2009-Feature. Sie ändern das XAML-Prinzip, dass Objekte über parameterlose Konstruktoren verfügen müssen. Factory-Methoden sind in diesem Artikel nicht dokumentiert. Siehe [x:FactoryMethod-Richtlinie](xfactorymethod-directive.md).

## <a name="enumerations"></a>Enumerationen

Enumerationen weisen ein systemeigenes XAML-Konvertierungsverhalten auf. Die in XAML angegebenen Enumerationskonstantennamen werden für den zugrunde liegenden Enumerationstyp aufgelöst und geben den Enumerationswert an einen XAML-Objektschreiber zurück.

XAML unterstützt eine Verwendung im Flags-Stil <xref:System.FlagsAttribute> für Enumerationen mit angewendeter Anwendung. Weitere Informationen finden Sie unter [XAML-Syntax im Detail](../../framework/wpf/advanced/xaml-syntax-in-detail.md). ([XAML Syntax In Detail](../../framework/wpf/advanced/xaml-syntax-in-detail.md) wird für die WPF-Zielgruppe geschrieben, aber die meisten Informationen in diesem Thema sind für XAML relevant, das nicht spezifisch für ein bestimmtes Implementierungsframework ist.)

## <a name="member-definitions"></a>Elementdefinitionen

Typen können Member für die XAML-Verwendung definieren. Es ist möglich, dass Typen Member definieren, die XAML-fähig sind, auch wenn dieser bestimmte Typ nicht XAML-verwendbar ist. Dies ist aufgrund der CLR-Vererbung möglich. Solange ein Typ, der das Member erbt, die XAML-Verwendung als Typ unterstützt und das Member die XAML-Verwendung für den zugrunde liegenden Typ unterstützt oder über eine systemeigene XAML-Syntax verfügt, ist dieser Member XAML-fähig.

### <a name="properties"></a>Eigenschaften

Wenn Sie Eigenschaften als öffentliche CLR-Eigenschaft `get` definieren, die die typischen CLR- und `set` Accessormuster und das sprachgerechte Schlüsselwortverwendet umsetzt, kann das XAML-Typsystem die Eigenschaft als Member mit entsprechenden Informationen melden, die für <xref:System.Xaml.XamlMember> Eigenschaften bereitgestellt werden, z. <xref:System.Xaml.XamlMember.IsReadPublic%2A> B. und <xref:System.Xaml.XamlMember.IsWritePublic%2A>.

Bestimmte Eigenschaften können eine Textsyntax aktivieren, indem Sie <xref:System.ComponentModel.TypeConverterAttribute>. Weitere Informationen finden Sie unter [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions.md).

In Ermangelung einer Textsyntax oder systemeigenen XAML-Konvertierung und in Ermangelung weiterer Indirektionen,<xref:System.Xaml.XamlMember.TargetType%2A> z. B. einer Markuperweiterungsverwendung, muss der Typ einer Eigenschaft (im XAML-Typsystem) in der Lage sein, eine Instanz an einen XAML-Objektwriter zurückzugeben, indem der Zieltyp als CLR-Typ behandelt wird.

Bei Verwendung von XAML 2009 kann [x:Reference Markup Extension](xreference-markup-extension.md) verwendet werden, um Werte bereitzustellen, wenn die vorherigen Überlegungen nicht erfüllt werden. Dies ist jedoch eher ein Verwendungsproblem als ein Typdefinitionsproblem.

### <a name="events"></a>Ereignisse

Wenn Sie Ereignisse als öffentliches CLR-Ereignis definieren, kann das XAML-Typsystem das Ereignis als Member mit <xref:System.Xaml.XamlMember.IsEvent%2A> als `true`melden. Das Verdrahten der Ereignishandler liegt nicht im Bereich der .NET XAML Services-Funktionen. Die Verdrahtung wird bestimmten Frameworks und Implementierungen überlassen.

### <a name="methods"></a>Methoden

Inlinecode für Methoden ist keine Standard-XAML-Funktion. In den meisten Fällen verweisen Sie nicht direkt auf Methodenmember aus XAML, und die Rolle von Methoden in XAML besteht nur darin, Unterstützung für bestimmte XAML-Muster bereitzustellen. [x:FactoryMethod-Richtlinie](xfactorymethod-directive.md) ist eine Ausnahme.

### <a name="fields"></a>Felder

CLR-Entwurfsrichtlinien verhindern nicht statische Felder. Bei statischen Feldern können Sie nur über [x:Static Markup Extension](xstatic-markup-extension.md)auf statische Feldwerte zugreifen. In diesem Fall tun Sie nichts Besonderes in der CLR-Definition, um ein Feld für [x:Static-Verwendungen](xstatic-markup-extension.md) verfügbar zu machen.

## <a name="attachable-members"></a>Anfügbis-Mitglieder

Anfügbare Member werden XAML durch ein Accessormethodenmuster für einen definierenden Typ verfügbar gemacht. Der definierende Typ selbst muss nicht als Objekt verwendet werden. Ein allgemeines Muster besteht darin, eine Dienstklasse zu deklarieren, deren Rolle darin besteht, das anfügbisierbare Element zu besitzen und die zugehörigen Verhaltensweisen zu implementieren, aber keine andere Funktion wie eine UI-Darstellung zu erfüllen. In den folgenden Abschnitten stellt der Platzhalter *PropertyName* den Namen ihres anfügbaren Elements dar. Dieser Name muss in der [XamlName-Grammatik](xamlname-grammar.md)gültig sein.

Seien Sie vorsichtig bei Namenskollisionen zwischen diesen Mustern und anderen Methoden eines Typs. Wenn ein Member vorhanden ist, das mit einem der Muster übereinstimmt, kann es von einem XAML-Prozessor als anfügbarer Membernutzungspfad interpretiert werden, auch wenn dies nicht Ihre Absicht war.

#### <a name="the-getpropertyname-accessor"></a>Der GetPropertyName-Accessor

Die Signatur `GetPropertyName` für den Accessor muss sein:

`public static object GetPropertyName(object target)`

- Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Sie können dies verwenden, um die Verwendung Ihres anfügbaren Mitglieds zu erweitern. Verwendungen außerhalb des beabsichtigten Bereichs werden ungültige Cast-Ausnahmen auslösen, die dann durch einen XAML-Analysefehler angezeigt werden. Der Parametername `target` ist keine Anforderung, `target` wird aber in den meisten Implementierungen konventionell benannt.

- Der Rückgabewert kann als spezifischerer Typ in Ihrer Implementierung angegeben werden.

Um eine <xref:System.ComponentModel.TypeConverter> aktivierte Textsyntax für die Attributverwendung <xref:System.ComponentModel.TypeConverterAttribute> des `GetPropertyName` anfügbaren Elements zu unterstützen, gelten Sie für den Accessor. Die Anwendung `get` auf `set` die anstelle der kann nicht-intuitiv erscheinen; Diese Konvention kann jedoch das Konzept der schreibgeschützten anfügbaren Member unterstützen, die serialisierbar sind, was in Designerszenarien nützlich ist.

#### <a name="the-setpropertyname-accessor"></a>Der SetPropertyName-Accessor

Die Signatur `SetPropertyName` für den Accessor muss sein:

`public static void SetPropertyName(object target, object value)`

- Das `target` Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden, mit der gleichen Logik und den gleichen Folgen wie im vorherigen Abschnitt beschrieben.

- Das `value`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden.

Denken Sie daran, dass der Wert für diese Methode die Eingabe ist, die von der XAML-Verwendung stammt, in der Regel in Attributform. Aus dem Attributformular muss es Eine Wertkonverterunterstützung für `GetPropertyName`eine Textsyntax geben, und Sie schreiben dem s-Accessor zu.

### <a name="attachable-member-stores"></a>Anfügbis Member Stores

Die Accessormethoden reichen in der Regel nicht aus, um eine Möglichkeit bereitzustellen, anfügbare Elementwerte in einem Objektdiagramm zu platzieren oder Werte aus dem Objektdiagramm abzurufen und ordnungsgemäß zu serialisieren. Um diese Funktionalität `target` bereitzustellen, müssen die Objekte in den vorherigen Accessorsignaturen in der Lage sein, Werte zu speichern. Der Speichermechanismus sollte mit dem Elementelementprinzip im Einklang stehen, dass das Element an Ziele anhängt werden kann, bei denen das anfügbisierbare Element nicht in der Mitgliederliste aufgeführt ist. .NET XAML Services bietet eine Implementierungstechnik für <xref:System.Xaml.IAttachedPropertyStore> anfügbisierbare Memberspeicher über die APIs und <xref:System.Xaml.AttachablePropertyServices>. <xref:System.Xaml.IAttachedPropertyStore>wird von den XAML-Writern verwendet, um die Speicherimplementierung zu `target` ermitteln, und sollte für den Typ implementiert werden, der der Accessoren ist. Die <xref:System.Xaml.AttachablePropertyServices> statischen APIs werden im Körper der Accessoren verwendet und <xref:System.Xaml.AttachableMemberIdentifier>verweisen auf das ansteckbare Element durch seine .

## <a name="xaml-related-clr-attributes"></a>XAML-bezogene CLR-Attribute

Das korrekte Zuweisen ihrer Typen, Member und Assemblys ist wichtig, um Systeminformationen vom XAML-Typ an .NET XAML Services zu melden. Die Meldung von XAML-Typsysteminformationen ist relevant, wenn eine der folgenden Situationen anwendung ist:

- Sie beabsichtigen, Ihre Typen für die Verwendung mit XAML-Systemen zu verwenden, die direkt auf .NET XAML Services XAML-Lesegeräten und XAML-Writern basieren.
- Sie definieren oder verwenden ein XAML-verwendendes Framework, das auf diesen XAML-Readern und XAML-Writern basiert.

Eine Auflistung der einzelnen XAML-bezogenen Attribute, die für die XAML-Unterstützung Ihrer benutzerdefinierten Typen relevant sind, finden Sie unter [XAML-verknüpfte CLR-Attribute für benutzerdefinierte Typen und Bibliotheken](clr-attributes-with-custom-types-and-libraries.md).

## <a name="usage"></a>Verwendung

Die Verwendung benutzerdefinierter Typen erfordert, dass der Markupautor ein Präfix für die Assembly und den CLR-Namespace zuordnen muss, die den benutzerdefinierten Typ enthalten. Dieses Verfahren ist in diesem Thema nicht dokumentiert.

## <a name="access-level"></a>Zugriffsebene

XAML bietet eine Möglichkeit zum Laden und Instanziieren von Typen mit Zugriffsebene. `internal` Diese Funktion wird bereitgestellt, damit Benutzercode eigene Typen definieren und dann diese Klassen aus Markup instanziieren kann, das ebenfalls Teil desselben Benutzercodebereichs ist.

Ein Beispiel von WPF ist immer <xref:System.Windows.Controls.UserControl> dann, wenn Benutzercode eine definiert, die als eine Möglichkeit zum Umgestalten eines UI-Verhaltens `public` gedacht ist, jedoch nicht als Teil eines möglichen Erweiterungsmechanismus, der durch Deklarieren der unterstützenden Klasse mit Zugriffsebene impliziert werden könnte. Ein <xref:System.Windows.Controls.UserControl> solcher kann `internal` mit Zugriff deklariert werden, wenn der Sicherungscode in dieselbe Assembly kompiliert wird, von der aus als XAML-Typ verwiesen wird.

Für eine Anwendung, die XAML <xref:System.Xaml.XamlObjectWriter>unter voller `internal` Vertrauenswürdigkeit lädt und verwendet, ist das Laden von Klassen mit Zugriffsebene immer aktiviert.

Für eine Anwendung, die XAML unter teilweiser Vertrauenswürdigkeit lädt, können Sie die Merkmale der Zugriffsebene mithilfe der <xref:System.Xaml.Permissions.XamlAccessLevel> API steuern. Außerdem müssen Verzögerungsmechanismen (z. B. das WPF-Vorlagensystem) in der Lage sein, Berechtigungen auf Zugriffsebene weiterzuleiten und für die eventuellelaufzeitauswertung beizubehalten. Dies wird intern durch <xref:System.Xaml.Permissions.XamlAccessLevel> Übergeben der Informationen behandelt.

### <a name="wpf-implementation"></a>WPF-Implementierung

WPF XAML verwendet ein teilweise vertrauenswürdiges Zugriffsmodell, wobei, wenn BAML unter teilweiser Vertrauenswürdigkeit geladen wird, der Zugriff auf <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> die Assembly, die die BAML-Quelle ist, beschränkt ist. Für den Aufschub verwendet <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> WPF als Mechanismus zum Übergeben der Informationen auf Zugriffsebene.

In der WPF XAML-Terminologie ist ein *interner Typ* ein Typ, der von derselben Assembly definiert wird und auch die referenzierende XAML enthält. Ein solcher Typ kann über einen XAML-Namespace zugeordnet werden, der absichtlich den `xmlns:local="clr-namespace:WPFApplication1"`Assembly=-Teil einer Zuordnung auslässt, z. B. . Wenn BAML auf einen internen `internal` Typ verweist und `GeneratedInternalTypeHelper` dieser Typ über Zugriffsebene verfügt, wird eine Klasse für die Assembly generiert. Wenn Sie vermeiden `GeneratedInternalTypeHelper`möchten, müssen `public` Sie entweder die Zugriffsebene verwenden oder die entsprechende Klasse in eine separate Assembly einteilen und diese Assembly abhängig machen.

## <a name="see-also"></a>Weitere Informationen

- [XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken](clr-attributes-with-custom-types-and-libraries.md)
- [XAML-Dienste](../../../api/index.md)
