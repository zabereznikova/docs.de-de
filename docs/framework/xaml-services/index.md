---
title: XAML-Dienste
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: 8e1e8dc9a1410d05c19e4dd1bccb30c65d7c5e66
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837284"
---
# <a name="xaml-services"></a>XAML-Dienste
In diesem Thema werden die Funktionen eines Technologie Satzes beschrieben, der als .NET Framework XAML-Dienste bezeichnet wird. Die Mehrzahl der beschriebenen Dienste und APIs befinden sich in der Assembly System. XAML, bei der es sich um eine Assembly handelt, die mit dem .NET Framework 4-Satz von .net Core-Assemblys eingeführt wurde. Zu den Diensten zählen Reader und Writer, Schema Klassen und Schema Unterstützung, Factorys, die Attributierung von Klassen, systeminterne XAML-Sprachunterstützung und andere XAML-sprach Features.  
  
## <a name="about-this-documentation"></a>Informationen zu dieser Dokumentation  
 Bei der konzeptionellen Dokumentation für .NET Framework XAML-Dienste wird vorausgesetzt, dass Sie bereits mit der XAML-Sprache vertraut sind und wie Sie auf ein bestimmtes Framework (z. b. [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] oder Windows Workflow Foundation) oder einen bestimmten Technologie Funktionsbereich angewendet werden kann, z. b. die buildanpassungsfeatures in <xref:Microsoft.Build.Framework.XamlTypes>. In dieser Dokumentation wird nicht versucht, die Grundlagen von XAML als Markup Sprache, XAML-Syntax Terminologie oder anderes Einführ Endes Material zu erläutern. Stattdessen konzentriert sich diese Dokumentation speziell auf die Verwendung der .NET Framework XAML-Dienste, die in der Assembly "System. XAML" aktiviert sind. Die meisten dieser APIs sind für Szenarien der XAML-Sprachintegration und-Erweiterbarkeit vorgesehen. Dies kann Folgendes umfassen:  
  
- Erweitern der Funktionen der Basis-XAML-Reader oder XAML-Writer (die direkte Verarbeitung des XAML-knotenstreams; Ableiten eines eigenen XAML-Readers oder XAML-Writers).  
  
- Definieren von XAML-verwendbaren benutzerdefinierten Typen, die keine spezifischen frameworkabhängigkeiten aufweisen, und Zuweisen der Typen, um Ihre XAML-typsystemmerkmale an .NET Framework XAML-Dienste zu übermitteln.  
  
- Das Hosting von XAML-Readern oder XAML-Writern als Komponente einer Anwendung, z. b. ein visueller Designer oder interaktiver Editor für XAML-Markup Quellen.  
  
- Schreiben von XAML-Wert Konvertern (Markup Erweiterungen; Typkonverter für benutzerdefinierte Typen).  
  
- Definieren eines benutzerdefinierten XAML-Schema Kontexts (mithilfe alternativer Methoden zum Laden von Assemblys zum unterstützen von typquellen; verwenden bekannter Typen, anstelle von immer reflektierenden Assemblys; Verwendung geladener Assemblykonzepte, die die CLR-`AppDomain` und das zugehörige Sicherheitsmodell nicht verwenden).  
  
- Erweitern des Basis-XAML-Typsystems.  
  
