---
title: XAML-Dienste
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: b8d1214e011e4a6569b5612d7be93ed05b776166
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-services"></a>XAML-Dienste
Dieses Thema beschreibt die Funktionen einer Technologie Menge als .NET Framework-XAML-Dienste bezeichnet. Die meisten Dienste und der beschriebenen APIs befinden sich in der Assembly "System.xaml", also eine Assembly eingeführt wird, mit der [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] Satz von .NET Core-Assemblys. Dienste umfassen, Reader und Writer, Schemaklassen und schemaunterstützung, Factorys, Attributierung von Klassen, systeminterne Unterstützung von XAML-Sprache und anderen Features der XAML-Sprache.  
  
## <a name="about-this-documentation"></a>Informationen zu dieser Dokumentation  
 Konzeptionelle Dokumentation für .NET Framework XAML Services wird vorausgesetzt, dass Sie bereits Erfahrung mit XAML-Sprache und wie es für ein bestimmtes Framework, z. B. möglicherweise gelten [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] oder [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)], oder eine bestimmte Technologie Bereich für Funktion Beispiel für die Buildanpassung-in Funktionen <xref:Microsoft.Build.Framework.XamlTypes>. In dieser Dokumentation versucht nicht, die Grundlagen von XAML als Markup Language, XAML-Syntax Terminologie oder andere einführendes Material zu erläutern. Stattdessen konzentriert sich dieser Dokumentation auf die Verwendung der .NET Framework-XAML-Dienste, die aktiviert sind in der System.Xaml-Assembly-Bibliothek. Die meisten dieser APIs sind für Szenarien mit der Verwendung von XAML-Sprache-Integration und Erweiterbarkeit. Dies kann Folgendes umfassen:  
  
-   Erweitern Sie die Funktionen der grundlegenden XAML-Reader oder XAML-Writer (verarbeiten direkt im XAML-Knotenstream; ableiten eigene XAML-Reader oder XAML-Writer).  
  
-   XAML verwendet werden kann, benutzerdefinierte Typen, die keine Abhängigkeiten von bestimmten Frameworks definieren und diese Typen zum Übermitteln ihrer XAML Geben Sie den Systemmerkmalen auf .NET Framework XAML-Dienste.  
  
-   Hosten von XAML-Reader und XAML-Writern als Komponente von einer Anwendung, z. B. einen visuellen Designer oder interaktive-Editor für XAML-Markupquellen.  
  
-   Schreiben von XAML-Wertkonvertern (Markuperweiterungen, Typkonverter für benutzerdefinierte Typen).  
  
-   Definieren einen benutzerdefinierten XAML-Schemakontext (verwenden Alternative Techniken für das Laden von Assemblys zu unterstützenden Typ Quellen; "reflektieren Assemblys; geladene Assembly Konzepte, die die CLR nicht verwenden" bekannte Typen Suche Techniken verwenden, statt immer `AppDomain` und die zugeordneten Sicherheits-Modell).  
  
-   Erweitern Sie die grundlegende XAML-Typsystem.  
  
