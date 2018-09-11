---
title: XAML-Dienste
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: 373478e8c21fca66cbfbf7a58fc7d53f65ce5d0b
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44339213"
---
# <a name="xaml-services"></a>XAML-Dienste
Dieses Thema beschreibt die Funktionen einer Technologie-Gruppe, die .NET Framework XAML Services genannt. Die meisten Dienste und APIs beschrieben befinden sich in der Assembly "System.xaml" enthalten, die eine Assembly wird eingeführt, mit der [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] Satz von .NET Core-Assemblys. Dienste umfassen, Reader und Writer, Schemaklassen und schemaunterstützung, Factorys, Attributieren von Klassen, systeminternen XAML-sprachunterstützung und andere Funktionen der XAML-Sprache.  
  
## <a name="about-this-documentation"></a>Informationen zu dieser Dokumentation  
 Dokumentation für .NET Framework-XAML-Dienste wird vorausgesetzt, dass Sie bereits Erfahrung mit der XAML-Sprache und wie es für ein bestimmtes Framework, z. B. gelten möglicherweise [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] oder Windows Workflow Foundation oder eine bestimmte Technologie-Funktion Bereich, z. B. die Buildanpassung-Funktionen in <xref:Microsoft.Build.Framework.XamlTypes>. In dieser Dokumentation versucht nicht, Erläutern Sie die Grundlagen von XAML als eine Markupsprache, Terminologie der XAML-Syntax oder andere einführendes Material. Stattdessen diese Dokumentation konzentriert sich auf die Verwendung der .NET Framework-XAML-Dienste, die aktiviert sind in der System.Xaml-Assembly-Bibliothek. Die meisten dieser APIs sind für Szenarien, die XAML-Sprache-Integration und Erweiterbarkeit. Dies kann Folgendes umfassen:  
  
-   Erweitern Sie die Funktionen von der grundlegenden XAML-Reader oder XAML-Writer (den XAML-Knotenstream direkt zu verarbeiten; ableiten, Ihre eigenen XAML-Reader oder XAML-Writer).  
  
-   Geben Sie XAML verwendet, werden benutzerdefinierte Typen, die keine bestimmte Framework-Abhängigkeiten definieren und diese Typen zum vermitteln ihrer XAML Systemmerkmalen für .NET Framework-XAML-Dienste.  
  
-   Hosten von XAML-Reader oder XAML-Writern als eine Komponente einer Anwendung, z. B. einem visuellen Designer oder einen interaktiven Editor für XAML-Markup-Datenquellen.  
  
-   Schreiben von XAML-Wertkonverter (Markuperweiterungen, Typkonverter für benutzerdefinierte Typen).  
  
-   Definieren einen benutzerdefinierten XAML-Schemakontext (Verwenden von alternativen Verfahren für das Laden von Assemblys zu unterstützenden Typ Quellen; Assemblys reflektieren; verwenden Sie die geladene Assembly-Konzepte, die die CLR nicht verwenden anstelle von bekannten Typen immer `AppDomain` und die zugeordneten Sicherheits-Modell).  
  
-   Erweitern Sie das grundlegende XAML-Typsystem.  
  
