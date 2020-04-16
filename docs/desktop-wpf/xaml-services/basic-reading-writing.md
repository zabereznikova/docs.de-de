---
title: XAMLServices-Klasse und grundlegende XAML-Lese- und -Schreibvorgänge
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], XamlServices class
- XamlServices class [XAML Services], how to use
ms.assetid: 6ac27fad-3687-4d7a-add1-3e90675fdfde
ms.openlocfilehash: 264a8c4abcf9a7efceb7c7accd786495d35476e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433091"
---
# <a name="xamlservices-class-and-basic-xaml-reading-or-writing"></a>XAMLServices-Klasse und grundlegendes XAML-Lesen oder -Schreiben

<xref:System.Xaml.XamlServices>ist eine von .NET bereitgestellte Klasse, die verwendet werden kann, um XAML-Szenarien zu adressieren, die keinen bestimmten Zugriff auf den XAML-Knotenstream oder auf Systeminformationen vom XAML-Typ erfordern, die von diesen Knoten abgerufen werden. <xref:System.Xaml.XamlServices>API kann wie folgt `Load` zusammengefasst `Parse` werden: oder zur Unterstützung `Save` eines XAML-Ladepfads, zur Unterstützung eines XAML-Speicherpfads und `Transform` zur Bereitstellung einer Technik, die einen Ladepfad verbindet und den Pfad speichert. `Transform` kann verwendet werden, um von einem XAML-Schema zu einem anderen zu wechseln. In diesem Thema sind diese API-Klassifizierungen zusammengefasst, und die Unterschiede zwischen bestimmten Methodenüberladungen werden beschrieben.

## <a name="load"></a>Laden

Verschiedene Überladungen von <xref:System.Xaml.XamlServices.Load%2A> implementieren die vollständige Logik für einen Ladepfad. Der Ladepfad verwendet XAML und gibt einen XAML-Knotenstream aus. Die meisten dieser Ladepfade verwenden XAML in Form einer codierten XML-Textdatei. Sie können jedoch auch einen allgemeinen Stream laden oder eine vorab geladene XAML-Quelle, die bereits in einer anderen <xref:System.Xaml.XamlReader> -Implementierung enthalten ist.

Die einfachste Überladung für die meisten Szenarien ist <xref:System.Xaml.XamlServices.Load%28System.String%29>. Diese Überladung verfügt über einen `fileName` -Parameter, bei dem es sich einfach um den Namen einer Textdatei handelt, die die zu ladende XAML enthält. Dies eignet sich für Anwendungsszenarien wie Anwendungen mit voller Vertrauenswürdigkeit, die zuvor den Zustand oder Daten in den lokalen Computer serialisiert haben. Dies ist auch für Frameworks nützlich, bei denen Sie das Anwendungsmodell definieren und eine der Standarddateien laden möchten, die Anwendungsverhalten, die beim Start angezeigte Benutzeroberfläche oder andere vom Framework definierte Funktionen definieren.

<xref:System.Xaml.XamlServices.Load%28System.IO.Stream%29> hat ähnliche Szenarien. Diese Überladung kann nützlich sein, wenn Sie zu ladende Dateien vom Benutzer auswählen lassen, da ein <xref:System.IO.Stream> eine häufige Ausgabe von anderen <xref:System.IO> -APIs ist, die auf ein Dateisystem zugreifen können. Oder Sie könnten über asynchrone Downloads oder andere Netzwerktechniken, die ebenfalls einen Stream bereitstellen, auf XAML-Quellen zugreifen. (Das Laden aus einem Stream oder einer vom Benutzer ausgewählten Quelle hat Auswirkungen auf die Sicherheit. Weitere Informationen finden Sie unter [XAML Security Considerations](security-considerations.md).)

<xref:System.Xaml.XamlServices.Load%28System.IO.TextReader%29>und <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29> sind Überladungen, die auf Leser von Formaten aus früheren Versionen von .NET angewiesen sind. Um diese Überladungen zu verwenden, sollten Sie `Create` bereits eine Reader-Instanz erstellt und deren API verwendet haben, um das XAML in der entsprechenden Form (Text oder XML) zu laden. Wenn Sie bereits Datensatzzeiger in die anderen Reader verschoben oder andere Vorgänge damit ausgeführt haben, spielt dies keine Rolle. Die Ladepfadlogik aus <xref:System.Xaml.XamlServices.Load%2A> verarbeitet immer die gesamte XAML-Eingabe vom Stamm abwärts. Die folgenden Szenarien können die Verwendung dieser Überladungen rechtfertigen:

