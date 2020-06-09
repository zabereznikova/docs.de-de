---
title: Filterung
ms.date: 03/30/2017
ms.assetid: 4002946c-e34a-4356-8cfb-e25912a4be63
ms.openlocfilehash: d04141e4720320784bc92c332a3f0b96a7b1ac92
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595465"
---
# <a name="filtering"></a>Filterung
Das Filtersystem Windows Communication Foundation (WCF) kann deklarative Filter verwenden, um Nachrichten abzugleichen und betriebliche Entscheidungen zu treffen. Sie können anhand von Filtern einen Teil der Nachricht untersuchen und so bestimmen, was mit der Nachricht geschehen soll. Ein Warteschlangenprozess kann beispielsweise eine XPath 1.0-Abfrage verwenden, um das Prioritätselement eines bekannten Headers im Hinblick darauf zu prüfen, ob eine Nachricht in der Warteschlange an den Anfang verschoben werden soll.  
  
 Das Filtersystem besteht aus einer Reihe von Klassen, mit denen effizient bestimmt werden kann, welcher Filtersatz `true` für eine bestimmte WCF-Nachricht gilt.  
  
 Das Filtersystem ist eine Kernkomponente von WCF Messaging. die Anwendung ist äußerst schnell. Jede Filter Implementierung wurde für eine bestimmte Art von Abgleich mit WCF-Nachrichten optimiert.  
  
 Das Filtersystem ist nicht threadsicher. Sperrsemantik muss von der Anwendung verarbeitet werden. Es unterstützt jedoch mehrere Reader und einen Writer.  
  
## <a name="where-filtering-fits"></a>Anwendung des Filtersystems  
 Die Filterung wird nach Eingang einer Nachricht durchgeführt und ist Teil des Prozesses, durch den eine Nachricht an die richtige Anwendungskomponente verteilt wird. Der Entwurf des Filtersystems erfüllt die Anforderungen mehrerer WCF-Subsysteme, einschließlich Messaging, Routing, Sicherheit, Ereignis Behandlung und Systemverwaltung.  
  
## <a name="filters"></a>Filter  
 Die Filter-Engine besteht aus zwei primären Komponenten: Filtern und Filtertabellen. Ein Filter trifft anhand von benutzerdefinierten logischen Bedingungen boolesche Entscheidungen bezüglich der Nachricht. Filter implementieren die <xref:System.ServiceModel.Dispatcher.MessageFilter>-Klasse.  
  
 Mit den <xref:System.ServiceModel.Dispatcher.MessageFilter.Match%2A>-Methoden wird ermittelt, ob eine Nachricht zu einem Filter passt. Eine der Methoden prüft den Nachrichtenheader, kann jedoch nicht den Nachrichtentext überprüfen. Die andere Methode nimmt einen *Nachrichten Puffer* als Eingabeparameter an und kann den Nachrichtentext überprüfen.  
  
 Filter werden im Allgemeinen nicht einzeln überprüft, sondern als Teil einer Filtertabelle, bei der es sich um eine durch die <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601.CreateFilterTable%2A>-Methode erstellte generische Klasse handelt.  
  
 Die verschiedenen Filter sind jeweils für den Vergleich einer bestimmten Art von boolescher Bedingung optimiert. Nach der Erstellung eines Filters können die vom Filter verwendeten Kriterien nicht mehr geändert werden. Soll ein Filter andere Kriterien verwenden, erstellen Sie einen neuen Filter und löschen den bestehenden.  
  
### <a name="action-filters"></a>Aktionsfilter  
 <xref:System.ServiceModel.Dispatcher.ActionMessageFilter> enthält eine Liste mit Aktionszeichenfolgen. Falls eine der Aktionen in der Filterliste mit dem Action-Header in der Nachricht bzw. im Nachrichtenpuffer übereinstimmt, gibt die `Match`-Methode `true` zurück. Falls die Liste leer ist, gilt der Filter als ein Filter, bei dem es nur Übereinstimmungen gibt, das heißt, jede Nachricht bzw. jeder Nachrichtenpuffer liefert eine Übereinstimmung, und von `Match` wird `true` zurückgegeben. Falls keine der Aktionen in der Filterliste mit dem Action-Header in der Nachricht bzw. im Nachrichtenpuffer übereinstimmt, gibt die `Match`-Methode `false` zurück. Falls die Nachricht keine Aktion enthält und die Filterliste nicht leer ist, gibt die `Match`-Methode `false` zurück.  
  
