---
title: ASP.NET Core gRPC für WCF-Entwickler – gRPC für WCF-Entwickler
description: Einführung in die Erstellung von gRPC-Diensten in ASP.NET Core 3.0 für WCF-Entwickler
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: b89f5974dd18e7005c6479c5b9eead039364e654
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738072"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a>ASP.NET Core gRPC für WCF-Entwickler

![Titelbild](./media/cover.png)

VERÖFFENTLICHT VON

Microsoft Developer Division, .NET- und Visual Studio-Produktteams

Eine Abteilung der Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2019 Microsoft Corporation

Alle Rechte vorbehalten. Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die auf der Webseite „Marken“ unter https://www.microsoft.com aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.

Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.

Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.

Autor:

> **Mark Rendle** – Chief Technical Officer – [Visual ReCode](https://visualrecode.com)
>
> **Miranda Steiner** – Technical Author

Editoren:

> **Maira Wenzel** – Senior Content Developer – Microsoft

## <a name="introduction"></a>Einführung

gRPC ist ein modernes Framework zur Erstellung vernetzter Dienste und verteilter Anwendungen. Stellen Sie sich die Leistung der NetTCP-Bindungen von WCF mit der plattformübergreifenden Interoperabilität von SOAP vor. gRPC baut auf HTTP/2 und dem Protobuf-Nachrichtencodierungsprotokoll auf, um eine hochleistungsfähige, bandbreitenarme Kommunikation zwischen Anwendungen und Diensten zu ermöglichen. Der Dienst unterstützt die Generierung von Server- und Clientcode in den gängigsten Programmiersprachen und Plattformen, einschließlich .NET, Java, Python, Node.js, Go, C++ und weitere. Mit der erstklassigen Unterstützung für gRPC in ASP.NET Core 3.0, neben den bestehenden gRPC-Tools und -Bibliotheken für .NET 4.x, gilt es als eine ausgezeichnete Alternative zur WCF für Entwicklungsteams, die .NET Core in ihren Organisationen einsetzen wollen.

## <a name="who-should-use-this-guide"></a>Zielgruppe dieses Leitfadens

Dieser Leitfaden richtet sich an Entwickler, die in .NET Framework oder.NET Core arbeiten, die zuvor WCF verwendet haben und ihre Anwendungen auf eine moderne RPC-Umgebung für .NET Core 3.0 und spätere Versionen migrieren möchten. Der Leitfaden richtet sich auch an Entwickler, die ein Upgrade auf .NET Core 3.0 in Betracht ziehen und die integrierten gRPC-Tools verwenden möchten.

## <a name="how-you-can-use-this-guide"></a>Wie Sie diesen Leitfaden verwenden können

Dies ist eine kurze Einführung in das Erstellen von gRPC-Diensten in ASP.NET Core 3.0 mit einem bestimmten Verweis auf die WCF als analoge Plattform. Darin werden die Prinzipien von gRPC erläutert, indem die einzelnen Konzepte den entsprechenden Features von WCF zugeordnet werden, und es wird ein Leitfaden zum Migrieren einer vorhandenen WCF-Anwendung zu gRPC geboten. Sie ist auch für Entwickler nützlich, die WCF-Kenntnisse haben und gRPC erlernen möchten, um neue Dienste zu erstellen. Die Beispielanwendungen können als Vorlage oder Verweis für Ihre eigenen Projekte verwendet werden, und Sie können Code aus dem Buch oder seinen Beispielen kopieren und erneut verwenden.

Sie können diesen Leitfaden gerne an Ihr Team weiterleiten, um ein gemeinsames Verständnis dieser Überlegungen und Möglichkeiten zu gewährleisten. Wenn alle Beteiligten mit einer gemeinsamen Terminologie und den zugrunde liegenden Prinzipien arbeiten, kann eine konsistente Anwendung von Architekturmustern und -praktiken gewährleistet werden.

## <a name="references"></a>Verweise

- **gRPC-Website**  
  <https://grpc.io>
- **Wahl zwischen .NET Core und .NET Framework für Server-Apps**  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[Nächste](introduction.md)
