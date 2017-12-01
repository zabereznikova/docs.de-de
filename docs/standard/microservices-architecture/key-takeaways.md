---
title: die wichtigsten Vorteile
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | die wichtigsten Vorteile"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b557d0b641bfe95c025cadb13f82c3f8927f4bc8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="key-takeaways"></a>Die wichtigsten Vorteile

Als eine Zusammenfassung und die wichtigsten Vorteile sind die folgenden die wichtigsten Schlussfolgerungen aus diesem Handbuch.

**Vorteile der Verwendung von Containern.** Container-basierten Lösungen bereitstellen den wichtigen Vorteil, dass Kosten einsparen, da Container eine Lösung für die Bereitstellungsproblemen, die aufgrund des fehlenden Abhängigkeiten in produktionsumgebungen sind. DevOps und Produktions-Vorgänge wird von Containern erheblich verbessern.

**Container werden weit verbreitete.** Docker-basierte Container werden Industriestandard in Container-Branche, von der wichtigsten Hersteller in der Windows- und Linux-Ökosysteme unterstützt immer. Dies schließt Microsoft, Amazon AWS Google und IBM. In der nahen Zukunft wird die Docker wahrscheinlich in Cloud- und lokalen Datencentern weit verbreitete haben.

**Die Container als eine Einheit der Bereitstellung.** Docker-Container ist die Standardeinheit für die Bereitstellung für alle Server-basierten Anwendung oder ein Dienst immer.

**Microservices.** Die Architektur des Microservices gewinnt den optimalen Ansatz für verteilte und großen oder komplexen unternehmenswichtigen Anwendungen basierend auf mehrere unabhängige Subsysteme in Form von autonome Dienste. In einer Microservice-basierte Architektur basiert die Anwendung als eine Sammlung von Diensten, die entwickelt, getestet und Versionsangaben bereitgestellt, und unabhängig voneinander skaliert werden können; Dies kann verknüpfte autonome Datenbank einschließen.

**Domain driven Design und SOA.** Die Microservices Architekturmuster abgeleitet von dienstorientierten Architektur (SOA) und Domain driven Design (DDD) ab. Beim Entwerfen und entwickeln Microservices für Umgebungen mit Geschäftsregeln Strukturieren einer bestimmten Domäne weiterentwickelt, ist es wichtig, und Konto DDD Ansätze und Muster angewendet werden.

**Microservices Herausforderungen.** Microservices bieten viele leistungsstarke Funktionen wie unabhängige Bereitstellung starken Subsystem Grenzen und Technologie Vielfalt an. Allerdings löst sie auch viele neue Herausforderungen, die im Zusammenhang mit für die Entwicklung der verteilten Anwendung, z. B. fragmentiert und unabhängige Datenmodelle, robusten Kommunikation zwischen Microservices eventuellen Konsistenz und operative Komplexität, die durch entsteht aggregieren Sie die Protokollierung und Überwachung von Informationen aus mehreren Microservices. Diese Aspekte stellen ein höheres Maß an Komplexität als eine herkömmliche monolithischen vor. Dies hat zur Folge, dass nur bestimmte Szenarien für Microservice-basierte Anwendungen geeignet ist. Dazu gehören große und komplexe Anwendungen mit mehreren wachsenden Subsysteme; in diesen Fällen lohnt sich in einer komplexeren Softwarearchitektur investieren da besser langfristigen Flexibilität und Anwendungswartung bereitgestellt wird.

**Container für jede Anwendung.** Container eignen sich gut für Microservices, aber Sie sind nicht exklusiv für sie. Container können auch mit monolithisch-Anwendungen, einschließlich Legacyanwendungen auf herkömmlichen .NET Framework basiert und modernisiert über Windows-Containern verwendet werden. Die Vorteile der Verwendung von Docker, wie viele Bereitstellung zur Produktion Probleme lösen und das Bereitstellen von Entwicklungs- und testumgebungen hochmodern gelten für viele verschiedene Arten von Anwendungen.

