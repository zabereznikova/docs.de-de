---
title: "XAML Services | Microsoft Docs"
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
  - "XAML [XAML Services], System.Xaml concepts"
  - "XAML Services in WPF [XAML Services]"
  - "System.Xaml [XAML Services], conceptual documentation"
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
caps.latest.revision: 13
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 13
---
# XAML Services
In diesem Thema werden die Funktionen der .NET Framework\-XAML\-Dienste beschrieben.  Der Großteil der beschriebenen Dienste und APIs ist in der System.Xaml\-Assembly enthalten, die im [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]\-Satz der .NET\-Kernassemblys eingeführt wurde.  Die Dienste beinhalten Reader und Writer, Schemaklassen und Schemaunterstützung, Factorys, das Festlegen von Attributen von Klassen, systeminterne Unterstützung der XAML\-Sprache und andere XAML\-Sprachfunktionen.  
  
## Info über diese Dokumentation  
 Die Begriffsdokumentation für .NET Framework\-XAML\-Dienste geht davon aus, dass Sie bereits über Erfahrung mit der XAML\-Sprache verfügen und wissen, wie sie auf ein bestimmtes Framework, z. B. [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] oder [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] oder einen bestimmten Technologiefunktionsbereich, z. B. die Buildanpassungsfunktionen in <xref:Microsoft.Build.Framework.XamlTypes>, angewendet werden könnte.  Diese Dokumentation versucht nicht, die Grundlagen von XAML als Markupsprache, die XAML\-Syntaxterminologie oder anderes einführendes Material zu erklären.  Vielmehr konzentriert sich diese Dokumentation auf die Verwendung der .NET Framework\-XAML\-Dienste, die in der System.Xaml\-Assemblybibliothek aktiviert sind.  Die meisten dieser APIs dienen für Szenarien im Zusammenhang mit der XAML\-Sprachintegration und \-Erweiterbarkeit.  Folgende Szenarien sind möglich:  
  
-   Erweitern der Funktionen der grundlegenden XAML\-Reader oder XAML\-Writer \(der XAML\-Knotenstream wird direkt verarbeitet, wobei ein personalisierter XAML\-Reader oder XAML\-Writer abgeleitet wird\)  
  
-   Definieren in XAML verwendbarer benutzerdefinierter Typen ohne bestimmte Frameworkabhängigkeiten und Zuordnen der Typen, um XAML\-Typsystemeigenschaften in .NET Framework\-XAML\-Dienste einzubinden  
  
-   Hosten von XAML\-Readern oder XAML\-Writern als Anwendungskomponente \(z. B. visuelle Designer oder interaktive Editoren für XAML\-Markupquellen\)  
  
-   Schreiben von XAML\-Wertkonvertern \(Markuperweiterungen, Typkonverter für benutzerdefinierte Typen\)  
  
-   Definieren eines benutzerdefinierten XAML\-Schemakontexts \(Verwenden alternativer Assemblyladetechniken für Unterstützungstypquellen, Verwenden einer Suchtechnik für bekannte Typen anstelle der Reflektion von Assemblys, Verwenden der Konzepte geladener Assemblys, die nicht die CLR\-`AppDomain` und das zugehörige Sicherheitsmodell verwenden\).  
  
-   Erweitern des grundlegenden XAML\-Typsystems  
  
