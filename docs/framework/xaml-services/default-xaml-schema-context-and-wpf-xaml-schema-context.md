---
title: Standard-XAML-Schemakontext und WPF-XAML-Schemakontext
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: 1312541321e74668e6527c6c54e712342fbb3a17
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124695"
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>Standard-XAML-Schemakontext und WPF-XAML-Schemakontext
Ein XAML-Schemakontext ist eine konzeptionelle Entität, die beschreibt, wie eine XAML-Produktion, die ein bestimmtes XAML-Vokabular verwendet interagiert mit dem Schreiben von Verhalten führen, einschließlich wie Zuordnung eines Typs aufgelöst wird, wie Assemblys geladen werden, wie bestimmte Reader- und Writer-Objekt Einstellungen werden interpretiert. Dieses Thema beschreibt die Funktionen von .NET Framework-XAML-Dienste und der zugeordnetes standardmäßiges XAML-Schemakontext, basierend auf der CLR-Typsystems. Dieses Thema beschreibt auch die XAML-Schemakontext, der für WPF verwendet wird.  
  
## <a name="default-xaml-schema-context"></a>Standard-XAML-Schemakontext  
 .NET Framework-XAML-Dienste sowohl implementiert und eine Standard-XAML-Schemakontext. Das standardkontextverhalten für XAML-Schema ist nicht immer vollständig sichtbar ist, in den APIs von den <xref:System.Xaml.XamlSchemaContext> Klasse. Allerdings ist das Verhalten, das die XAML-Standardschemakontext wirkt sich auf in vielen Fällen Observable-Objekt über die allgemeine-API, der dem XAML-Typsystem, z. B. Mitglieder der <xref:System.Xaml.XamlMember> oder <xref:System.Xaml.XamlType>, oder über APIs verfügbar gemacht werden, auf XAML-Readern und XAML-Writer, die verwendet werden der Standard-XAML-Schemakontext.  
  
 Sie erstellen eine <xref:System.Xaml.XamlSchemaContext> , kapselt das Standardverhalten durch Aufrufen der <xref:System.Xaml.XamlSchemaContext> Konstruktor. Dadurch wird explizit auf den Standard-XAML-Schemakontext erstellt. Die gleiche XAML-Standardschemakontext wird implizit erstellt, wenn eine XAML-Reader oder XAML-Writer, die mithilfe von APIs, die explizit nicht akzeptieren, initialisieren Sie ein <xref:System.Xaml.XamlSchemaContext> input-Parameters.  
  
 Der Standard-XAML-Schemakontext basiert auf CLR-Reflektion für das Verhalten des Typs zuordnen. Dies beinhaltet die Untersuchung der definierenden CLR <xref:System.Type>, und die zugehörigen <xref:System.Reflection.PropertyInfo> oder <xref:System.Reflection.MethodInfo>. Außerdem wird die CLR-Zuordnung für Typen oder Member verwendet, um die Details für den XAML-Typ oder XAML-Member-Informationen, die die CLR-Unterstützungstyp verwendet. Der Standard-XAML-Schemakontext erfordert keinen Typ System Erweiterung Techniken wie z. B. die `Invoker` Muster, da die erforderlichen Informationen über CLR-Typsystem verfügbar ist.  
  
 Laden der Logik von Assemblys verwendet die XAML-Standardschemakontext hauptsächlich auf eine beliebige Assembly Werte in der XAML-Namespacezuordnungen. Darüber hinaus <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> können als Hinweise für eine Assembly geladen werden, für Szenarien wie das Laden interner Typen.  
  