- Verwenden der `Lookup`-oder `Invoker` Techniken, um das XAML-Typsystem zu beeinflussen, und wie typbacken ausgewertet werden.  
  
 Wenn Sie ein Einführungs Material zu XAML als Sprache suchen, können Sie [XAML Overview (WPF)](../../desktop-wpf/fundamentals/xaml.md)ausprobieren. In diesem Thema wird XAML für eine Zielgruppe erläutert, die sowohl für [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] als auch für die Verwendung von XAML-Markup-und XAML-sprach Features neu ist. Ein weiteres nützliches Dokument ist das einführende Material der [XAML-Sprachspezifikation](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>.NET Framework XAML-Dienste und System. XAML in der .NET-Architektur  
 In früheren Versionen von Microsoft .NET Framework wurde die Unterstützung für XAML-sprach Features von Frameworks implementiert, die auf Microsoft .NET Framework ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Windows Workflow Foundation und Windows Communication Foundation (WCF)) basieren, und daher in seinem Verhalten und in Abhängigkeit davon, welches bestimmtes Framework Sie verwendet haben, unterschiedlich ist. Dazu gehörten der XAML-Parser und der Erstellungs Mechanismus des Objekt Diagramms, systeminterne XAML-Sprache, Serialisierungsunterstützung usw.  
  
 In .NET Framework 4 definieren .NET Framework XAML-Dienste und die System. XAML-Assembly einen Großteil der Anforderungen, die für die Unterstützung von XAML-sprach Features erforderlich sind. Dies schließt Basisklassen für XAML-Reader und XAML-Writer ein. Das wichtigste Feature, das .NET Framework XAML-Diensten hinzugefügt wurde, die in keiner der Framework-spezifischen XAML-Implementierungen vorhanden waren, ist eine Typsystem Darstellung für XAML. Die Typsystem Darstellung stellt XAML in einer objektorientierten Weise dar, die auf XAML-Funktionen zentriert ist, ohne dass dabei Abhängigkeiten von bestimmten Funktionen von Frameworks übernommen werden.  
  
 Das XAML-Typsystem ist nicht durch das Markup Formular oder die Lauf Zeit Besonderheiten des XAML-Ursprungs beschränkt. Es ist auch nicht durch ein bestimmtes Unterstützungs-Typsystem eingeschränkt. Das XAML-Typsystem umfasst Objekt Darstellungen für Typen, Member, XAML-Schema Kontexte, Konzepte auf XML-Ebene und andere XAML-sprach Konzepte oder intrinsie XAML-Funktionen. Die Verwendung oder Erweiterung des XAML-Typsystems ermöglicht das Ableiten von Klassen wie XAML-Readern und XAML-Writern und das Erweitern der Funktionalität der XAML-Darstellungen in bestimmte Features, die von einem Framework, einer Technologie oder einer Anwendung, die oder verwendet, aktiviert sind. gibt XAML aus. Das Konzept eines XAML-Schema Kontexts ermöglicht praktische Objekt Graph-Schreibvorgänge aus der Kombination aus einer XAML-objektwriter-Implementierung, einem Technologie Unterstützungs-Typsystem, das über Assemblyinformationen im Kontext kommuniziert wird, und aus dem XAML-Knoten. Ausgangs. Weitere Informationen zum XAML-Schema Konzept. Weitere Informationen finden Sie unter [XAML-Standardschema Kontext und WPF-XAML-Schema Kontext](default-xaml-schema-context-and-wpf-xaml-schema-context.md).  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>XAML-knotenstreams, XAML-Reader und XAML-Writer  
 Um die Rolle zu verstehen, die .NET Framework XAML-Dienste in der Beziehung zwischen der XAML-Sprache und bestimmten Technologien spielen, die XAML als Sprache verwenden, ist es hilfreich, das Konzept eines XAML-knotenstreams zu verstehen und zu verstehen, wie das Konzept die API bildet und Begriffs. Der XAML-knotenstream ist ein konzeptioneller zwischen Punkt zwischen einer XAML-Sprachdarstellung und dem Objekt Diagramm, das die XAML-Datei darstellt oder definiert.  
  
- Ein XAML-Reader ist eine Entität, die XAML in irgendeiner Form verarbeitet und einen XAML-knotenstream erzeugt. In der-API wird ein XAML-Reader durch die Basisklasse <xref:System.Xaml.XamlReader>dargestellt.  
  
- Ein XAML-Writer ist eine Entität, die einen XAML-knotenstream verarbeitet und etwas anderes erzeugt. In der-API wird ein XAML-Writer durch die Basisklasse <xref:System.Xaml.XamlWriter>dargestellt.  
  
 Die beiden gängigsten Szenarien, die XAML betreffen, sind das Laden von XAML zum Instanziieren eines Objekt Diagramms und das Speichern eines Objekt Diagramms aus einer Anwendung oder einem Tool und das Erstellen einer XAML-Darstellung (in der Regel in der als Textdatei gespeicherten Markup Form). Das Laden von XAML und das Erstellen eines Objekt Diagramms werden häufig in dieser Dokumentation als Ladepfad bezeichnet. Das Speichern oder Serialisieren eines vorhandenen Objekt Diagramms in XAML wird häufig in dieser Dokumentation als Speicherpfad bezeichnet.  
  
 Der häufigste Typ von Ladepfad kann wie folgt beschrieben werden:  
  