-   Verwenden der `Lookup`\- oder `Invoker`\-Techniken zum Beeinflussen des XAML\-Typsystems und der Auswertung von Typunterstützungen  
  
 Einführende Informationen zu XAML als Sprache finden Sie unter [Übersicht über XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  In diesem Thema wird XAML für eine Zielgruppe erläutert, die noch keine Erfahrung mit [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] und der Verwendung von XAML\-Markup und XAML\-Sprachfunktionen hat.  Ein weiteres nützliches Dokument ist das einführende Material in der [XAML\-Sprachspezifikation](http://go.microsoft.com/fwlink/?LinkId=114525) \(möglicherweise in englischer Sprache\).  
  
## .NET Framework\-XAML\-Dienste und System.Xaml in der .NET\-Architektur  
 In früheren Versionen von [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)] wurde die Unterstützung für XAML\-Sprachfunktionen von Frameworks implementiert, die auf [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)] \([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] und [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)]\) basierten. Das Verhalten und die verwendete API richtete sich danach, welches Framework Sie eingesetzt haben.  Hierzu gehörten der XAML\-Parser und der Objektdiagramm\-Erstellungsmechanismus, systeminterne XAML\-Sprachelemente, Serialisierungsunterstützung usw.  
  
 In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] sind die wichtigsten Funktionen zur Unterstützung von XAML\-Sprachfunktionen in den .NET Framework\-XAML\-Diensten und der System.Xaml\-Assembly definiert.  Dies beinhaltet Basisklassen für XAML\-Reader und XAML\-Writer.  Die wichtigste Funktion, die den .NET Framework\-XAML\-Diensten hinzugefügt wurde und in keiner der frameworkspezifischen XAML\-Implementierungen vorhanden war, ist eine Typsystemdarstellung für XAML.  Die Typsystemdarstellung beschreibt XAML auf eine objektorientierte Weise. Diese gründet auf XAML\-Funktionen, wobei keine Abhängigkeiten von bestimmten Frameworkfunktionen forciert werden.  
  
 Das XAML\-Typsystem ist weder durch das Markupformat oder die spezifischen Laufzeitmerkmale des XAML\-Ursprungs noch durch ein bestimmtes Unterstützungstypsystem eingeschränkt.  Das XAML\-Typsystem beinhaltet Objektdarstellungen für Typen, Member, XAML\-Schemakontexte, Konzepte auf XML\-Ebene und andere XAML\-Sprachkonzepte oder systeminterne XAML\-Komponenten.  Die Verwendung oder Erweiterung des XAML\-Typsystems ermöglicht die Ableitung von Klassen wie XAML\-Readern und XAML\-Writern und erweitert die Funktionalität von XAML\-Darstellungen in bestimmten Funktionen, die durch ein Framework, eine Technologie oder eine Anwendung, die XAML verbraucht oder ausgibt, aktiviert werden.  Das Konzept eines XAML\-Schemakontexts ermöglicht praktische Objektdiagramm\-Schreibvorgänge durch die Kombination einer XAML\-Objektwriterimplementierung \(ein Unterstützungstypsystem einer Technologie, gemäß Kommunikation durch Assemblyinformationen im Kontext\) und der XAML\-Knotenquelle.  Weitere Informationen zum XAML\-Schemakonzept  finden Sie unter [Default XAML Schema Context and WPF XAML Schema Context](../../../docs/framework/xaml-services/default-xaml-schema-context-and-wpf-xaml-schema-context.md).  
  
## XAML\-Knotenstreams, XAML\-Reader und XAML\-Writer  
 Um die Rolle zu verstehen, die die .NET Framework\-XAML\-Dienste in der Beziehung zwischen der XAML\-Sprache und bestimmten Technologien spielt, die XAML als Sprache verwenden, ist es hilfreich, das Konzept eines XAML\-Knotenstreams sowie die API und Terminologie des Konzepts zu verstehen.  Der XAML\-Knotenstream liegt begrifflich zwischen einer XAML\-Sprachdarstellung und dem Objektdiagramm, das die XAML darstellt oder definiert.  
  
-   Ein XAML\-Reader ist eine Entität, die XAML in einer bestimmten Form verarbeitet und einen XAML\-Knotenstream erstellt.  In der API wird ein XAML\-Reader durch die <xref:System.Xaml.XamlReader>\-Basisklasse dargestellt.  
  
-   Ein XAML\-Writer ist eine Entität, die einen XAML\-Knotenstream verarbeitet und etwas anderes erzeugt.  In der API wird ein XAML\-Writer durch die <xref:System.Xaml.XamlWriter>\-Basisklasse dargestellt.  
  
 Die zwei gängigsten Szenarios, an denen XAML beteiligt ist, laden XAML, um ein Objektdiagramm zu instantiieren und speichern ein Objektdiagramm aus einer Anwendung oder einem Tool und erzeugen eine XAML\-Darstellung \(in der Regel in  einem als Textdatei gespeicherten Markupformat\).  Das Laden von XAML und das Erstellen eines Objektdiagramms wird in dieser Dokumentation oft als Ladepfad bezeichnet.  Das Speichern oder Serialisieren eines vorhandenen Objektdiagramms in XAML wird in dieser Dokumentation häufig als Speicherpfad bezeichnet.  
  
 Der allgemeinste Typ des Ladepfads kann wie folgt beschrieben werden:  
  
