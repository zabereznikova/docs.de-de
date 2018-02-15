---
title: Was ist mit der Cloud-optimierte Anwendungen?
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Was ist mit der Cloud-optimierte Anwendungen?"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4cb85c9dbcc7586510db9947d0151e3856964ef4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="what-about-cloud-optimized-applications"></a>Was ist mit der Cloud-optimierte Anwendungen?

Obwohl Cloudoptimiertes und [Cloud systemeigenen](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) Anwendungen sind nicht der Schwerpunkt dieses Handbuchs ist es hilfreich, um einen Überblick über diese Modernisierung Reifegrad haben und zur Unterscheidung von DevOps Cloudfähige.

Abbildung 4 – 3 positioniert Cloudoptimiertes apps in der Anwendung Modernisierung Reifegrade:

![Positionieren von Cloud-optimierte Anwendungen](./media/image3.png)

> **Abbildung 4 – 3.** Positionieren von Cloud-optimierte Anwendungen

Cloud-optimierten Modernisierung Entwicklungsstands erfordert in der Regel neue Entwicklung Investitionen. Verschieben in der Regel auf die Cloud optimierten wird gesteuert durch geschäftliche Notwendigkeit modernisieren Anwendungen so weit wie möglich, Kostensenkung und erhöhen die Flexibilität und konkurrieren, nutzen. Diese Ziele werden erreicht, indem die Verwendung von PaaS-Cloud zu maximieren. Dies bedeutet nicht nur PaaS-Dienste wie DBaaS, CaaS und Speicherressourcen als Dienst (STaaS), sondern auch durch die Migration von Anwendungen und Dienste in einer PaaS Plattform wie Azure App Service compute oder Orchestrators.

Diese Art von Modernisierung erfordert normalerweise eine Umgestaltung oder neuen Code schreiben, der optimiert ist cloud PaaS-Plattformen (wie für Azure App Service). Kann es auch erforderlich sein Architektur speziell für die Cloud-Umgebung, insbesondere dann, wenn Sie Cloud-systemeigenen Anwendungsmodelle verschieben auf Microservices basieren. Dies ist ein Schlüssel zur Differenzierung Faktor im Vergleich zu Cloud DevOps bereit, die keine Architektur erforderlich ist und keine neuen Code.