### <a name="endpoint-address-filters"></a>Endpunktadressenfilter  
 <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter> filtert Nachrichten und Nachrichtenpuffer auf Grundlage einer Endpunktadresse entsprechend der Headerauflistung. Damit eine Nachricht einen solchen Filter passieren kann, müssen die folgenden Voraussetzungen erfüllt sein:  
  
- Der Adress-URI (Uniform Resource Identifier) des Filters muss dem Adress-URI im To-Header der Nachricht entsprechen.  
  
- Jedem Endpunktparameter in der Adresse des Filters (`address.Headers`-Auflistung) muss ein Header in der Nachricht zugeordnet werden können. Auch bei zusätzlichen Headern in der Nachricht oder im Nachrichtenpuffer bleibt die Übereinstimmung `true`.  
  
### <a name="prefix-endpoint-address-filters"></a>Präfixfilter für Endpunktadressen  
  
1. <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> funktioniert wie <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter>, mit der Ausnahme, dass sich die Übereinstimmung in einem Präfix des Nachrichten-URIs befinden kann. Ein Filter, der die Adresse angibt, `http://www.adatum.com` entspricht z. b. den Nachrichten, die an `http://www.adatum.com/userA`  
  
### <a name="xpath-message-filters"></a>XPath-Nachrichtenfilter  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> überprüft anhand eines XPath-Ausdrucks, ob ein XML-Dokument bestimmte Elemente, Attribute, Text oder andere syntaktische XML-Konstrukte enthält. Der Filter ist so optimiert, dass er sehr effizient bei einer eng gefassten Teilmenge von XPath funktioniert. Die XML-Pfad Sprache wird in der [Spezifikation der W3C XML Path Language 1,0](https://www.w3.org/TR/xpath/all/)beschrieben.  
  
 Im Allgemeinen wird der Inhalt einer SOAP-Nachricht von einer Anwendung mithilfe von <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> an einem Endpunkt abgefragt. Anschließend wird auf Grundlage des Abfrageergebnisses die entsprechende Aktion eingeleitet. Ein Warteschlangenprozess kann beispielsweise mithilfe einer XPath-Abfrage das Prioritätselement eines bekannten Headers im Hinblick darauf untersuchen, ob eine Nachricht in der Warteschlange an den Anfang verschoben werden soll.  
  
## <a name="filter-tables"></a>Filtertabellen  
 In Filtertabellen werden Schlüssel-Wert-Paare gespeichert, wobei ein Filter der Schlüssel ist und zugehörige Daten der Wert sind. Die Filterdaten können verwendet werden, um die Aktionen anzugeben, die durchgeführt werden, wenn eine Nachricht mit dem Filter übereinstimmt und es sich bei der Art der Filterdaten um den generischen Parameter für die Filtertabellenklasse handelt. Die Filterdaten können Routingregeln, Sitzungs- und Sicherheitsstatus, Kanallistener usw. umfassen. Die Daten können verwendet werden, wenn eine Datenflusssteuerung erforderlich ist.  
  
 Filtertabellen implementieren die generische Schnittstelle <xref:System.ServiceModel.Dispatcher.IMessageFilterTable%601>.  
  
 Filtertabellen verfügen über mehrere Methoden, die eine Nachricht mit allen Filtern in der Tabelle vergleichen und eine nicht sortierte Auflistung der passenden Filter bzw. Daten zurückgeben. Einige Vergleichsmethoden suchen mehrere Übereinstimmungen und geben alle passenden Elemente zurück. Andere Methoden suchen nur eine Übereinstimmung, geben nur ein Element zurück und lösen eine <xref:System.ServiceModel.Dispatcher.MultipleFilterMatchesException> aus, wenn mehr als ein Filter passt.  
  
