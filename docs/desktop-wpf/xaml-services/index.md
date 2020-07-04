---
title: XAML-Dienste
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: bfb3efb479668bcd70a3ce87b80253a73c18bb51
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "85840274"
---
# <a name="xaml-services"></a>XAML-Dienste

In diesem Thema werden die Funktionen einer Technologie beschrieben, die als .NET XAML-Dienste bezeichnet wird. Die Mehrzahl der beschriebenen Dienste und APIs befinden sich in der Assembly `System.Xaml`. Zu den Diensten zählen Reader und Writer, Schemaklassen und Schemaunterstützung, Factorys, die Attributierung von Klassen, systeminterne XAML-Sprachunterstützung und andere XAML-Sprachfeatures.

## <a name="about-this-documentation"></a>Informationen zu dieser Dokumentation

Die konzeptionelle Dokumentation für die .NET XAML-Dienste setzt voraus, dass Sie bereits Erfahrung mit der XAML-Sprache haben und wissen, wie sie auf ein bestimmtes Framework (z. B. Windows Presentation Foundation (WPF) oder Windows Workflow Foundation) oder auf einen bestimmten Technologiefeaturebereich (z. B. die Buildanpassungsfunktionen in <xref:Microsoft.Build.Framework.XamlTypes>) angewendet werden kann. Diese Dokumentation versucht nicht, die Grundlagen von XAML als Markupsprache, XAML-Syntaxterminologie oder anderes einführendes Material zu erläutern. Stattdessen konzentriert sich diese Dokumentation speziell auf die Verwendung von .NET XAML-Diensten, die in der Assemblybibliothek „System.Xaml“ aktiviert sind. Die meisten dieser APIs sind für Szenarien der XAML-Sprachintegration und -Erweiterbarkeit vorgesehen. Dies kann die folgenden Szenarien einschließen:

- Erweitern der Funktionen der XAML-Basisreader oder XAML-Writer (direkte Verarbeitung des XAML-Knotenstreams, Ableiten eines eigenen XAML-Readers oder XAML-Writers).

- Definieren von durch XAML verwendbaren benutzerdefinierten Typen, die keine spezifischen Frameworkabhängigkeiten aufweisen, und Zuweisen der Typen, um Ihre XAML-Typsystemmerkmale an .NET XAML-Dienste zu übermitteln.

- Hosting von XAML-Readern oder XAML-Writern als Komponente einer Anwendung, z. B. ein visueller Designer oder interaktiver Editor für XAML-Markupquellen.

- Schreiben von XAML-Wertkonvertern (Markuperweiterungen; Typkonverter für benutzerdefinierte Typen).

- Definieren eines benutzerdefinierten XAML-Schemakontexts (mithilfe alternativer Methoden zum Laden von Assemblys zum Unterstützen von Typquellen, Verwenden von Nachschlagetechniken bekannter Typen, anstatt Assemblys immer zu reflektieren, Verwenden geladener Assemblykonzepte, die nicht die Common Language Runtime (CLR) `AppDomain` und das zugehörige Sicherheitsmodell verwenden).

- Erweitern des XAML-Basistypsystems.

- Verwenden der `Lookup`- oder `Invoker`-Techniken, um das XAML-Typsystem und die Auswertung von Typunterstützungen zu beeinflussen.

