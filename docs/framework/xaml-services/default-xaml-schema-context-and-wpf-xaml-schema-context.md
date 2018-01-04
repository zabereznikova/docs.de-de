---
title: Standard-XAML-Schemakontext und WPF-XAML-Schemakontext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
caps.latest.revision: "7"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ee7c83868934f1a524bb0068ea5e749e6cbfab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>Standard-XAML-Schemakontext und WPF-XAML-Schemakontext
Ein XAML-Schemakontext ist eine konzeptionelle Entität, die kennzeichnet, wie eine XAML-Produktion, die ein bestimmtes XAML-Vokabular verwendet interagiert mit dem Schreiben von Verhalten, z. B. wie Typmapping aufgelöst wird, wie Assemblys geladen werden, wie bestimmte Reader- und Writer-Objekt Einstellungen werden interpretiert. Dieses Thema beschreibt die Funktionen von .NET Framework-XAML-Dienste und die zugeordneten XAML-Standardschemakontext, die auf CLR-Typsystem basiert. Dieses Thema beschreibt auch das XAML-Schemakontext, der für WPF verwendet wird.  
  
## <a name="default-xaml-schema-context"></a>XAML-Standardschemakontext  
 .NET Framework XAML Services sowohl implementiert und einen standardmäßigen XAML-Schemakontext. Das standardmäßige Verhalten bei Verwendung von XAML-Schema Kontext ist nicht immer vollständig sichtbar, in der API für die <xref:System.Xaml.XamlSchemaContext> Klasse. Allerdings ist das Verhalten, das die Verwendung von XAML-Standardschemakontext wirkt sich auf in vielen Fällen Observable-Objekt über gemeinsame-API von XAML-Typsystem, z. B. Mitglieder der <xref:System.Xaml.XamlMember> oder <xref:System.Xaml.XamlType>, oder über APIs verfügbar gemacht werden, auf XAML-Readern und XAML-Writern, die verwendet werden die Verwendung von XAML-Standardschemakontext.  
  
 Sie erstellen eine <xref:System.Xaml.XamlSchemaContext> , kapselt das Standardverhalten durch Aufrufen der <xref:System.Xaml.XamlSchemaContext> Konstruktor. Dadurch wird explizit die Verwendung von XAML-Standardschemakontext erstellt. Die gleiche standardmäßigen XAML-Schemakontext ist implizit, erstellt, wenn Sie initialisieren ein XAML-Reader oder XAML-Writer, die mithilfe von APIs, die nicht explizit Ausführen einer <xref:System.Xaml.XamlSchemaContext> input-Parameters.  
  
 Die Verwendung von XAML-Standardschemakontext basiert auf CLR-Reflektion für seine Zuordnung typverhalten. Dies beinhaltet die Untersuchung der definierenden CLR <xref:System.Type>, und die zugehörigen <xref:System.Reflection.PropertyInfo> oder <xref:System.Reflection.MethodInfo>. Darüber hinaus ist CLR-Zuordnung für Typen oder Member verwendet, um die Details für die Verwendung von XAML-Typ oder die Verwendung von XAML-Member-Informationen, die die CLR-Unterstützungstyp verwendet. Die Verwendung von XAML-Standardschemakontext erfordert keinen Typ System Erweiterung Techniken, wie z. B. die `Invoker` Muster, da die erforderlichen Informationen aus dem CLR-Typsystem verfügbar ist.  
  
 Für die Assembly Laden von Logik verwendet der XAML-Standardschemakontext hauptsächlich angegebene Namespacezuordnungen, die Verwendung von XAML-Werte der Assembly. Darüber hinaus <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> können-Hinweis eine Assembly für Szenarien wie das Laden von internen Typen geladen.  
  
