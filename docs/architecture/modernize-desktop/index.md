---
title: Modernisieren von Desktop-Apps unter Windows 10 mit .NET Core 3.1
description: Hier erfahren Sie, wie Sie Desktop-Apps mit .NET Core 3.1 modernisieren können.
ms.date: 05/12/2020
ms.openlocfilehash: 5861f806a9158ef761c47bc23e51327d4e2d0480
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83422662"
---
# <a name="modernizing-desktop-apps-on-windows-10-with-net-core-31"></a>Modernisieren von Desktop-Apps unter Windows 10 mit .NET Core 3.1

![Screenshot: Cover des E-Books „Modernisieren von Desktop-Apps“](./media/modernizing-existing-desktop-apps-ebook-cover.png)

VERÖFFENTLICHT VON

Microsoft Developer Division, .NET- und Visual Studio-Produktteams

Eine Abteilung der Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2020 by Microsoft Corporation

Alle Rechte vorbehalten. Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.

Mac und macOS sind Marken von Apple Inc.

Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.

Mitautoren:

> **Olia Gavrysh**, Senior Program Manager, .NET-Team, Microsoft

> **Miguel Angel Castejón Dominguez**, Innovation Architect bei Kabel

Teilnehmer und Prüfer:

> **Maira Wenzel**, Senior Program Manager, .NET-Team, Microsoft

> **Andy De Gorge**, Senior Content Developer, .NET-Dokumentationsteam, Microsoft

> **Miguel Ramos**, Senior Program Manager, UWP-Team, Microsoft

> **Adam Braden**, Principal Program Manager, UWP-Team, Microsoft

> **Ricardo Minguez Pablos**, Senior Program Manager, Azure IoT-Team, Microsoft

> **Nish Anil**, Senior Program Manager, .NET-Team, Microsoft

> **Beth Massi**, Senior Product Marketing Manager, Microsoft

> **Scott Hunter**, Partner Director Program Manager, .NET-Team, Microsoft

> **Marta Fuentes Lara**, Kabel

> **Raúl Fernández de Córdoba**, Kabel

> **Antonio Manuel Fernández Cantos**, Kabel

## <a name="introduction"></a>Einführung

In diesem E-Book werden Strategien für die Migration vorhandener Desktop-Apps behandelt. Zu diesen zählen die Modernisierung und Integration der aktuellen Runtime, Sprache und Plattformfeatures. Sie werden feststellen, dass es keine Pauschallösung gibt, denn jede Anwendung ist einzigartig – genau wie Ihre Anforderungen. Es gibt jedoch gängige Ansätze zum Hinzufügen neuer Features und Funktionen zu Ihren Anwendungen, die Ihnen nützlich sein können. Bei einigen von diesen muss Ihr Code nur geringfügig geändert werden. In diesem E-Book wird erklärt, wie alle diese Features unter der Haube funktionieren. Zudem werden Implementierungsverfahren erläutert. Einige gängige Szenarios für die Modernisierung vorhandener Desktop-Apps werden ausführlich vorgestellt, sodass Sie sich Anregungen für Ihre eigenen Projekte holen können.

Der Microsoft-Ansatz für die Modernisierung vorhandener Apps ermöglicht es Ihnen, Ihren eigenen flexiblen Weg zu finden. Die in diesem Buch beschriebenen Modernisierungsstrategien sind größtenteils unabhängig. Sie können diejenigen auswählen, die für Ihre Anwendung relevant sind, und die restlichen überspringen. Die Strategien können also so kombiniert werden, dass sie Ihren Anwendungsanforderungen bestmöglich gerecht werden.

## <a name="who-should-use-the-book"></a>Zielgruppe dieses Buchs

Dieses Buch richtet sich an Entwickler und Lösungsarchitekten, die vorhandene Windows Forms- und WPF-Desktop-Apps modernisieren möchten, um die Vorteile von .NET Core und Windows 10 zu nutzen.

Auch Entscheidungsträgern in technischen Abteilungen kann dieses E-Book nützlich sein – zum Beispiel Unternehmensarchitekten, Entwicklungsleitern oder Führungskräften, die sich einen Überblick über die Vorteile verschaffen möchten, die die Aktualisierung vorhandener Desktop-Apps bietet.

## <a name="how-to-use-the-book"></a>So verwenden Sie dieses Buch

Dieses E-Book befasst sich mit dem „Warum“, das hinter der Modernisierung vorhandener Anwendungen steht, sowie mit den speziellen Vorteilen, die Ihnen .NET Core 3.1 und MSIX bieten, wenn Sie Ihre Desktop-Apps modernisieren. Der Inhalt des E-Books richtet sich an Architekten und technische Entscheidungsträger, die einen Überblick benötigen, sich aber nicht auf die Umsetzung und technische Details konzentrieren müssen.

In den verschiedenen Kapiteln finden Sie Codeausschnitte und Screenshots für Implementierungsbeispiele. In Kapitel 5 wird sogar ein vollständiger Migrationsprozess für Beispielanwendungen dargestellt.

## <a name="what-this-book-doesnt-cover"></a>Was in diesem Buch nicht behandelt wird

In diesem E-Book werden vor allem Lift-&-Shift-Szenarios behandelt, bei denen die Vorteile der Modernisierungsverfahren im Vordergrund stehen, für die Ihr Code nicht umgeschrieben werden muss.

Die Entwicklung moderner Anwendungen mit .NET Core und der Einstieg in Windows Forms und WPF werden in diesem E-Book nicht thematisiert. Der Fokus liegt darauf, wie Sie vorhandene Desktop-Apps mithilfe der neuesten Technologien für die Desktopentwicklung aktualisieren können.

## <a name="samples-used-in-this-book"></a>Beispiele in diesem E-Book

Die Beispielanwendung `eShopModernizing` wird verwendet, um die für eine Modernisierung erforderlichen Schritte zu veranschaulichen. Diese Anwendung ist in zwei Varianten verfügbar: Windows Forms und WPF. Für beide wird ausführlich erläutert, wie der die Modernisierung auf .NET Core abläuft.

Darüber hinaus finden Sie im GitHub-Repository für dieses E-Book die Ergebnisse des Prozesses, die für Sie relevant werden können, wenn Sie das ausführliche Tutorial befolgen.

## <a name="send-your-feedback"></a>Senden Sie uns Ihr Feedback

Dieses Buch und die dazugehörigen Beispiele werden ständig weiterentwickelt, deshalb freuen wir uns über Ihr Feedback. Wenn Sie Anmerkungen zur Verbesserung dieses Buchs haben, nutzen Sie den Feedbackabschnitt, der unten auf jeder Seite zu finden ist und über den [GitHub-Issues](https://github.com/dotnet/docs/issues) erstellt werden.

>[!div class="step-by-step"]
>[Nächste](why-modern-applications.md)
