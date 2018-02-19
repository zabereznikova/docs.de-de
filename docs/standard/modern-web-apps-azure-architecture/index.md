---
title: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure
description: "Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure | Einführung"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: db9f0ddd875df1f84bcc5681ee1383b0185f8b7e
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2018
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a>Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure

![Titelbild](./media/cover.jpg)


.NET Core und ASP.NET Core bieten mehrere Vorteile gegenüber der traditionellen .NET-Entwicklung. Sie sollten .NET Core für Ihre Serveranwendungen verwenden, wenn einige oder alle der folgenden Punkte für den Erfolg Ihrer Anwendung wichtig sind:

-   Plattformübergreifende Unterstützung

-   Verwendung von Microservices

-   Verwendung von Docker-Containern

-   Anforderungen für hohe Leistung und Skalierbarkeit

-   Parallele Versionsverwaltung von .NET-Versionen durch Anwendung auf demselben Server

Traditionelle .NET-Anwendungen können und werden diese Anforderungen unterstützen, aber ASP.NET Core und .NET Core wurden optimiert, um eine verbesserte Unterstützung für die oben genannten Szenarien zu bieten.

Immer mehr Unternehmen entscheiden sich dafür, ihre Webanwendungen in der Cloud zu hosten, indem sie Dienste wie Microsoft Azure nutzen. Sie sollten in Erwägung ziehen, Ihre Anwendung in der Cloud zu hosten, wenn die folgenden Punkte für Ihre Anwendung oder Organisation wichtig sind:

-   Geringere Investitionen in die Kosten des Datencenters (Hardware, Software, Speicherplatz, Hilfsprogramme usw.)

-   Flexible Preisgestaltung (nutzungsbasierte Abrechnung, nicht nach Leerlaufkapazität)

-   Extreme Zuverlässigkeit

-   Verbesserte App-Mobilität, einfaches Ändern, wo und wie Ihre App bereitgestellt wird

-   Flexible Kapazität, Hoch- oder Herunterskalierung basieren auf dem tatsächlichen Bedarf

Das Erstellen von Webanwendungen mit ASP.NET Core (gehostet in Microsoft Azure) bietet zahlreiche Wettbewerbsvorteile gegenüber herkömmlichen Alternativen. ASP.NET Core ist für moderne Webanwendungs-Entwicklungspraktiken und Cloudhostingszenarien optimiert. In diesem Leitfaden erfahren Sie, wie Sie Ihre ASP.NET Core-Anwendungen so gestalten, dass Sie diese Funktionen optimal nutzen können.

## <a name="purpose"></a>Zweck

Dieser Leitfaden bietet eine End-to-End-Anleitung zur Erstellung monolithischer Webanwendungen mit ASP.NET Core und Azure.

Dieser Leitfaden ist das Gegenstück zum Dokument „*Entwerfen und Entwickeln von containerisierten und auf Microservices basierenden Anwendungen mit .NET*“, das sich mehr auf Docker, Microservices und die Bereitstellung von Containern für Unternehmensanwendungen konzentriert.

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a>Entwerfen und Entwickeln von containerisierten und auf Microservices basierenden Apps in .NET
> - **E-Book**  
> <http://aka.ms/MicroservicesEbook>
> - **Beispielanwendung**  
> <http://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a>Zielgruppe dieses Leitfadens

Die Zielgruppe dieses Leitfadens sind hauptsächlich Entwickler, Entwicklungsleiter und Architekten, die daran interessiert sind, moderne Webanwendungen mit Microsoft-Technologien und -Diensten in der Cloud zu erstellen.

Eine zweite Zielgruppe sind technische Entscheidungsträger, die bereits mit ASP.NET und/oder Azure vertraut sind und Informationen dazu suchen, ob ein Upgrade auf ASP.NET Core für neue oder vorhandene Projekte sinnvoll ist.

## <a name="how-you-can-use-this-guide"></a>Wie Sie diesen Leitfaden verwenden können

Dieser Leitfaden wurde in einem relativ kleinen Dokument zusammengefasst, das sich auf die Erstellung von Webanwendungen mit modernen .NET-Technologien und Windows Azure konzentriert. Als solches kann er in seiner Gesamtheit gelesen werden, um eine Grundlage für das Verständnis solcher Anwendungen und ihrer technischen Überlegungen zu schaffen. Der Leitfaden kann zusammen mit seiner Beispielanwendung auch als Ausgangspunkt oder Referenz dienen. Verwenden Sie die zugehörige Beispielanwendung als Vorlage für Ihre eigenen Anwendungen oder um zu sehen, wie Sie die einzelnen Komponenten Ihrer Anwendung organisieren können. Erinnern Sie sich an die Grundsätze des Leitfadens und die Beschreibung von Architektur- und Technologieoptionen und Entscheidungsüberlegungen, wenn Sie diese Entscheidungen für Ihre eigene Anwendung abwägen.

Sie können diesen Leitfaden gerne an Ihr Team weiterleiten, um ein gemeinsames Verständnis dieser Überlegungen und Möglichkeiten zu gewährleisten. Wenn alle Beteiligten mit einer gemeinsamen Terminologie und den zugrunde liegenden Prinzipien arbeiten, kann eine konsistente Anwendung von Architekturmustern und -praktiken gewährleistet werden.

## <a name="references"></a>Verweise
- **Wahl zwischen .NET Core und .NET Framework für Server-Apps**  
<https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
[Nächster] (modern-web-applications-characteristics.md)