-   Beginnen Sie mit einer XAML\-Darstellung in UTF\-codiertem XML\-Format, die als Textdatei gespeichert ist.  
  
-   Laden Sie diese XAML in <xref:System.Xaml.XamlXmlReader>.  <xref:System.Xaml.XamlXmlReader> ist eine  <xref:System.Xaml.XamlReader>\-Unterklasse.  
  
-   Das Ergebnis ist ein XAML\-Knotenstream.  Sie können mit der <xref:System.Xaml.XamlXmlReader>\-\/ <xref:System.Xaml.XamlReader>\-API auf einzelne Knoten des XAML\-Knotenstreams zugreifen.  Der gängigste Vorgang besteht dabei darin, den XAML\-Knotenstream zu durchlaufen und jeden Knoten mithilfe einer "aktuellen Datensatz"\-Metapher zu verarbeiten.  
  
-   Übergeben Sie die daraufhin angezeigten Knoten aus dem XAML\-Knotenstream an eine <xref:System.Xaml.XamlObjectWriter>\-API.  <xref:System.Xaml.XamlObjectWriter> ist eine <xref:System.Xaml.XamlWriter>\-Unterklasse.  
  
-   Der <xref:System.Xaml.XamlObjectWriter> schreibt ein Objektdiagramm mit jeweils einem Objekt, um den XAML\-Quellknotenstream abzuarbeiten.  Dies erfolgt mit der Unterstützung eines XAML\-Schemakontexts und einer Implementierung, die auf die Assemblys und die Typen eines Unterstützungstypsystems und eines Frameworks zugreifen kann.  
  
-   Rufen Sie am Ende des XAML\-Knotenstreams <xref:System.Xaml.XamlObjectWriter.Result%2A> auf, um das Stammobjekt des Objektdiagramms abzurufen.  
  
 Der allgemeinste Typ des Speicherpfads kann wie folgt beschrieben werden:  
  
-   Beginnen Sie mit dem Objektdiagramm einer vollständigen Anwendungslaufzeit, dem Benutzeroberflächeninhalt und \-zustand einer Laufzeit oder einem kleineren Segment der Objektdarstellung einer Gesamtanwendung zur Laufzeit.  
  
-   Laden Sie die Objekte aus einem logischem Startobjekt \(z. B. einem Anwendungsstamm oder Dokumentstamm\) in <xref:System.Xaml.XamlObjectReader>.  <xref:System.Xaml.XamlObjectReader> ist eine <xref:System.Xaml.XamlReader>\-Unterklasse.  
  
-   Das Ergebnis ist ein XAML\-Knotenstream.  Sie können mit der <xref:System.Xaml.XamlObjectReader>\- und <xref:System.Xaml.XamlReader>\-API auf einzelne Knoten des XAML\-Knotenstreams zugreifen.  Der gängigste Vorgang besteht dabei darin, den XAML\-Knotenstream zu durchlaufen und jeden Knoten mithilfe einer "aktuellen Datensatz"\-Metapher zu verarbeiten.  
  
-   Übergeben Sie die daraufhin angezeigten Knoten aus dem XAML\-Knotenstream an eine <xref:System.Xaml.XamlXmlWriter>\-API.  <xref:System.Xaml.XamlXmlWriter> ist eine <xref:System.Xaml.XamlWriter>\-Unterklasse.  
  
-   Der <xref:System.Xaml.XamlXmlWriter> schreibt XAML in einer XML\-UTF\-Codierung.  Sie können diese Ausgabe als Textdatei, als Stream oder in anderen Formaten speichern.  
  
