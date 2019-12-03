---
title: 'Einführung: GrpC für WCF-Entwickler'
description: Einführung
ms.date: 09/02/2019
ms.openlocfilehash: 2f36d6294e2c76309b051fb3af21157cbfc1087a
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711238"
---
# <a name="introduction"></a>Einführung

Die Unterstützung der Kommunikation zwischen Computern ist eine der primären vorab Berufe des digitalen Alters. Insbesondere wird ein fortlaufender Versuch unternommen, den optimalen Remote Kommunikationsmechanismus zu ermitteln, der den Interoperabilitäts Anforderungen der aktuellen Infrastruktur entspricht. Wie Sie sich vorstellen können, ändert sich dieses Verfahren, wenn sich die Anforderungen oder die Infrastruktur weiterentwickelt.

Mit der Veröffentlichung von .net Core 3,0 wird eine Umstellung auf die Art und Weise, wie Microsoft Remote Kommunikationslösungen für Entwickler bereitstellt, die Dienste auf verschiedenen Plattformen bereitstellen möchten. .Net Core bietet standardmäßig keine Windows Communication Foundation (WCF), aber mit der Veröffentlichung von ASP.net Core 3,0 bietet es integrierte GrpC-Funktionen.

GrpC ist ein beliebtes Framework in der umfassenderen Software Community. Sie wird von Entwicklern für moderne RPC-Szenarien in vielen Programmiersprachen verwendet. Die Community und das Ökosystem sind dynamisch und aktiv. Unterstützung für das GrpC-Protokoll wird Infrastrukturkomponenten wie Kubernetes, Service Meshes, Load Balancer usw. hinzugefügt. Diese Faktoren sind neben der Leistung, Effizienz und plattformübergreifenden Kompatibilität GrpC eine natürliche Wahl für neue apps und WCF-apps, die auf .net Core umgestellt werden.

## <a name="history"></a>Versionsgeschichte

Das Grundprinzip eines Computernetzwerks ist nicht mehr als eine Gruppe von Computern, die Daten untereinander austauschen, um eine Reihe von zusammenhängenden Aufgaben zu erreichen, die sich seit der Inbetriebnahme nicht geändert haben. Komplexität, Skalierung und Erwartungen wurden jedoch exponentiell vergrößert.  

In den 90er Jahren lag der Schwerpunkt hauptsächlich auf der Verbesserung interner Netzwerke, die dieselbe Sprache und dieselben Plattformen verwendeten. TCP/IP wurde für diese Art von Kommunikation der Gold-Standard.

Der Schwerpunkt lag in Kürze auf die optimale Optimierung der Kommunikation auf mehreren Plattformen durch die herauf Stufung eines sprach agnostischen Ansatzes. Die Dienst orientierte Architektur (Service Oriented Architecture, SOA) stellt eine Struktur für die lose Kopplung einer umfassenden Sammlung von Diensten bereit, die für eine Anwendung bereitgestellt werden können.

Die Entwicklung von *Webdiensten* ist aufgetreten, als alle wichtigen Plattformen auf das Internet zugreifen konnten, aber Sie konnten trotzdem nicht miteinander interagieren. Webdienste verfügen über offene Standards und Protokolle, einschließlich:

- XML zum Markieren und Codieren von Daten.
- Simple Object Access-Protokoll (SOAP) zum Übertragen von Daten.
- Web Services Definition Language (WSDL) zum beschreiben und Verbinden von Webdiensten mit Client Anwendungen.
- Universal Description, Discovery und Integration (UDDI), damit Webdienste von anderen Diensten erkannt werden können.

SOAP definiert die Regeln, nach denen verteilte Elemente einer Anwendung miteinander kommunizieren können, auch wenn Sie sich auf unterschiedlichen Plattformen befinden. SOAP basiert auf XML und ist daher Menschen lesbar. Das Opfer der leicht verständlichen Erstellung von SOAP ist die Größe. SOAP-Nachrichten sind größer als Nachrichten in vergleichbaren Protokollen. SOAP wurde entwickelt, um monolithische Anwendungen in mehrteilige Formen zu unterbrechen, ohne Sicherheit oder Kontrolle zu verlieren. WCF wurde daher für das Arbeiten mit dieser Art von System entwickelt, im Gegensatz zu GrpC, das als verteiltes System begann. WCF hat einige dieser Einschränkungen behoben, indem er proprietäre Erweiterungs Protokolle für den SOAP-Stapel entwickelt und dokumentiert hat, aber auf Kosten der fehlenden Unterstützung anderer Plattformen.

