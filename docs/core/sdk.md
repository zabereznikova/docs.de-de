---
title: .NET Core SDK – Übersicht
description: Erfahren Sie mehr über das .NET Core SDK, das ein Set von Bibliotheken und Tools zum Erstellen von .NET Core-Projekten ist.
ms.date: 07/31/2019
ms.technology: dotnet-cli
ms.openlocfilehash: c2723e0e28c889f91f79ea3c0b26aa38f69fb41c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157465"
---
# <a name="net-core-sdk-overview"></a>.NET Core SDK – Übersicht

Das .NET Core SDK ist eine Sammlung von Bibliotheken und Tools, mit der Entwickler .NET Core-Anwendungen und -Bibliotheken erstellen können. Sie enthält die folgenden Komponenten zum Erstellen und Ausführen von Anwendungen:

- .NET Core-CLI
- .NET Core-Bibliotheken und -Runtime
- `dotnet`-[Treiber](tools/index.md#driver)

## <a name="acquiring-the-net-core-sdk"></a>.NET Core SDK erwerben

Wie bei allen Tools ist der erste Schritt, diese auf dem Computer zu installieren. Je nach Szenario können Sie das SDK mit einer der folgenden Methoden installieren:

- Verwenden Sie die nativen Installationsprogramme.
- Verwenden Sie das Shellskript für die Installation.

Der native Installer ist in erster Linie für Entwicklercomputer vorgesehen. Das SDK wird mithilfe des nativen Installationsmechanismus der jeweils unterstützten Plattform verteilt, z. B. Debian-Pakete unter Ubuntu oder MSI-Bündel unter Windows. Diese Installationsprogramme führen die Installation durch und richten die Umgebung je nach Bedarf des Benutzers ein, damit das SDK sofort nach der Installation genutzt werden kann. Jedoch benötigen sie auch Administratorrechte auf dem Computer. Sie finden das zu installierende SDK auf der Seite mit den [.NET-Downloads](https://dotnet.microsoft.com/download).

Installationsskripts hingegen erfordern keine Administratorrechte. Allerdings installieren diese auch keine erforderlichen Komponenten auf dem Computer, sodass Sie alle erforderlichen Komponenten manuell installieren müssen. Die Skripts werden hauptsächlich für das Einrichten von Buildservern verwendet oder in dem Fall, dass Sie die Tools ohne Administratorrechte installieren möchten (beachten Sie hierzu die oben genannten Einschränkungen hinsichtlich der erforderlichen Komponenten). Weitere Informationen finden Sie im Artikel mit der [Referenz zum Installationsskript](tools/dotnet-install-script.md). Falls Sie daran interessiert sind, wie das SDK auf Ihrem CI-Buildserver eingerichtet wird, helfen Ihnen die Informationen im Artikel [Verwenden des .NET Core SDK und der zugehörigen Tools in Continuous Integration (CI)](tools/using-ci-with-cli.md) weiter.

Das SDK wird standardmäßig im parallelen Modus installiert. Das bedeutet, dass auf einem Computer jederzeit mehrere Versionen gleichzeitig vorhanden sein können. Die Auswahl der Version beim Ausführen von CLI-Befehlen ist im Artikel [Auswählen der zu verwendenden .NET Core-Version](versions/selection.md) ausführlicher beschrieben.

## <a name="see-also"></a>Siehe auch

- [Übersicht über die .NET Core-CLI](tools/index.md)
- [.NET Core-Versionskontrolle: Übersicht](versions/index.md)
- [Entfernen von .NET Core-Runtime und SDK](versions/remove-runtime-sdk-versions.md)
- [Auswählen der zu verwendenden .NET Core-Version](versions/selection.md)