- Beginnen Sie mit einer XAML-Darstellung im UTF-codierten XML-Format, und speichern Sie Sie als Textdatei.  
  
- Laden Sie dieses XAML in <xref:System.Xaml.XamlXmlReader>. <xref:System.Xaml.XamlXmlReader> ist eine <xref:System.Xaml.XamlReader>-Unterklasse.  
  
- Das Ergebnis ist ein XAML-knotenstream. Mithilfe <xref:System.Xaml.XamlXmlReader> / <xref:System.Xaml.XamlReader>-API können Sie auf einzelne Knoten des XAML-knotenstreams zugreifen. Der typische Vorgang besteht darin, den XAML-knotenstream zu durchlaufen und jeden Knoten mit einer "aktuellen Daten Satz"-Metapher zu verarbeiten.  
  
- Übergeben Sie die resultierenden Knoten aus dem XAML-knotenstream an eine <xref:System.Xaml.XamlObjectWriter>-API. <xref:System.Xaml.XamlObjectWriter> ist eine <xref:System.Xaml.XamlWriter>-Unterklasse.  
  
- Der <xref:System.Xaml.XamlObjectWriter> schreibt ein Objekt Diagramm, ein Objekt, in Übereinstimmung mit dem Fortschritt durch den Quell-XAML-knotenstream. Dies erfolgt mit der Unterstützung eines XAML-Schema Kontexts und einer-Implementierung, die auf die Assemblys und Typen eines Sicherungstyp Systems und-Frameworks zugreifen können.  
  
- Rufen Sie <xref:System.Xaml.XamlObjectWriter.Result%2A> am Ende des XAML-knotenstreams auf, um das Stamm Objekt des Objekt Diagramms zu erhalten.  
  
 Die gängigste Art von Speicherpfad kann wie folgt beschrieben werden:  
  
- Beginnen Sie mit dem Objekt Diagramm für eine gesamte Anwendungs Laufzeit, den Inhalt der Benutzeroberfläche und den Zustand einer Laufzeit oder ein kleineres Segment der Objektdarstellung einer Gesamtanwendung zur Laufzeit.  
  
- Laden Sie die Objekte aus einem logischen Start Objekt, z. b. einem Anwendungs Stamm oder einem Dokument Stamm, in <xref:System.Xaml.XamlObjectReader>. <xref:System.Xaml.XamlObjectReader> ist eine <xref:System.Xaml.XamlReader>-Unterklasse.  
  
- Das Ergebnis ist ein XAML-knotenstream. Mithilfe <xref:System.Xaml.XamlObjectReader> und <xref:System.Xaml.XamlReader>-API können Sie auf einzelne Knoten des XAML-knotenstreams zugreifen. Der typische Vorgang besteht darin, den XAML-knotenstream zu durchlaufen und jeden Knoten mit einer "aktuellen Daten Satz"-Metapher zu verarbeiten.  
  
- Übergeben Sie die resultierenden Knoten aus dem XAML-knotenstream an eine <xref:System.Xaml.XamlXmlWriter>-API. <xref:System.Xaml.XamlXmlWriter> ist eine <xref:System.Xaml.XamlWriter>-Unterklasse.  
  
- Der <xref:System.Xaml.XamlXmlWriter> schreibt XAML in eine XML-UTF-Codierung. Sie können dies als Textdatei, als Stream oder in anderen Formularen speichern.  
  
- Rufen Sie <xref:System.Xaml.XamlXmlWriter.Flush%2A> auf, um die endgültige Ausgabe zu erhalten.  
  
 Weitere Informationen zu XAML-knotenstreamkonzepten finden Sie Untergrund Legendes zu [XAML-knotenstreamstrukturen und-Konzepten](understanding-xaml-node-stream-structures-and-concepts.md).  
  
