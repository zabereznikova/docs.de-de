---
title: .NET-Installationstool für VS Code-Erweiterungsautoren
description: Eine Übersicht über das .NET-Installations Tool für Erweiterungsautoren, eine Visual Studio Code-Erweiterung zum Installieren der .NET-Laufzeit.
author: sfoslund
ms.date: 11/18/2020
ms.openlocfilehash: 37be1b9dcdb9fba99554800fea23f28443efb5fa
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599897"
---
# <a name="net-install-tool-for-extension-authors"></a>.NET-Installationstool für Erweiterungsautoren

Das [.NET-Installationstool für Erweiterungsautoren](https://github.com/dotnet/vscode-dotnet-runtime) ist eine Visual Studio Code-Erweiterung, die speziell VS Code-Erweiterungsautoren die Nutzung der .NET-Laufzeit ermöglicht. Dieses Tool soll in Erweiterungen verwendet werden, die in .NET geschrieben sind und .NET zum Starten von Komponenten der Erweiterung (z. B. eines Sprachservers) erfordern. Die Erweiterung soll nicht direkt von Benutzern verwendet werden, um .NET für die Entwicklung zu installieren.

## <a name="getting-started-extension-authors"></a>Erste Schritte: Erweiterungsautoren

Um sicherzustellen, dass das .NET-Installations Tool für Erweiterungsautoren das Richtige für Ihr Szenario ist, überprüfen Sie zunächst die [Ziele dieser Erweiterung](https://github.com/dotnet/vscode-dotnet-runtime#goals-acquiring-net-core-for-extensions) auf unserer GitHub-Seite.

> [!NOTE]
> Dieses Tool kann nur verwendet werden, um die .NET-Runtime zu installieren, es ermöglicht zurzeit nicht die Installation des .NET SDK.

Nachdem Sie sich vergewissert haben, dass das .NET-Installationstool für Erweiterungsautoren Ihren Anforderungen entspricht, können Sie eine Abhängigkeit davon in Ihr [Erweiterungsmanifest](https://code.visualstudio.com/api/references/extension-manifest) eintragen und mit der Verwendung der Befehle beginnen, die wir mit der [VS Code-API](https://code.visualstudio.com/api/extension-guides/command#programmatically-executing-a-command) verfügbar machen. Auf [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/commands.md) finden Sie die Liste der Befehle, die diese Erweiterung verfügbar macht.

Sehen Sie sich diese [Beispielerweiterung](https://github.com/dotnet/vscode-dotnet-runtime/tree/master/sample) an, um diese Schritte in Aktion zu sehen.

Weitere Beispiele finden Sie in diesen Open-Source-Erweiterungen, die dieses Tool zurzeit nutzen:

- [Azure Resource Manager-Tools (ARM) für Visual Studio Code](https://github.com/microsoft/vscode-azurearmtools)

- [.NET Interactive Notebooks](https://github.com/dotnet/interactive/tree/main/src/dotnet-interactive-vscode)

## <a name="getting-started-end-users"></a>Erste Schritte: Endbenutzer

Im Allgemeinen sollte eine Interaktion des Endbenutzers mit dem .NET-Installationstool für Erweiterungsautoren nicht nötig sein. Wenn Probleme mit der Erweiterung auftreten, besuchen Sie unsere [Problembehandlungsseite](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/troubleshooting.md), oder melden Sie ein Problem auf [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/issues).
