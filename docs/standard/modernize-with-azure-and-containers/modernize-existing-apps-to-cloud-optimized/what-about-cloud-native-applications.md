---
title: Was ist mit der Cloud-systemeigenen Anwendungen?
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Was ist mit der Cloud-systemeigenen Anwendungen?
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 0e880689001ece2b770811cfbe3fea43aa425b32
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
---
# <a name="what-about-cloud-native-applications"></a>Was ist mit der Cloud-systemeigenen Anwendungen?

Obwohl [Cloud systemeigenen](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) Anwendungen sind nicht der Schwerpunkt dieses Handbuchs ist es hilfreich, um einen Überblick über diese Modernisierung Reifegrad haben und zur Unterscheidung von Cloud-optimierte Anwendungen.

Abbildung 4 – 3 positioniert Cloud systemeigenen apps in der Anwendung Modernisierung Reifegrade:

![Positionieren von Cloud-systemeigene Anwendungen](./media/image3.png)

> **Abbildung 4 – 3.** Positionieren von Cloud-systemeigene Anwendungen

Cloud-systemeigenen Modernisierung Entwicklungsstands erfordert in der Regel neue Entwicklung Investitionen. In der Regel auf die Cloud - systemeigenen Ebene verschieben wird von geschäftliche Notwendigkeit modernisieren drastisch verbessern Skalierung in großen Anwendungen durch autonome Subsysteme (Microservices), die bereitgestellt werden können, erstellen und Skalierung so weit wie möglich Anwendungen unabhängig gesteuert konkurrieren Sie aus anderen Bereichen der Anwendung Kosten in die lange Flexibilität eines Begriff und Zunahme Entwicklung von diese autonomen app Teile, die bereitstellen eingespart erhebliche Vorteile. 

