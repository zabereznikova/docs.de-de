---
title: Wichtige Erkenntnisse
description: Entnehmen Sie wichtige Erkenntnisse dem Handbuch/E-Buch „.NET Microservices Architecture for Containerized .NET Applications“ (.NET Microservices-Architektur für .NET-Containeranwendungen), um einen schnellen Einblick in die allgemeinen Fragen bei der Verwendung einer Microservices-Architektur zu bekommen wie Vor- und Nachteile, DDD-Muster für Entwurf und Entwicklung sowie Stabilität, Sicherheit und die Verwendung von Orchestratoren.
ms.date: 10/19/2018
ms.openlocfilehash: 0e793a76fa59d6c131422480071d85ab3f18102c
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988777"
---
# <a name="key-takeaways"></a>Wichtige Erkenntnisse

In diesem Artikel werden die wichtigsten Erkenntnisse dieses Leitfadens zusammengefasst.

**Vorteile der Verwendung von Containern.** Containerbasierte Ansätze sorgen für wichtige Kosteneinsparungen, da sie dazu beitragen, Bereitstellungsprobleme zu reduzieren, die durch das Fehlen von Abhängigkeiten in Produktionsumgebungen verursacht werden. Container verbessern DevOps und Produktionsabläufe erheblich.

**Container werden allgegenwärtig sein.** Auf Docker basierende Container entwickeln sich praktisch zum Standard in der Industrie und werden von den wichtigsten Anbietern der Windows- und Linux-Ökosysteme wie Microsoft, Amazon AWS, Google und IBM unterstützt. Docker wird wahrscheinlich bald sowohl in der Cloud als auch in lokalen Datencentern allgegenwärtig sein.

**Container als Bereitstellungseinheit.** Ein Docker-Container wird zur Standardeinheit für jede serverbasierte Anwendung oder jeden serverbasierten Dienst.

**Microservices.** Die Architektur der Microservices wird schnell zum bevorzugten Ansatz für verteilte und große oder komplexe unternehmenskritische Anwendungen, die auf vielen unabhängigen Subsystemen in Form von autonomen Diensten basieren. In einer auf Microservices basierenden Architektur wird die Anwendung als Sammlung von Diensten erstellt, die unabhängig entwickelt, getestet, mit Versionsangaben versehen, bereitgestellt und skaliert werden. Jeder Dienst kann jegliche verwandte autonome Datenbank enthalten.

**Domänengesteuertes Design und SOA.** Die Architekturmuster der Microservices sind von der dienstorientierten Architektur (SOA) und vom domänengesteuerten Design (DDD) abgeleitet. Es ist wichtig, die Ansätze und Muster von DDD zu berücksichtigen, wenn Sie Microservices für Umgebungen mit sich weiterentwickelnden Geschäftsanforderungen und -regeln entwerfen und entwickeln.

**Herausforderungen von Microservices.** Microservices bieten viele leistungsstarke Funktionen, wie z.B. unabhängige Bereitstellung, starke Subsystemgrenzen und technologische Vielfalt. Sie stellen jedoch auch viele neue Herausforderungen im Zusammenhang mit der Entwicklung von verteilten Anwendungen dar, z.B. fragmentierte und unabhängige Datenmodelle, die robuste Kommunikation zwischen Microservices, die letztendliche Konsistenz und operative Komplexität, die aus der aggregierten Protokollierung und der Überwachung der Informationen von mehreren Microservices resultiert. Diese Aspekte führen eine Komplexitätsebene ein, die viel höher als eine herkömmliche monolithische Anwendung ist. Deshalb sind nur spezifische Szenarios für auf Microservices basierende Anwendungen geeignet. Dazu gehören große und komplexe Anwendungen mit mehreren sich entwickelnden Subsystemen. In diesen Fällen lohnt es sich, in komplexere Softwarearchitektur zu investieren, da damit für bessere langfristige Flexibilität und Anwendungswartung gesorgt wird.

**Container für beliebige Anwendungen.** Container sind praktisch für Microservices, können jedoch bei Verwendung von Windows-Containern auch für monolithische Anwendungen nützlich sein, die auf dem herkömmlichen .NET Framework basieren. Die Vorteile der Verwendung von Docker, wie z.B. das Lösen vieler Probleme bei der Bereitstellung in der Produktion und das Bereitstellen von hochmodernen Entwicklungs- und Testumgebungen, gelten für viele verschiedene Arten von Anwendungen.

