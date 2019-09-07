---
title: Installieren von F#
description: Erfahren Sie, wie F# Sie basierend auf Ihrer Umgebung installieren.
ms.date: 09/05/2019
ms.openlocfilehash: 18b660ff640904119d63f57405752a14f7673e0c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400721"
---
# <a name="install-f"></a>Installieren von F\#

Sie können F# auf verschiedene Arten, abhängig von Ihrer Umgebung installieren.

## <a name="install-f-with-visual-studio"></a>Installieren F# mit Visual Studio

Wenn Sie [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) zum ersten Mal herunterladen, wird zunächst der Visual Studio-Installer installiert. Installieren Sie die entsprechende SKU von Visual Studio über den Installer. Wenn Sie es bereits installiert haben, klicken Sie auf **ändern**.

Im nächsten Schritt sehen Sie eine Liste der Workloads. Wählen Sie **ASP.NET und Webentwicklung** der F#-Unterstützung und Unterstützung für ASP.NET Core-Projekte für .NET Core installieren.

Klicken Sie anschließend in der unteren rechten Ecke auf **ändern** .  Dadurch wird alles installiert, was Sie ausgewählt haben. Sie können dann Visual Studio 2017 mit F# Sprachunterstützung öffnen, indem Sie auf **starten**klicken.

## <a name="install-f-with-visual-studio-for-mac"></a>Installieren von F# in Visual Studio für Mac

F#wird standardmäßig in [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)installiert, unabhängig von der Konfiguration, die Sie auswählen.

Nachdem die Installation abgeschlossen ist, wählen Sie "Visual Studio starten" aus. Sie können Sie auch über Finder unter macOS starten.

## <a name="install-f-with-visual-studio-code"></a>Installieren von F# mit Visual Studio Code

[Git muss installiert](https://git-scm.com/download) sein und auf dem Pfad verfügbar sein, um Projektvorlagen verwenden zu können. Sie können überprüfen, ob die Installation korrekt ist `git --version` , indem Sie an einer Eingabeaufforderung eingeben und die **Eingabe**Taste drücken.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

[Mono](https://www.mono-project.com) dient zur [F# Interactive](../tutorials/fsharp-interactive/index.md) unterstützen. Die einfachste Möglichkeit, Mono unter macOS zu installieren, ist über Homebrew. Geben Sie im Terminal einfach Folgendes ein:

```console
brew install mono
```

Installieren Sie auch die [.net Core SDK](https://www.microsoft.com/net/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

[Mono](https://www.mono-project.com) dient zur [F# Interactive](../tutorials/fsharp-interactive/index.md) unterstützen. Wenn Sie mit Debian oder Ubuntu arbeiten, können Sie Folgendes verwenden:

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

Installieren Sie auch die [.net Core SDK](https://www.microsoft.com/net/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Installieren Sie [Visual Studio mit F#-Unterstützung](#install-f-with-visual-studio). Dadurch werden alle erforderlichen Komponenten zum Schreiben, kompilieren und Ausführen von F#-Code installiert.

Installieren Sie auch die [.net Core SDK](https://www.microsoft.com/net/download/).

---

Sie müssen dann [Visual Studio Code](https://code.visualstudio.com) installieren.

Klicken Sie anschließend auf das Symbol Erweiterungen, und suchen Sie nach "ionide":

Erforderlich für F#-Unterstützung in Visual Studio Code ist die einzige-Plug-in [Ionide-Fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Sie können jedoch auch [ionide-Fake](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) installieren, um [gefälschte](https://fsharp.github.io/FAKE/) Unterstützung und [ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) zu erhalten, um Unterstützung für das [Paket](https://fsprojects.github.io/Paket/) zu erhalten. Fake und Paket sind zusätzliche F# communitytools zum Entwickeln von Projekten und zum Verwalten von Abhängigkeiten.

## <a name="install-f-on-a-build-server"></a>Auf F# einem Buildserver installieren

Wenn Sie .net Core oder .NET Framework über das .NET SDK verwenden, müssen Sie einfach das .NET SDK auf dem Buildserver installieren. Sie verfügt über alles, was Sie benötigen.

Wenn Sie .NET Framework verwenden und das .NET SDK **nicht** verwenden, müssen Sie die [Visual Studio Build Tools-SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) auf Ihrem Windows-Server installieren. Wählen Sie im Installationsprogramm **.net-** desktopbuildtools aus, und wählen Sie dann die  **F# Compilerkomponente** auf der rechten Seite des Installations Menüs aus.