Windows Communication Foundation ist ein Framework zum Entwickeln von Diensten. Es wurde in den frühen 2000er Jahren entworfen, um Entwicklern bei der Verwendung von frühen SOA bei der Verwaltung der komplexen arbeiten mit SOAP zu helfen. Obwohl es nicht erforderlich ist, dass die Entwickler eigene SOAP-Protokolle schreiben, verwendet WCF weiterhin SOAP, um die Interoperabilität mit anderen Systemen zu ermöglichen. WCF wurde auch entwickelt, um Lösungen über mehrere Protokolle (http/1.1, net. TCP usw.) bereitzustellen.

## <a name="microservices"></a>Microservices

In microservice-Architekturen werden große Anwendungen als eine Sammlung von kleineren modularen Diensten erstellt. Jede Komponente führt eine bestimmte Aufgabe oder einen bestimmten Prozess aus, und die Komponenten sind für die Interoperabilität konzipiert, können jedoch nach Bedarf isoliert werden.

Zu den Vorteilen von-Diensten gehören:

- Änderungen und Upgrades können unabhängig voneinander gehandhabt werden.
- Die Fehlerbehandlung wird effizienter, da Probleme auf bestimmte Dienste nachverfolgt werden können, die dann unabhängig von den anderen Diensten isoliert, neu erstellt, getestet und erneut bereitgestellt werden.
- Die Skalierbarkeit kann auf bestimmte Instanzen oder Dienste und nicht auf die gesamte Anwendung beschränkt werden.
- Die Entwicklung kann über mehrere Teams hinweg erfolgen, und es treten weniger Probleme auf, als wenn viele Teams an einer einzelnen CodeBase arbeiten.

Der Umstieg auf die Erhöhung von Virtualisierung, Cloud Computing, Containern und Internet der Dinge hat zu einem kontinuierlichen Anstieg der-Dienste beigetragen. Allerdings sind die-Dienste nicht ohne Ihre Herausforderungen. Die fragmentierte/dezentralisierte Infrastruktur hat bei der Kommunikation zwischen den Diensten mehr Zeit auf den Bedarf an Einfachheit und Geschwindigkeit. Dies hat wiederum auf die manchmal mühsame und konforme Art von SOAP hingewiesen.

In dieser Umgebung wurde GrpC gestartet, 10 Jahre nach der ersten Veröffentlichung von Microsoft WCF. GrpC, das direkt von der internen Infrastruktur von Google (Stubby) entwickelt wurde, basiert nie auf denselben Standards und Protokollen, die die Parameter vieler früherer RPCs aufwiesen. Und GrpC war bisher nur auf http/2 basiert. Aus diesem Grund könnte es auf die neuen Funktionen von Advanced Transport Protocol zurückgreifen. Insbesondere bidirektionales Streaming, binäres Messaging und Multiplexing.

## <a name="about-this-guide"></a>Informationen zur Anleitung

In dieser Anleitung werden die wichtigsten Features von GrpC behandelt. In den frühen Kapiteln sehen Sie sich die wichtigsten Features von WCF genauer an und vergleichen Sie mit denen von GrpC. Es gibt an, wo direkte Korrelationen zwischen WCF und GrpC vorhanden sind und wie GrpC einen Vorteil bietet. Wenn es keine Korrelation zwischen WCF und GrpC gibt, oder wenn GrpC keine äquivalente Lösung für WCF anbieten kann, werden in diesem Handbuch Problem Umgehungen oder der Speicherort für weitere Informationen vorgeschlagen.

Mithilfe eines Satzes von WCF-Beispielanwendungen ist Kapitel 5 ein ausführlicher Einblick in das Umwandeln der Haupttypen von WCF-Diensten (Simple Request-Reply, unidirektional und Streaming) in ihre Entsprechungen in GrpC.

Im letzten Abschnitt des Buchs wird erläutert, wie Sie in der Praxis das beste von GrpC erhalten. Dieser Abschnitt enthält Informationen zur Verwendung zusätzlicher Tools wie docker-Container oder Kubernetes, um die Effizienz von GrpC zu nutzen. Außerdem enthält es einen detaillierten Einblick in die Überwachung mit Protokollierung, Metriken und verteilter Ablauf Verfolgung.

## <a name="who-this-guide-is-for"></a>Für wen ist dieser Leitfaden gedacht?

Dieses Handbuch wurde für Entwickler entwickelt, die in .NET Framework oder .net Core arbeiten, die WCF verwendet haben und die Ihre Anwendungen zu einer modernen RPC-Umgebung für .net Core 3,0 und höhere Versionen migrieren möchten. Das Handbuch ist möglicherweise im Allgemeinen nützlich für Entwickler, die ein Upgrade auf .net Core 3,0 ausführen und die integrierten GrpC-Tools verwenden möchten.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](grpc-overview.md)
