---
title: Standard-XAML-Schemakontext und WPF-XAML-Schemakontext
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: 2e92372de61230a98a02282cc28fc3f479cd94eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433079"
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>Standard-XAML-Schemakontext und WPF-XAML-Schemakontext
Ein XAML-Schemakontext ist eine konzeptionelle Entität, die qualifiziert, wie eine XAML-Produktion, die ein bestimmtes XAML-Vokabular verwendet, mit dem Objektschreibverhalten interagiert, einschließlich wie Typzuordnungen aufgelöst werden, wie Assemblys geladen werden, wie bestimmte Reader- und Writer-Einstellungen interpretiert werden. In diesem Thema werden die Features von .NET XAML Services und der zugehörige Standard-XAML-Schemakontext beschrieben, der auf dem CLR-Typsystem basiert. In diesem Thema wird auch der XAML-Schemakontext beschrieben, der für WPF verwendet wird.

## <a name="default-xaml-schema-context"></a>Standard-XAML-Schemakontext

.NET XAML Services implementiert und verwendet einen Standardmäßigen XAML-Schemakontext. Das standardmäßige XAML-Schemakontextverhalten ist in der <xref:System.Xaml.XamlSchemaContext> API der Klasse nicht immer vollständig sichtbar. In vielen Fällen kann das Verhalten, das der standardmäßige XAML-Schemakontext beeinflusst, jedoch über die <xref:System.Xaml.XamlMember> <xref:System.Xaml.XamlType>allgemeine API des XAML-Typsystems, z. B. Member von oder , oder über APIs, die auf XAML-Readern und XAML-Writern verfügbar gemacht werden, die den standardmäßigen XAML-Schemakontext verwenden, beobachtet werden.

Sie können <xref:System.Xaml.XamlSchemaContext> eine erstellen, die das Standardverhalten <xref:System.Xaml.XamlSchemaContext> kapselt, indem Sie den Konstruktor aufrufen. Dadurch wird explizit der standardmäßige XAML-Schemakontext erstellt. Derselbe Standard-XAML-Schemakontext wird implizit erstellt, wenn Sie einen XAML-Reader oder XAML-Writer mithilfe von APIs initialisieren, die keinen <xref:System.Xaml.XamlSchemaContext> Eingabeparameter explizit verwenden.

Der standardmäßige XAML-Schemakontext basiert auf CLR-Reflektion für sein Typzuordnungsverhalten. Dazu gehört die Prüfung <xref:System.Type>der <xref:System.Reflection.PropertyInfo> definierenden CLR und der zugehörigen oder <xref:System.Reflection.MethodInfo>. Außerdem wird die CLR-Attribution für Typen oder Member verwendet, um die Spezifikationen für XAML-Typ- oder XAML-Memberinformationen auszufüllen, die den CLR-Sicherungstyp verwenden. Für den Standardmäßigen XAML-Schemakontext sind keine `Invoker` Typsystemerweiterungstechniken wie das Muster erforderlich, da die erforderlichen Informationen über das CLR-Typsystem verfügbar sind.

Bei der Ladelogik für Assemblys basiert der standardmäßige XAML-Schemakontext hauptsächlich auf allen Assemblywerten, die in XAML-Namespacezuordnungen bereitgestellt werden. Kann <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> auch eine Assembly zum Laden anweisen, z. B. für das Laden interner Typen.

## <a name="wpf-xaml-schema-context"></a>WPF XAML-Schemakontext

Der WPF XAML-Schemakontext wird in diesem Thema beschrieben, da die WPF-Implementierung eine interessante Illustration der Arten von Features bietet, die durch implementieren eines nicht standardmäßigen XAML-Schemakontexts eingeführt werden können. Außerdem wird das XAML-Schemakontextkonzept in der WPF-Dokumentation, die sich mit WPF XAML befasst, nicht sehr ausführlich behandelt. Das Verhalten, das der XAML-Schemakontext aktiviert, ist möglicherweise nur dann vollständig verständlich, wenn es in eine Diskussion über die Funktionsweise des standardmäßigen XAML-Schemakontexts integriert ist. Der WPF XAML-Schemakontext implementiert das folgende Verhalten.

**Nachschlagen überschreibt:** WPF verfügt über einige Inhaltsmodelle für XAML, bei denen <xref:System.Windows.Markup.ContentPropertyAttribute> XAML-Inhaltseigenschaften funktionieren, ohne dass attributiert wird. <xref:System.Xaml.XamlType.LookupContentProperty%2A>Überschreibungen für WPF implementieren dieses Verhalten.