-   Mithilfe der `Lookup` oder `Invoker` Techniken, mit denen Sie beeinflussen, den XAML-Code Geben Sie System- und wie auf der Grundlage von Typ ausgewertet werden.  
  
 Wenn Sie einführende Informationen zu XAML als Sprache suchen, Sie könnten versuchen [XAML Overview (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md). Dieses Thema erläutert XAML für eine Zielgruppe die neuen sowohl auf [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] und auch für die Verwendung von XAML-Markup und XAML-Sprachfeatures. Eine andere nützliches Dokument ist die einleitenden Informationen in den [XAML-Sprachspezifikation](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>.NET Framework-XAML-Dienste und "System.xaml" in der .NET-Architektur  
 In früheren Versionen von [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)], Unterstützung für die Verwendung von XAML-Sprachfunktionen von Frameworks, die auf implementiert wurde [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)] ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] und [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)]), und daher variiert in ihr Verhalten und je nachdem, welche verwendete API bestimmten Frameworks, die Sie verwendet haben. Diese enthalten die XAML-Parser und der Objektdiagramm Erstellungsmechanismus, systeminterne XAML-Sprachelemente, Serialisierungsunterstützung und So weiter.  
  
 In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework-XAML-Dienste und der System.Xaml-Assembly definieren Großteil zur Unterstützung von XAML-Sprachfeatures benötigt wird. Dies schließt die Basisklassen für XAML-Readern und XAML-Writern. Die wichtigste Funktion hinzugefügt, die nicht in keiner der Framework-spezifischen XAML-Implementierungen war .NET Framework XAML Services ist eine Darstellung für die Verwendung von XAML-System. Die Typ-Darstellung System stellt XAML auf objektorientierte Weise, die Funktionen der XAML-Rechenzentren ohne Abhängigkeiten auf bestimmte Funktionen des Frameworks.  
  
 Das XAML-Typsystem ist nicht die markupformular oder zur Laufzeit Besonderheiten der Verwendung von XAML-Ursprungs beschränkt; auch durch eine bestimmte Unterstützungstypsystem beschränkt. Das XAML-Typsystem umfasst Objekt Darstellungen für Typen, Member, XAML-Schema-Kontexten, XML-Level-Konzepte und andere XAML-Sprachkonzepte oder XAML-systeminterne Funktionen. Verwenden oder Erweitern von XAML-Typsystem ermöglicht von Klassen wie XAML-Readern und XAML-Writern ableiten und erweitern die Funktionen der XAML-Darstellungen in bestimmte Funktionen aktiviert, indem ein Framework, eine Technologie oder eine Anwendung, die verbraucht oder Gibt aus XAML. Das Konzept von einem XAML-Schemakontext ermöglicht praktische Objekt Graph Schreibvorgänge aus der Kombination einer XAML-Objekt-Writer-Implementierung, eine Technologie Unterstützungstypsystem wie durch die Assemblyinformationen in den Kontext und den XAML-Knoten kommuniziert Quelle. Weitere Informationen über das Konzept des XAML-Schema. finden Sie unter [Standard XAML-Schemakontext und WPF-XAML-Schemakontext](../../../docs/framework/xaml-services/default-xaml-schema-context-and-wpf-xaml-schema-context.md).  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>Verwendung von XAML-Knotenstreams, XAML-Readern und XAML-Writern  
 Um die Rolle zu verstehen, die .NET Framework XAML Services spielt in der Beziehung zwischen dem XAML-Sprache und spezieller Technologien, die XAML als Sprache verwenden, ist es hilfreich zu verstehen das Konzept von einem XAML-Knotenstream und wie dieses Konzept die API shapes und Terminologie. XAML-Knotenstream ist eine grundlegende Zwischendateien zwischen einem XAML-sprachdarstellung und das Objektdiagramm, das der XAML-Code darstellt, oder definiert.  
  
-   Ein XAML-Reader ist eine Entität, die XAML in irgendeiner Form verarbeitet und erzeugt einen XAML-Knotenstream. In der API wird ein XAML-Reader von der Basisklasse dargestellt <xref:System.Xaml.XamlReader>.  
  
-   Ein XAML-Writer ist eine Entität, die einen XAML-Knotenstream verarbeitet und etwas anderes erzeugt. In der API-ein XAML-Writer wird dargestellt, von der Basisklasse <xref:System.Xaml.XamlWriter>.  
  
 Die beiden häufigsten Szenarien im Zusammenhang mit XAML sind Laden von XAML zum Instanziieren eines Objektdiagramms und ein Objektdiagramm aus einer Anwendung oder einem Tool speichern und erzeugt eine XAML-Darstellung (in der Regel in markupformular als Textdatei gespeichert). Laden von XAML und das Erstellen eines Objektdiagramms wird häufig in dieser Dokumentation als Ladepfad bezeichnet. Speichern oder Serialisieren eines vorhandenen Objektdiagramms in XAML wird häufig bezeichnet in dieser Dokumentation als speichern Pfad.  
  
 Die am häufigsten verwendete Typ der Ladepfad kann wie folgt beschrieben werden:  
  
