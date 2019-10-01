---
title: ASP.NET Core gRPC für WCF-Entwickler – gRPC für WCF-Entwickler
description: ZU SCHREIBEND
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: dc39fc96e7154fb50acd0b65a58586b3fa12ab50
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696919"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a>ASP.NET Core gRPC für WCF-Entwickler

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

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

TODO

## <a name="purpose"></a>Zweck

TODO

## <a name="who-should-use-this-guide"></a>Zielgruppe dieses Leitfadens

**AKTUALISIEREN**

Die Zielgruppe für diesen Leitfaden sind WCF-Entwickler, Entwicklungsleiter und Architekten, die an der Migration von WCF-Lösungen auf .NET 4 und früheren Versionen zu ASP.NET Core 3.0 mithilfe von gRPC-Diensten interessiert sind.

## <a name="how-you-can-use-this-guide"></a>Wie Sie diesen Leitfaden verwenden können

**AKTUALISIEREN**

Dies ist eine kurze Einführung in das Erstellen von gRPC-Diensten in ASP.NET Core 3.0 mit einem bestimmten Verweis auf die WCF als analoge Plattform. Darin werden die Prinzipien von gRPC erläutert, indem die einzelnen Konzepte den entsprechenden Features von WCF zugeordnet werden, und es wird ein Leitfaden zum Migrieren einer vorhandenen WCF-Anwendung zu gRPC geboten. Sie ist auch für Entwickler nützlich, die WCF-Kenntnisse haben und gRPC erlernen möchten, um neue Dienste zu erstellen. Die Beispielanwendung kann als Vorlage oder Verweis für Ihre eigenen Projekte verwendet werden, und Sie können Code aus dem Buch oder seinen Beispielen kopieren und erneut verwenden.

Sie können diesen Leitfaden gerne an Ihr Team weiterleiten, um ein gemeinsames Verständnis dieser Überlegungen und Möglichkeiten zu gewährleisten. Wenn alle Beteiligten mit einer gemeinsamen Terminologie und den zugrunde liegenden Prinzipien arbeiten, kann eine konsistente Anwendung von Architekturmustern und -praktiken gewährleistet werden.

## <a name="references"></a>Verweise

- **gRPC-Website**  
  <https://grpc.io>
- **Wahl zwischen .NET Core und .NET Framework für Server-Apps**  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[Nächste](introduction.md)