**Aufschub für WPF-Ausdrücke:** WPF verfügt über mehrere Ausdrucksklassen, die einen Wert aufschieben, bis ein Laufzeitkontext verfügbar ist. Außerdem ist die Vorlagenerweiterung ein Laufzeitverhalten, das auf Stundungstechniken basiert.

**Typsystem-Suchoptimierungen:** WPF verfügt über ein umfangreiches XAML-Vokabular und Objektmodell, einschließlich Basisklassenmemberdefinitionen, die buchstäblich Hunderte von WPF-definierten Klassen erben. Außerdem ist WPF selbst auf mehrere Assemblys verteilt. WPF optimiert die Typsuche mithilfe von Suchtabellen und anderen Techniken. Dies bietet Leistungsverbesserungen gegenüber dem standardmäßigen XAML-Schemakontext und der CLR-basierten Typsuche. In Fällen, in denen Typen in einer Nachsuchtabelle nicht vorhanden sind, verwendet das Verhalten XAML-Schemakontexttechniken, die dem Standardmäßigen XAML-Schemakontext ähneln.

**XamlType- und XamlMember-Erweiterung:** WPF erweitert Eigenschaftskonzepte mit Abhängigkeitseigenschaften und Ereigniskonzepte mit routingierten Ereignissen. Um diesen Konzepten eine bessere Sichtbarkeit für XAML-Verarbeitungsvorgänge zu geben, erweitert und <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlMember>fügt WPF interne Eigenschaften hinzu, die Abhängigkeitseigenschaft und geroutete Ereignismerkmale melden.

### <a name="accessing-the-wpf-xaml-schema-context"></a>Zugriff auf den WPF XAML-Schemakontext

Wenn Sie XAML-Techniken verwenden, die <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> auf <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>der WPF- oder - - der WPF XAML-Schemakontext basieren, wird bereits für diese XAML-Reader- und XAML-Writerimplementierungen verwendet.

Wenn Sie andere XAML-Reader- oder XAML-Writerimplementierungen verwenden, die nicht mit dem WPF XAML-Schemakontext initialisiert <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>werden, können Sie möglicherweise einen funktionierenden WPF XAML-Schemakontext aus abrufen. Sie können diesen Wert dann als Initialisierung <xref:System.Xaml.XamlSchemaContext>für andere APIverwenden verwenden, die eine verwenden. Sie können z. <xref:System.Xaml.XamlXmlReader.%23ctor%2A> B. die Initialisierung aufrufen und den WPF XAML-Schemakontext übergeben. Sie können auch den WPF XAML-Schemakontext für Systemvorgänge vom Typ XAML verwenden. Dies kann die Bauinitialisierung eines <xref:System.Xaml.XamlType> oder <xref:System.Xaml.XamlMember>oder aufrufen <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>umfassen.

Beachten Sie, dass einige der WPF-Frameworkfunktionen möglicherweise noch nicht funktioniert haben, wenn Sie aus einer reinen XAML-Knotenstreamperspektive auf bestimmte Aspekte von WPF XAML zugreifen. Beispielsweise werden WPF-Vorlagen für Steuerelemente noch nicht angewendet. Wenn Sie also auf eine Eigenschaft zugreifen, die zur Laufzeit möglicherweise mit einer vollständigen visuellen Struktur gefüllt wird, wird möglicherweise nur ein Eigenschaftswert angezeigt, der auf eine Vorlage verweist. Der für WPF-Markuperweiterungen bereitgestellte Dienstkontext ist möglicherweise auch nicht korrekt, wenn er aus einer Situation anot-runtime bereitgestellt wird, und kann zu Ausnahmen beim Schreiben eines Objektdiagramms führen.

## <a name="xaml-and-assembly-loading"></a>XAML- und Assembly-Laden

Das Laden der Assembly für XAML und .NET XAML <xref:System.AppDomain>Services ist in das CLR-definierte Konzept von integriert. Ein XAML-Schemakontext interpretiert, wie Assemblys geladen oder Typen zur Laufzeit oder <xref:System.AppDomain> Entwurfszeit basierend auf der Verwendung und anderen Faktoren gefunden werden. Die Logik unterscheidet sich geringfügig, je nachdem, ob das XAML lose XAML für einen XAML-Reader ist, XAML in eine DLL von `XamlBuildTask`kompiliert wird oder OB BAML von WPF generiert `PresentationBuildTask`wird.