Die wichtigsten Säulen von [Cloud systemeigenen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungen basieren auf Microservices Architektur Ansätze, die mit Agilität entwickeln und zu skalieren, um Grenzwerte, die schwierig, in einer monolithischen Architektur bereitgestellt, die entweder zu erzielen können lokaler oder cloud-Umgebung.

Abbildung 4-4 zeigt die Hauptmerkmale des systemeigenen Cloud-Modells.  

> ![Cloud-systemeigenen Merkmale sind Microservices, Container, Cloud-robusten, Orchestrators und serverles](./media/image4.png)
>
> **Abbildung 4-4.** Merkmale der Cloud-systemeigen

Darüber hinaus können Sie grundlegende moderner Web-apps und Cloud-systemeigenen apps durch Hinzufügen von anderen Diensten, wie KI (AI), Machine Learning (ML) und IoT erweitern. Sie können eines dieser Dienste verwenden, um einen der möglichen Cloudoptimiertes Ansätze erweitern.

Der grundlegende Unterschied in Anwendungen auf der Cloud-systemeigenen Ebene ist in der Anwendungsarchitektur. [Cloud-systemeigenen](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) Anwendungen sind per Definition apps, die auf Microservices basieren. Cloud-systemeigenen apps erfordern besondere Architekturen, Technologien und Plattformen, im Vergleich zu einer monolithischen Webanwendung oder die herkömmliche N-Tier-Anwendung.

## <a name="cloud-native-applications-details"></a>Details der Cloud-systemeigene Anwendungen

[Cloud-systemeigenen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) ist ein erweiterter oder ausgereifte Zustand für große und unternehmenswichtige Anwendungen. Cloud-systemeigenen Anwendungen erfordern i. d. r. auf, Architektur und Entwurf, die von Grund auf neu, sondern Modernisierung vorhandene Anwendungen erstellt werden. Der Hauptunterschied zwischen einer Cloud-systemeigene Anwendung und eine einfachere Cloudoptimiertes Web-app ist die Empfehlung, Microservices Architekturen in einem Cloud-einheitlichen Ansatz zu verwenden. Cloud-optimierten apps können auch aufgrund eines monolithischen Web-apps oder apps, die N-Tier sein.

Die [zwölf Faktor App](https://12factor.net/) (eine Sammlung von Mustern, die Microservices Ansätzen eng miteinander verknüpft sind), wird auch als Voraussetzung für [Cloud systemeigenen](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) Anwendungsarchitektur.

Die [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) ist eine primäre Promoter systemeigenen Cloud-Grundsätzen. Microsoft ist ein [Mitglied der CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Eine Beispiel-Definition und Weitere Informationen über die Eigenschaften des Cloud-systemeigenen Anwendungen finden Sie im Gartner Artikel [zum Entwerfen und entwickeln Cloud-systemeigenen Anwendungen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). Bestimmte Anleitung von Microsoft dazu, wie eine systemeigene Cloud-Anwendung implementiert wird, finden Sie unter [.NET Microservices: Architektur für .NET Sammelartikeleinheit](https://aka.ms/microservicesebook).

Der wichtigste Faktor, berücksichtigen bei der Migration von einer vollständigen Anwendung, die [Cloud systemeigenen](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) Modell ist, dass Sie auf eine Microservices-basierte Architektur neu entwerfe müssen. Dies erfordert eine erhebliche Investition in der Entwicklung deutlich, aufgrund der großen beteiligten Umgestaltung. Diese Option wird normalerweise für unternehmenswichtige Anwendungen ausgewählt, die neue Ebenen von Skalierbarkeit und langfristige Agilität benötigen. Allerdings konnte zunächst Aneignung von Cloud-systemeigen durch Hinzufügen von Microservices nur wenige neue Szenarien und schließlich die Anwendung vollständig als Microservices umzugestalten. Dies ist ein inkrementeller Ansatz, der die beste Option für einige Szenarien ist.

## <a name="what-about-microservices"></a>Welche Rolle spielt Microservices? 

Grundlegendes zu Microservices und deren Funktionsweise ist wichtig, wenn Sie Cloud-systemeigenen Anwendungen für Ihre Organisation in Betracht ziehen.

Die Architektur des Microservices wird einen erweiterten Ansatz, den Sie für Anwendungen verwenden können, die erstellt werden, von Grund auf neu, oder wenn Sie vorhandene Anwendungen gegen Cloud systemeigenen Anwendungen entwickeln. Sie können zunächst einige Microservices zu vorhandenen Anwendungen, um weitere Informationen zu den neuen Microservices Paradigmen hinzufügen. Aber es ist offensichtlich, Architekt und Code, die speziell für diese Art von architektonische Ansatz werden müssen.

Microservices sind jedoch nicht für alle neuen oder modernen Anwendung obligatorisch. Microservices sind nicht "Magic Aufzählungszeichen", und sie sind nicht die einzigen, bewährte Möglichkeit, jede Anwendung zu erstellen. Wie und wann Sie Microservices verwenden, hängt vom Typ der Anwendung, die Sie erstellen möchten.

Die Architektur des Microservices gewinnt den optimalen Ansatz für verteilte und großen oder komplexen unternehmenswichtigen Anwendungen, die auf mehrere unabhängige Subsysteme in Form von autonome Services basieren. In einer Microservices-basierte Architektur basiert eine Anwendung als eine Sammlung von Diensten, die unabhängig entwickelt, getestet und Versionsangaben bereitgestellt und skaliert werden können. Dies kann verknüpfte autonome Datenbank pro Microservice einschließen.

Eine ausführliche Beschreibung der in eine Microservices-Architektur, die Sie mithilfe von .NET Core implementieren können, finden Sie unter herunterladbare PDF-Datei-e-Book [.NET Microservices: Architektur für .NET Sammelartikeleinheit](https://aka.ms/microservicesebook). Dieses Handbuch auch steht [online](../../microservices-architecture/index.md).

Aber auch in Szenarien, in dem Microservices bieten eine leistungsstarke Funktionen typunabhängig-Bereitstellung, sicheres Subsystem Grenzen und Technologie Vielfalt-auch viele neue Herausforderungen ausgelöst. Die Herausforderungen beziehen sich auf die Entwicklung einer verteilten Anwendung, z. B. fragmentiert und unabhängige Datenmodelle; erzielen von robusten Kommunikation zwischen Microservices; die Notwendigkeit für eventuelle Konsistenz; und operative Komplexität. Microservices stellen ein höheres Maß an Komplexität im Vergleich zu herkömmlichen monolithischen Anwendungen vor.

Aufgrund der Komplexität einer Microservices-Architektur sind nur für bestimmte Szenarien und bestimmte Anwendungstypen für Microservice-basierte Anwendungen geeignet. Dazu zählen große und komplexe Anwendungen, auf denen mehrere Subsysteme weiterentwickelt. In diesen Fällen lohnt es sich in einer komplexeren Softwarearchitektur für erhöhten langfristigen Flexibilität und eine effizientere Anwendungswartung investieren. Aber für weniger komplexe Szenarien ist es möglicherweise besser, einen Ansatz monolithischen Anwendung fortsetzen oder einfacher N-Tier fast erreicht wird.

Als letzten Knoten, auch wenn bei diesem Vorgang wird von Informationen zu diesem Konzept darf keine Informationen finden Sie unter Verwenden von Microservices in den Anwendungen als "-Ansatz repräsentieren oder gar nichts." Sie können erweitern und vorhandene monolithische Anwendungen durch Hinzufügen neuer, kleine Szenarien, die basierend auf Microservices weiterentwickeln. Sie müssen nicht von Grund auf neu, um erste Schritte mit einem Microservices Architekturkonzept starten. In der Tat empfohlen, dass Sie von der Verwendung einer vorhandenen monolithischen oder N-Tier-Anwendung durch Hinzufügen von neuen Szenarien weiterentwickeln. Schließlich können Sie die Anwendung in autonomen Komponenten oder Microservices unterteilen. Sie können die entwickelt, der aufgrund eines monolithischen-Anwendungen in eine Richtung Microservices, Schritt-für-Schritt starten.

Der Rest dieses Handbuchs vorhanden bezieht in jedem Fall sich die meisten aller auf "keine Microservices-apps" aus, da in dieser Anleitung hauptsächlich die Modernisierung vorhandener Apps abzielt, die in der Regel aufgrund eines monolithischen oder N-Tier-Architekturen aufweisen.


>[!div class="step-by-step"]
[Zurück](microsoft-technologies-in-cloud-optimized-applications.md)
[Weiter](deploy-existing-net-apps-as-windows-containers.md)
