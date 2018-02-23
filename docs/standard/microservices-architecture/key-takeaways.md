---
title: Wichtige Erkenntnisse
description: ".NET-Microservicesarchitektur für .NET-Containeranwendungen | Wichtige Erkenntnisse"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2dbcfbe28f5461b7a40e8b0b49dbcf5e31490d70
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="key-takeaways"></a>Wichtige Erkenntnisse

In diesem Artikel werden die wichtigsten Erkenntnisse dieses Leitfadens zusammengefasst.

**Vorteile der Verwendung von Containern.** Containerbasierte Ansätze bieten einen wichtigen Vorteil bei der Kosteneinsparung, da Container einen Ansatz für Bereitstellungsprobleme darstellen, die durch das Fehlen von Abhängigkeiten in Produktionsumgebungen verursacht werden. Container verbessern DevOps und Produktionsabläufe erheblich.

**Container werden allgegenwärtig sein.** Auf Docker basierende Container entwickeln sich praktisch zum Standard in der Containerindustrie und werden von den meisten wichtigen Anbietern der Windows- und Linux-Ökosysteme unterstützt. Dies schließt Microsoft, Amazon AWS, Google und IBM ein. In der nahen Zukunft wird Docker wahrscheinlich sowohl in der Cloud als auch in lokalen Datencentern allgegenwärtig sein.

**Container als Bereitstellungseinheit.** Ein Docker-Container wird zur Standardeinheit für jede serverbasierte Anwendung oder jeden serverbasierten Dienst.

**Microservices.** Die Architektur der Microservices wird schnell zum bevorzugten Ansatz für verteilte und große oder komplexe unternehmenskritische Anwendungen, die auf mehreren unabhängigen Subsystemen in Form von autonomen Diensten basieren. In einer auf Microservices basierenden Architektur wird die Anwendung als eine Sammlung von Diensten erstellt, die unabhängig entwickelt, getestet, bereitgestellt und skaliert werden können. Dies kann jegliche verknüpfte autonome Datenbanken einschließen.

**Domänengesteuertes Design und SOA.** Die Architekturmuster der Microservices sind von der dienstorientierten Architektur (SOA) und vom domänengesteuerten Design (DDD) abgeleitet. Es ist wichtig, die Ansätze und Muster von DDD in Betracht zu ziehen, wenn Sie Microservices für Umgebungen mit sich weiterentwickelnden Geschäftsregeln, die eine bestimmte Domäne formen, entwerfen und entwickeln.

**Herausforderungen von Microservices.** Microservices bieten viele leistungsstarke Funktionen, wie z.B. unabhängige Bereitstellung, starke Subsystemgrenzen und technologische Vielfalt. Sie stellen jedoch auch viele neue Herausforderungen im Zusammenhang mit der Entwicklung von verteilten Anwendungen dar, z.B. fragmentierte und unabhängige Datenmodelle, die robuste Kommunikation zwischen Microservices, die letztendliche Konsistenz und operative Komplexität, die aus der aggregierten Protokollierung und der Überwachung der Informationen von mehreren Microservices resultiert. Diese Aspekte führen eine Komplexität ein, die höher als eine herkömmliche monolithische Anwendung ist. Deshalb sind nur spezifische Szenarios für auf Microservices basierende Anwendungen geeignet. Dazu gehören große und komplexe Anwendungen mit mehreren sich entwickelnden Subsystemen. In diesen Fällen lohnt es sich, in komplexere Softwarearchitektur zu investieren, da damit für bessere langfristige Flexibilität und Anwendungswartung gesorgt wird.

**Container für beliebige Anwendungen.** Container sind praktisch für Microservices, aber sie sind nicht auf diese beschränkt. Container können auch mit monolithischen Anwendungen verwendet werden, einschließlich älteren Anwendungen, die auf dem herkömmlichen .NET Framework basieren und durch Windows-Container modernisiert werden. Die Vorteile der Verwendung von Docker, wie z.B. das Lösen vieler Probleme bei der Bereitstellung in der Produktion und das Bereitstellen von hochmodernen Entwicklungs- und Testumgebungen, gelten für viele verschiedene Arten von Anwendungen.

