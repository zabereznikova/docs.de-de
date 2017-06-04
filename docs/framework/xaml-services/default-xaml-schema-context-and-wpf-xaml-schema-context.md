---
title: "Default XAML Schema Context and WPF XAML Schema Context | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# Default XAML Schema Context and WPF XAML Schema Context
Ein XAML\-Schemakontext ist eine konzeptionelle Entität, die beschreibt, wie eine XAML\-Produktion, die ein bestimmtes XAML\-Vokabular verwendet, mit dem Objektschreibverhalten interagiert. Dies beinhaltet die Auflösung der Typzuordnung, das Laden von Assemblys und die Interpretation bestimmter Reader\- und Writereinstellungen.  In diesem Thema werden die Funktionen der .NET Framework\-XAML\-Dienste und der zugehörige, auf dem CLR\-Typsystem beruhende XAML\-Standardschemakontext beschrieben.  Außerdem wird in diesem Thema der für WPF verwendete XAML\-Schemakontext beschrieben.  
  
## XAML\-Standardschemakontext  
 .NET Framework\-XAML\-Dienste implementieren und verwenden einen XAML\-Standardschemakontext.  Das Verhalten des XAML\-Standardschemakontexts ist nicht immer vollständig in den APIs der <xref:System.Xaml.XamlSchemaContext>\-Klasse sichtbar.  In vielen Fällen ist das vom XAML\-Standardschemakontext beeinflusste Verhalten in gemeinsamen APIs des XAML\-Typsystems \(z. B. Member von <xref:System.Xaml.XamlMember> oder <xref:System.Xaml.XamlType>\) oder in den für XAML\-Reader und XAML\-Writer mit dem XAML\-Standardschemakontext verfügbar gemachten APIs sichtbar.  
  
 Sie können einen <xref:System.Xaml.XamlSchemaContext>, der das Standardverhalten kapselt, erstellen, indem Sie den <xref:System.Xaml.XamlSchemaContext>\-Konstruktor aufrufen.  Dadurch wird der XAML\-Standardschemakontext explizit erstellt.  Der gleiche XAML\-Standardschemakontext wird implizit erstellt, wenn Sie einen XAML\-Reader oder XAML\-Writer mit APIs initialisieren, die nicht explizit einen <xref:System.Xaml.XamlSchemaContext>\-Eingabeparameter akzeptieren.  
  
 Der XAML\-Standardschemakontext beruht auf der CLR\-Reflektion für dieses Typzuordnungsverhalten.  Dies beinhaltet die Untersuchung des definierenden CLR\-<xref:System.Type> und zugehöriger <xref:System.Reflection.PropertyInfo> oder <xref:System.Reflection.MethodInfo>.  Zudem wird die CLR\-Zuordnung für Typen oder Member verwendet, um die Details für XAML\-Typ\- oder XAML\-Memberinformationen anzugeben, die den CLR\-Unterstützungstyp verwenden.  Der XAML\-Standardschemakontext erfordert keine Techniken zur Typsystemerweiterung wie das `Invoker`\-Muster, da die erforderlichen Informationen im CLR\-Typsystem verfügbar sind.  
  
 Bei der Logik zum Laden von Assemblys beruht der XAML\-Standardschemakontext hauptsächlich auf den in XAML\-Namespacezuordnungen bereitgestellten Assemblywerten.  In bestimmten Szenarien, z. B. beim Laden interner Typen, kann auch <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> einen Hinweis auf eine zu ladende Assembly liefern.  
  
