---
title: Installieren von F#
description: 'Erfahren Sie, wie Sie F # auf verschiedene Arten installieren.'
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224292"
---
# <a name="install-f"></a>Installieren von F\#

Sie können F # auf verschiedene Weise installieren, abhängig von Ihrer Umgebung.

## <a name="install-f-with-visual-studio"></a>Installieren von F # mit Visual Studio

1. Wenn Sie [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) zum ersten Mal herunterladen, wird zuerst Visual Studio-Installer installiert. Installieren Sie die entsprechende Edition von Visual Studio über den Installer.

   Wenn Sie Visual Studio bereits installiert haben, wählen Sie neben der Edition, der Sie F # hinzufügen möchten, die Option **ändern** aus.

2. Wählen Sie auf der Seite "Workloads" die Arbeitsauslastung **ASP.net und Webentwicklung** aus, die Unterstützung für die Unterstützung von F # und .net Core für ASP.net Core Projekte umfasst

3. Wählen Sie in der unteren rechten Ecke **ändern** aus, um alles zu installieren, was Sie ausgewählt haben.

   Anschließend können Sie Visual Studio mit F # öffnen, indem Sie in Visual Studio-Installer **starten** auswählen.

## <a name="install-f-with-visual-studio-code"></a>Installieren von F # mit Visual Studio Code

1. Stellen Sie sicher, dass [git](https://git-scm.com/download) auf Ihrem Pfad installiert und verfügbar ist. Sie können überprüfen, ob Sie ordnungsgemäß installiert ist, indem Sie `git --version` an einer Eingabeaufforderung eingeben und die **Eingabe**Taste drücken.

2. Installieren Sie die [.net Core SDK](https://dotnet.microsoft.com/download) und [Visual Studio Code](https://code.visualstudio.com).

3. Wählen Sie das Symbol Erweiterungen aus, und suchen Sie nach "ionide":

   Das einzige für die F #-Unterstützung in Visual Studio Code erforderliche Plug-in ist " [ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)". Sie können jedoch auch [ionide-Fake](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) installieren, um [gefälschte](https://fake.build/) Unterstützung und [ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) zu erhalten, um Unterstützung für das [Paket](https://fsprojects.github.io/Paket/) zu erhalten. Fake und Paket sind zusätzliche F #-communitytools zum Entwickeln von Projekten und zum Verwalten von Abhängigkeiten.

## <a name="install-f-with-visual-studio-for-mac"></a>Installieren von F # mit Visual Studio für Mac

F # wird standardmäßig in [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)installiert, unabhängig von der Konfiguration, die Sie auswählen.

Nachdem die Installation abgeschlossen ist, klicken Sie auf **Visual Studio starten**. Sie können Visual Studio auch über Finder auf macOS öffnen.

## <a name="install-f-on-a-build-server"></a>Installieren von F # auf einem Buildserver

Wenn Sie .net Core oder .NET Framework über das .NET SDK verwenden, müssen Sie einfach das .NET SDK auf dem Buildserver installieren. Sie verfügt über alles, was Sie benötigen.

Wenn Sie .NET Framework verwenden und das .NET SDK **nicht** verwenden, müssen Sie die [Visual Studio Build Tools-SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) auf Ihrem Windows-Server installieren. Wählen Sie im Installationsprogramm **.net-** desktopbuildtools aus, und wählen Sie dann auf der rechten Seite des Installer-Menüs die **F #-Compilerkomponente** aus.
