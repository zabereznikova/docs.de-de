---
title: Einführung - gRPC für WCF-Entwickler
description: Einführung
ms.date: 09/02/2019
ms.openlocfilehash: 41f470eb02a77b1b6a26a7d4c2ca347ad07d828d
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988933"
---
# <a name="introduction"></a>Einführung

Die Kommunikation von Maschinen untereinander war eines der Hauptanliegen des digitalen Zeitalters. Insbesondere wird ständig versucht, den optimalen Fernkommunikationsmechanismus zu ermitteln, der den Interoperabilitätsanforderungen der aktuellen Infrastruktur entspricht. Wie Sie sich vorstellen können, ändert sich dieser Mechanismus, wenn sich entweder die Anforderungen oder die Infrastruktur weiterentwickelt.

Die Veröffentlichung von .NET Core 3.0 markiert eine Veränderung in der Art und Weise, wie Microsoft Remote-Kommunikationslösungen für Entwickler liefert, die Dienste über eine Reihe von Plattformen bereitstellen möchten. .NET Core bietet Windows Communication Foundation (WCF) nicht sofort an, bietet aber mit der Veröffentlichung von ASP.NET Core 3.0 integrierte gRPC-Funktionalität.

gRPC ist ein beliebter Rahmen in der breiteren Software-Community. Es wird von Entwicklern in vielen Programmiersprachen für moderne RPC-Szenarien verwendet. Die Gemeinschaft und das Ökosystem sind lebendig und aktiv. Die Unterstützung für das gRPC-Protokoll wird Infrastrukturkomponenten wie Kubernetes, Service-Meshes, Load Balancer und mehr hinzugefügt. Diese Faktoren machen gRPC zusammen mit seiner Leistung, Effizienz und plattformübergreifenden Kompatibilität zu einer natürlichen Wahl für neue Apps und WCF-Apps, die zu .NET Core wechseln.

## <a name="history"></a>Verlauf

Das Grundprinzip eines Computernetzwerks als nichts anderes als eine Gruppe von Computern, die Daten miteinander austauschen, um eine Reihe miteinander verbundener Aufgaben zu erreichen, hat sich seit seiner Gründung nicht geändert. Aber die Komplexität, das Ausmaß und die Erwartungen sind exponentiell gewachsen.  

In den 90er Jahren lag der Schwerpunkt hauptsächlich auf der Verbesserung interner Netzwerke, die dieselbe Sprache und plattformennutzten. TCP/IP wurde zum Goldstandard für diese Art der Kommunikation.

Der Fokus verlagerte sich bald darauf, wie die Kommunikation über mehrere Plattformen hinweg am besten optimiert werden kann, indem ein sprachagnostischer Ansatz gefördert wird. Serviceorientierte Architektur (SOA) bot eine Struktur für die lose Kopplung einer breiten Sammlung von Diensten, die einer Anwendung zur Verfügung gestellt werden konnten.

Die Entwicklung von *Webdiensten* erfolgte, als alle großen Plattformen auf das Internet zugreifen konnten, aber sie immer noch nicht miteinander interagieren konnten. Webdienste verfügen über offene Standards und Protokolle, einschließlich:

- XML zum Tag und Codedaten.
- Simple Object Access Protocol (SOAP) zum Übertragen von Daten.
- Web Services Definition Language (WSDL), um Webdienste zu beschreiben und mit Clientanwendungen zu verbinden.
- UdDI (Universal Description, Discovery, and Integration), um Webdienste für andere Dienste auffindbar zu machen.

SOAP definiert die Regeln, nach denen verteilte Elemente einer Anwendung miteinander kommunizieren können, auch wenn sie sich auf verschiedenen Plattformen befinden. SOAP basiert auf XML, daher ist es für den Menschen lesbar. Das Opfer, SOAP leicht verständlich zu machen, ist die Größe; SOAP-Nachrichten sind größer als Nachrichten in vergleichbaren Protokollen. SOAP wurde entwickelt, um monolithische Anwendungen in Mehrkomponentenform zu brechen, ohne die Sicherheit oder Kontrolle zu verlieren. So wurde WCF entwickelt, um mit dieser Art von System zu arbeiten, im Gegensatz zu gRPC, die als ein verteiltes System begann. WCF besprach einige dieser Einschränkungen, indem proprietäre Erweiterungsprotokolle für den SOAP-Stack entwickelt und dokumentiert wurden, jedoch auf Kosten mangelnder Unterstützung durch andere Plattformen.