**Der Vergleich von CLI mit IDE.** Mit Microsoft-Tools können Sie Ihren bevorzugten Ansatz verwenden, um .NET-Containeranwendungen zu entwickeln. Sie können mit einer CLI und einer Umgebung entwickeln, die auf einem Editor basiert, indem Sie die Docker-CLI und Visual Studio Code verwenden. Mit Visual Studio können Sie auch einen IDE-orientierten Ansatz und die einzigartigen Features für Docker verwenden, wie z.B. die Möglichkeit, Anwendungen mit mehreren Containern zu debuggen.

**Robuste Cloudanwendungen.** In cloudbasierten Systemen und verteilten Systemen generell gibt es immer das Risiko für Teilfehler. Da es sich bei Clients und Diensten um separate Vorgänge (Container) handelt, kann ein Dienst möglicherweise nicht schnell genug auf die Anforderung eines Clients reagieren. Ein Dienst kann zum Beispiel aufgrund eines Teilfehlers oder wegen Wartungsarbeiten nicht verfügbar sein. Der Dienst ist möglicherweise überlastet und antwortet langsam auf Anforderungen, oder er ist aufgrund von Netzwerkproblemen vorübergehend nicht verfügbar. Deshalb muss eine cloudbasierte Anwendung diese Fehler annehmen und über eine passende Strategie verfügen, um diesen Fehlern entgegenzukommen. Zu diesen Strategien können Wiederholungsrichtlinien (erneutes Senden von Nachrichten oder Aufrufen) und das Implementieren von Sicherungsmustern gehören, um die exponentielle Last durch wiederholte Anforderungen zu vermeiden. Im Wesentlichen müssen cloudbasierte Anwendungen über robuste Mechanismen verfügen – entweder auf Basis einer Cloud- oder benutzerdefinierten Infrastruktur, wie z.B. den von Orchestratoren oder Service Busses bereitgestellten allgemeinen.

**Sicherheit.** Die moderne Welt der Container und Microservices kann zu neuen Sicherheitslücken führen. Je nach Authentifizierung und Autorisierung gibt es mehrere Wege, diese grundlegende Anwendungssicherheit zu implementieren. Die Containersicherheit muss jedoch zusätzliche Schlüsselkomponenten berücksichtigen, die für grundsätzlich sicherere Anwendungen sorgen. Die sichere Kommunikation mit anderen Anwendungen und Systemen ist ein sicherheitskritisches Element für die Erstellung von sichereren Anwendungen. Dafür werden häufig Anmeldeinformationen, Tokens, Kennwörter und Ähnliches benötigt. Diese werden in der Regel als Anwendungsgeheimnisse bezeichnet. Eine sichere Lösung muss bewährte Methoden für die Sicherheit befolgen, wie z.B. das Verschlüsseln von Geheimnissen während der Übermittlung und im Ruhezustand sowie das Verhindern der Preisgabe von Geheimnissen, wenn diese von der fertigen Anwendung verwendet werden. Diese Geheimnisse müssen sicher gespeichert und aufbewahrt werden, wie bei der Verwendung von Azure Key Vault.

**Orchestratoren.** Containerbasierte Orchestratoren wie Azure Kubernetes Service und Azure Service Fabric sind wichtiger Bestandteil jeder signifikanten Anwendung auf Microservice- und Containerbasis. Diese Anwendungen bringen hohe Komplexität sowie Anforderungen an die Skalierbarkeit mit sich und durchlaufen eine konstante Weiterentwicklung. In diesem Leitfaden wurden Orchestratoren und deren Rolle in Ansätzen eingeführt, die auf Microservices und Containern basieren. Wenn Sie sich aufgrund der Anforderungen Ihrer Anwendung auf komplexere Containeranwendungen zu bewegen, kann das Suchen zusätzlicher Ressourcen für weitere Informationen über Orchestratoren sich als nützlich erweisen.

>[!div class="step-by-step"]
>[Vorherige](secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)