- Entwurfsoberflächen, auf denen einfache XAML-Bearbeitungsfunktionen eines vorhandenen XML-spezifischen Text-Editors bereitgestellt werden.

- Varianten der <xref:System.IO> -Kernszenarien, in denen zum Öffnen von Dateien oder Streams dedizierte Reader verwendet werden. Die Logik überprüft oder verarbeitet den Inhalt rudimentär, bevor er als XAML geladen wird.

Sie können entweder eine Datei oder einen <xref:System.Xml.XmlReader>Stream <xref:System.IO.TextReader>laden, oder Sie können eine , laden oder <xref:System.Xaml.XamlReader> die XAML-Eingabe durch Laden mit den APIs des Readers umschließt.

Intern ist jede der oben genannten Überladungen letztlich <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29>, und der übergebene <xref:System.Xml.XmlReader> wird verwendet, um einen neuen <xref:System.Xaml.XamlXmlReader>zu erstellen.

Die `Load` -Signatur für erweiterte Szenarien ist <xref:System.Xaml.XamlServices.Load%28System.Xaml.XamlReader%29>. Sie können diese Signatur für einen der folgenden Fälle verwenden:

- Sie haben Ihre eigene Implementierung <xref:System.Xaml.XamlReader>einer definiert.

- Sie müssen Einstellungen für <xref:System.Xaml.XamlReader> angeben, die von den Standardeinstellungen abweichen.

Beispiele für nicht standardmäßige Einstellungen:

<xref:System.Xaml.XamlReaderSettings.AllowProtectedMembersOnRoot%2A>\
<xref:System.Xaml.XamlReaderSettings.BaseUri%2A>\
<xref:System.Xaml.XamlReaderSettings.IgnoreUidsOnPropertyElements%2A>\
<xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A>\
<xref:System.Xaml.XamlReaderSettings.ValuesMustBeString%2A>.

Der Standardreader für <xref:System.Xaml.XamlServices> ist <xref:System.Xaml.XamlXmlReader>. Wenn Sie eigene <xref:System.Xaml.XamlXmlReader> Einstellungen angeben, sind die folgenden <xref:System.Xaml.XamlXmlReaderSettings>Eigenschaften, um nicht standardmäßig festzulegen:

<xref:System.Xaml.XamlXmlReaderSettings.CloseInput%2A>\
<xref:System.Xaml.XamlXmlReaderSettings.SkipXmlCompatibilityProcessing%2A>\
<xref:System.Xaml.XamlXmlReaderSettings.XmlLang%2A>\
<xref:System.Xaml.XamlXmlReaderSettings.XmlSpacePreserve%2A>

## <a name="parse"></a>Analysieren

<xref:System.Xaml.XamlServices.Parse%2A> entspricht `Load` , da es sich um eine Ladepfad-API handelt, die einen XAML-Knotenstream aus der XAML-Eingabe erstellt. In diesem Fall wird die XAML-Eingabe jedoch direkt als Zeichenfolge bereitgestellt, die das gesamte zu ladende XAML enthält. <xref:System.Xaml.XamlServices.Parse%2A> ist ein einfacher Ansatz, der sich besser für Anwendungsszenarien eignet als für Frameworkszenarien. Weitere Informationen finden Sie unter <xref:System.Xaml.XamlServices.Parse%2A>. <xref:System.Xaml.XamlServices.Parse%2A>ist nur <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29> ein umschlossener Anruf, der intern <xref:System.IO.StringReader> beteiligt ist.

## <a name="save"></a>Speichern

Verschiedene Überladungen von <xref:System.Xaml.XamlServices.Save%2A> implementieren den Speicherpfad. Alle <xref:System.Xaml.XamlServices.Save%2A> -Methoden verwenden ein Objektdiagramm als Eingabe und erstellen die Ausgabe als Stream, Datei oder <xref:System.Xml.XmlWriter>/<xref:System.IO.TextWriter> -Instanz.

Es wird davon ausgegangen, dass das Eingabeobjekt das Stammobjekt einer Objektdarstellung ist. Dies könnte der einzelne Stamm eines Geschäftsobjekts sein, der Stamm einer Objektstruktur für eine Seite in einem Benutzeroberflächenszenario, die Bearbeitungsoberfläche in einem Entwurfstool oder andere Stammobjektkonzepte, die für Szenarien geeignet sind.