## <a name="wpf-xaml-schema-context"></a>WPF-XAML-Schemakontext  
 Der WPF XAML-Schemakontext ist in diesem Thema beschrieben werden, da die WPF-Implementierung eine interessante Abbildung für die Arten von Funktionen bereitstellt, die durch die Implementierung von einem nicht standardmäßigen XAML-Schemakontext eingeführt werden kann. Darüber hinaus wird die Kontext-Konzept von XAML-Schema nicht sehr viel in der WPF-Dokumentation erläutert, die WPF XAML-Adressen; das Verhalten, das der XAML-Schemakontext kann möglicherweise nur vollständig verständlich, wenn mit einer Erläuterung der Funktionsweise der XAML-Standardschemakontext integriert. Der WPF XAML-Schemakontext wird das folgende Verhalten implementiert.  
  
 **Suche überschreibt:** WPF enthält ein paar Inhaltsmodelle für XAML mit XAML-Inhaltseigenschaften, die ohne funktionieren <xref:System.Windows.Markup.ContentPropertyAttribute> zugeordnet sind. <xref:System.Xaml.XamlType.LookupContentProperty%2A> Außerkraftsetzungen für WPF wird dieses Verhalten implementiert.  
  
 **Die Verzögerung für WPF-Ausdrücke:** WPF bietet mehrere Expression-Klassen, die einen Wert zu verzögern, bis ein Laufzeitkontext verfügbar ist. Darüber hinaus ist die vorlagenerweiterung ein Laufzeitverhalten, die Verzögerung Techniken verwendet.  
  
 **Geben Sie die System-Lookup-Optimierungen:** WPF verfügt über eine umfangreiche XAML Vokabular und das Objektmodell, einschließlich der Basisklasse Memberdefinitionen, die auf Hunderten von WPF definierte Klassen erben. Darüber hinaus ist die WPF selbst auf mehrere Assemblys verteilt. WPF optimiert Typsuche mithilfe von Nachschlagetabellen und andere Techniken. Dies bietet leistungsverbesserungen über den Standard-XAML-Schemakontext und der CLR-basierten das Nachschlagen des Replikationstyps an. In Fällen, in denen Typen nicht in einer Nachschlagetabelle vorhanden sind, verwendet das Verhalten für XAML-Schema Kontext Techniken wie auf der Standard-XAML-Schemakontext.  
  
 **XamlType und XamlMember-Erweiterung:** WPF erweitert die Konzepte der Abhängigkeitseigenschaften und Ereignis-Konzepte zu Routingereignissen. Um diese Konzepte mehr Transparenz für XAML-Verarbeitung zu ermöglichen, sich WPF erweitert <xref:System.Xaml.XamlType> und <xref:System.Xaml.XamlMember>, und fügt der interne Eigenschaften, die Abhängigkeitseigenschaft zu melden und Ereignis-Merkmale weitergeleitet.  
  
### <a name="accessing-the-wpf-xaml-schema-context"></a>Zugreifen auf den WPF-XAML-Schemakontext  
 Wenn Sie XAML-Techniken verwenden, die auf WPF basieren <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> oder <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>, der WPF XAML-Schemakontext wird bereits für diese XAML-Reader und XAML-Writer-Implementierungen.  
  
 Wenn Sie mit anderen XAML-Reader oder XAML-Writer-Implementierungen, die nicht initialisieren der WPF XAML-Schemakontext, können Sie möglicherweise eine funktionierende WPF XAML-Schemakontext aus abrufen <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>. Sie können dann diesen Wert verwenden, als Initialisierung für andere API, mit denen eine <xref:System.Xaml.XamlSchemaContext>. Sie können z. B. Aufrufen <xref:System.Xaml.XamlXmlReader.%23ctor%2A> für die Initialisierung und übergeben Sie der WPF XAML-Schemakontext. Oder Sie können den WPF XAML-Schemakontext für XAML-Typ Systemvorgänge verwenden. Dazu gehören beispielsweise Konstruktion Initialisierung einer <xref:System.Xaml.XamlType> oder <xref:System.Xaml.XamlMember>, oder das Aufrufen <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>.  
  
 Beachten Sie, dass wenn Sie bestimmte Aspekte der WPF XAML aus einer reinen XAML-Knoten Stream Perspektiven zugreifen, einige der Funktionen der WPF-Framework noch nicht verarbeitet wurden möglicherweise. WPF-Vorlagen für Steuerelemente sind z. B. noch nicht angewendet. Daher sollten Sie eine Eigenschaft, die zur Laufzeit mit einer vollständigen visuellen Struktur aufgefüllt werden kann zugreifen, können Sie nur angezeigt, auf einen Eigenschaftswert, der auf eine Vorlage verweist. Der Dienstkontext für WPF-Markuperweiterungen auch möglicherweise nicht genau, wenn ein Problem nicht zur Laufzeit bereitgestellt und kann dazu führen, Ausnahmen beim Schreiben eines Objektdiagramms.  
  