**Der Vergleich von CLI mit IDE.** Mit Microsoft-Tools können Sie Ihren bevorzugten Ansatz verwenden, um .NET-Containeranwendungen zu entwickeln. Sie können mit einer CLI und einer Umgebung entwickeln, die auf einem Editor basiert, indem Sie die Docker-CLI und Visual Studio Code verwenden. Mit Visual Studio können Sie auch einen IDE-orientierten Ansatz und die einzigartigen Features für Docker verwenden, wie z.B. die Möglichkeit, Anwendungen mit mehreren Containern zu debuggen.

**Robuste Cloudanwendungen.** In cloudbasierten Systemen und verteilten Systemen generell gibt es immer das Risiko für Teilfehler. Da es sich bei Clients und Diensten um separate Vorgänge (Container) handelt, kann ein Dienst möglicherweise nicht schnell genug auf die Anforderung eines Clients reagieren. Ein Dienst kann zum Beispiel aufgrund eines Teilfehlers oder wegen Wartungsarbeiten nicht verfügbar sein. Der Dienst ist möglicherweise überlastet und antwortet sehr langsam auf Anforderungen, oder er ist aufgrund von Netzwerkproblemen vorübergehend nicht verfügbar. Deshalb muss eine cloudbasierte Anwendung diese Fehler annehmen und über eine passende Strategie verfügen, um diesen Fehlern entgegenzukommen. Zu diesen Strategien können Wiederholungsrichtlinien (erneutes Senden von Nachrichten oder Aufrufen) und das Implementieren von Sicherungsmustern gehören, um die exponentielle Last durch wiederholte Anforderungen zu vermeiden. Im Wesentlichen müssen cloudbasierte Anwendungen über robuste Mechanismen verfügen – entweder über eine benutzerdefinierte oder cloudbasierte Infrastruktur, wie z.B. allgemeine Frameworks von Orchestratoren oder Service Bussen.

**Sicherheit.** Die moderne Welt der Container und Microservices kann zu neuen Sicherheitslücken führen. Die grundlegende Anwendungssicherheit basiert auf der Authentifizierung und der Autorisierung. Es gibt mehrere Wege, diese zu implementieren. Die Containersicherheit enthält jedoch zusätzliche Schlüsselkomponenten, die für grundsätzlich sicherere Anwendungen sorgen. Die sichere Kommunikation mit anderen Anwendungen und Systemen ist ein sicherheitskritisches Element für die Erstellung von sichereren Anwendungen. Dafür werden häufig Anmeldeinformationen, Tokens, Kennwörter und andere vertrauliche Informationen benötigt. Diese werden in der Regel als Anwendungsgeheimnisse bezeichnet. Eine sichere Lösung muss bewährte Methoden für die Sicherheit befolgen, wie z.B. das Verschlüsseln von Geheimnissen während der Übermittlung, das Verschlüsseln von Geheimnissen im Ruhezustand und das Verhindern der unbeabsichtigten Preisgabe von Geheimnissen, wenn diese von der fertigen Anwendung verwendet werden. Diese Geheimnisse müssen sicher gespeichert werden. Sie können die Infrastruktur Ihres Orchestrators oder Cloudinfrastrukturen wie Azure Key Vault und deren Methoden für die Verwendung von Anwendungscode nutzen, um die Sicherheit zu unterstützen.

**Orchestratoren.** Containerbasierte Orchestratoren wie die, die in Azure Container Service bereitgestellt werden (Kubernetes, Mesos DC/OS und Docker Swarm), und Azure Service Fabric sind unentbehrlich für jede produktionsbereite Anwendung, die auf Microservices basiert, und jede Anwendung mit mehreren Containern mit erheblichen Anforderungen, Skalierbarkeitsanforderungen und konstanter Weiterentwicklung. In diesem Leitfaden wurden Orchestratoren und deren Rolle in Ansätzen eingeführt, die auf Microservices und Containern basieren. Wenn Sie sich aufgrund der Anforderungen Ihrer Anwendung auf komplexere Containeranwendungen zu bewegen, kann das Suchen zusätzlicher Ressourcen für weitere Informationen über Orchestratoren sich als nützlich erweisen.

>[!div class="step-by-step"]
[Zurück] (secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)