-   Rufen Sie <xref:System.Xaml.XamlXmlWriter.Flush%2A> auf, um die endgültige Ausgabe zu erhalten.  
  
 Weitere Informationen zu XAML\-Knotenstreamkonzepten finden Sie unter [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
### Die XamlServices\-Klasse  
 Es ist nicht immer erforderlich, einen XAML\-Knotenstream zu verwenden.  Wenn Sie einen grundlegenden Ladepfad oder Speicherpfad verwenden möchten, können Sie APIs in der <xref:System.Xaml.XamlServices>\-Klasse verwenden.  
  
-   Verschiedene Signaturen von <xref:System.Xaml.XamlServices.Load%2A> implementieren einen Ladepfad.  Sie können eine Datei oder einen Stream laden, oder Sie können einen <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> oder <xref:System.Xaml.XamlReader> laden, der die XAML\-Eingabe durch das Laden mit den APIs dieses Readers umschließt.  
  
-   Verschiedene Signaturen von <xref:System.Xaml.XamlServices.Save%2A> speichern ein Objektdiagramm und erzeugen Ausgabe als Stream, Datei oder <xref:System.Xml.XmlWriter>\-\/<xref:System.IO.TextWriter>\-Instanz.  
  
-   <xref:System.Xaml.XamlServices.Transform%2A> konvertiert XAML, indem sie einen Ladepfad und einen Speicherpfad als einzelnen Vorgang verknüpft.  Ein anderer Schemakontext oder ein anderes Unterstützungstypsystem könnte für <xref:System.Xaml.XamlReader> und <xref:System.Xaml.XamlWriter> verwendet werden. Dies wirkt sich darauf aus, wie die resultierende XAML transformiert wird.  
  
 Weitere Informationen zum Verwenden von <xref:System.Xaml.XamlServices> finden Sie unter [XAMLServices Class and Basic XAML Reading or Writing](../../../docs/framework/xaml-services/xamlservices-class-and-basic-xaml-reading-or-writing.md).  
  
## XAML\-Typsystem  
 Das XAML\-Typsystem stellt die erforderlichen APIs für die Arbeit mit einem bestimmten einzelnen Knoten eines XAML\-Knotenstreams bereit.  
  
 <xref:System.Xaml.XamlType> ist die Darstellung für ein Objekt \- also das, was Sie zwischen einem Startobjektknoten und einem Endobjektknoten verarbeiten.  
  
 <xref:System.Xaml.XamlMember> ist die Darstellung für ein Member eines Objekts \- also das, was Sie zwischen einem Startmemberknoten und einem Endmemberknoten verarbeiten.  
  
 APIs wie <xref:System.Xaml.XamlType.GetAllMembers%2A> und <xref:System.Xaml.XamlType.GetMember%2A> und <xref:System.Xaml.XamlMember.DeclaringType%2A> melden die Beziehungen zwischen einem <xref:System.Xaml.XamlType> und einem <xref:System.Xaml.XamlMember>.  
  
 Das Standardverhalten des von .NET Framework\-XAML\-Diensten implementierten XAML\-Typsystems basiert auf der Common Language Runtime \(CLR\) und der statischen Analyse von CLR\-Typen in Assemblys mittels Reflektion.  Daher kann die Standardimplementierung des XAML\-Typsystems für einen bestimmten CLR\-Typ das XAML\-Schema dieses Typs und seiner Member verfügbar machen und im Hinblick auf das XAML\-Typsystem dokumentieren.  Im XAML\-Standardtypsystem wird das Konzept von Zuweisungsfähigkeit von Typen der CLR\-Vererbung zugeordnet, und die Konzepte von Instanzen, Werttypen usw. werden ebenfalls dem unterstützenden Verhalten und den Funktionen der CLR zugeordnet.  
  
## Referenz für XAML\-Sprachfunktionen  
 .NET Framework\-XAML\-Dienste stellen zur Unterstützung von XAML bestimmte Implementierung von XAML\-Sprachkonzepten bereit, gemäß der Definition für den XAML\-Sprachnamespace.  Diese werden als bestimmte Referenzseiten dokumentiert.  Die Sprachfunktionen werden gemäß ihrem Verhalten bei der Verarbeitung durch einen in den .NET Framework\-XAML\-Diensten definierten XAML\-Reader oder XAML\-Writer dokumentiert.  Weitere Informationen finden Sie unter [XAML Namespace \(x:\) Language Features](../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md).