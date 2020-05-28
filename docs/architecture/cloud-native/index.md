---
title: Entwickeln cloudnativer .NET-Anwendungen für Azure
description: Leitfaden zum Erstellen cloudnativer Anwendungen, die Container, Microservices und serverlose Features von Azure nutzen.
author: ardalis
ms.date: 05/13/2020
ms.openlocfilehash: 196671468e56147f714078d1671f44af21bcf327
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83840883"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a>Entwickeln cloudnativer .NET-Anwendungen für Azure

![Titelbild](./media/cover.png)

**Edition 1.0**

VERÖFFENTLICHT VON

Microsoft Developer Division, .NET- und Visual Studio-Produktteams

Eine Abteilung der Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright &copy; 2020 Microsoft Corporation

Alle Rechte vorbehalten. Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die auf der Webseite „Marken“ unter [https://www.microsoft.com](https://www.microsoft.com) aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.

Mac und macOS sind Marken von Apple Inc.

Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.

Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.

Autoren:

> **Rob Vettor**, Principal Cloud System Architect und IP Architect bei Microsoft – [thinkingincloudnative.com](http://thinkingincloudnative.com/about/)
>
> **Steve „ardalis“ Smith**, Software Architect und Trainer – [Ardalis.com](https://ardalis.com)

Teilnehmer und Prüfer:

> **Cesar De la Torre**, Principal Program Manager, .NET-Team, Microsoft
>
> **Nish Anil**, Senior Program Manager, .NET-Team, Microsoft
>
> **Jeremy Likness**, Senior Program Manager, .NET-Team, Microsoft
>
> **Cecil Phillip**, Senior Cloud Advocate, Microsoft

Editoren:

> **Maira Wenzel**, Senior Program Manager, .NET-Team, Microsoft

## <a name="version"></a>Version

Dieser Leitfaden wurde für **.NET Core 3.1** geschrieben und enthält viele weitere Updates zu ähnlichen Technologien (wie Azure und entsprechende Drittanbietertechnologien), die zeitgleich mit .NET Core 3.1 veröffentlicht wurden.

## <a name="who-should-use-this-guide"></a>Zielgruppe dieses Leitfadens

Die Zielgruppe dieses Leitfadens sind hauptsächlich Entwickler, Entwicklungsleiter und Architekten, die lernen möchten, wie Anwendungen für die Cloud erstellt werden.

Technische Entscheidungsträger, die überlegen, ihre Anwendungen mithilfe eines cloudnativen Ansatzes zu erstellen, sind eine sekundäre Zielgruppe.

## <a name="how-you-can-use-this-guide"></a>Wie Sie diesen Leitfaden verwenden können

In diesem Leitfaden wird zunächst der Begriff „Cloudnativ“ definiert und eine Referenzanwendung vorgestellt, die mithilfe cloudnativer Prinzipien und Technologien erstellt wurde. Nach diesen ersten beiden Kapiteln ist das Buch in spezifische Kapitel unterteilt, die sich mit gängigen Themen im Bezug zu den meisten cloudnativen Anwendungen befassen. Sie können zu einem dieser Kapitel springen, um die folgenden cloudnativen Ansätze kennenzulernen:

- Daten und Datenzugriff
- Kommunikationsmuster
- Skalierung und Skalierbarkeit
- Anwendungsresilienz
- Überwachung und Integrität
- Identität und Sicherheit
- DevOps

Dieser Leitfaden ist sowohl im PDF-Format als auch online verfügbar. Sie können dieses Dokument oder Links zur Onlineversion an Ihr Team weiterleiten, um ein allgemeines Verständnis dieser Themen sicherzustellen. Die meisten dieser Themen profitieren von einem einheitlichen Verständnis der zugrunde liegenden Prinzipien und Muster sowie der Nachteile einiger Entscheidungen, die in Relation zu diesen Entscheidungen stehen. Das Ziel dieses Dokuments ist es, Teams und Teamleiter mit den Informationen auszustatten, die sie benötigen, um fundierte Entscheidungen bezüglich der Architektur, der Entwicklung und des Hostings ihrer Anwendungen zu treffen.

## <a name="send-your-feedback"></a>Senden Sie uns Ihr Feedback

Dieses Buch und die dazugehörigen Beispiele werden ständig weiterentwickelt, deshalb freuen wir uns über Ihr Feedback. Wenn Sie Anmerkungen zur Verbesserung dieses Buchs haben, nutzen Sie den Feedbackabschnitt, der unten auf jeder Seite zu finden ist und über den [GitHub-Issues](https://github.com/dotnet/docs/issues) erstellt werden.

>[!div class="step-by-step"]
>[Nächste](introduction.md)