## <a name="wpf-xaml-schema-context"></a>WPF-XAML-Schemakontext  
 Der WPF XAML-Schemakontext ist in diesem Thema beschrieben werden, da die WPF-Implementierung eine interessante Abbildung die Arten von Funktionen bereitstellt, die durch die Implementierung eines nicht standardmäßigen XAML-Schemakontexts eingeführt werden kann. Darüber hinaus wird die Verwendung von XAML-Schema-Kontext-Konzept nicht sehr viel in der WPF-Dokumentation erläutert, die von WPF XAML behandelt; das Verhalten, das der XAML-Schemakontext kann möglicherweise nur vollständig verständlich, wenn mit einer Erläuterung der Funktionsweise der XAML-Standardschemakontext integriert. Der WPF XAML-Schemakontext implementiert das folgende Verhalten an.  
  
 **Überschreibt der Suche:** WPF verfügt über einige Inhaltsmodelle für XAML vorliegen von XAML-Content-Eigenschaften, die verwendet werden ohne <xref:System.Windows.Markup.ContentPropertyAttribute> attributiert. <xref:System.Xaml.XamlType.LookupContentProperty%2A>Außerkraftsetzungen für WPF dieses Verhalten zu implementieren.  
  
 **Verzögerung für WPF-Ausdrücke:** WPF enthält mehrere Ausdrucksklassen, die einen Wert zu verzögern, bis ein Laufzeitkontext verfügbar ist. Vorlage-Erweiterung ist auch ein Common Language Runtime-Verhalten, das Deferral-Techniken abhängt.  
  
 **Geben Sie Suche-Optimierungen System:** WPF verfügt über eine umfangreiche Verwendung von XAML-Vokabular und -Objektmodell, einschließlich Basisklasse Memberdefinitionen, die auf Hunderttausenden von WPF definierte Klassen erben. Darüber hinaus wird WPF selbst über mehrere Assemblys verteilt. WPF optimiert Typsuche mithilfe von Nachschlagetabellen und anderen Techniken. Dies bietet leistungsverbesserungen, über die Verwendung von XAML-Standardschemakontext und CLR-basierten Typsuche. In Fällen, in denen Typen nicht in einer Nachschlagetabelle vorhanden sind, verwendet das Verhalten von XAML-Schema Kontext Techniken, die die Verwendung von XAML-Standardschemakontext ähneln.  
  
 **XamlType und XamlMember Erweiterung:** WPF erweitert Eigenschaft Konzepte mit Abhängigkeitseigenschaften und Ereignis-Konzepte mit Routingereignisse. Um diese Konzepte größer Sichtbarkeit für die Verwendung von XAML-Verarbeitung von Vorgängen zu gewähren, WPF erweitert <xref:System.Xaml.XamlType> und <xref:System.Xaml.XamlMember>, und fügt der interne Eigenschaften, die Abhängigkeitseigenschaft und Merkmale weitergeleitet.  
  
### <a name="accessing-the-wpf-xaml-schema-context"></a>Zugreifen auf den WPF-XAML-Schemakontext  
 Bei Verwendung von XAML-Techniken, die auf WPF basieren <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> oder <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>, der WPF XAML-Schemakontext ist bereits auf diese XAML-Reader und XAML-Writer-Implementierungen.  
  
 Bei Verwendung anderer XAML-Reader oder XAML-Writer-Implementierungen, die nicht initialisieren mit der WPF XAML-Schemakontext, können Sie möglicherweise eine funktionierende WPF XAML Schemakontext abgerufen <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>. Sie können dann verwenden Sie diesen Wert als für andere-API, mit denen die Initialisierung einer <xref:System.Xaml.XamlSchemaContext>. Sie können z. B. Aufrufen <xref:System.Xaml.XamlXmlReader.%23ctor%2A> für Initialisierung und übergeben der WPF XAML-Schemakontext. Oder Sie könnte den WPF XAML-Schemakontext für die Verwendung von XAML-Typ Systemvorgänge verwenden. Dazu gehören beispielsweise Initialisierung zur Erstellung einer <xref:System.Xaml.XamlType> oder <xref:System.Xaml.XamlMember>, oder zum Aufrufen von <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>.  
  
 Beachten Sie, dass wenn Sie bestimmte Aspekte von WPF-XAML aus der Perspektive einer reinen XAML-Knoten Stream zuzugreifen, einige der WPF-Framework-Funktionen noch nicht verarbeitet wurden möglicherweise. WPF-Vorlagen für Steuerelemente werden z. B. noch nicht angewendet. Daher sollten Sie eine Eigenschaft, die zur Laufzeit mit einer vollständigen visuellen Struktur aufgefüllt werden kann zugreifen, nur möglicherweise einen Eigenschaftswert, der auf eine Vorlage verweist. Dienstkontext für WPF-Markuperweiterungen auch möglicherweise nicht genau, wenn eine Situation nicht zur Laufzeit zur Verfügung gestellt und kann dazu führen, Ausnahmen beim Schreiben eines Objektdiagramms.  
  