Der XAML-Schemakontext für WPF lässt sich in das <xref:System.AppDomain> WPF-Anwendungsmodell integrieren, das wiederum neben anderen Faktoren, die WPF-Implementierungsdetails sind, verwendet wird.

#### <a name="xaml-reader-input-loose-xaml"></a>XAML-Lesereingabe (lose XAML)

01. Der XAML-Schemakontext durchforstet die <xref:System.AppDomain> der Anwendung und sucht nach einer bereits geladenen Assembly, die allen Aspekten des Namens entspricht, beginnend mit der zuletzt geladenen Assembly. Wenn eine Übereinstimmung gefunden wird, wird diese Assembly für die Auflösung verwendet.

02. Andernfalls wird eine der folgenden Techniken, die auf der CLR-API <xref:System.Reflection.Assembly> basieren, zum Laden einer Assembly verwendet:

    - Wenn der Name in der <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> Zuordnung qualifiziert ist, rufen Sie den qualifizierten Namen auf.

    - Wenn der vorherige Schritt fehlschlägt, verwenden Sie den Kurznamen <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>(und das öffentliche Schlüsseltoken, falls vorhanden), um aufzurufen.

    - Wenn der Name in der Zuordnung <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>nicht qualifiziert ist, rufen Sie auf.

#### <a name="xamlbuildtask"></a>XamlBuildTask

`XamlBuildTask`wird für Windows Communication Foundation (WCF) und Windows Workflow Foundation verwendet.

Beachten Sie, `XamlBuildTask` dass Assemblyverweise durch immer voll qualifiziert sind.

1. Rufen <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> Sie den qualifizierten Namen auf.

2. Wenn der vorherige Schritt fehlschlägt, verwenden Sie den Kurznamen <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>(und das öffentliche Schlüsseltoken, falls vorhanden), um aufzurufen.

#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)

Das Laden der Baugruppen für BAML hat zwei Aspekte: das Laden der ursprünglichen Baugruppe, die die BAML als Komponente enthält, und das Laden der Typsicherungsassemblys für alle Typen, auf die von der BAML-Produktion verwiesen wird.

##### <a name="assembly-load-for-initial-markup"></a>Baugruppenlast für das anfängliche Markup:

Der Verweis auf die Assembly, aus der das Markup geladen werden soll, ist immer nicht qualifiziert.

1. Der WPF XAML-Schemakontext iteriert durch die <xref:System.AppDomain> der WPF-Anwendung und sucht nach einer bereits geladenen Assembly, die allen Aspekten des Namens entspricht, beginnend mit der zuletzt geladenen Assembly. Wenn eine Übereinstimmung gefunden wird, wird diese Assembly für die Auflösung verwendet.

2. Wenn der vorherige Schritt fehlschlägt, verwenden Sie den Kurznamen <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>(und das öffentliche Schlüsseltoken, falls vorhanden), um aufzurufen.

##### <a name="assembly-references-by-baml-types"></a>Assemblyreferenzen nach BAML-Typen:

Assemblyreferenzen für Typen, die in der BAML-Produktion verwendet werden, sind als Ausgabe der Buildaufgabe immer voll qualifiziert.

01. Der WPF XAML-Schemakontext iteriert durch die <xref:System.AppDomain> der WPF-Anwendung und sucht nach einer bereits geladenen Assembly, die allen Aspekten des Namens entspricht, beginnend mit der zuletzt geladenen Assembly. Wenn eine Übereinstimmung gefunden wird, wird diese Assembly für die Auflösung verwendet.

02. Andernfalls wird eine der folgenden Techniken zum Laden einer Baugruppe verwendet:

    - Rufen <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> Sie den qualifizierten Namen auf.
  
    - Wenn eine Kombination aus einem kurzen Namen + einem öffentlichen Schlüsseltoken mit der Assembly übereinstimmt, aus der die BAML geladen wurde, verwenden Sie diese Assembly.

    - Verwenden Sie kurzname + <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>öffentliches Schlüsseltoken, um aufzurufen.

## <a name="see-also"></a>Weitere Informationen

- [Grundlagen zu XAML-Knotenstreamstrukturen und -konzepten](understanding-xaml-node-stream-structures-and-concepts.md)
