---
title: Was gilt für cloudnative Anwendungen?
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Was gilt für cloudnative Anwendungen?
ms.date: 04/28/2018
ms.openlocfilehash: d2a7f89e347d75ddbdae84c8eb57e32447b83297
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77543546"
---
# <a name="what-about-cloud-native-applications"></a>Was gilt für cloudnative Anwendungen?

Obwohl [Cloud-Native](https://azure.microsoft.com/overview/cloudnative/)-Anwendungen (cloudnativ) nicht der Hauptschwerpunkt dieses Leitfadens sind, ist es hilfreich, ein Verständnis für diesen Modernisierungsreifegrad zu besitzen und ihn von Cloud-Optimized-Anwendungen (cloudoptimiert) zu unterscheiden.

In Abbildung 4–3 werden Cloud-Native-Apps in den Reifegraden für Anwendungsmodernisierung positioniert:

![Diagramm, das die Positionierung von Cloud-Native-Anwendungen zeigt.](./media/what-about-cloud-native-applications/positioning-cloud-native-applications.png)

**Abbildung 4–3.** . Positionierung von Cloud-Native-Anwendungen

Der Modernisierungsreifegrad „Cloud-Native“ erfordert normalerweise neue Entwicklungsinvestitionen. Die Umstellung auf den Reifegrad „Cloudnative“ ist in der Regel durch geschäftliche Anforderungen motiviert, um Anwendungen so weit wie möglich zu modernisieren und so die Skalierung in großen Anwendungen drastisch zu verbessern. Dafür werden autonome Subsysteme (Microservices) erstellt, die unabhängig von anderen Bereichen der Anwendung bereitgestellt und skaliert werden können. Zugleich werden langfristig die Kosten gesenkt und die Flexibilität bei der Entwicklung der Teile dieser autonomen App erhöht, die bedeutende Wettbewerbsvorteile bringen.

Die Hauptpfeiler cloudnativer Anwendungen ruhen auf Ansätzen mit Microservices-Architektur, die sich mit Agilität weiterentwickeln und auf Limits skalieren lassen, die sich in einer monolithischen Architektur, die in einer lokalen oder Cloudumgebung bereitgestellt ist, schwer erzielen ließen.

Abbildung 4–4 zeigt die Haupteigenschaften des Cloud-Native-Modells.

![Diagramm, in dem die Haupteigenschaften von „Cloud-Native“ aufgeführt sind.](./media/what-about-cloud-native-applications/cloud-native-characteristics.png)

**Abbildung 4–4.** Eigenschaften von „Cloud-Native“

Zusätzlich können Sie einfache moderne Web-Apps und cloudnative Apps erweitern, indem Sie weitere Dienste wie Künstliche Intelligenz (KI), Machine Learning (ML) und IoT hinzufügen. Sie können einen dieser Dienste verwenden, um jeden der möglichen cloudoptimierten Ansätze zu erweitern.

Der grundlegende Unterschied bei Anwendungen auf der cloudnativen Ebene liegt in der Anwendungsarchitektur. Cloudnative Anwendungen sind definitionsgemäß Apps, die auf Microservices basieren. Cloudnative Apps erfordern besondere Architekturen, Technologien und Plattformen im Vergleich zu einer monolithischen Webanwendung oder einer herkömmlichen N-schichtigen Anwendung.

## <a name="cloud-native-applications-details"></a>Details zu Cloud-Native-Anwendungen

„Cloud-Native“ ist ein komplexerer oder ausgereifterer Zustand für große und unternehmenskritische Anwendungen. Cloudnative Anwendungen erfordern in der Regel eine Architektur und ein Design, die von Grund auf neu erstellt werden, anstatt vorhandene Anwendungen zu modernisieren. Der Hauptunterschied zwischen einer cloudnativen Anwendung und einer einfacheren cloudoptimierten Web-App liegt in der Empfehlung, Microservice-Architekturen in einem cloudnativen Ansatz zu verwenden. Cloudoptimierte Apps können auch monolithische Web-Apps oder N-schichtige Apps sein.

Die [Twelve-Factor-App](https://12factor.net/) (eine Sammlung von Mustern, die in enger Beziehung zu Microservice-Ansätzen stehen) wird ebenfalls als eine Voraussetzung für cloudnative Anwendungsarchitekturen angesehen.

Die [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) ist ein primärer Förderer der cloudnativen Prinzipien. Microsoft ist [Mitglied de CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Eine detaillierte Anleitung zum Entwerfen und Entwickeln cloudnativer Anwendungen finden Sie in den folgenden kostenlosen E-Books:

* [Entwickeln cloudnativer .NET-Anwendungen für Azure](../../cloud-native/introduction.md)
* [.NET-Microservices: Architektur für containerisierte .NET-Anwendungen](../../microservices/index.md).

Der wichtigste Faktor, der bei der Migration einer vollständigen Anwendung zum cloudnativen Modell zu berücksichtigen ist, besteht darin, dass Sie die Architektur vollständig neu auf eine auf Microservices basierende Architektur umstellen müssen. Dies erfordert aufgrund des umfangreichen Refactoring-Prozesses natürlich erhebliche Investitionen in die Entwicklung. Diese Option wird in der Regel für unternehmenskritische Anwendungen gewählt, die neue Skalierbarkeitsniveaus und langfristige Agilität benötigen. Sie könnten aber auch mit der Umstellung auf Cloud-Native beginnen, indem Sie Microservices nur für ein paar neue Szenarios hinzufügen und schließlich ein vollständiges Refactoring der Anwendung als Microservices durchführen. Dies ist ein inkrementeller Ansatz, der in einigen Szenarien die beste Option darstellt.

## <a name="what-about-microservices"></a>Und Microservices...?

Das Verständnis von Microservices und ihrer Funktionsweise ist wichtig, wenn Sie cloudnative Anwendungen für Ihre Organisation in Erwägung ziehen.

Die Microservices-Architektur ist ein komplexer Ansatz, den Sie für Anwendungen verwenden können, die von Grund auf neu erstellt werden, oder wenn Sie vorhandene Anwendungen in Richtung cloudnative Anwendungen weiterentwickeln. Sie können damit beginnen, dass Sie vorhandenen Anwendungen ein paar Microservices hinzufügen, um mehr über die neuen Paradigmen von Microservices zu erfahren. Natürlich müssen Sie aber auch speziell auf diesen Architekturansatz hin die Architektur entwickeln und programmieren.

Microservices sind allerdings für keine neue oder moderne Anwendung obligatorisch. Bei Microservices handelt es sich nicht um eine „Wunderwaffe“, und sie sind nicht die einzige, optimale Methode, um jede Anwendung zu erstellen. Wie und wann Sie Microservices verwenden, hängt vom Typ der Anwendung ab, die Sie erstellen müssen.

Die Microservices-Architektur wird zum bevorzugten Ansatz für verteilte und große oder komplexe unternehmenskritische Anwendungen, die auf mehreren unabhängigen Subsystemen in Form von autonomen Diensten basieren. In einer auf Microservices basierenden Architektur wird eine Anwendung als Sammlung von Diensten erstellt, die unabhängig voneinander entwickelt, getestet, mit Versionsangaben versehen, bereitgestellt und skaliert werden. Dies kann alle jegliche verwandte, autonome Datenbank pro Microservice einschließen.

Einen detaillierten Einblick in eine Microservice-Architektur, die Sie mithilfe von .NET Core implementieren können, finden Sie in dem herunterladbaren PDF-e-Book [.NET-Microservices: Architektur für containerisierte .NET-Anwendungen](https://aka.ms/microservicesebook). Das Handbuch steht auch [online](../../microservices/index.md) zur Verfügung.

Doch selbst in Szenarios, in denen Microservices viele leistungsstarke Funktionen bieten, wie unabhängige Bereitstellung, starke Subsystemgrenzen und technologische Vielfalt, bringen sie auch viele neue Herausforderungen mit sich. Die Herausforderungen stehen im Zusammenhang mit der Entwicklung von verteilten Anwendungen, z. B. fragmentierte und unabhängige Datenmodelle, dem Erzielen von robuster Kommunikation zwischen Microservices, der letztendlichen Notwendigkeit von Konsistenz sowie der operativen Komplexität. Microservices führen einen höheren Komplexitätsgrad ein im Vergleich zu herkömmlichen monolithischen Anwendungen.

Aufgrund der Komplexität einer Microservices-Architektur sind nur bestimmte Szenarien und bestimmte Anwendungstypen für auf Microservices basierende Anwendungen geeignet. Dazu gehören große und komplexe Anwendungen mit mehreren sich entwickelnden Subsystemen. In diesen Fällen lohnt es sich, in komplexere Softwarearchitektur zu investieren, da damit für bessere langfristige Flexibilität und eine effizientere Anwendungswartung gesorgt wird. Für weniger komplexe Szenarien kann es jedoch möglicherweise besser sein, mit einem monolithischen Anwendungsansatz Herangehensweise oder einfacheren N-schichtigen Ansätzen fortzufahren.

Abschließend sei zu diesem Konzept bemerkt, auch auf die Gefahr, sich zu wiederholen, dass Sie die Verwendung von Microservices in Ihren Anwendungen nicht als „Ganz oder garn nicht“-Lösung betrachten sollten. Sie können vorhandene monolithische Anwendungen erweitern und weiterentwickeln, indem Sie neue, kleine Szenarios hinzufügen, die auf Microservices basieren. Sie müssen nicht von Grund auf neu beginnen, um die Arbeit mit einem Microservices-Architekturansatz zu beginnen. De facto empfehlen wir, dass Sie sich von der Verwendung einer vorhandenen monolithischen oder n-schichtigen Anwendung durch Hinzufügen neuer Szenarien weiterentwickeln. Als letzten Schritt können Sie dann die Anwendung in autonome Komponenten und Microservices aufteilen. Mit der Weiterentwicklung Ihrer monolithischen Anwendungen in Richtung von Microservices können Sie schrittweise beginnen.

Auf jeden Fall konzentriert sich der Rest der vorliegenden Anleitung vorwiegend auf „nicht auf Microservices basierende Anwendungen“, da diese Anleitung hauptsächlich auf die Modernisierung vorhandener Anwendungen abzielt, die in der Regel monolithische oder N-schichtige Architekturen aufweisen.

> [!div class="step-by-step"]
> [Zurück](microsoft-technologies-in-cloud-optimized-applications.md)
> [Weiter](deploy-existing-net-apps-as-windows-containers.md)
