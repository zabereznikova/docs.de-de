---
title: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
description: Hier erhalten Sie einen allgemeinen Überblick über den Entwicklungs- und Bereitstellungsprozess für containerisierte Anwendungen mit Docker- und Microsoft-Plattformen und -Tools.
ms.date: 01/06/2021
ms.openlocfilehash: 94c277e349bacee9b9fc7b160043005dd4135958
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970114"
---
# <a name="containerized-docker-application-lifecycle-with-microsoft-platform-and-tools"></a>Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools

![Bucheinband](./media/devops-book-cover-large-we.png)

**EDITION v5.0:** auf ASP.NET Core 5.0 aktualisiert

Informationen zu den Buchaktualisierungen und Communitybeiträgen finden Sie im [Änderungsprotokoll](https://aka.ms/DockerLifecycleEbookChangelog).

Dieser Leitfaden bietet eine allgemeine Übersicht über die Entwicklung und Bereitstellung containerisierter ASP.NET Core-Anwendungen in Docker mithilfe der Microsoft-Plattform und -Tools. Zudem ist eine allgemeine Einführung in Azure DevOps für die Implementierung von CI/CD-Pipelines und in Azure Container Registry (ACR) und Azure Kubernetes Service (AKS) für die Bereitstellung enthalten.

Ausführlichere entwicklungsbezogene Details finden Sie im Leitfaden [.NET-Microservices: Architektur für containerisierte .NET-Anwendungen](../microservices/index.md) und in der zugehörigen Referenzanwendung [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).

## <a name="send-us-your-feedback"></a>Senden Sie uns Ihr Feedback!

Dieser Leitfaden wurde geschrieben, um Ihnen die Architektur von Containeranwendungen und Microservices in .NET näherzubringen. Der Leitfaden und die verknüpfte Verweisanwendung werden weiterentwickelt. Wir freuen uns über Ihr Feedback! Wenn Sie Kommentare dazu haben, wie dieser Leitfaden verbessert werden kann, senden Sie Ihr Feedback bitte an <https://aka.ms/ebookfeedback>.

## <a name="credits"></a>Mitwirkende

Autor:

> **Cesar de la Torre**, leitender PM, .NET-Produktteam, Microsoft Corp.

Autorenbetreuung:

> **Janine Patrick**

Entwicklungslektor:

> **Bob Russell**, Solutions Professional bei Microsoft
>
> [**Octal Publishing, Inc.**](http://www.octalpub.com/)

Redaktionelle Produktion:

> [Dianne Russell](http://www.octalpub.com/)
>
> **Octal Publishing, Inc.**

Redakteur:

> **Bob Russell**, Solutions Professional bei Microsoft

Teilnehmer und Prüfer:

> **Nish Anil**, Senior Program Manager, .NET-Team, Microsoft
>
> **Miguel Veloso**, Software Development Engineer bei Plain Concepts
>
> **Sumit Ghosh**, Principal Consultant bei Neudesic

## <a name="copyright"></a>Copyright

VERÖFFENTLICHT VON

Microsoft Developer Division, .NET- und Visual Studio-Produktteams

Eine Abteilung der Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright &copy; 2021 by Microsoft Corporation

Alle Rechte vorbehalten. Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.

Mac und macOS sind Marken von Apple Inc.

Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.

Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.

>[!div class="step-by-step"]
>[Nächste](introduction-to-containers-and-docker.md)