-   Beginnen Sie mit einer XAML-Darstellung in UTF-codierte XML-Format und als Textdatei gespeichert.  
  
-   Laden Sie diese XAML in <xref:System.Xaml.XamlXmlReader>. <xref:System.Xaml.XamlXmlReader>ist eine <xref:System.Xaml.XamlReader> Unterklasse.  
  
-   Das Ergebnis ist ein XAML-Knotenstream. Sie können einzelne Knoten der XAML-Knoten Datenstrom mit zugreifen <xref:System.Xaml.XamlXmlReader>  /  <xref:System.Xaml.XamlReader> API. Hier die am häufigsten verwendete Vorgang ist zum Fortsetzen der Verarbeitung der XAML-Knotenstream wird die Verarbeitung der einzelnen Knoten mit "aktuellen Datensatz" Metapher.  
  
-   Übergeben Sie die daraus resultierenden Knoten aus dem XAML-Knotenstream auf einem <xref:System.Xaml.XamlObjectWriter> API. <xref:System.Xaml.XamlObjectWriter>ist eine <xref:System.Xaml.XamlWriter> Unterklasse.  
  
-   Die <xref:System.Xaml.XamlObjectWriter> Objektdiagramm, ein Objekt zu einem Zeitpunkt unter Verwendung von Gerätepixeln Fortschritt über die Quelle von XAML-Knotenstream schreibt. Dies erfolgt mit der Unterstützung von einem XAML-Schemakontext und eine Implementierung, die die Assemblys und Typen von einem Unterstützungstypsystem und Framework zugreifen kann.  
  
-   Rufen Sie <xref:System.Xaml.XamlObjectWriter.Result%2A> am Ende des XAML-Knotenstream zum Abrufen des Stammobjekts des Objektdiagramm enthalten sind.  
  
 Die am häufigsten verwendete Typ der Speicherpfad kann wie folgt beschrieben werden:  
  
-   Beginnen Sie mit dem Objektdiagramm eine Zeit für die gesamte Anwendung ausführen, UI-Inhalt und Status einer Laufzeit oder ein kleiner Teil objektdarstellung zur Laufzeit eine allgemeine Anwendung.  
  
-   Aus einem logischen Startobjekt, z. B. ein Anwendungsstamm oder Dokumentstamm, laden Sie die Objekte in <xref:System.Xaml.XamlObjectReader>. <xref:System.Xaml.XamlObjectReader>ist eine <xref:System.Xaml.XamlReader> Unterklasse.  
  
-   Das Ergebnis ist ein XAML-Knotenstream. Sie können einzelne Knoten der XAML-Knoten Datenstrom mit zugreifen <xref:System.Xaml.XamlObjectReader> und <xref:System.Xaml.XamlReader> API. Hier die am häufigsten verwendete Vorgang ist zum Fortsetzen der Verarbeitung der XAML-Knotenstream wird die Verarbeitung der einzelnen Knoten mit "aktuellen Datensatz" Metapher.  
  
-   Übergeben Sie die daraus resultierenden Knoten aus dem XAML-Knotenstream auf einem <xref:System.Xaml.XamlXmlWriter> API. <xref:System.Xaml.XamlXmlWriter>ist eine <xref:System.Xaml.XamlWriter> Unterklasse.  
  
-   Die <xref:System.Xaml.XamlXmlWriter> schreibt XAML in einer XML-UTF-Codierung. Sie können dies als eine Textdatei, die als Datenstrom oder in anderen Formen speichern.  
  