-   Mithilfe der `Lookup` oder `Invoker` Verfahren, um die XAML beeinflussen geben, System- und wie auf der Grundlage von Typ ausgewertet werden.  
  
 Wenn Sie einführende Informationen zu XAML als Sprache suchen, können Sie versuchen [XAML Overview (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md). Dieses Thema wird erläutert, XAML für ein Publikum die neuen für [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] und der Verwendung von XAML-Markup und XAML-Sprachfunktionen. Eine andere nützliches-Dokument ist die einleitenden Informationen in den [XAML-Sprachspezifikation](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>.NET Framework-XAML-Dienste und "System.xaml" enthalten, in der Architektur von .NET  
 In früheren Versionen von Microsoft .NET Framework, die Unterstützung für Funktionen der XAML-Sprache wurde implementiert, Frameworks, die auf Microsoft .NET Framework aufbauen ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Windows Workflow Foundation und Windows Communication Foundation (WCF)), und daher Je nach den spezifischen Framework Sie verwenden ihr Verhalten und der verwendeten API unterscheiden. Diese enthalten den XAML-Parser und der Objektdiagramm Erstellungsmechanismus, XAML-Sprache systeminternen Funktionen, Serialisierungsunterstützung und So weiter.  
  
 In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework-XAML-Dienste und der System.Xaml-Assembly zu definieren Großteil, was benötigt wird, für die Unterstützung von XAML-Sprachfunktionen. Dies umfasst die Basisklassen für XAML-Reader und XAML-Writer. Die wichtigste Funktion hinzugefügt, die auf .NET Framework XAML-Dienste, die nicht in den von der Framework-spezifischen XAML-Implementierungen ist eine System-Typ-Darstellung für XAML. Die Darstellung des Typs System stellt XAML auf objektorientierte Weise, die für XAML-Funktionen zu stehen, ohne Abhängigkeiten auf bestimmte Funktionen des Frameworks.  
  
 Das XAML-Typsystem ist durch die markupformular oder Laufzeit Besonderheiten der XAML-Ursprung nicht eingeschränkt. noch ist es von jedem bestimmten unterstützenden Typsystem beschränkt. Das XAML-Typsystem enthält objektdarstellungen für Typen, Member, XAML-Schema-Kontexten, auf XML-Ebene-Konzepte und anderen XAML-Sprachkonzepte oder XAML-systeminterne Funktionen. Verwenden oder Erweitern der XAML-Typsystem ermöglicht Klassen wie XAML-Readern und XAML-Writern abgeleitet, und erweitern die Funktionalität von XAML-Darstellungen in bestimmte Funktionen aktiviert, indem ein Framework, eine Technologie oder eine Anwendung, die verbraucht oder Gibt XAML. Das Konzept von einem XAML-Schemakontext ermöglicht praktische Objekt Graph Schreibvorgänge von der Kombination aus einer XAML-Objekt-Writer-Implementierung, einer Technologie Unterstützungstypsystem wie kommuniziert über Assemblyinformationen in den Kontext und den XAML-Knoten Quelle. Weitere Informationen auf dem Konzept des XAML-Schema. finden Sie unter [standardmäßig XAML-Schemakontext und WPF-XAML-Schemakontext](../../../docs/framework/xaml-services/default-xaml-schema-context-and-wpf-xaml-schema-context.md).  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>XAML-Knotenstreams, XAML-Readern und XAML-Writern  
 Um die Rolle zu verstehen, die .NET Framework-XAML-Dienste in der Beziehung zwischen den XAML-Sprache und bestimmte Technologien, mit denen XAML als Sprache spielt, es ist hilfreich zum besseren Verständnis des Konzepts von einem XAML-Knotenstream und wie dieses Konzept auf die API Formen und -Terminologie verwenden. Der XAML-Knotenstream ist eine konzeptionelle fortgeschrittene zwischen eine Darstellung der XAML-Sprache und das Objektdiagramm, das die XAML definiert oder darstellt.  
  
-   Ein XAML-Reader ist eine Entität, die XAML in irgendeiner Form verarbeitet und erzeugt einen XAML-Knotenstream. In der API ein XAML-Reader wird von der Basisklasse dargestellt <xref:System.Xaml.XamlReader>.  
  
-   Ein XAML-Writer ist eine Entität, die einen XAML-Knotenstream verarbeitet und etwas anderes erzeugt. In der API ein XAML-Writer wird von der Basisklasse dargestellt <xref:System.Xaml.XamlWriter>.  
  
 Die beiden häufigsten Szenarien im Zusammenhang mit XAML sind Laden von XAML zum Instanziieren eines Objektdiagramms und ein Objektdiagramm aus einer Anwendung oder einem Tool speichern und erstellen eine XAML-Darstellung (in der Regel im Markup-Form, die als Textdatei gespeichert). Laden von XAML, und erstellen ein Objektdiagramm wird häufig in dieser Dokumentation als dem Ladepfad bezeichnet. Speichern oder ein vorhandenes Objektdiagramm in XAML zu serialisieren ist bezeichnet in dieser Dokumentation als speichern Pfad.  
  
 Die am häufigsten verwendete Typ der Ladepfad kann wie folgt beschrieben werden:  
  
-   Beginnen Sie mit einer XAML-Darstellung in UTF-codierter XML-Format und als Textdatei gespeichert.  
  
-   Laden Sie dieses XAML in <xref:System.Xaml.XamlXmlReader>. <xref:System.Xaml.XamlXmlReader> ist eine <xref:System.Xaml.XamlReader> Unterklasse.  
  
-   Das Ergebnis ist ein XAML-Knotenstream. Sie können einzelne Knoten von der Stream mit XAML Knoten zugreifen <xref:System.Xaml.XamlXmlReader>  /  <xref:System.Xaml.XamlReader> API. Hier der typische Vorgang ist, fahren Sie fort, über die XAML-Knotenstream verarbeiten von einzelnen Knoten mit "aktuellen Datensatz" Metapher.  
  
-   Übergeben Sie die daraus resultierenden Knoten werden aus der XAML-Knotenstream auf einem <xref:System.Xaml.XamlObjectWriter> API. <xref:System.Xaml.XamlObjectWriter> ist eine <xref:System.Xaml.XamlWriter> Unterklasse.  
  
-   Die <xref:System.Xaml.XamlObjectWriter> schreibt ein Objektdiagramm, die ein Objekt zu einem Zeitpunkt in Übereinstimmung mit dem Status der Quelle XAML-Knotenstream. Dies erfolgt mit der Hilfe von einem XAML-Schemakontext und eine Implementierung, die die Assemblys und Typen von einem System von Unterstützungstypen und Framework zugreifen kann.  
  
-   Rufen Sie <xref:System.Xaml.XamlObjectWriter.Result%2A> am Ende der XAML-Knotenstream auf das Stammobjekt des Objektdiagramms abzurufen.  
  
 Die am häufigsten verwendete Typ der Speicherpfad kann wie folgt beschrieben werden:  
  
-   Beginnen Sie mit der ein Objektdiagramm aus eine Zeit für die gesamte Anwendung ausführen, die Inhalte der Benutzeroberfläche und Status einer Laufzeit oder ein kleiner Teil einer gesamtanwendung objektdarstellung zur Laufzeit.  
  
-   Laden Sie von einem logischen Start-Objekt, z. B. ein Stammverzeichnis der Anwendung oder den Dokumentstamm der Objekte in <xref:System.Xaml.XamlObjectReader>. <xref:System.Xaml.XamlObjectReader> ist eine <xref:System.Xaml.XamlReader> Unterklasse.  
  
-   Das Ergebnis ist ein XAML-Knotenstream. Sie können einzelne Knoten von der Stream mit XAML Knoten zugreifen <xref:System.Xaml.XamlObjectReader> und <xref:System.Xaml.XamlReader> API. Hier der typische Vorgang ist, fahren Sie fort, über die XAML-Knotenstream verarbeiten von einzelnen Knoten mit "aktuellen Datensatz" Metapher.  
  
-   Übergeben Sie die daraus resultierenden Knoten werden aus der XAML-Knotenstream auf einem <xref:System.Xaml.XamlXmlWriter> API. <xref:System.Xaml.XamlXmlWriter> ist eine <xref:System.Xaml.XamlWriter> Unterklasse.  
  
-   Die <xref:System.Xaml.XamlXmlWriter> schreibt XAML in einer XML-UTF-Codierung. Sie können dies als Textdatei als Stream oder in anderer Form speichern.  
  
-   Rufen Sie <xref:System.Xaml.XamlXmlWriter.Flush%2A> um die endgültige Ausgabe zu erhalten.  
  
 Weitere Informationen zu XAML-Knotenstreamkonzepte, finden Sie unter [Understanding XAML Node Stream Structures und Konzepte](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
### <a name="the-xamlservices-class"></a>XamlServices-Klasse  
 Es ist nicht immer erforderlich, für den Umgang mit einem XAML-Knotenstream. Wenn Sie einen grundlegenden Ladepfad oder Speicherpfad möchten, können Sie APIs in der <xref:System.Xaml.XamlServices> Klasse.  
  
-   Verschiedene Signaturen von <xref:System.Xaml.XamlServices.Load%2A> implementieren einen Ladepfad. Sie können entweder eine Datei oder den Stream laden oder laden kann ein <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> oder <xref:System.Xaml.XamlReader> umschließen, die Ihre XAML-Eingabe, durch das Laden mit den Reader APIs.  
  
-   Verschiedene Signaturen von <xref:System.Xaml.XamlServices.Save%2A> speichern ein Objektdiagramm aus, und erstellen die Ausgabe als Stream, Datei oder <xref:System.Xml.XmlWriter> / <xref:System.IO.TextWriter> Instanz.  
  
-   <xref:System.Xaml.XamlServices.Transform%2A> Konvertiert einen Ladepfad und einen XAML-Pfad als einen einzelnen Vorgang. Ein anderer Schemakontext oder ein anderes Unterstützungstypsystem kann für verwendet werden <xref:System.Xaml.XamlReader> und <xref:System.Xaml.XamlWriter>, d.h. welche beeinflusst, wie die resultierende XAML transformiert wird.  
  
 Weitere Informationen zur Verwendung von <xref:System.Xaml.XamlServices>, finden Sie unter [XAMLServices-Klasse und grundlegende XAML-Lesen oder Schreiben von](../../../docs/framework/xaml-services/xamlservices-class-and-basic-xaml-reading-or-writing.md).  
  
## <a name="xaml-type-system"></a>XAML-Typsystem  
 Das XAML-Typsystem bietet APIs, die für die Arbeit mit einem bestimmten einzelnen Knoten eines XAML-Knotenstreams erforderlich sind.  
  
 <xref:System.Xaml.XamlType> ist die Darstellung für ein Objekt – was Sie zwischen einem Startobjektknoten und Endobjektknoten verarbeiten.  
  
 <xref:System.Xaml.XamlMember> ist die Darstellung für einen Member eines Objekts – was Sie zwischen einem Startmemberknoten und Endmemberknoten verarbeiten.  
  
 APIs wie z. B. <xref:System.Xaml.XamlType.GetAllMembers%2A> und <xref:System.Xaml.XamlType.GetMember%2A> und <xref:System.Xaml.XamlMember.DeclaringType%2A> melden die Beziehungen zwischen einem <xref:System.Xaml.XamlType> und <xref:System.Xaml.XamlMember>.  
  
 Das Standardverhalten des XAML-Typsystem von .NET Framework-XAML-Dienste implementiert basiert auf der common Language Runtime (CLR), und statische Analyse von CLR-Typen in Assemblys mit Reflektion. Für einen bestimmten CLR-Typ, die standardmäßige Implementierung des XAML-Typsystems daher verfügbar machen das XAML-Schema des Typs und ihre Member und melden Sie es in Bezug auf die XAML-Typsystem. In der Standard-XAML-Typsystem das Konzept der zuweisungsfähigkeit von Typen, die auf CLR-Vererbung zugeordnet ist, und die Konzepte von Instanzen, Werttypen und usw. werden auch auf die unterstützende CLR-Funktionen und Verhaltensweisen zugeordnet.  
  
## <a name="reference-for-xaml-language-features"></a>Referenz für die XAML-Sprachfunktionen  
 Zur Unterstützung von XAML bietet .NET Framework-XAML-Dienste die konkrete Implementierung der XAML-Sprachkonzepte wie für die XAML-Namespace der XAML-Sprache definiert. Diese sind als bestimmte Referenzseiten dokumentiert. Die Sprachfunktionen sind dokumentiert, aus der Perspektive des diese Sprachfeatures wie Verhalten, bei der Verarbeitung von einem XAML-Reader oder XAML-Writer, die von .NET Framework-XAML-Dienste definiert ist. Weitere Informationen finden Sie unter [XAML Namespace (x:) Language Features](../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md).
