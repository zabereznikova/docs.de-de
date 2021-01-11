---
title: ASP.NET Core gRPC für WCF-Entwickler – gRPC für WCF-Entwickler
description: Einführung in die Erstellung von gRPC-Diensten in ASP.NET Core 5.0 für WCF-Entwickler
ms.date: 01/06/2021
ms.openlocfilehash: 26cce6bb784c08a5b59623ff5882fcf2fbb9e9ac
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970192"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a>ASP.NET Core gRPC für WCF-Entwickler

![Titelbild](./media/cover.png)

EDITION v1.0.1: auf ASP.NET Core 5.0 aktualisiert

Informationen zu den Buchaktualisierungen und Communitybeiträgen finden Sie im [Änderungsprotokoll](https://aka.ms/grpc-ebook-changelog).

VERÖFFENTLICHT VON

Microsoft Developer Division, .NET- und Visual Studio-Produktteams

Eine Abteilung der Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2021 by Microsoft Corporation

Alle Rechte vorbehalten. Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.

Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.

Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.

Autoren:

> **Mark Rendle** – Chief Technical Officer – [Visual ReCode](https://visualrecode.com)
>
> **Miranda Steiner** – Technical Author

Editor:

> **Maira Wenzel** – Senior Content Developer – Microsoft

## <a name="introduction"></a>Einführung

gRPC ist ein modernes Framework zur Erstellung vernetzter Dienste und verteilter Anwendungen. Stellen Sie sich die Leistung der NetTCP-Bindungen der Windows Communication Foundation (WCF) in Kombination mit der plattformübergreifenden Interoperabilität von SOAP vor. gRPC baut auf HTTP/2 und dem Protobuf-Nachrichtencodierungsprotokoll auf, um eine hochleistungsfähige, bandbreitenarme Kommunikation zwischen Anwendungen und Diensten zu ermöglichen. Der Dienst unterstützt die Generierung von Server- und Clientcode in den gängigsten Programmiersprachen und Plattformen, einschließlich .NET, Java, Python, Node.js, Go und C++. Mit der erstklassigen Unterstützung für gRPC in ASP.NET Core 5.0, neben den bestehenden gRPC-Tools und -Bibliotheken für .NET Framework 4.x, gilt es als eine ausgezeichnete Alternative zur WCF für Entwicklungsteams, die .NET in ihren Organisationen einsetzen möchten.

## <a name="who-should-use-this-guide"></a>Zielgruppe dieses Leitfadens

Dieser Leitfaden richtet sich an Entwickler, die in .NET Framework oder .NET arbeiten, zuvor WCF verwendet haben und ihre Anwendungen auf eine moderne RPC-Umgebung für .NET Core 3.0 und spätere Versionen migrieren möchten. Der Leitfaden ist ebenfalls nützlich, wenn Sie ein Upgrade auf .NET 5 durchführen oder in Betracht ziehen und die integrierten gRPC-Tools verwenden möchten.

## <a name="how-you-can-use-this-guide"></a>Wie Sie diesen Leitfaden verwenden können

Dies ist eine kurze Einführung in das Erstellen von gRPC-Diensten in ASP.NET Core 5.0 mit einem besonderen Verweis auf die WCF als analoge Plattform. Darin werden die Prinzipien von gRPC erläutert, indem die einzelnen Konzepte den entsprechenden Features von WCF zugeordnet werden, und es wird ein Leitfaden zum Migrieren einer vorhandenen WCF-Anwendung zu gRPC geboten. Sie ist auch für Entwickler nützlich, die WCF-Kenntnisse besitzen und gRPC erlernen möchten, um neue Dienste zu erstellen. Die Beispielanwendungen können Sie als Vorlage oder Verweis für Ihre eigenen Projekte verwenden, zudem können Sie Code aus dem Buch oder den Beispielen kopieren und diesen so wiederverwenden.

Sie können diesen Leitfaden gerne an Ihr Team weiterleiten, um ein gemeinsames Verständnis dieser Überlegungen und Möglichkeiten zu gewährleisten. Wenn alle Beteiligten mit einer gemeinsamen Terminologie und den zugrunde liegenden Prinzipien arbeiten, kann eine konsistente Anwendung der Architekturmuster und -praktiken gewährleistet werden.

## <a name="references"></a>Verweise

- **Website zu gRPC**
  <https://grpc.io>
- **.NET 5 für Server-Apps im Vergleich zum .NET Framework**
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[Nächste](introduction.md)