-   Rufen Sie <xref:System.Xaml.XamlXmlWriter.Flush%2A> auf die endgültige Ausgabe zu erhalten.  
  
 Weitere Informationen zur Verwendung von XAML-Knotenstreamkonzepte finden Sie unter [Grundlegendes zur Verwendung von XAML-Knotenstreamstrukturen und Konzepte](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
### <a name="the-xamlservices-class"></a>XamlServices-Klasse  
 Es ist nicht immer erforderlich, um einen XAML-Knotenstream zu verarbeiten. Wenn Sie einen grundlegenden Ladepfad oder ein grundlegender Speicherpfad möchten, können Sie APIs in der <xref:System.Xaml.XamlServices> Klasse.  
  
-   Verschiedene Signaturen von <xref:System.Xaml.XamlServices.Load%2A> implementieren einen Ladepfad. Sie können entweder eine Datei oder einen Stream laden, oder laden können eine <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> oder <xref:System.Xaml.XamlReader> Ihre XAML-Eingabe durch das Laden mit den Reader APIs umschlossen.  
  
-   Verschiedene Signaturen von <xref:System.Xaml.XamlServices.Save%2A> Objektdiagramm speichern und erstellen die Ausgabe als Stream, Datei oder <xref:System.Xml.XmlWriter> / <xref:System.IO.TextWriter> Instanz.  
  
-   <xref:System.Xaml.XamlServices.Transform%2A>konvertiert XAML, indem Sie einen Ladepfad und einen Speicherpfad als einzelnen Vorgang. Ein anderer Schemakontext oder ein anderes Unterstützungstypsystem kann für verwendet werden <xref:System.Xaml.XamlReader> und <xref:System.Xaml.XamlWriter>, also in was beeinflusst, wie das resultierende XAML transformiert wird.  
  
 Weitere Informationen zur Verwendung von <xref:System.Xaml.XamlServices>, finden Sie unter [XamlServices-Klasse und grundlegende XAML Lesen oder Schreiben von](../../../docs/framework/xaml-services/xamlservices-class-and-basic-xaml-reading-or-writing.md).  
  
## <a name="xaml-type-system"></a>XAML-Typsystem  
 Das XAML-Typsystem stellt die APIs, die erforderlich sind, um einen bestimmten einzelnen Knoten eines XAML-Knotenstreams zu arbeiten.  
  
 <xref:System.Xaml.XamlType>ist die Darstellung für ein Objekt – was Sie zwischen einem Startobjektknoten und End-Objektknoten verarbeiten.  
  
 <xref:System.Xaml.XamlMember>ist die Darstellung für ein Element eines Objektes – was Sie zwischen einem Memberknotens Start und Ende Memberknotens verarbeiten.  
  
 APIs, wie z. B. <xref:System.Xaml.XamlType.GetAllMembers%2A> und <xref:System.Xaml.XamlType.GetMember%2A> und <xref:System.Xaml.XamlMember.DeclaringType%2A> melden die Beziehungen zwischen einem <xref:System.Xaml.XamlType> und <xref:System.Xaml.XamlMember>.  
  
 Das Standardverhalten für das .NET Framework-XAML-Diensten implementierten XAML-Typsystem basiert auf der common Language Runtime (CLR) und die statische Analyse von CLR-Typen in Assemblys mit Reflektion. Für einen bestimmten CLR-Typ, die standardmäßige Implementierung des XAML-Typsystem deshalb verfügbar machen die Verwendung von XAML-Schema des Typs und ihre Member und im Hinblick auf die Verwendung von XAML-Typsystem zu melden. In der Standardeinstellung XAML-Typsystem das Konzept der zuweisungsfähigkeit Typen auf CLR-Vererbung zugeordnet ist und die Konzepte von Instanzen, Werttypen und So weiter auch auf die unterstützenden Verhalten und CLR-Funktionen zugeordnet werden.  
  
## <a name="reference-for-xaml-language-features"></a>Referenz für die Verwendung von XAML-Sprachfunktionen  
 Zur Unterstützung von XAML bietet .NET Framework XAML Services spezifische Implementierung der XAML-Sprachkonzepte für XAML-Namespace der XAML-Sprache definiert. Diese sind als bestimmte Referenzseiten dokumentiert. Die Sprachfunktionen sind dokumentiert, aus der Perspektive eines Verhalten diese Sprachfunktionen, bei der Verarbeitung durch einen XAML-Reader oder XAML-Writer, die von .NET Framework XAML Services definiert ist. Weitere Informationen finden Sie unter [XAML Namespace (x:) Language Features](../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md).
