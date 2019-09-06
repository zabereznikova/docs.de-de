---
title: Was gilt für cloudnative Anwendungen?
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Wie sieht es mit cloudbasierten Anwendungen aus?
ms.date: 04/28/2018
ms.openlocfilehash: 86153b04790eb21276e58b3fe33c0a680d9ea1c4
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373922"
---
# <a name="what-about-cloud-native-applications"></a>Was gilt für cloudnative Anwendungen?

Obwohl sich die [cloudbasierten](https://azure.microsoft.com/overview/cloudnative/) Anwendungen nicht im Mittelpunkt dieses Handbuchs befinden, ist es hilfreich, sich mit diesem Modernisierungsgrad vertraut zu machen und ihn von cloudoptimierten Anwendungen zu unterscheiden.

In Abbildung 4-3 werden Native Cloud-apps in den Fälligkeits Stufen der Anwendungs Modernisierung positioniert:

![Positionieren von Cloud-native Anwendungen](./media/image3.png)

**Abbildung 4-3.** Positionieren von Cloud-native Anwendungen

Die Cloud-Native Modernisierung der Modernisierung erfordert in der Regel neue Entwicklungsinvestitionen. Die Umstellung auf die cloudbasierte Ebene wird in der Regel von geschäftlichen Anforderungen gesteuert, um Anwendungen so weit wie möglich zu modernisieren und die Skalierung in großen Anwendungen drastisch zu verbessern, indem autonome Subsysteme (microservices) erstellt werden, die unabhängig bereitgestellt und skaliert werden können aus anderen Bereichen der Anwendung, während die Kosten langfristig gesenkt werden und die Flexibilität der Teile der autonomen App erhöht wird, die bedeutende Wettbewerbsvorteile bieten.

Die Hauptpfeiler der cloudbasierten Anwendungen basieren auf microservices-Architektur Ansätzen, die sich mit Agilität und Skalierbarkeit auf Grenzen entwickeln können, die in einer monolithischen Architektur, die in einer lokalen Umgebung oder in der Cloud bereitgestellt wird, schwierig zu erreichen sind. Umgebung.

Abbildung 4-4 zeigt die Hauptmerkmale des cloudbasierten Modells.

![Native Cloud-Merkmale sind mikrodienste, Container, cloudrobust, orchestratoren und Server lose](./media/image4.png)

**Abbildung 4-4.** In der Cloud Native Merkmale

Außerdem können Sie grundlegende moderne Web-Apps und Native Cloud-apps erweitern, indem Sie weitere Dienste wie künstliche Intelligenz (KI), Machine Learning (ml) und IOT hinzufügen. Sie können einen dieser Dienste verwenden, um die möglichen cloudoptimierten Ansätze zu erweitern.

Der grundlegende Unterschied bei Anwendungen auf der cloudbasierten Ebene ist die Anwendungsarchitektur. Native cloudanwendungen sind definitionsgemäß apps, die auf-Webdiensten basieren. Native Cloud-apps erfordern besondere Architekturen, Technologien und Plattformen im Vergleich zu einer monolithischen Webanwendung oder einer herkömmlichen N-Tier-Anwendung.

## <a name="cloud-native-applications-details"></a>Details zur Cloud-native Anwendung

Cloud-Native ist ein fortschrittlicher oder ausgereifter Status für große und unternehmenskritische Anwendungen. Native Cloud-Anwendungen erfordern in der Regel Architektur und Entwurf, die von Grund auf neu erstellt werden, anstatt vorhandene Anwendungen zu modernisieren. Der Hauptunterschied zwischen einer cloudbasierten Anwendung und einer einfacheren cloudoptimierten Web-App ist die Empfehlung, microservicearchitekturen in einem cloudbasierten Ansatz zu verwenden. Cloud-optimierte Apps können auch monolithische Web-Apps oder N-Tier-apps sein.

Die [zwölfstufige App](https://12factor.net/) (eine Sammlung von Mustern, die eng mit den microserviceansätzen verknüpft sind) wird auch als Voraussetzung für cloudidentielle Anwendungsarchitekturen angesehen.

Die [Cloud Native Computing Foundation (cncf)](https://www.cncf.io/) ist ein primärer Förderer der cloudbasierten Prinzipien. Microsoft ist [Mitglied von cncf](https://azure.microsoft.com/blog/announcing-cncf/).

Eine Beispiel Definition und weitere Informationen zu den Merkmalen von cloudbasierten Anwendungen finden Sie im Gartner [-Artikel entwerfen und Entwerfen von cloudbasierten Anwendungen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). Spezifische Anleitungen von Microsoft zur Implementierung einer cloudbasierten Anwendung finden [Sie unter .NET-Funktionen: Architektur für containerisierte .NET-Anwendungen](https://aka.ms/microservicesebook).

Der wichtigste Faktor, der bei der Migration einer vollständigen Anwendung zum cloudbasierten Modell zu berücksichtigen ist, besteht darin, dass Sie eine Architektur in einer auf microservices basierenden Architektur entwickeln müssen. Dies erfordert aufgrund des großen Umgestaltungs Prozesses natürlich erhebliche Investitionen in die Entwicklung. Diese Option wird in der Regel für unternehmenskritische Anwendungen gewählt, die neue Skalierbarkeits Stufen und langfristige Agilität benötigen. Aber Sie könnten mit der Umstellung auf die Cloud-Native beginnen, indem Sie für ein paar neue Szenarios die folgenden Funktionen hinzufügen und die Anwendung dann vollständig als "mikroservices" umgestalten. Dies ist ein inkrementeller Ansatz, der in einigen Szenarien die beste Option ist.

## <a name="what-about-microservices"></a>Wie sieht es mit den Funktionen von "

Das Verständnis von mikrodiensten und deren Funktionsweise ist wichtig, wenn Sie in der Cloud native Anwendungen für Ihre Organisation in Erwägung ziehen.

Die microservices-Architektur ist ein erweiterter Ansatz, den Sie für Anwendungen verwenden können, die von Grund auf neu erstellt werden, oder wenn Sie vorhandene Anwendungen in Cloud-native Anwendungen weiterentwickeln. Sie können beginnen, indem Sie vorhandenen Anwendungen einige-Dienste hinzufügen, um mehr über die neuen Paradigmen für den Einsatz von Modellen zu erfahren. Natürlich müssen Sie aber auch einen Architekt und Code entwickeln, insbesondere für diese Art von Architektur.

Allerdings sind die-mikrodienste für keine neue oder moderne Anwendung obligatorisch. Bei der Verwendung von mikroservices handelt es sich nicht um die einzige, beste Methode, um jede Anwendung zu erstellen. Wie und wann Sie-Webdienste verwenden, hängt von der Art der Anwendung ab, die Sie erstellen müssen.

Die microservices-Architektur wird zum bevorzugten Ansatz für verteilte und große oder komplexe unternehmenskritische Anwendungen, die auf mehreren unabhängigen Subsystemen in Form von autonomen Diensten basieren. In einer auf microservices basierenden Architektur wird eine Anwendung als eine Sammlung von Diensten erstellt, die unabhängig entwickelt, getestet, versioniert, bereitgestellt und skaliert werden können. Dies kann jede zugehörige, autonome Datenbank pro mikroservice einschließen.

Einen detaillierten Einblick in eine microservicearchitektur, die Sie mithilfe von .net Core implementieren können, finden Sie in der herunterladbaren [PDF-e-book .net-microservices: Architektur für containerisierte .NET-Anwendungen](https://aka.ms/microservicesebook). Das Handbuch ist auch [Online](../../microservices/index.md)verfügbar.

Aber auch in Szenarios, in denen die Funktionen von Mikro Diensten eine leistungsstarke, unabhängige Bereitstellung, starke subsystemgrenzen und Technologie Vielfalt bieten, sind auch viele neue Herausforderungen zu meistern. Die Herausforderungen beziehen sich auf die Entwicklung verteilter Anwendungen, wie z. b. fragmentierte und unabhängige Datenmodelle. erreichen robuster Kommunikation zwischen den-und-Diensten der Bedarf an letztlicher Konsistenz; und betriebliche Komplexität. Im Vergleich zu herkömmlichen monolithischen Anwendungen führt der-Dienst zu einem höheren Komplexitäts Grad.

Aufgrund der Komplexität einer microservicesarchitektur sind nur bestimmte Szenarien und bestimmte Anwendungs Typen für auf microservices basierende Anwendungen geeignet. Dazu zählen große und komplexe Anwendungen mit mehreren, sich entwickelnden Subsystemen. In diesen Fällen ist es sinnvoll, in eine komplexere Softwarearchitektur zu investieren, um eine höhere langfristige Agilität und eine effizientere Anwendungs Wartung zu erhalten. Für weniger komplexe Szenarien ist es jedoch möglicherweise besser, mit einer monolithischen Anwendungs Herangehensweise oder einfacheren N-Tier-Ansätzen fortzufahren.

Zum Schluss sollten Sie selbst dann, wenn das Risiko besteht, dass Sie sich nicht mehr mit diesem Konzept beschäftigen, die Verwendung von in Ihren Anwendungen verwendeten mikroservices nicht als "alles oder gar nichts" betrachten. Sie können vorhandene monolithische Anwendungen erweitern und entwickeln, indem Sie neue, kleine Szenarios basierend auf den-Diensten hinzufügen. Sie müssen nicht von Grund auf neu beginnen, um mit einem microservices-Architekturansatz zu arbeiten. Es wird empfohlen, dass Sie sich von der Verwendung einer vorhandenen monolithischen oder N-Tier-Anwendung durch Hinzufügen neuer Szenarien weiterentwickeln. Schließlich können Sie die Anwendung in Autonome Komponenten oder in die-Dienste zerlegen. Sie können mit der Entwicklung monolithischer Anwendungen in einer Richtung für die Richtung eines einzelnen Schritts beginnen.

In jedem Fall konzentriert sich der Rest dieses Leitfadens am meisten auf "keine auf microservices basierenden Apps", da diese Richtlinien hauptsächlich auf die Modernisierung vorhandener apps abzielen, die normalerweise monolithische oder N-Tier-Architekturen haben.

> [!div class="step-by-step"]
> [Zurück](microsoft-technologies-in-cloud-optimized-applications.md)
> [Weiter](deploy-existing-net-apps-as-windows-containers.md)
