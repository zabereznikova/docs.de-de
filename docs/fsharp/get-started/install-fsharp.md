---
title: Installieren von F#
description: Erfahren Sie, wie Sie die Datei auf verschiedene Arten installieren.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401094"
---
# <a name="install-f"></a>Installieren F\#

Je nach Umgebung können Sie die Datei auf verschiedene Arten installieren.

## <a name="install-f-with-visual-studio"></a>Installieren von F-Code mit Visual Studio

1. Wenn Sie Visual [Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) zum ersten Mal herunterladen, wird Visual Studio Installer zuerst installiert. Installieren Sie die entsprechende Edition von Visual Studio aus dem Installationsprogramm.

   Wenn Sie Visual Studio bereits installiert haben, wählen Sie neben der Edition, der Sie F- hinzufügen möchten, die Option **Ändern** aus.

2. Wählen Sie auf der Seite Workloads die **ASP.NET- und Webentwicklungs-Workload** aus, die die Unterstützung von F- und .NET Core für ASP.NET Core-Projekte umfasst.

3. Wählen Sie In der unteren rechten Ecke **ändern** aus, um alles zu installieren, was Sie ausgewählt haben.

   Anschließend können Sie Visual Studio mit F- öffnen, indem Sie **Launch** in Visual Studio Installer auswählen.

## <a name="install-f-with-visual-studio-code"></a>Installieren von F-Code mit Visual Studio-Code

1. Stellen Sie sicher, dass [Git](https://git-scm.com/download) auf Ihrem PATH installiert und verfügbar ist. Sie können überprüfen, ob es ordnungsgemäß `git --version` installiert ist, indem Sie eine Eingabeaufforderung eingeben und **die Eingabeeingabe**drücken.

2. Installieren Sie [das .NET Core SDK](https://dotnet.microsoft.com/download) und [Visual Studio Code](https://code.visualstudio.com).

3. Wählen Sie das Symbol Erweiterungen und suchen Sie nach "Ionide":

   Das einzige Plugin, das für die F-Unterstützung in Visual Studio Code erforderlich ist, ist [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Sie können jedoch auch [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) installieren, um [FAKE-Unterstützung](https://fake.build/) und [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) zu erhalten, um [Paket-Unterstützung](https://fsprojects.github.io/Paket/) zu erhalten. FAKE und Paket sind zusätzliche Tools für die Community, um Projekte zu erstellen bzw. Abhängigkeiten zu verwalten.

## <a name="install-f-with-visual-studio-for-mac"></a>Installieren von F-Code mit Visual Studio für Mac

In [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)wird standardmäßig f- installiert, unabhängig davon, welche Konfiguration Sie auswählen.

Nachdem die Installation abgeschlossen ist, wählen Sie **Visual Studio starten**. Sie können Visual Studio auch über Finder unter macOS öffnen.

## <a name="install-f-on-a-build-server"></a>Installieren von F- auf einem Buildserver

Wenn Sie .NET Core oder .NET Framework über das .NET SDK verwenden, müssen Sie einfach das .NET SDK auf Ihrem Buildserver installieren. Es hat alles, was Sie brauchen.

Wenn Sie .NET Framework verwenden und das .NET SDK **nicht** verwenden, müssen Sie die [Visual Studio Build Tools-SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) auf Ihrem Windows Server installieren. Wählen Sie im Installationsprogramm **.NET Desktopbuildtools**aus, und wählen Sie dann auf der rechten Seite des Installationsmenüs die **Compilerkomponente "F"** aus.