## WPF\-XAML\-Schemakontext  
 Der WPF\-XAML\-Schemakontext wird in diesem Thema beschrieben, da die WPF\-Implementierung eine interessante Erklärung der Funktionstypen liefert, die durch das Implementieren eines nicht standardmäßigen XAML\-Schemakontexts verwendet werden können.  Zudem wird das Konzept des XAML\-Schemakontexts in der WPF\-Dokumentation für WPF\-XAML nicht sehr ausführlich erörtert. Das durch den XAML\-Schemakontext aktivierte Verhalten ist möglicherweise nur im Zusammenhang mit einer Erläuterung der Funktionsweise des XAML\-Standardschemakontexts verständlich.  Der WPF\-XAML\-Schemakontext implementiert das im Folgenden beschriebene Verhalten.  
  
 **Suche nach Überschreibungen:** WPF verfügt über mehrere Inhaltsmodelle für XAML, in denen XAML\-Inhaltseigenschaften ohne <xref:System.Windows.Markup.ContentPropertyAttribute>\-Zuordnung funktionieren.  <xref:System.Xaml.XamlType.LookupContentProperty%2A>\-Überschreibungen für WPF implementieren dieses Verhalten.  
  
 **Verzögerung für WPF\-Ausdrücke:** WPF enthält mehrere Ausdrucksklassen, die einen Wert verzögern, bis ein Laufzeitkontext verfügbar ist.  Die Vorlagenerweiterung ist ebenfalls ein Laufzeitverhalten, das auf Verzögerungstechniken beruht.  
  
 **Optimierungen der Typsystemsuche:** WPF verfügt über ein umfangreiches XAML\-Vokabular und \-Objektmodell. Dazu zählen Basisklassenmember\-Definitionen, die buchstäblich von Hunderten von in WPF definierten Klassen geerbt werden.  Außerdem wird WPF selbst über mehrere Assemblys weitergegeben.  WPF optimiert die Typsuche mithilfe von Nachschlagetabellen und anderen Techniken.  Durch diese Optimierungen wird die Leistung im XAML\-Standardschemakontext und der zugehörigen CLR\-basierten Typsuche verbessert.  Wenn Typen nicht in einer Nachschlagetabelle vorhanden sind, werden XAML\-Schemakontexttechniken verwendet, die dem XAML\-Standardschemakontext ähneln.  
  
 **XamlType\- und XamlMember\-Erweiterung:** WPF erweitert Eigenschaftenkonzepte durch Abhängigkeitseigenschaften und Ereigniskonzepte durch Routingereignisse.  Zur Verbesserung der Sichtbarkeit dieser Konzepte bei XAML\-Verarbeitungsvorgängen werden in WPF <xref:System.Xaml.XamlType> und <xref:System.Xaml.XamlMember> erweitert und interne Eigenschaften hinzugefügt, die Merkmale von Abhängigkeitseigenschaften und Routingereignissen melden.  
  
### Zugriff auf den WPF\-XAML\-Schemakontext  
 Wenn Sie XAML\-Techniken verwenden, die auf dem <xref:System.Windows.Markup.XamlReader?displayProperty=fullName> oder <xref:System.Windows.Markup.XamlWriter?displayProperty=fullName> von WPF basieren, wird der WPF\-XAML\-Schemakontext bereits für diese XAML\-Reader\- und XAML\-Writerimplementierungen verwendet.  
  
 Wenn Sie andere XAML\-Reader\- oder XAML\-Writerimplementierungen verwenden, die nicht mit dem WPF\-XAML\-Schemakontext initialisiert werden, können Sie möglicherweise mit <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=fullName> einen funktionierenden WPF\-XAML\-Schemakontext abrufen.  Dieser Wert kann dann als Initialisierung für andere APIs mit einem <xref:System.Xaml.XamlSchemaContext> verwendet werden.  Sie können z. B. <xref:System.Xaml.XamlXmlReader.%23ctor%2A> zur Initialisierung aufrufen und den WPF\-XAML\-Schemakontext übergeben.  Sie können den WPF\-XAML\-Schemakontext auch für Vorgänge des XAML\-Typsystems verwenden.  Bei dieser Vorgehensweise müssen Sie möglicherweise eine <xref:System.Xaml.XamlType>\- oder <xref:System.Xaml.XamlMember>\-Initialisierung erstellen oder <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=fullName> aufrufen.  
  
 Wenn Sie über reine XAML\-Knotenstreamperspektiven auf bestimmte WPF\-XAML\-Aspekte zugreifen, kann es vorkommen, dass einige WPF\-Frameworkfunktionen noch nicht verarbeitet wurden.  WPF\-Vorlagen für Steuerelemente wurden z. B. noch nicht angewendet.  Wenn Sie auf eine Eigenschaft zugreifen, die zur Laufzeit mit einer vollständigen visuellen Struktur aufgefüllt werden kann, wird möglicherweise nur ein Eigenschaftswert angezeigt, der auf eine Vorlage verweist.  Zudem ist der Dienstkontext für WPF\-Markuperweiterungen möglicherweise nicht genau, wenn er nicht zur Laufzeit bereitgestellt wird. Dies kann beim Schreiben eines Objektdiagramms zu Ausnahmen führen.  
  