## <a name="xaml-and-assembly-loading"></a>XAML und das Laden von Assemblys  
 Laden von Assemblys für XAML und .NET Framework-XAML-Dienste integriert, die von CLR definierte Konzept von <xref:System.AppDomain>. Ein XAML-Schemakontext interpretiert, wie Assemblys geladen werden oder finden von Typen zur Laufzeit oder Entwurfszeit basierend auf der Verwendung von <xref:System.AppDomain> und anderen Faktoren. Die Logik ist geringfügig, je nachdem, ob der XAML loose XAML für einen XAML-Reader, XAML, die in eine DLL kompiliert `XamlBuildTask`, oder BAML wird generiert werden, indem der WPF `PresentationBuildTask`.  
  
 Der XAML-Schemakontext für WPF-Integration mit dem WPF-Anwendungsmodell, die wiederum <xref:System.AppDomain> sowie von anderen Faktoren, die die Details der WPF-Implementierung sind.  
  
#### <a name="xaml-reader-input-loose-xaml"></a>XAML-Reader-Eingabe (loose XAML)  
  
1.  Der XAML-Schemakontext durchläuft die <xref:System.AppDomain> der Anwendung nach einer bereits geladenen Assembly mit allen Aspekten des Namens, beginnend mit dem zuletzt geladenen Assembly. Wenn eine Übereinstimmung gefunden wird, wird diese Assembly für die Auflösung verwendet.  
  
2.  Andernfalls, eine der folgenden Methoden auf der Grundlage CLR <xref:System.Reflection.Assembly> -API zum Laden einer Assembly verwendet werden:  
  
    -   Wenn der Name in der Zuordnung gekennzeichnet ist, rufen Sie <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> für den qualifizierten Namen.  
  
    -   Wenn der vorherige Schritt fehlschlägt, verwenden Sie den kurzen Namen (und das öffentliche Schlüsseltoken, falls vorhanden) aufrufen, <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
    -   Wenn der Name in der Zuordnung nicht qualifiziert ist, rufen Sie <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
#### <a name="xamlbuildtask"></a>XamlBuildTask  
 `XamlBuildTask` wird für Windows Communication Foundation (WCF) und Windows Workflow Foundation verwendet.  
  
 Beachten Sie, die über Assemblyverweise `XamlBuildTask` sind stets vollqualifiziert.  
  
1.  Rufen Sie <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> für den qualifizierten Namen.  
  
2.  Wenn der vorherige Schritt fehlschlägt, verwenden Sie den kurzen Namen (und das öffentliche Schlüsseltoken, falls vorhanden) aufrufen, <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)  
 Es gibt zwei Aspekte: das Laden von Assemblys für BAML: Laden der ursprünglichen Assembly, die die BAML als Komponente enthält, und laden den Typ Unterstützungsassemblys für alle Typen, die von der BAML-Produktion verwiesen wird.  
  
##### <a name="assembly-load-for-initial-markup"></a>Laden der Assembly für das ursprüngliche Markup:  
 Der Verweis auf die Assembly, die das Markup geladen ist immer nicht qualifiziert.  
  
1.  Der WPF XAML-Schemakontext durchläuft die <xref:System.AppDomain> der WPF-Anwendung und Suche nach einer bereits geladenen Assembly mit allen Aspekten des Namens, beginnend mit dem zuletzt geladenen Assembly. Wenn eine Übereinstimmung gefunden wird, wird diese Assembly für die Auflösung verwendet.  
  
2.  Wenn der vorherige Schritt fehlschlägt, verwenden Sie den kurzen Namen (und das öffentliche Schlüsseltoken, falls vorhanden) aufrufen, <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
##### <a name="assembly-references-by-baml-types"></a>Assemblyverweise von BAML-Typen:  
 Assemblyverweise für Typen in der BAML-Produktion sind immer voll gekennzeichnet sein, als Ausgabe des Tasks "Build".  
  
1.  Der WPF XAML-Schemakontext durchläuft die <xref:System.AppDomain> der WPF-Anwendung und Suche nach einer bereits geladenen Assembly mit allen Aspekten des Namens, beginnend mit dem zuletzt geladenen Assembly. Wenn eine Übereinstimmung gefunden wird, wird diese Assembly für die Auflösung verwendet.  
  
2.  Andernfalls wird eine der folgenden Methoden zum Laden einer Assembly verwendet:  
  
    -   Rufen Sie <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> für den qualifizierten Namen.  
  
    -   Wenn ein Kurzname und das öffentliche token Kombination aus der Assembly übereinstimmen, der aus der BAML geladen wurde, verwenden Sie diese Assembly.  
  
    -   Verwenden Sie zum Aufrufen Kurzname und das Token des öffentlichen Schlüssels <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- [Grundlagen zu XAML-Knotenstreamstrukturen und -konzepten](understanding-xaml-node-stream-structures-and-concepts.md)
