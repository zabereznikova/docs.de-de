---
title: Installieren von F#
description: Erfahren Sie, wie F# Sie basierend auf Ihrer Umgebung installieren.
ms.date: 09/05/2019
ms.openlocfilehash: 592a4c7763266cee68809fca84f9604d7e96b8f1
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204873"
---
# <a name="install-f"></a>Installieren von F\#

Sie können F# auf verschiedene Arten, abhängig von Ihrer Umgebung installieren.

## <a name="install-f-with-visual-studio"></a>Installieren F# mit Visual Studio

Wenn Sie [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) zum ersten Mal herunterladen, wird zunächst der Visual Studio-Installer installiert. Installieren Sie die entsprechende SKU von Visual Studio über den Installer. Wenn Sie es bereits installiert haben, klicken Sie auf **ändern**.

Im nächsten Schritt sehen Sie eine Liste der Workloads. Wählen Sie **ASP.net und Webentwicklung** , um F# Unterstützung und .net Core-Unterstützung für ASP.net Core Projekte zu installieren.

Klicken Sie anschließend in der unteren rechten Ecke auf **ändern** .  Dadurch wird alles installiert, was Sie ausgewählt haben. Sie können dann Visual Studio 2017 mit F# Sprachunterstützung öffnen, indem Sie auf **starten**klicken.

## <a name="install-f-with-visual-studio-code"></a>Installieren von F# mit Visual Studio Code

Vergewissern Sie sich zunächst, dass git auf Ihrem Pfad [installiert](https://git-scm.com/download) und verfügbar ist. Sie können überprüfen, ob die Installation ordnungsgemäß erfolgt ist, indem Sie `git --version` an einer Eingabeaufforderung eingeben und die **Eingabe**Taste drücken.

Installieren Sie als nächstes die [.net Core SDK](https://dotnet.microsoft.com/download).

Anschließend müssen [Visual Studio Code](https://code.visualstudio.com) installiert sein.

Klicken Sie anschließend auf das Symbol Erweiterungen, und suchen Sie nach "ionide":

Das einzige für F# die Unterstützung in Visual Studio Code erforderliche Plug-in ist " [ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)". Sie können jedoch auch [ionide-Fake](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) installieren, um [gefälschte](https://fake.build/) Unterstützung und [ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) zu erhalten, um Unterstützung für das [Paket](https://fsprojects.github.io/Paket/) zu erhalten. Fake und Paket sind zusätzliche F# communitytools zum Entwickeln von Projekten und zum Verwalten von Abhängigkeiten.

## <a name="install-f-with-visual-studio-for-mac"></a>Installieren von F# in Visual Studio für Mac

F#wird standardmäßig in [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)installiert, unabhängig von der Konfiguration, die Sie auswählen.

Nachdem die Installation abgeschlossen ist, wählen Sie "Visual Studio starten" aus. Sie können Sie auch über Finder unter macOS starten.

## <a name="install-f-on-a-build-server"></a>Auf F# einem Buildserver installieren

Wenn Sie .net Core oder .NET Framework über das .NET SDK verwenden, müssen Sie einfach das .NET SDK auf dem Buildserver installieren. Sie verfügt über alles, was Sie benötigen.

Wenn Sie .NET Framework verwenden und das .NET SDK **nicht** verwenden, müssen Sie die [Visual Studio Build Tools-SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) auf Ihrem Windows-Server installieren. Wählen Sie im Installationsprogramm **.net-** desktopbuildtools aus, und wählen Sie dann die  **F# Compilerkomponente** auf der rechten Seite des Installations Menüs aus.