### <a name="the-xamlservices-class"></a>Die XamlServices-Klasse  
 Der Umgang mit einem XAML-knotenstream ist nicht immer erforderlich. Wenn Sie einen grundlegenden Ladepfad oder einen grundlegenden Speicherpfad verwenden möchten, können Sie APIs in der <xref:System.Xaml.XamlServices>-Klasse verwenden.  
  
- Verschiedene Signaturen <xref:System.Xaml.XamlServices.Load%2A> implementieren einen Ladepfad. Sie können entweder eine Datei oder einen Stream laden oder eine <xref:System.Xml.XmlReader>laden, <xref:System.IO.TextReader> oder <xref:System.Xaml.XamlReader>, die die XAML-Eingabe einschließen, indem Sie Sie mit den APIs des Readers laden.  
  
- Verschiedene Signaturen von <xref:System.Xaml.XamlServices.Save%2A> ein Objekt Diagramm speichern und die Ausgabe als Stream, Datei oder <xref:System.Xml.XmlWriter>/<xref:System.IO.TextWriter> Instanz erzeugt.  
  
- <xref:System.Xaml.XamlServices.Transform%2A> konvertiert XAML, indem ein Ladepfad und ein Speicherpfad als einzelner Vorgang verknüpft werden. Ein anderer Schema Kontext oder ein anderes Unterstützungstyp System kann für <xref:System.Xaml.XamlReader> und <xref:System.Xaml.XamlWriter>verwendet werden. Dies wirkt sich auf das Transformieren der resultierenden XAML aus.  
  
 Weitere Informationen zur Verwendung von <xref:System.Xaml.XamlServices>finden Sie unter [XamlServices-Klasse und Grundlegendes zum Lesen oder Schreiben von XAML](xamlservices-class-and-basic-xaml-reading-or-writing.md).  
  
## <a name="xaml-type-system"></a>XAML-Typsystem  
 Das XAML-Typsystem stellt die APIs bereit, die erforderlich sind, um mit einem bestimmten einzelnen Knoten eines XAML-knotenstreams zu arbeiten.  
  
 <xref:System.Xaml.XamlType> ist die Darstellung eines Objekts, das Sie zwischen einem Start Objekt Knoten und einem Endobjekt Knoten verarbeiten.  
  
 <xref:System.Xaml.XamlMember> ist die Darstellung für ein Element eines Objekts, das Sie zwischen einem StartMember-Knoten und einem endmember-Knoten verarbeiten.  
  
 APIs wie <xref:System.Xaml.XamlType.GetAllMembers%2A> und <xref:System.Xaml.XamlType.GetMember%2A> und <xref:System.Xaml.XamlMember.DeclaringType%2A> melden die Beziehungen zwischen einer <xref:System.Xaml.XamlType> und <xref:System.Xaml.XamlMember>.  
  
 Das Standardverhalten des XAML-Typsystems, das von .NET Framework XAML-Diensten implementiert wird, basiert auf der Common Language Runtime (CLR) und der statischen Analyse von CLR-Typen in Assemblys mithilfe von Reflektion. Daher kann die Standard Implementierung des XAML-Typsystems bei einem bestimmten CLR-Typ das XAML-Schema dieses Typs und seiner Member verfügbar machen und es in Bezug auf das XAML-Typsystem melden. Im standardmäßigen XAML-Typsystem wird das Konzept der Zustell barkeit von Typen der CLR-Vererbung zugeordnet, und die Konzepte von Instanzen, Werttypen usw. werden ebenfalls dem unterstützenden Verhalten und den Funktionen der CLR zugeordnet.  
  
## <a name="reference-for-xaml-language-features"></a>Referenz zu XAML-sprach Features  
 Zur Unterstützung von XAML bietet .NET Framework XAML-Dienste eine spezifische Implementierung der XAML-sprach Konzepte, die für den XAML-Namespace der XAML-Sprache definiert wurden. Diese werden als spezifische Referenzseiten dokumentiert. Die sprach Features sind aus der Perspektive der Verhalten dieser sprach Features dokumentiert, wenn Sie von einem XAML-Reader oder XAML-Writer verarbeitet werden, der durch .NET Framework XAML-Dienste definiert ist. Weitere Informationen finden Sie unter [XAML Namespace (x:) Language Features](xaml-namespace-x-language-features.md).