Möglicherweise erstellen Sie in einigen komplexeren Fällen [Cloud systemeigenen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungen auf der Grundlage von Microservices-Architekturen, die mit Agilität entwickeln und zu skalieren, um Grenzwerte, die in einer Architektur mit monolithisch erzielen schwierig wäre können in einer lokalen Umgebung bereitgestellt.

Abbildung 4-4 zeigt den Typ der Anwendungen, die Sie bereitstellen können, wenn Sie die Cloud-optimierte Modell verwenden. Sie haben zwei grundlegende Optionen moderner Webanwendungen und Cloud-systemeigenen Anwendungen.

> ![App-Typen auf der Ebene Cloudoptimiertes](./media/image4.png)
>
> **Abbildung 4-4.** App-Typen auf der Ebene Cloudoptimiertes

Sie können grundlegende moderner Web-apps und Cloud-systemeigenen apps durch Hinzufügen von anderen Diensten, wie KI (AI), Machine Learning (ML) und IoT erweitern. Sie können eines dieser Dienste verwenden, um einen der möglichen Cloudoptimiertes Ansätze erweitern.

Der grundlegende Unterschied in Anwendungen auf der Ebene Cloudoptimiertes ist in der Anwendungsarchitektur. [Cloud-systemeigenen](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) Anwendungen sind per Definition apps, die auf Microservices basieren. Cloud-systemeigenen apps erfordern besondere Architekturen, Technologien und Plattformen, im Vergleich zu einer monolithischen Webanwendung oder die herkömmliche N-Tier-Anwendung.

Erstellen neue Anwendungen, die Microservices verwenden, ist auch sinnvoll. Es gibt viele neue und weiterhin moderne Szenarien, die in denen ein Microservices basierender Ansatz Ihren Anforderungen überschreiten kann. In einigen Fällen sollten Sie nur eine einfachere monolithischen Webanwendung erstellen, oder eine N-Tier-Anwendung groben Services hinzu. In diesen Fällen können Sie weiterhin voll ausgelastet Cloud PaaS-Funktionen, wie z. B. diejenigen, die von Azure App Service angeboten. Sie reduzieren weiterhin Ihre Wartungsarbeiten auf den Grenzwert.

Auch, da Sie neuen Code entwickeln in Cloud-optimierten Szenarien (für eine vollständige Anwendung oder für partielle Subsysteme), wenn Sie neuen Code erstellen sollten Sie verwenden die neueren Versionen von .NET ([.NET Core](https://docs.microsoft.com/dotnet/core/) und [ASP.NET Core](https://docs.microsoft.com/aspnet/core/), insbesondere). Dies gilt insbesondere, wenn Sie Microservices und Container erstellt werden, weil .NET Core eine schnelle und rationell-Framework ist. Sie erhalten eine minimale speicherbeanspruchung und Schnellstart in Containern, und Ihre Anwendungen werden hochleistungsfähiger. Dieser Ansatz durchaus den Anforderungen des Microservices und Container passt, und Sie erhalten die Vorteile von einer plattformübergreifenden Framework-die Fähigkeit zum Ausführen der gleichen Anwendung unter Linux, Mac (Mac für entwicklungsumgebungen) und unter Windows Server.

## <a name="cloud-native-applications-with-cloud-optimized-applications"></a>Cloud-systemeigenen Anwendungen mit Cloud-optimierte Anwendungen

[Cloud-systemeigenen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) ist ein erweiterter oder ausgereifte Zustand für große und unternehmenswichtige Anwendungen. Cloud-systemeigenen Anwendungen erfordern i. d. r. auf, Architektur und Entwurf, die von Grund auf neu, sondern Modernisierung vorhandene Anwendungen erstellt werden. Der Hauptunterschied zwischen einer Cloud-systemeigene Anwendung und eine einfachere Cloudoptimiertes Web-app, die für PaaS bereitgestellt ist die Empfehlung, Microservices Architekturen in einem Cloud-einheitlichen Ansatz zu verwenden. Cloud-optimierten apps können auch aufgrund eines monolithischen Web-apps oder N-Tier-apps, die in einer PaaS-Dienst wie Azure App Service-Cloud bereitgestellt sein.

Die [zwölf Faktor App](https://12factor.net/) (eine Sammlung von Mustern, die Microservices Ansätzen eng miteinander verknüpft sind) wird ebenfalls eine Voraussetzung für berücksichtigt [Cloud systemeigenen](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) Anwendungsarchitektur.

Die [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) ist eine primäre Promoter systemeigenen Cloud-Grundsätzen. Microsoft ist ein [Mitglied der CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Eine Beispiel-Definition und Weitere Informationen über die Eigenschaften des Cloud-systemeigenen Anwendungen finden Sie im Gartner Artikel [zum Entwerfen und entwickeln Cloud-systemeigenen Anwendungen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). Bestimmte Anleitung von Microsoft dazu, wie eine systemeigene Cloud-Anwendung implementiert wird, finden Sie unter [.NET Microservices: Architektur für .NET Sammelartikeleinheit](https://aka.ms/microservicesebook).

Der wichtigste Faktor, berücksichtigen bei der Migration von einer vollständigen Anwendung, die [Cloud systemeigenen](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) Modell ist, dass Sie auf eine Microservices-basierte Architektur Umgestalten müssen. Dies erfordert eine erhebliche Investition in der Entwicklung deutlich, aufgrund der großen beteiligten Umgestaltung. Diese Option wird normalerweise für unternehmenswichtige Anwendungen ausgewählt, die neue Ebenen von Skalierbarkeit und langfristige Agilität benötigen. Allerdings konnte zunächst Aneignung von Cloud-systemeigen durch Hinzufügen von Microservices nur wenige neue Szenarien und schließlich die Anwendung vollständig als Microservices umzugestalten. Dies ist ein inkrementeller Ansatz, der die beste Option für einige Szenarien ist.

## <a name="what-about-microservices"></a>Welche Rolle spielt Microservices? 

Grundlegendes zu Microservices und deren Funktionsweise ist wichtig, wenn Sie Cloud-systemeigenen Anwendungen für Ihre Organisation in Betracht ziehen.

Die Architektur des Microservices wird einen erweiterten Ansatz, die Sie für Anwendungen verwenden können, die erstellt werden, von Grund auf neu, oder wenn Sie vorhandene Anwendungen entwickeln (einer lokalen oder cloud-apps DevOps einsatzfähige) bis zum Cloud-systemeigenen Anwendungen. Sie können zunächst einige Microservices zu vorhandenen Anwendungen, um weitere Informationen zu den neuen Microservices Paradigmen hinzufügen. Aber es ist offensichtlich, Architekt und Code, die speziell für diese Art von architektonische Ansatz werden müssen.

Microservices sind jedoch nicht für alle neuen oder modernen Anwendung obligatorisch. Microservices sind nicht "Magic Aufzählungszeichen", und sie sind nicht die einzigen, bewährte Möglichkeit, jede Anwendung zu erstellen. Wie und wann Sie Microservices verwenden, hängt vom Typ der Anwendung, die Sie erstellen möchten.

Die Architektur des Microservices gewinnt den optimalen Ansatz für verteilte und großen oder komplexen unternehmenswichtigen Anwendungen, die auf mehrere unabhängige Subsysteme in Form von autonome Services basieren. In einer Microservices-basierte Architektur basiert eine Anwendung als eine Sammlung von Diensten, die unabhängig entwickelt, getestet und Versionsangaben bereitgestellt und skaliert werden können. Dies kann verknüpfte autonome Datenbank pro Microservice einschließen.

Eine ausführliche Beschreibung der in eine Microservices-Architektur, die Sie mithilfe von .NET Core implementieren können, finden Sie unter herunterladbare PDF-Datei-e-Book [.NET Microservices: Architektur für .NET Sammelartikeleinheit](https://aka.ms/microservicesebook). Dieses Handbuch auch steht [online](https://docs.microsoft.com/dotnet/standard/microservices-architecture/).

Aber auch in Szenarien, in dem Microservices bieten eine leistungsstarke Funktionen typunabhängig-Bereitstellung, sicheres Subsystem Grenzen und Technologie Vielfalt-auch viele neue Herausforderungen ausgelöst. Die Herausforderungen beziehen sich auf die Entwicklung einer verteilten Anwendung, z. B. fragmentiert und unabhängige Datenmodelle; erzielen von robusten Kommunikation zwischen Microservices; die Notwendigkeit für eventuelle Konsistenz; und operative Komplexität. Microservices stellen ein höheres Maß an Komplexität im Vergleich zu herkömmlichen monolithischen Anwendungen vor.

Aufgrund der Komplexität einer Microservices-Architektur sind nur für bestimmte Szenarien und bestimmte Anwendungstypen für Microservice-basierte Anwendungen geeignet. Dazu zählen große und komplexe Anwendungen, auf denen mehrere Subsysteme weiterentwickelt. In diesen Fällen lohnt es sich in einer komplexeren Softwarearchitektur für erhöhten langfristigen Flexibilität und eine effizientere Anwendungswartung investieren. Aber für weniger komplexe Szenarien ist es möglicherweise besser, einen Ansatz monolithischen Anwendung fortsetzen oder einfacher N-Tier fast erreicht wird.

Als letzten Knoten, auch wenn bei diesem Vorgang werden Informationen zu diesem Konzept von betrachten Sie darf nicht mit Microservices in Ihren Anwendungen als "-Ansatz repräsentieren oder gar nichts*.*" Sie können erweitern und vorhandene monolithische Anwendungen durch Hinzufügen neuer, kleine Szenarien, die basierend auf Microservices weiterentwickeln. Sie müssen nicht von Grund auf neu, um erste Schritte mit einem Microservices Architekturkonzept starten. In der Tat empfohlen, dass Sie von der Verwendung einer vorhandenen monolithischen oder N-Tier-Anwendung durch Hinzufügen von neuen Szenarien weiterentwickeln. Schließlich können Sie die Anwendung in autonomen Komponenten oder Microservices unterteilen. Sie können die entwickelt, der aufgrund eines monolithischen-Anwendungen in eine Richtung Microservices, Schritt-für-Schritt starten.

## <a name="when-to-use-azure-app-service-for-modernizing-existing-net-apps"></a>Azure App Service-Verwendung für vorhandene .NET apps Modernisierung

Wenn Sie vorhandene ASP.NET-Webanwendungen Cloudoptimiertes Entwicklungsstands modernisieren, da die Webanwendungen mithilfe von .NET Framework entwickelt wurden, sind die wichtigsten Abhängigkeiten auf Windows- und sehr wahrscheinlich, dass Internet Information Server (IIS). Sie verwenden und Bereitstellen von Windows-basierten und IIS-basierte Anwendungen können entweder durch Bereitstellen von direkt für [Azure App Service](https://docs.microsoft.com/azure/app-service/app-service-value-prop-what-is) oder containerizing Sie zuerst Ihre Anwendung mithilfe von Windows-Containern. Wenn containerizing, bereitstellen, die Anwendungen entweder auf Windows-Container hostet (VM-basiert) oder auf ein Azure Service Fabric-cluster, die von Windows-Container unterstützt.

Wenn Sie Windows-Container verwenden, erhalten Sie sämtliche Vorteile einer Containerization. Sie zusätzliche Flexibilität bei der Auslieferung und Bereitstellen Ihrer app zu erhöhen und reduzieren Unstimmigkeiten für Umgebungsprobleme ("Staging", "Dev/Test", "Produktion"). Wechseln Sie in den nächsten Abschnitten wir ausführlicher Informationen zu den Vorteilen, die aus der Verwendung von Containern.

Zum Zeitpunkt der Verfassung dieses Handbuchs unterstützt nicht Windows-Container Azure App Service. Container werden für Linux unterstützt. Damit Ihre nächste Frage möglicherweise, "Wie treffe ich zwischen Azure App Service- und Windows-Containern?"

Wenn Azure App Service für Ihre Anwendung funktioniert, und es stehen keine Server oder benutzerdefinierte Abhängigkeiten, die Blockierung des Pfads zum Anwendungsdienst verwenden, sollten Sie grundsätzlich die vorhandene .NET Web-Anwendung in App-Dienst migrieren. Das ist die einfachste und effektivste Methode zum Verwalten Ihrer Anwendungsstatus. In Azure wird die Anwendung auch einen einfacheren Wartung Pfad aufgrund von den Vorteilen von PaaS-Infrastruktur, z. B. DBaaS CaaS und STaaS verfügen.

Wenn Ihre Anwendung verfügt, Server oder benutzerdefinierte Abhängigkeiten, die nicht in Azure App Service unterstützt werden, müssen Sie jedoch möglicherweise Optionen in Betracht ziehen, die auf Windows-Containern basieren. Beispiele für Server oder benutzerdefinierte Abhängigkeiten sind Drittanbieter-Software oder eine MSI-Datei, die auf dem Server installiert werden muss, aber der nicht in Azure App Service unterstützt. Ein weiteres Beispiel ist eine andere Serverkonfiguration, die in Azure App Service, nicht unterstützt wird, wie die Verwendung von Assemblys im globalen Assemblycache (GAC) oder COM / COM+-Komponenten. Unser Dank gilt Windows-containerimages können Sie Ihre benutzerdefinierte Abhängigkeiten in der gleichen "Bereitstellungseinheit." einschließen.

Alternativ können Sie die Bereiche der Anwendung Umgestalten, die nicht von Azure App Service unterstützt werden. Abhängig vom Datenvolumen Arbeit müsste Umgestaltung, müssten Sie sorgfältig, ob dieses lohnen ist.

### <a name="benefits-of-moving-to-azure-app-service"></a>Vorteile der Umstellung auf Azure App Service

Azure App Service ist ein vollständig verwaltetes PaaS-Angebot, das erleichtert die Web-apps erstellen, die von der Geschäftsprozesse unterstützt werden. Bei Verwendung von App Service vermeiden Sie die Management-Infrastrukturkosten, aktualisieren und Verwalten von Web apps, lokal zugeordnet. Insbesondere schneiden Sie die Hardware und Lizenzkosten Web apps, lokal ausführen.

Wenn Ihre Webanwendung für die Migration zu Azure App Service geeignet ist, ist der Hauptvorteil der kürzester Zeit zum Verschieben der app benötigte. App Service bietet eine sehr einfache Umgebung aus, die für den Einstieg.

Azure App Service ist die beste Wahl für die meisten Web-apps, da es sich um das einfachste PaaS in Azure handelt, die mit der Web-apps ausgeführt werden können. Bereitstellung und Verwaltung sind in der Plattform integriert, Websites schnell so um hohe Datenverkehrsvolumen zu bewältigen skaliert, und der integrierte laden Lastenausgleich und Traffic Manager hohe Verfügbarkeit bereitstellen.

Überwachen auch Ihre Web-apps ist einfach, über Azure Application Insights. Application Insights stammt mit App Service kostenlos und erfordert keine speziellen Code in Ihrer Anwendung schreiben zu müssen. Führen Sie einfach Ihre Web-app im App-Dienst, und Sie erhalten eine überzeugende Überwachungssystem ohne zusätzliche Arbeit.

Mit App-Dienst auch direkt können Sie viele Open-Source-apps aus dem Azure-Webanwendungskatalog (wie WordPress oder Umbraco), oder Sie können einen neuen Standort erstellen, mit dem Framework und den Tools Ihrer Wahl, z. B. ASP.NET. Die App Service-WebJobs-Funktion vereinfacht die Verarbeitung auf Ihre App Service-Web-app Hintergrundauftrag hinzufügen.

Folgende: wichtige Vorteile für Ihre Web-apps mithilfe der Web-Apps-Funktion von Azure App Service migrieren

-   Automatische Skalierung zur Erfüllung des Bedarfs Zeiten und zur Reduzierung von Kosten stillen Zeiten.

-   Automatische Sicherungen Änderungen und Daten zu schützen.

-   Hohe Verfügbarkeit und Flexibilität der Azure-PaaS-Plattform.

-   Bereitstellungsslots für Entwicklung und Stagingumgebungen und für das Testen mehrerer Standortentwürfe.

-   Lastenausgleich und Schutz Distributed Denial of Service (DDoS durchführen).

-   Datenverkehrsmanagement, Benutzer, der am nächsten geografischen Bereitstellung zu leiten.

Obwohl Anwendungsdienst die beste Wahl für neue Web-apps sein kann, jedoch für vorhandene Anwendungen Anwendungsdienst die beste Wahl möglicherweise nur, wenn Ihre anwendungsabhängigkeiten im App-Dienst unterstützt werden.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Analyse der Kompatibilität für Azure App Service**  
[https://www.migratetoazure.net/Resources](https://www.migratetoazure.net/Resources)


### <a name="benefits-of-moving-to-windows-containers"></a>Vorteile der Migration zu Windows-Containern

Der wichtigste Vorteil der Verwendung von Windows-Container ist, dass Sie eine zuverlässigere und verbesserte Bereitstellung erzielen Sie, im Vergleich zu nicht-Containern apps erhalten. Darüber hinaus erhöht eine die Anwendung effektiv mit Containern modernisiert Ihrer Anwendung bereit, für andere Plattformen und Clouds, die Windows-Containern zu unterstützen. Die Vorteile der Migration zu Windows-Container werden in den nächsten Abschnitten ausführlicher behandelt.

Die primäre Compute-Umgebungen in Azure (bei der allgemeinen Verfügbarkeit, seit Mitte 2017), die Windows-Container unterstützen sind Azure Service Fabric und grundlegende Windows-Container-Hosts (Windows Server 2016-VMs). Diese Umgebungen sind die wichtigsten Infrastruktur-Szenarien, die in diesem Handbuch behandelt.

Sie können Windows-Container auch auf andere Orchestrators, wie Kubernetes, Docker Containerhostclustern oder DC/OS bereitstellen. Derzeit (frühzeitig fallen 2017), diese Plattformen sind in der Vorschau im Azure-Container-Dienst für die Verwendung von Windows-Containern.

>[!div class="step-by-step"]
[Zurück](microsoft-technologies-in-cloud-devops-ready-applications.md)
[Weiter](how-to-deploy-existing-net-apps-to-azure-app-service.md)