In vielen Szenarien bezieht sich die objektstruktur, die Sie speichern, <xref:System.Xaml.XamlServices.Load%2A> auf einen ursprünglichen Vorgang, der XAML entweder mit oder mit einer anderen API geladen hat, die von einem Framework/Anwendungsmodell implementiert wurde. Unter Umständen werden Unterschiede in der Objektstruktur erfasst. Diese hängen mit Zustandsänderungen, mit Änderungen, bei denen die Anwendung Laufzeiteinstellungen von einem Benutzer erfasst hat, geänderter XAML zusammen, da die Anwendung eine XAML-Entwurfsoberfläche usw. Mit oder ohne Änderungen wird das Konzept zum Laden von XAML aus dem Markup und dem anschließenden erneuten Speichern und Vergleichen der zwei XAML-Markupformen manchmal als Roundtripdarstellung der XAML bezeichnet.

Die Herausforderung beim Speichern und Serialisieren eines komplexen Objekts in Markupform besteht darin, ein Gleichgewicht zwischen vollständiger Darstellung ohne Informationsverlust und übermäßiger Ausführlichkeit zu erreichen, durch die die Lesbarkeit des XAML beeinträchtigt wird. Darüber hinaus könnten andere Kunden für XAML über andere Definitionen oder Erwartungen im Hinblick darauf verfügen, wie dieses Gleichgewicht festgelegt werden sollte. Die <xref:System.Xaml.XamlServices.Save%2A> -APIs stellen eine Definition dieses Gleichgewichts dar. Die <xref:System.Xaml.XamlServices.Save%2A> -APIs verwenden den verfügbaren XAML-Schemakontext und die CLR-basierten Standardeigenschaften von <xref:System.Xaml.XamlType>, <xref:System.Xaml.XamlMember>sowie andere XAML-systeminterne und XAML-Typsystemkonzepte, um zu bestimmen, wo bestimmte XAML-Knotenstreamkonstrukte beim erneuten Speichern im Markup optimiert werden können. Beispiel: <xref:System.Xaml.XamlServices> -Speicherpfade können den CLR-basierten XAML-Standardschemakontext verwenden, um <xref:System.Xaml.XamlType> für Objekte aufzulösen, eine <xref:System.Xaml.XamlType.ContentProperty%2A?displayProperty=nameWithType>bestimmen und anschließend Eigenschaftselementtags weglassen, wenn sie die Eigenschaft in den XAML-Inhalt des Objekts schreiben.

<a name="transform"></a>
## <a name="transform"></a>Transformieren

<xref:System.Xaml.XamlServices.Transform%2A> konvertiert oder transformiert XAML, indem sie einen Ladepfad und einen Speicherpfad als einzelnen Vorgang verknüpft. Ein anderer Schemakontext oder ein anderes Unterstützungstypsystem kann für <xref:System.Xaml.XamlReader> und <xref:System.Xaml.XamlWriter>verwendet werden. Dies wirkt sich darauf aus, wie das resultierende XAML transformiert wird. Es funktioniert gut für umfassende Transformationsvorgänge.

Für Vorgänge, bei denen jeder Knoten in einem XAML-Knotenstream untersucht wird, wird <xref:System.Xaml.XamlServices.Transform%2A>in der Regel nicht verwendet. Stattdessen müssen Sie eigene Ladepfad-/Speicherpfadvorgänge definieren und eigene Logik verwenden. Verwenden Sie in einem der Pfade ein XAML Reader/XAML-Writer-Paar um Ihre eigene Knotenschleife. Laden Sie z. B. die ursprüngliche XAML mit <xref:System.Xaml.XamlXmlReader> , und springen Sie mit aufeinander folgenden <xref:System.Xaml.XamlXmlReader.Read%2A> -Aufrufen in die Knoten. Durch das Vorgehen auf XAML-Knotenstreamebene können Sie jetzt einzelne Knoten (Typen, Member, andere Knoten) anpassen, um eine Transformation anzuwenden, oder die Knoten unverändert beibehalten. Anschließend senden Sie den Knoten an die relevante `Write` -API eines <xref:System.Xaml.XamlObjectWriter> und schreiben das Objekt aus. Weitere Informationen finden Sie unter [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xaml.XamlObjectWriter>
- <xref:System.Xaml.XamlServices>
- [XAML-Dienste](../../../api/index.md)