### <a name="message-filter-table"></a>Nachrichtenfiltertabelle  
 <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> ist die allgemeinste Implementierung von <xref:System.ServiceModel.Dispatcher.IMessageFilterTable%601>. Sie können alle Arten von Filtern in der Tabelle speichern.  
  
 Sie können Filtern eine numerische Priorität zuweisen, wobei die höchste Priorität durch die höchste Zahl angegeben wird. Verschiedene Arten von Filtern können die gleiche Priorität haben. Ein bestimmter Filtertyp kann auch in verschiedenen Prioritätsstufen erscheinen.  
  
 Der Vergleich beginnt mit der höchsten Priorität. Sobald passende Filter mit der angegebenen Priorität gefunden werden, werden keine weiteren Filter mit einer niedrigeren Priorität mehr überprüft. Wenn Sie also eine Vergleichsmethode für einen einzelnen Filter verwenden und mehrere Filter mit einer Nachricht übereinstimmen, jedoch verschiedene Prioritätsstufen aufweisen, wird keine Ausnahme ausgelöst, und der Filter mit der höchsten Priorität wird zurückgegeben. Ebenso geben Vergleichsmethoden für mehrere Filter nur die passenden Filter mit der höchsten Priorität zurück.  
  
### <a name="xpath-message-filter-table"></a>XPath-Nachrichtenfiltertabelle  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilterTable%601> ist für deklarative XPath-Filter optimiert, daher handelt es sich beim Tabellenschlüssel um einen <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.  
  
 Die <xref:System.ServiceModel.Dispatcher.XPathMessageFilterTable%601>-Klasse optimiert den Vergleich für eine XPath-Teilmenge, durch die die meisten Messaging-Szenarien abgedeckt werden und die zudem die vollständige XPath 1.0-Grammatik unterstützt. Sie verfügt über optimierte Algorithmen für einen effizienten Parallelvergleich.  
  
 Diese Tabelle verfügt über mehrere spezielle `Match`-Methoden, die mit <xref:System.Xml.XPath.XPathNavigator> und <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator> arbeiten. <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator> erweitert die <xref:System.Xml.XPath.XPathNavigator>-Klasse durch Hinzufügen einer <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator.CurrentPosition%2A>-Eigenschaft. Diese Eigenschaft ermöglicht es, Positionen innerhalb des XML-Dokuments zu speichern und rasch zu laden, ohne den Navigator klonen zu müssen (eine ressourcenintensive Speicherbelegung, die <xref:System.Xml.XPath.XPathNavigator> für einen solchen Vorgang benötigt). Die WCF-XPath-Engine muss die Position des Cursors im Verlauf der Ausführung von Abfragen für XML-Dokumente häufig aufzeichnen, sodass die <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator> eine wichtige Optimierung für die Nachrichtenverarbeitung bereitstellt.  
  
## <a name="customer-scenarios"></a>Kundenszenarien  
 Sie können die Filterung verwenden, wenn Sie eine Nachricht basierend auf den darin enthaltenen Daten an verschiedene Verarbeitungsmodule senden möchten. Zwei typische Szenarien sind die Weiterleitung einer Nachricht auf Grundlage ihres Aktionscodes und das Demultiplexing eines Nachrichtenstroms basierend auf der Endpunktadresse der Nachricht.  
  
### <a name="routing"></a>Routing  
 Der Listener eines Endpunkts hört Nachrichten ab, die einen oder mehrere Aktionscodes im SOAP-Header der Nachricht aufweisen. Diese Funktion wird durch Erstellen eines <xref:System.ServiceModel.Dispatcher.ActionMessageFilter> implementiert, indem ein Array mit den Aktionscodes an den Konstruktor übergeben wird. Dieser Filter wird für die Registrierung bei `ListenerFactory` verwendet, das heißt, dass nur Nachrichten, deren Aktion mit einer der Aktionen im Filter übereinstimmt, zu diesem Endpunkt geleitet werden.  
  
### <a name="de-multiplexing"></a>Demultiplexing  
 Falls ein `ServiceListener` auf mehrere Endpunkte verzweigt, gibt es nur eine Möglichkeit, ein Demultiplexing für die Nachrichten durchzuführen und herauszufinden, ob sie zu einer bestimmten Endpunktadresse gehören: Sie müssen mehrere <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter> verwenden, die Nachrichten über eine Suche in den im Header gespeicherten Informationen für die registrierten Endpunkte auswählen. In diesen Filtern weisen nur die Nachrichten, die passieren dürfen, die notwendigen Header auf, die den folgenden beiden Punkten entsprechen:  
  
- dem URI in der `EndpointAddress`  
  
- den übrigen Endpunktparametern in der `EndpointAddress`, wie in <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter> angegeben  
  
## <a name="see-also"></a>Weitere Informationen

- [Datenübertragung und Serialisierung](data-transfer-and-serialization.md)
