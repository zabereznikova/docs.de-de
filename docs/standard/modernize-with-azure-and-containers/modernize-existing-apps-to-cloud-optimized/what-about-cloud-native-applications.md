---
title: Was geschieht mit Cloudnativen Anwendungen?
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Was geschieht mit Cloudnativen Anwendungen?
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 10f7761b7c0d2ddd8cb9247b1a02aa49cdc4e5d4
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679280"
---
# <a name="what-about-cloud-native-applications"></a>Was geschieht mit Cloudnativen Anwendungen?

Obwohl [Cloudnative](https://azure.microsoft.com/overview/cloudnative/) Anwendungen sind nicht im Mittelpunkt dieses Handbuchs, es ist hilfreich, um einen Überblick über diese modernisierungsreifegrad zu erhalten, und klicken Sie zur Unterscheidung von Cloudoptimierte Anwendungen.

Abbildung 4-3 positioniert Native Cloud-apps in der Anwendung Modernisierung Reifegrads erforderlich:

![Positionieren Native Cloudanwendungen](./media/image3.png)

> **Abbildung 4: 3.** Positionieren Native Cloudanwendungen

Die Native Cloud-modernisierungsreifegrad ist in der Regel neue Investitionen erforderlich. Verschieben auf die Native Cloud - Ebene in der Regel hängt von unternehmensanforderung zu modernisieren Sie Anwendungen so weit wie möglich ist, um deutlich zu verbessern, Skalierung in großen Anwendungen durch autonome Subsysteme (Microservices), die bereitgestellt werden können erstellen und skalieren unabhängig beanspruchen Sie aus anderen Bereichen der Anwendung während Sie zugleich senken in die lange Laufzeit und Erhöhung Weiterentwicklung-Agilität, diese autonomen app-Komponenten, die angeben erheblich Vorteile.

Basiert die Hauptsäulen von cloudbasierten Anwendungen auf Ansätze für Microservices-Architektur, die mit Agilität weiterentwickeln und an Grenzen, die nur schwer zu erreichen in einer monolithischen Architektur, die entweder lokal oder Cloud bereitgestellt, skaliert werden kann Umgebung.

Abbildung 4-4 zeigt die wesentlichen Merkmale von Native Cloud-Modell.

> ![Native Cloud-Eigenschaften sind cloudrobust, orchestratoren für Container, Microservices und serverlose Apps](./media/image4.png)
>
> **Abbildung 4-4.** Native Cloud-Eigenschaften

Darüber hinaus können Sie grundlegende moderner Web-apps und Native Cloud-apps erweitern, durch das Hinzufügen von anderen Diensten, wie Sie künstliche Intelligenz (KI), Machine Learning (ML) und IoT. Sie können eines dieser Dienste verwenden, um einen der möglichen Cloudoptimierte Ansätze zu erweitern.

Der grundlegende Unterschied in Anwendungen auf der Ebene des Cloudnativen besteht in der Anwendungsarchitektur. Native Cloudanwendungen sind per Definition apps, die auf Microservices basieren. Native Cloud-apps erfordern spezielle Architekturen, Technologien und Plattformen, im Vergleich zu einer monolithischen Webanwendung oder den herkömmlichen N-Tier-Anwendung.

## <a name="cloud-native-applications-details"></a>Native Cloudanwendungen-details

Cloudnative ist eine erweiterte oder ausgereifte nur vorrübergehend für umfangreiche und geschäftskritische Anwendungen. Cloudbasierte Anwendungen erfordern in der Regel auf, Architektur und Entwurf, die von Grund auf neu, nicht erstellt werden, indem Sie vorhandene Anwendungen modernisieren. Der Hauptunterschied zwischen einer Cloudnative Anwendungs- und eine einfachere Cloudoptimierte Web-app ist die Empfehlung, Microservices-Architekturen in einem cloudbasierten Ansatz zu verwenden. Cloudoptimiert apps können auch monolithische Web-apps oder N-schichtige apps sein.

Die [zwölf-Faktoren-App](https://12factor.net/) (eine Sammlung von Mustern, die Ansätze für Microservices eng miteinander verknüpft sind) gilt auch für Native Cloud-Architekturen erforderlich.

Die [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) ist eine primäre Befürworter von Native Cloud-Prinzipien. Microsoft ist ein [Mitglied der CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Für eine Beispieldefinition und Weitere Informationen zu den Eigenschaften von cloudbasierten Anwendungen finden Sie im Gartner-Artikel [wie entwerfen und entwickeln Native Cloudanwendungen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). Spezielle Anweisungen von Microsoft dazu, wie Sie eine Native Cloud-Anwendung zu implementieren, finden Sie [.NET Microservices: Architektur für containerisierte .NET-Anwendungen](https://aka.ms/microservicesebook).

Der wichtigste Faktor zu beachten, wenn Sie eine vollständige Anwendung für das Native Cloud-Modell migrieren ist, dass Sie auf eine auf Microservices basierende Architektur überarbeiten müssen. Dies erfordert natürlich eine erhebliche Investition in der Entwicklung aufgrund der großen umgestaltungsprozess Beteiligten. Diese Option wird für unternehmenskritische Anwendungen, die Skalierbarkeit und bessere langfristige Flexibilität benötigen, in der Regel ausgewählt. Aber Sie könnten dann starten, auf dem Weg cloudnative durch Hinzufügen von Microservices nur wenige neue Szenarien und schließlich die Anwendung vollständig als Microservices umzugestalten. Dies ist ein inkrementeller Ansatz, der die beste Option für einige Szenarien ist.

## <a name="what-about-microservices"></a>Was ist mit Microservices?

Es ist wichtig, zu verstehen, Microservices und wie sie funktionieren, wenn Sie cloudbasierte Anwendungen für Ihre Organisation in Betracht ziehen.

Die Microservices-Architektur ist, einen erweiterten Ansatz, mit denen Sie für Anwendungen, die erstellt werden, von Grund auf neu, oder wenn Sie vorhandene Anwendungen für Native Cloud-Anwendungen entwickeln. Sie können zunächst einige Microservices für vorhandene Anwendungen Informationen zu den neuen Microservices Paradigmen hinzufügen. Aber Sie müssen natürlich Architect und Code, besonders für diese Art von Architekturansatz.

Microservices sind jedoch nicht für alle neuen oder moderne Anwendung erforderlich. Microservices sind nicht "Gegenmittel", und sie nicht die einzigen, bewährte Möglichkeit, jede Anwendung zu erstellen sind. Wie und wann Sie Microservices verwenden, hängt von der Art der Anwendung, die Sie erstellen müssen.

Die Microservices-Architektur wird der bevorzugte Ansatz für verteilte und große oder komplexe unternehmenskritische Anwendungen immer, die auf mehreren unabhängigen Subsystemen in Form von autonomen Diensten basieren. In einer Basis von Microservices-Architektur ist eine Anwendung als eine Sammlung von Diensten erstellt, die unabhängig entwickelt, getestet, versioniert, bereitgestellt und skaliert werden können. Dies kann verknüpfte autonome Datenbank pro Microservice einschließen.

Eine ausführliche Betrachtung einer Microservices-Architektur, die Sie mithilfe von .NET Core implementieren können, finden Sie im herunterladbare PDF-Datei-e-Book [.NET Microservices: Architektur für containerisierte .NET-Anwendungen](https://aka.ms/microservicesebook). Dieses Handbuch ist auch verfügbar [online](../../microservices-architecture/index.md).

Aber auch in Szenarien, die in der Microservices leistungsstarke Funktionen unabhängige Bereitstellung, starke subsystemgrenzen und technologische Vielfalt bieten-auch viele neue Herausforderungen ausgelöst. Die Herausforderungen beziehen sich auf die Entwicklung einer verteilten Anwendung, z.B. fragmentierte und unabhängige Datenmodelle; erreichen robuste Kommunikation zwischen Microservices; die Notwendigkeit der letztlichen Konsistenz; und Komplexität des Betriebs. Microservices stellen ein höheres Maß an Komplexität, die im Vergleich zu herkömmlichen monolithischen Anwendungen vor.

Aufgrund der Komplexität einer Microservices-Architektur sind nur für bestimmte Szenarien und bestimmte Anwendungstypen für Microservice basierende Anwendungen geeignet. Dazu gehören große und komplexe Anwendungen, die mehrere Subsysteme weiterentwickelt. In diesen Fällen lohnt es Investitionen in eine komplexere Softwarearchitektur, für höhere langfristige Flexibilität und Anwendungswartung effizienter. Aber für weniger komplexe Szenarien ist es möglicherweise besser, um eine monolithische Anwendung Ansatz fortzusetzen, oder einfacher N-schichtige fast erreicht wird.

Ein letzter Hinweis, auch wenn bei diesem Vorgang werden über dieses Konzept sich wiederholende, sollte nicht Sie betrachten Sie mithilfe von Microservices in Ihren Anwendungen als "Cloud- oder gar nichts." Sie können erweitern und bestehende monolithische Anwendungen durch Hinzufügen neuer, kleine Szenarien, die auf Microservices basierenden weiterentwickeln. Sie müssen nicht von Grund auf neu, um mit einem microservice-Architektur-Ansatz zu arbeiten beginnen. In der Tat empfehlen wir, dass Sie von der Verwendung einer vorhandenen monolithischen oder N-Tier-Anwendung durch Hinzufügen von neuen Szenarien entwickeln. Schließlich können Sie die Anwendung in autonomen Komponenten oder Microservices unterteilen. Sie können die Weiterentwicklung Ihrer monolithischen Anwendungen in einer Microservices-Richtung, Schritt für Schritt starten.

In jedem Fall konzentriert der Rest dieses Leitfadens vorhanden vor allem auf "keine Microservices basierende apps", da diese Anleitung vor allem die Modernisierung vorhandener Apps als Ziel verwendet, die normalerweise monolithische oder N-schichtige Architekturen.

> [!div class="step-by-step"]
> [Zurück](microsoft-technologies-in-cloud-optimized-applications.md)
> [Weiter](deploy-existing-net-apps-as-windows-containers.md)