## <a name="xaml-and-assembly-loading"></a>XAML und das Laden von Assemblys  
 Für XAML und .NET Framework XAML Services das Laden einer Assembly mit dem CLR-definierten Konzept der integriert <xref:System.AppDomain>. Ein XAML-Schemakontext zum Laden von Assemblys oder Typen zur Laufzeit oder zur Entwurfszeit suchen basierend auf die Verwendung von <xref:System.AppDomain> und anderen Faktoren. Die Logik ist geringfügig, je nachdem, ob der XAML-Code loose XAML für einen XAML-Reader, XAML, die in einer DLL kompiliert `XamlBuildTask`, oder BAML wird generiert werden, indem der WPF `PresentationBuildTask`.  
  
 Die Verwendung von XAML-Schemakontext für WPF integriert, das WPF-Anwendungsmodell, was wiederum <xref:System.AppDomain> sowie anderen Faktoren, die WPF-Implementierungsdetails sind.  
  
#### <a name="xaml-reader-input-loose-xaml"></a>XAML-Reader-Eingabe (loose XAML)  
  
1.  Der XAML-Schemakontext durchläuft die <xref:System.AppDomain> der Anwendung, für eine bereits geladene Assembly, die alle Aspekte des Namens übereinstimmt sucht beginnend mit der zuletzt geladenen Assembly. Wenn eine Übereinstimmung gefunden wird, wird diese Assembly für die Auflösung verwendet.  
  
2.  Andernfalls einer der folgenden Methoden auf CLR basiert <xref:System.Reflection.Assembly> API zum Laden einer Assembly verwendet werden:  
  
    -   Wenn der Name in der Zuordnung qualifiziert ist, rufen Sie <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> für den qualifizierten Namen.  
  
    -   Wenn der vorherige Schritt fehlschlägt, verwenden Sie den kurzen Namen (und das öffentliche Schlüsseltoken, falls vorhanden) aufrufen, <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
    -   Wenn der Name in der Zuordnung nicht qualifiziert ist, rufen Sie <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
#### <a name="xamlbuildtask"></a>XamlBuildTask  
 `XamlBuildTask`Dient zum [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)] und [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)].  
  
 Beachten Sie, die über Assemblyverweise `XamlBuildTask` immer vollständig qualifiziert sind.  
  
1.  Rufen Sie <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> für den qualifizierten Namen.  
  
2.  Wenn der vorherige Schritt fehlschlägt, verwenden Sie den kurzen Namen (und das öffentliche Schlüsseltoken, falls vorhanden) aufrufen, <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)  
 Es gibt zwei Aspekte das Laden von Assemblys für BAML: Laden der ursprünglichen Assembly, die das BAML als Komponente enthält, und Laden der Assemblys Typ-Unterstützung für alle Typen, die die BAML-Produktion verweist.  
  
##### <a name="assembly-load-for-initial-markup"></a>Laden von Assembly für das ursprüngliche Markup:  
 Der Verweis auf die Assembly, aus das Markup geladen ist immer nicht qualifiziert.  
  
1.  Der WPF XAML-Schemakontext durchläuft die <xref:System.AppDomain> der WPF-Anwendung, die Suche nach einer bereits geladenen Assembly, die alle Aspekte des Namens übereinstimmt beginnend mit der zuletzt geladenen Assembly. Wenn eine Übereinstimmung gefunden wird, wird diese Assembly für die Auflösung verwendet.  
  
2.  Wenn der vorherige Schritt fehlschlägt, verwenden Sie den kurzen Namen (und das öffentliche Schlüsseltoken, falls vorhanden) aufrufen, <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
##### <a name="assembly-references-by-baml-types"></a>Assemblyverweise von BAML-Typen:  
 Assemblyverweise für Typen, die in der Produktion BAML verwendet, sind immer vollqualifizierte als Ausgabe des Tasks "Build".  
  
1.  Der WPF XAML-Schemakontext durchläuft die <xref:System.AppDomain> der WPF-Anwendung, die Suche nach einer bereits geladenen Assembly, die alle Aspekte des Namens übereinstimmt beginnend mit der zuletzt geladenen Assembly. Wenn eine Übereinstimmung gefunden wird, wird diese Assembly für die Auflösung verwendet.  
  
2.  Andernfalls wird eine der folgenden Methoden zum Laden einer Assembly verwendet:  
  
    -   Rufen Sie <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> für den qualifizierten Namen.  
  
    -   Wenn ein Kurzname Tastenkombination öffentlichen token der Assembly entsprechen, der das BAML geladen wurde, verwenden Sie diese Assembly.  
  
    -   Verwenden Sie kurze Namen + Token des öffentlichen Schlüssels Aufrufen <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen zu XAML-Knotenstreamstrukturen und -konzepten](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)