Windows Communication Foundation ist ein Framework für das Erstellen von Diensten. Es wurde in den frühen 2000er Jahren entwickelt, um Entwicklern zu helfen, frühe SOA zu verwenden, um die Komplexität der Arbeit mit SOAP zu verwalten. Obwohl die Entwickler ihre eigenen SOAP-Protokolle nicht mehr benötigen, verwendet WCF weiterhin SOAP, um die Interoperabilität mit anderen Systemen zu ermöglichen. WCF wurde auch entwickelt, um Lösungen für mehrere Protokolle bereitzustellen (HTTP/1.1, Net.TCP usw.).

## <a name="microservices"></a>Microservices

In Microservice-Architekturen werden große Anwendungen als eine Sammlung kleinerer modularer Services erstellt. Jede Komponente führt eine bestimmte Aufgabe oder einen bestimmten Prozess aus, und Komponenten sind so konzipiert, dass sie interoperabel funktionieren, können aber bei Bedarf isoliert werden.

Zu den Vorteilen von Microservices gehören:

- Änderungen und Upgrades können unabhängig voneinander behandelt werden.
- Die Fehlerbehandlung wird effizienter, da Probleme auf bestimmte Dienste zurückverfolgt werden können, die dann unabhängig von den anderen Diensten isoliert, neu erstellt, getestet und erneut bereitgestellt werden.
- Die Skalierbarkeit kann auf bestimmte Instanzen oder Dienste beschränkt werden und nicht auf die gesamte Anwendung.
- Die Entwicklung kann in mehreren Teams erfolgen, mit weniger Reibung als bei der Arbeit vieler Teams an einer einzelnen Codebasis.

Der Schritt hin zu zunehmender Virtualisierung, Cloud Computing, Containern und dem Internet der Dinge hat zum anhaltenden Anstieg von Microservices beigetragen. Aber Microservices sind nicht ohne ihre Herausforderungen. Die fragmentierte/dezentralisierte Infrastruktur legt mehr Gewicht auf die Notwendigkeit von Einfachheit und Geschwindigkeit bei der Kommunikation zwischen Diensten. Dies wiederum machte auf die manchmal mühsame und verzerrte Natur von SOAP aufmerksam.

Es war in dieser Umgebung, dass gRPC gestartet wurde, 10 Jahre, nachdem Microsoft zum ersten Mal WCF veröffentlicht. GRPC wurde direkt aus der internen Infrastruktur RPC (Stubby) von Google entwickelt und basierte nie auf den gleichen Standards und Protokollen, die die Parameter vieler früherer RPCs informiert hatten. Und gRPC wurde immer nur auf HTTP/2 basiert. Aus diesem Grund könnte es auf die neuen Funktionen zurückgreifen, die das erweiterte Transportprotokoll bereitstellt. Insbesondere bidirektionales Streaming, binäres Messaging und Multiplexing.

## <a name="about-this-guide"></a>Über diesen Leitfaden

Dieses Handbuch behandelt die wichtigsten Merkmale von gRPC. In den ersten Kapiteln werden die Hauptmerkmale von WCF auf hoher Ebene betrachtet und mit denen von gRPC verglichen. Es identifiziert, wo es direkte Korrelationen zwischen WCF und gRPC gibt und auch, wo gRPC einen Vorteil bietet. Wenn es keine Korrelation zwischen WCF und gRPC gibt oder wenn gRPC nicht in der Lage ist, WCF eine gleichwertige Lösung anzubieten, schlägt dieses Handbuch Problemumgehungen vor oder wo Sie weitere Informationen erhalten möchten.

Mit einer Reihe von WCF-Beispielanwendungen betrachtet Kapitel 5 die wichtigsten Arten von WCF-Diensten (einfache Anforderungsantwort, einwegund wie möglich) in ihre Entsprechungen in gRPC.

Im letzten Abschnitt des Buches geht es um die Frage, wie man das Beste aus gRPC in der Praxis abholt. Dieser Abschnitt enthält Informationen zur Verwendung zusätzlicher Tools, wie Docker-Container oder Kubernetes, um die Effizienz von gRPC zu nutzen. Es enthält auch einen detaillierten Blick auf die Überwachung mit Protokollierung, Metriken und verteilter Ablaufverfolgung.

## <a name="who-this-guide-is-for"></a>Für wen ist dieser Leitfaden gedacht?

Dieses Handbuch wurde für Entwickler geschrieben, die in .NET Framework oder .NET Core arbeiten und WCF verwendet haben und ihre Anwendungen in eine moderne RPC-Umgebung für .NET Core 3.0 und neuere Versionen migrieren möchten. Das Handbuch kann auch generell für Entwickler nützlich sein, die ein Upgrade auf .NET Core 3.0 durchführen oder ein Upgrade in Betracht ziehen und die integrierten gRPC-Tools verwenden möchten.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](grpc-overview.md)