Wenn Sie nach Einführungsmaterial zu XAML als Sprache suchen, finden Sie ggf. weitere Informationen unter [Übersicht über XAML (WPF)](../fundamentals/xaml.md). In diesem Thema wird XAML für eine Zielgruppe erläutert, für die sowohl Windows Presentation Foundation (WPF) als auch die Verwendung von XAML-Markup- und XAML-Sprachfeatures neu ist. Ein weiteres nützliches Dokument ist das Einführungsmaterial der [XAML-Sprachspezifikation](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="net-xaml-services-and-systemxaml-in-the-net-architecture"></a>.NET XAML-Dienste und `System.Xaml` in der .NET-Architektur

.NET XAML-Dienste und die `System.Xaml`-Assembly definieren einen Großteil der Funktionen, die für die Unterstützung von XAML-Sprachfeatures erforderlich sind. Dies schließt Basisklassen für XAML-Reader und XAML-Writer ein. Das wichtigste Feature, das .NET XAML-Diensten hinzugefügt wurde, das in keiner der frameworkspezifischen XAML-Implementierungen vorhanden war, ist eine Typsystemdarstellung für XAML. Die Typsystemdarstellung stellt XAML in einer objektorientierten Weise dar, die sich auf XAML-Funktionen konzentriert, ohne dass dabei Abhängigkeiten von bestimmten Funktionen von Frameworks übernommen werden.

Das XAML-Typsystem wird nicht durch die Markupform oder die Laufzeitbesonderheiten des XAML-Ursprungs beschränkt. Es ist auch nicht durch ein bestimmtes Unterstützungstypsystem eingeschränkt. Das XAML-Typsystem umfasst Objektdarstellungen für Typen, Member, XAML-Schemakontexte, Konzepte auf XML-Ebene und andere XAML-Sprachkonzepte oder XAML-Interna. Die Verwendung oder Erweiterung des XAML-Typsystems ermöglicht das Ableiten von Klassen wie XAML-Readern und XAML-Writern sowie das Erweitern der Funktionalität von XAML-Darstellungen in bestimmte Features, die von einem Framework, einer Technologie oder einer Anwendung aktiviert werden, die XAML nutzt oder ausgibt. Das Konzept eines XAML-Schemakontexts ermöglicht praktische Objektgraph-Schreibvorgänge aus der Kombination aus einer XAML-Objektwriterimplementierung, dem unterstützenden Typsystem einer Technologie, das über Assemblyinformationen im Kontext kommuniziert wird, und der XAML-Knotenquelle. Weitere Informationen zum XAML-Schemakonzept finden Sie unter [XAML-Standardschemakontext und WPF-XAML-Schemakontext](default-schema-context.md).

## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>XAML-Knotenstreams, XAML-Reader und XAML-Writer

Um die Rolle zu verstehen, die .NET XAML-Dienste in der Beziehung zwischen der XAML-Sprache und bestimmten Technologien spielen, die XAML als Sprache verwenden, ist es hilfreich, das Konzept eines XAML-Knotenstreams zu verstehen und zu erfahren, wie dieses Konzept die API und die Terminologie formt. Der XAML-Knotenstream ist eine konzeptionelle Zwischenstufe zwischen einer XAML-Sprachdarstellung und dem Objektgraphen, den XAML darstellt oder definiert.

- Ein XAML-Reader ist eine Entität, die XAML in irgendeiner Form verarbeitet und einen XAML-Knotenstream generiert. In der API wird ein XAML-Reader durch die Basisklasse <xref:System.Xaml.XamlReader> dargestellt.

- Ein XAML-Writer ist eine Entität, die einen XAML-Knotenstream verarbeitet und etwas anderes erzeugt. In der API wird ein XAML-Writer durch die Basisklasse <xref:System.Xaml.XamlWriter> dargestellt.

  Die beiden häufigsten XAML-Szenarien sind das Laden von XAML zum Instanziieren eines Objektgraphen und das Speichern eines Objektgraphen aus einer Anwendung oder einem Tool und das Generieren einer XAML-Darstellung (in der Regel in als Textdatei gespeicherter Markupform). Das Laden von XAML und das Erstellen eines Objektgraphen werden häufig in dieser Dokumentation als Ladepfad bezeichnet. Das Speichern oder Serialisieren eines vorhandenen Objektgraphen in XAML wird häufig in dieser Dokumentation als Speicherpfad bezeichnet.

  Der häufigste Typ von Ladepfad kann wie folgt beschrieben werden:

- Starten mit einer XAML-Darstellung im UTF-codierten XML-Format und Speichern als Textdatei.

- Laden dieses XAML in <xref:System.Xaml.XamlXmlReader>. <xref:System.Xaml.XamlXmlReader> ist eine <xref:System.Xaml.XamlReader>-Unterklasse.

- Das Ergebnis ist ein XAML-Knotenstream. Mithilfe der <xref:System.Xaml.XamlXmlReader> / <xref:System.Xaml.XamlReader>-API können Sie auf einzelne Knoten des XAML-Knotenstreams zugreifen. Der typische Vorgang besteht darin, den XAML-Knotenstream zu durchlaufen und jeden Knoten mit einer Metapher „aktueller Datensatz“ zu verarbeiten.

- Übergeben der resultierenden Knoten aus dem XAML-Knotenstream an eine <xref:System.Xaml.XamlObjectWriter>-API. <xref:System.Xaml.XamlObjectWriter> ist eine <xref:System.Xaml.XamlWriter>-Unterklasse.

- <xref:System.Xaml.XamlObjectWriter> schreibt einen Objektgraphen. Dabei werden die Objekte gemäß dem Fortschritt durch den XAML-Quellknotenstream nacheinander geschrieben. Das Schreiben von Objekten erfolgt mit Unterstützung eines XAML-Schemakontexts und einer Implementierung, die auf die Assemblys und Typen eines unterstützenden Typsystems und Frameworks zugreifen kann.

- Rufen Sie <xref:System.Xaml.XamlObjectWriter.Result%2A> am Ende des XAML-Knotenstreams auf, um das Stammobjekt des Objektgraphen abzurufen.

  Der häufigste Typ von Speicherpfad kann wie folgt beschrieben werden:

- Beginnen mit dem Objektgraphen einer vollständigen Anwendungslaufzeit, dem Benutzeroberflächeninhalt und dem Zustand einer Laufzeit oder mit einem kleineren Segment der Objektdarstellung einer vollständigen Anwendung zur Laufzeit.

- Laden der Objekte aus einem logischen Startobjekt (etwa einem Anwendungsstamm oder einem Dokumentstamm) in <xref:System.Xaml.XamlObjectReader>. <xref:System.Xaml.XamlObjectReader> ist eine <xref:System.Xaml.XamlReader>-Unterklasse.

- Das Ergebnis ist ein XAML-Knotenstream. Mithilfe von <xref:System.Xaml.XamlObjectReader> und der <xref:System.Xaml.XamlReader>-API können Sie auf einzelne Knoten des XAML-Knotenstreams zugreifen. Der typische Vorgang besteht darin, den XAML-Knotenstream zu durchlaufen und jeden Knoten mit einer Metapher „aktueller Datensatz“ zu verarbeiten.

- Übergeben der resultierenden Knoten aus dem XAML-Knotenstream an eine <xref:System.Xaml.XamlXmlWriter>-API. <xref:System.Xaml.XamlXmlWriter> ist eine <xref:System.Xaml.XamlWriter>-Unterklasse.

- <xref:System.Xaml.XamlXmlWriter> schreibt XAML in eine XML-UTF-Codierung. Sie können diese als Textdatei, als Stream oder in anderen Formaten speichern.

- Rufen Sie <xref:System.Xaml.XamlXmlWriter.Flush%2A> auf, um die endgültige Ausgabe abzurufen.

Weitere Informationen zu den Konzepten von XAML-Knotenstreams finden Sie unter [Grundlagen zu XAML-Knotenstreamstrukturen und -konzepten](understanding-xaml-node-stream-structures-and-concepts.md).

### <a name="the-xamlservices-class"></a>Die XamlServices-Klasse

Es ist nicht immer erforderlich, sich mit einem XAML-Knotenstrom zu befassen. Wenn Sie einen grundlegenden Ladepfad oder einen grundlegenden Speicherpfad verwenden möchten, können Sie APIs in der <xref:System.Xaml.XamlServices>-Klasse verwenden.

- Verschiedene Signaturen von <xref:System.Xaml.XamlServices.Load%2A> implementieren einen Ladepfad. Sie können eine Datei, einen Stream, einen <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> oder <xref:System.Xaml.XamlReader> laden, von der bzw. dem die XAML-Eingabe durch das Laden mit den APIs dieses Readers umschlossen wird.

- Verschiedene Signaturen von <xref:System.Xaml.XamlServices.Save%2A> speichern einen Objektgraphen und generieren eine Ausgabe als Stream, Datei oder <xref:System.Xml.XmlWriter>/<xref:System.IO.TextWriter>-Instanz.

- <xref:System.Xaml.XamlServices.Transform%2A> konvertiert XAML, indem ein Ladepfad und ein Speicherpfad als einzelner Vorgang verknüpft wird. Ein anderer Schemakontext oder ein anderes Unterstützungstypsystem kann für <xref:System.Xaml.XamlReader> und <xref:System.Xaml.XamlWriter> verwendet werden. Dies wirkt sich darauf aus, wie das sich ergebende XAML transformiert wird.

Weitere Informationen zur Verwendung von <xref:System.Xaml.XamlServices> finden Sie unter [XAMLServices-Klasse und grundlegende XAML-Lese- oder Schreibvorgänge](basic-reading-writing.md).

## <a name="xaml-type-system"></a>XAML-Typsystem

Das XAML-Typsystem stellt die APIs bereit, die erforderlich sind, um mit einem bestimmten einzelnen Knoten eines XAML-Knotenstreams zu arbeiten.

<xref:System.Xaml.XamlType> die Darstellung für ein Objekt: das, was Sie zwischen einem Startobjektknoten und einem Endobjektknoten verarbeiten.

<xref:System.Xaml.XamlMember> ist die Darstellung für einen Member eines Objekts: das, was Sie zwischen einem Startmemberknoten und einem Endmemberknoten verarbeiten.

APIs wie <xref:System.Xaml.XamlType.GetAllMembers%2A>, <xref:System.Xaml.XamlType.GetMember%2A> und <xref:System.Xaml.XamlMember.DeclaringType%2A> melden die Beziehungen zwischen einem <xref:System.Xaml.XamlType> und einem <xref:System.Xaml.XamlMember>.

Das Standardverhalten des von den .NET XAML-Diensten implementierten XAML-Typsystems basiert auf der CLR (Common Language Runtime) sowie einer statischen Analyse von CLR-Typen in Assemblys mithilfe von Reflexion. Daher kann die Standardimplementierung des XAML-Typsystems für einen bestimmten CLR-Typ das XAML-Schema dieses Typs und seine Member bereitstellen und in Bezug auf das XAML-Typsystem melden. Im XAML-Standardtypsystem wird das Konzept der Zuweisbarkeit von Typen anhand von CLR-Vererbung abgebildet, und die Konzepte von Instanzen, Werttypen usw. werden ebenfalls den unterstützenden Verhaltensweisen und Merkmalen der CLR zugeordnet.

## <a name="reference-for-xaml-language-features"></a>Referenz für Features der XAML-Sprache

Zur Unterstützung von XAML bieten .NET XAML-Dienste eine spezifische Implementierung der XAML-Sprachkonzepte, die für den XAML-Namespace der XAML-Sprache definiert wurden. Diese werden als spezifische Referenzseiten dokumentiert. Die Sprachfeatures werden aus der Perspektive der Funktionsweise dieser Sprachfeatures dokumentiert, wenn sie von einem XAML-Reader oder XAML-Writer verarbeitet werden, der von den .NET XAML-Diensten definiert wird. Weitere Informationen finden Sie unter [XAML Namespace (x:) Language Features (Sprachfunktionen des XAML-Namespace (x:))](namespace-language-features.md).