**CLI im Vergleich zur IDE.** Mit Microsoft-Tools können Sie .NET Sammelartikeleinheit mit Ihren bevorzugten Ansatz entwickeln. Sie können mit einem CLI und eine Editor-basierte Umgebung entwickeln, mit dem Docker-Befehlszeilenschnittstelle und den Visual Studio-Code. Oder Sie können Sie einen IDE-orientierten Ansatz mit Visual Studio und der einzigartigen Funktionen für Docker, wie z. B. die Möglichkeit zum Debuggen von Multi-containeranwendungen.

**Flexibler Cloud-Anwendungen.** In der Cloud-basierte Systeme und verteilter Systeme im Allgemeinen besteht immer das Risiko eines Ausfalls teilweise. Da Clients und Dienste separate Prozesse (Container) sind, ein Dienst zeitnah auf einem Client-Anforderung reagiert möglicherweise nicht. Z. B. kann ein Dienst aufgrund eines Fehlers teilweise oder zu Wartungszwecken ausgeschaltet; der Dienst möglicherweise überladen werden und fordert extrem langsam zu reagieren. oder sie einfach möglicherweise nicht verfügbar für kurze Zeit aufgrund von Netzwerkproblemen. Daher muss eine Cloud-basierte Anwendung nutzen dieser Fehler und halten Sie eine Strategie bereit, auf diese Fehler reagieren. Diese Strategien können wiederholungsrichtlinien (erneuten Senden von Nachrichten oder Wiederholungsversuche von Anforderungen) enthalten, und Laden Sie implementierende Trennschalter Muster exponentiellen Vermeiden von wiederholten Anforderungen. Im Wesentlichen benötigen cloudbasierte Anwendungen robuste Mechanismen – benutzerdefinierte Argumente oder Argumente basierend auf Cloudinfrastruktur, z. B. auf hoher Ebene Frameworks Orchestrators oder Service Bus.

**Sicherheit.** Unsere modernen Welt von Containern und Microservices kann neue Sicherheitslücken verfügbar machen. Grundlegender anwendungssicherheit basiert auf Authentifizierung und Autorisierung. mehrere Methoden vorhanden sein, damit diese implementieren. Container-Sicherheit umfasst jedoch weitere wichtige Komponenten, die grundsätzlich sicherer Anwendungen führen. Ein sicherheitskritisches Element zum Erstellen sicherere Anwendungen hat eine sichere Möglichkeit der Kommunikation mit anderen apps und Systemen, etwa erfordert oft Anmeldeinformationen, Token, Kennwörter und andere Arten von vertraulichen Informationen – in der Regel als Anwendung geheime Schlüssel bezeichnet. Sichere Lösung muss, z. B. Verschlüsselung geheime Schlüssel bei der Übertragung bewährter Sicherheitsmethoden; Verschlüsseln von geheimen Daten im Ruhezustand; und verhindert, dass Kennwörter nicht unbeabsichtigt Speicherverluste verursachen, wenn von der endgültigen Anwendung genutzt. Dieser geheimen Schlüssel gespeichert und sicher aufbewahrt werden, an einer Stelle werden müssen. Um für Sicherheit zu finden, können Sie nutzen die ausgewählte Orchestrator-Infrastruktur oder Cloud-Infrastruktur wie Azure Key Vault und die Methoden, die es Anwendungscode verwenden bereitstellt.

**Orchestrators.** Container-basierte Orchestrators wie den angebotenen im Azure-Container-Dienst (Kubernetes Mesos DC/OS und Docker Containerhostclustern) und Azure Service Fabric sind unverzichtbar für eine produktionsbereite Microservice-basierte Anwendung und für jeden Multi-container die Anwendung mit wesentlich komplexer, skalierbarkeitserfordernisse und Konstanten Entwicklung. Dieses Handbuch wurde Orchestrators und ihrer Rolle in Microservice und Container-basierten Lösungen eingeführt. Wenn die anwendungsanforderungen Sie gegen komplexen Datenvolumes apps verschieben, finden es nützlich, um zusätzliche Ressourcen für Weitere Informationen zu Orchestrators seek Sie

>[!div class="step-by-step"]
[Vorherigen] (secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)