## XAML und Laden von Assemblys  
 Das Laden von Assemblys für XAML und .NET Framework\-XAML\-Dienste ist in das in CLR definierte <xref:System.AppDomain>\-Konzept integriert.  Ein XAML\-Schemakontext bestimmt basierend auf der Verwendung von <xref:System.AppDomain> und anderen Faktoren, wie zur Laufzeit oder Entwurfszeit Assemblys geladen werden oder nach Typen gesucht wird.  Abhängig davon, ob es sich um Loose XAML für einen XAML\-Reader, von `XamlBuildTask` in einer DLL kompiliertes XAML oder von `PresentationBuildTask` in WPF generiertes BAML handelt, unterscheidet sich die Logik geringfügig.  
  
 Der XAML\-Schemakontext für WPF ist in das WPF\-Anwendungsmodell integriert, das wiederum <xref:System.AppDomain> und andere Faktoren verwendet, bei denen es sich um WPF\-Implementierungsdetails handelt.  
  
#### XAML\-Readereingabe \(Loose XAML\)  
  
1.  Der XAML\-Schemakontext durchläuft die <xref:System.AppDomain> der Anwendung und sucht beginnend mit der zuletzt geladenen Assembly nach einer bereits geladenen Assembly, die allen Aspekten des Namens entspricht.  Wenn eine Übereinstimmung gefunden wird, wird diese Assembly zur Auflösung verwendet.  
  
2.  Andernfalls wird eine der folgenden Methoden auf Grundlage der CLR\-<xref:System.Reflection.Assembly>\-API verwendet, um eine Assembly zu laden:  
  
    -   Wenn der Name in der Zuordnung qualifiziert ist, rufen Sie <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> für den qualifizierten Namen auf.  
  
    -   Sollte der vorherige Schritt fehlschlagen, verwenden Sie den Kurznamen \(und sofern vorhanden das öffentliche Schlüsseltoken\), um <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> aufzurufen.  
  
    -   Wenn der Name in der Zuordnung nicht qualifiziert ist, rufen Sie <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName> auf.  
  
#### XamlBuildTask  
 `XamlBuildTask` wird für [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)] und [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] verwendet.  
  
 Beachten Sie, dass Assemblyverweise über `XamlBuildTask` immer vollqualifiziert sind.  
  
1.  Rufen Sie <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> für den qualifizierten Namen auf.  
  
2.  Sollte der vorherige Schritt fehlschlagen, verwenden Sie den Kurznamen \(und sofern vorhanden das öffentliche Schlüsseltoken\), um <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> aufzurufen.  
  
#### BAML \(PresentationBuildTask\)  
 Beim Laden von Assemblys für BAML sind zwei Aspekte zu beachten: das Laden der ursprünglichen Assembly, die das BAML als Komponente enthält, und das Laden der Typunterstützungsassemblys für alle Typen, auf die von der BAML\-Produktion verwiesen wird.  
  
##### Laden der Assembly für das ursprüngliche Markup:  
 Der Verweis auf die Assembly, aus der das Markup geladen werden soll, ist immer nicht qualifiziert.  
  
1.  Der WPF\-XAML\-Schemakontext durchläuft die <xref:System.AppDomain> der WPF\-Anwendung und sucht beginnend mit der zuletzt geladenen Assembly nach einer bereits geladenen Assembly, die allen Aspekten des Namens entspricht.  Wenn eine Übereinstimmung gefunden wird, wird diese Assembly zur Auflösung verwendet.  
  
2.  Sollte der vorherige Schritt fehlschlagen, verwenden Sie den Kurznamen \(und sofern vorhanden das öffentliche Schlüsseltoken\), um <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> aufzurufen.  
  
##### Assemblyverweise von BAML\-Typen:  
 Assemblyverweise für Typen, die in der BAML\-Produktion verwendet werden, sind immer vollqualifiziert \(als Ausgabe der Buildaufgabe\).  
  
1.  Der WPF\-XAML\-Schemakontext durchläuft die <xref:System.AppDomain> der WPF\-Anwendung und sucht beginnend mit der zuletzt geladenen Assembly nach einer bereits geladenen Assembly, die allen Aspekten des Namens entspricht.  Wenn eine Übereinstimmung gefunden wird, wird diese Assembly zur Auflösung verwendet.  
  
2.  Andernfalls wird eine der folgenden Techniken verwendet, um eine Assembly zu laden:  
  
    -   Rufen Sie <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> für den qualifizierten Namen auf.  
  
    -   Wenn eine Kombination von Kurzname und öffentlichem Schlüsseltoken mit der Assembly übereinstimmt, aus der das BAML geladen wurde, verwenden Sie diese Assembly.  
  
    -   Verwenden Sie den Kurznamen und das öffentliche Schlüsseltoken, um <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> aufzurufen.  
  
## Siehe auch  
 [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)