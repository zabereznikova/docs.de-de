---
title: Blazor für ASP.NET Web Forms-Entwickler
description: Erfahren Sie, wie Sie mit .NET unter Verwendung von Blazor und .NET Core auf einfache und vertraute Weise ausgewachsene Web-Apps entwickeln können.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 394d11038b59f4cbe9e9955df43b6198eb5daaf8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088128"
---
# <a name="blazor-for-aspnet-web-forms-developers"></a>Blazor für ASP.NET Web Forms-Entwickler

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![Screenshot: Covers des E-Books „Serverless Apps“ (Serverlose Apps)](./media/index/blazor-for-web-forms-developers-cover.png)

> DOWNLOAD verfügbar unter: <https://aka.ms/blazor-ebook>

VERÖFFENTLICHT VON

Microsoft Developer Division, .NET- und Visual Studio-Produktteams

Eine Abteilung der Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2019 Microsoft Corporation

Alle Rechte vorbehalten. Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.

Mac und macOS sind Marken von Apple Inc.

Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.

Autoren:

> **[Daniel Roth](https://github.com/danroth27)** , Principal Program Manager, Microsoft Corp.

> **[Jeff Fritz](https://github.com/csharpfritz)** , Senior Program Manager, Microsoft Corp.

> **[Taylor Southwick](https://github.com/twsouthwick)** , Senior Software Engineer, Microsoft Corp.

> **[Scott Addie](https://github.com/scottaddie)** , Senior Content Developer, Microsoft Corp.

## <a name="introduction"></a>Einführung

.NET unterstützt schon seit langem die Entwicklung von Web-Apps mithilfe von ASP.NET, einen umfassenden Satz von Frameworks und Tools zum Erstellen von Web-Apps jeder Art. ASP.NET kann auf eine eigene Erbfolge von Web-Frameworks und Technologien zurückblicken, an deren Anfang die klassischen Active Server Pages (ASP) stehen. Frameworks wie ASP.NET Web Forms, ASP.NET MVC, ASP.NET Web Pages und in jüngerer Zeit ASP.NET Core bieten einen produktiven und leistungsstarken Weg zum Erstellen von *auf dem Server gerenderten* Web-Apps, bei denen die Inhalte der Benutzeroberfläche als Reaktion auf HTTP-Anforderungen dynamisch auf dem Server generiert werden. Jedes ASP.NET-Framework richtet sich an eine andere Zielgruppe und steht für eine andere Philosophie bei der Web-App-Erstellung. ASP.NET Web Forms wurde mit der ursprünglichen Version von .NET Framework geliefert und ermöglichte die Webentwicklung auf der Grundlage vieler Muster, die Desktopentwicklern vertraut sind, wie etwa wiederverwendbare Steuerelemente der Benutzeroberfläche mit einfachem Ereignishandling. Allerdings bot keins der ASP.NET-Angebote eine Möglichkeit zum Ausführen von Code im Browser des Benutzers. Dazu sind das Schreiben von JavaScript-Code und die Verwendung eines der vielen JavaScript-Frameworks und -Tools erforderlich, die sich im Lauf der Jahre wechselnder Beliebtheit erfreut haben: jQuery, Knockout, Angular, React usw.

[Blazor](https://blazor.net) ist ein neues Framework, mit dem sich die Grenzen des Möglichen beim Erstellen von Web-Apps mit .NET verschieben. Blazor ist ein clientseitiges Framework für Webbenutzeroberflächen, das auf C# anstelle von JavaScript basiert. Mit Blazor können Sie Ihre clientseitige Logik und die Komponenten der Benutzeroberfläche in C# schreiben, sie in normale .NET-Assemblys kompilieren und sie dann mithilfe eines neuen offenen Webstandards namens WebAssembly direkt im Browser ausführen. Alternativ kann Blazor Ihre .NET-Benutzeroberflächenkomponenten auf dem Server ausführen und alle Interaktionen mit der Benutzeroberfläche flüssig über eine Echtzeitverbindung mit dem Browser verarbeiten. In Kombination mit auf dem Server ausgeführtem .NET ermöglicht Blazor die vollständige Webentwicklung mit .NET. Zwar hat Blazor viele Gemeinsamkeiten mit ASP.NET Web Forms, etwa ein wiederverwendbares Komponentenmodell und ein einfaches Verfahren zum Verarbeiten von Benutzerereignissen, es baut aber außerdem auf den Grundlagen von .NET Core auf, um eine moderne und leistungsstarke Benutzeroberfläche zur Webentwicklung zur Verfügung zu stellen.

Dieses Buch macht ASP.NET Web Forms-Entwickler auf vertraute und komfortable Weise mit Blazor bekannt. Es stellt Blazor-Konzepte parallel mit analogen Konzepten in ASP.NET Web Forms vor und erläutert zugleich neue Konzepte, die möglicherweise weniger vertraut sind. Es behandelt eine große Bandbreite von Themen und Anliegen, einschließlich Komponentenerstellung, Routing, Layout, Konfiguration und Sicherheit. Und obwohl die Inhalte dieses Buchs sich hauptsächlich auf die Förderung von Neuentwicklung beziehen, werden auch Richtlinien und Strategien für das Migrieren vorhandener ASP.NET Web Forms zu Blazor behandelt, für den Fall, dass Sie eine vorhandene App modernisieren möchten.

## <a name="who-should-use-the-book"></a>Zielgruppe dieses Buchs

Dieses Buch richtet sich an ASP.NET Web Forms-Entwickler, die nach einer Einführung in Blazor suchen, die auf ihren vorhandenen Kenntnissen und Qualifikationen aufbaut. Dieses Buch kann beim schnellen Einstieg in ein neues Blazor-basiertes Projekt oder beim Festlegen einer Roadmap zum Modernisieren einer vorhandenen ASP.NET Web Forms-Anwendung helfen.

## <a name="how-to-use-the-book"></a>So verwenden Sie dieses Buch

Der erste Teil des Buchs befasst sich damit, was Blazor ist, und vergleicht es mit der Web-App-Entwicklung mit ASP.NET Web Forms. Anschließend behandelt das Buch Kapitel für Kapitel eine Reihe von Blazor-Themen und setzt jedes Blazor-Konzept zu dem entsprechenden Konzept in ASP.NET Web Forms in Beziehung oder erläutert gründlich die vollständig neuen Konzepte. Das Buch verweist außerdem regelmäßig auf eine vollständige Beispiel-App, die sowohl in ASP.NET Web Forms als auch in Blazor implementiert wurde, um Blazor-Features zu veranschaulichen und eine Fallstudie für das Migrieren von ASP.NET Web Forms zu Blazor zu bieten. Sie finden beide Implementierungen der Beispiel-App (ASP.NET Web Forms- und Blazor-Version) auf [GitHub](https://github.com/dotnet-architecture/eshoponblazor).

## <a name="what-this-book-doesnt-cover"></a>Was in diesem Buch nicht behandelt wird

Dieses Buch ist eine Einführung in Blazor, kein umfassendes Migrationshandbuch. Es bietet zwar Anleitung, wie man sich dem Migrieren eines Projekts von ASP.NET Web Forms zu Blazor nähern kann, es behandelt aber nicht jede Nuance und jedes Detail. Einen allgemeineren Leitfaden zum Migrieren von ASP.NET zu ASP.NET Core finden Sie im [Migrationsleitfaden](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/) in der ASP.NET Core-Dokumentation.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

Die offizielle Blazor-Homepage und -Dokumentation finden Sie unter <https://blazor.net>.

## <a name="send-your-feedback"></a>Senden Sie uns Ihr Feedback

Dieses Buch und die dazugehörigen Beispiele werden ständig weiterentwickelt, deshalb freuen wir uns über Ihr Feedback. Wenn Sie Anmerkungen zur Verbesserung dieses Buchs haben, nutzen Sie den Feedbackabschnitt, der unten auf jeder Seite zu finden ist und über den [GitHub-Issues](https://github.com/dotnet/docs/issues) erstellt werden.

>[!div class="step-by-step"]
>[Nächste](introduction.md)
