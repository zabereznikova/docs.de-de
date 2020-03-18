---
title: Microservicearchitektur
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über die Microservicearchitektur
ms.date: 09/20/2018
ms.openlocfilehash: d1c58d218be9e5f8c0ae8ae732f9bdd06674a2c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "71834389"
---
# <a name="microservices-architecture"></a>Microservicearchitektur

Wie der Name schon sagt, ist eine Microservicesarchitektur der Ansatz, der beim Erstellen einer Serveranwendung als mehrere kleine Dienste verwendet wird. Das bedeutet, dass eine Microservicearchitektur hauptsächlich auf das Back-End ausgerichtet ist, obwohl der Ansatz auch für das Front-End genutzt wird. Jeder Dienst wird in einem eigenen Prozess ausgeführt und kommuniziert über Protokolle wie HTTP/HTTPS, WebSockets oder [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) mit anderen Prozessen. Jeder Microservice implementiert eine bestimmte End-to-End-Domäne oder Unternehmensfunktion in einer bestimmten Kontextgrenze und muss autonom entwickelt worden und unabhängig bereitstellbar sein. Außerdem muss jeder Dienst ein eigenes Domänendatenmodell und eine eigene Domänenlogik aufweisen (Souveränität und dezentralisierte Datenverwaltung), und kann auf verschiedenen Datenspeichertechnologien (SQL, NoSQL) und Programmiersprachen basieren.

Welche Größe sollte ein Microservice haben? Beim Entwickeln eines Microservices sollte Größe keine Rolle spielen. Stattdessen sollte das Augenmerk darauf liegen, lose gekoppelte Dienste zu erstellen, damit bei der Entwicklung, Bereitstellung und Skalierung für jeden Dienst Autonomie gewährleistet ist. Natürlich sollten Sie darauf achten, Microservices so klein wie möglich zu entwerfen, wenn nicht zu viele direkte Abhängigkeiten mit anderen Microservices bestehen. Wichtiger als die Größe eines Microservices ist die interne Kohäsion, die er benötigt, und seine Unabhängigkeit von anderen Diensten.

Welche Vorteile hat eine Microservicearchitektur? Die Antwort lautet: langfristige Flexibilität. Mit Microservices lassen sich komplexe, große und hochgradig skalierbare Systeme einfacher verwalten, da Anwendungen aus vielen unabhängig bereitstellbaren Diensten erstellt werden, die präzise und autonome Lebenszyklen haben.

Ein weiterer Vorteil ist, dass Microservices unabhängig voneinander horizontal hochskaliert werden können. Statt einer riesigen monolithischen Anwendung können Sie nur bestimmte Microservices horizontal hochskalieren. So können Sie nur die Funktionsbereiche skalieren, die mehr Verarbeitungsleistung oder Netzwerkbandbreite zum Erfüllen der Nachfrage brauchen, anstatt nicht benötigte Anwendungsbereiche zu erweitern. Dadurch sparen Sie auch Kosten, da Sie weniger Hardware benötigen.

![Diagramm zu den Unterschieden zwischen den beiden Bereitstellungsmethoden.](./media/microservices-architecture/monolith-deployment-vs-microservice-approach.png)

**Abbildung 4-6:** Monolithische Bereitstellung im Vergleich zum Microservicesansatz

Wie in Abbildung 4-6 gezeigt, skaliert die Anwendung im traditionellen monolithischen Ansatz durch Klonen der gesamten App auf mehrere Server/VMs. Beim Microservicesansatz ist die Funktion in kleinere Dienste unterteilt, sodass jeder Dienst unabhängig skaliert werden kann. Die Nutzung von Microservices ermöglicht flexible Änderungen und eine schnelle Iteration der einzelnen Microservices, da Sie bestimmte kleine Bereiche von großen skalierbaren und komplexen Anwendungen ändern können.

Das Entwerfen von Anwendungen, die auf präzisen Microservices basieren, ermöglicht eine fortlaufende Integration und kontinuierliche Bereitstellung und beschleunigt die Bereitstellung neuer Funktionen in der Anwendung. Ein präziser Entwurf einer Anwendung ermöglicht es Ihnen außerdem, Microservices isoliert auszuführen und zu testen und sie unabhängig voneinander weiterzuentwickeln und dabei eindeutige Verträge zwischen ihnen beizubehalten. Solange Sie die Schnittstellen oder Verträge nicht ändern, können Sie die interne Implementierung jedes Microservices ändern oder eine neue Funktionalität hinzufügen, ohne dass andere Microservices in ihrer Funktion negativ beeinflusst werden.

Im Folgenden finden Sie einige wichtige Aspekte für eine erfolgreiche Produktionsphase mit einem auf Microservices basierenden System:

- Überwachung und Integrität der Dienste und der Infrastruktur

- Skalierbare Infrastruktur der Dienste, d.h. Cloud und Orchestratoren

- Entwurf und Implementierung von Sicherheitsmaßnahmen auf mehreren Ebenen: Authentifizierung, Autorisierung, Verwaltung geheimer Schlüssel, sichere Kommunikation usw.

- Schnelle Anwendungsübermittlung, in der Regel mit verschiedenen Teams, die sich auf verschiedene Microservices konzentrieren

- DevOps und CI/CD-Methoden und -Infrastruktur

In diesem Leitfaden werden nur die ersten drei abgedeckt oder eingeführt. Die letzten beiden Punkte, die mit dem Lebenszyklus der Anwendung zu tun haben, finden Sie im E-Book [Containerized Docker Application Lifecycle with Microsoft Platform and Tools (Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und -Tools)](https://aka.ms/dockerlifecycleebook).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Mark Russinovich. Microservices: An application revolution powered by the cloud (Microservices: Revolution der App-Entwicklung in der Cloud)**  \
  <https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/>

- **Martin Fowler. Microservices** \
  <https://www.martinfowler.com/articles/microservices.html>

- **Martin Fowler. Microservice Prerequisites (Voraussetzungen für Microservices)**  \
  <https://martinfowler.com/bliki/MicroservicePrerequisites.html>

- **Jimmy Nilsson. Chunk Cloud Computing (Einteilen von Cloud Computing)**  \
  <https://www.infoq.com/articles/CCC-Jimmy-Nilsson>

- **Cesar de la Torre. Containerized Docker Application Lifecycle with Microsoft Platform and Tools (Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Microsoft-Tools)** (E-Book zum Download) \
  <https://aka.ms/dockerlifecycleebook>

>[!div class="step-by-step"]
>[Zurück](service-oriented-architecture.md)
>[Weiter](data-sovereignty-per-microservice.md)
