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
# <a name="net-install-tool-for-extension-authors"></a><span data-ttu-id="62a36-103">.NET-Installationstool für Erweiterungsautoren</span><span class="sxs-lookup"><span data-stu-id="62a36-103">.NET install tool for extension authors</span></span>

<span data-ttu-id="62a36-104">Das [.NET-Installationstool für Erweiterungsautoren](https://github.com/dotnet/vscode-dotnet-runtime) ist eine Visual Studio Code-Erweiterung, die speziell VS Code-Erweiterungsautoren die Nutzung der .NET-Laufzeit ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="62a36-104">The [.NET install tool for extension authors](https://github.com/dotnet/vscode-dotnet-runtime) is a Visual Studio Code extension that allows acquisition of the .NET runtime specifically for VS Code extension authors.</span></span> <span data-ttu-id="62a36-105">Dieses Tool soll in Erweiterungen verwendet werden, die in .NET geschrieben sind und .NET zum Starten von Komponenten der Erweiterung (z. B. eines Sprachservers) erfordern.</span><span class="sxs-lookup"><span data-stu-id="62a36-105">This tool is intended to be leveraged in extensions that are written in .NET and require .NET to boot pieces of the extension (for example, a language server).</span></span> <span data-ttu-id="62a36-106">Die Erweiterung soll nicht direkt von Benutzern verwendet werden, um .NET für die Entwicklung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="62a36-106">The extension is not intended to be used directly by users to install .NET for development.</span></span>

## <a name="getting-started-extension-authors"></a><span data-ttu-id="62a36-107">Erste Schritte: Erweiterungsautoren</span><span class="sxs-lookup"><span data-stu-id="62a36-107">Getting started: extension authors</span></span>

<span data-ttu-id="62a36-108">Um sicherzustellen, dass das .NET-Installations Tool für Erweiterungsautoren das Richtige für Ihr Szenario ist, überprüfen Sie zunächst die [Ziele dieser Erweiterung](https://github.com/dotnet/vscode-dotnet-runtime#goals-acquiring-net-core-for-extensions) auf unserer GitHub-Seite.</span><span class="sxs-lookup"><span data-stu-id="62a36-108">To ensure that the .NET install tool for extension authors is the right fit for your scenario, start by reviewing the [goals of this extension](https://github.com/dotnet/vscode-dotnet-runtime#goals-acquiring-net-core-for-extensions) on our GitHub page.</span></span>

> [!NOTE]
> <span data-ttu-id="62a36-109">Dieses Tool kann nur verwendet werden, um die .NET-Runtime zu installieren, es ermöglicht zurzeit nicht die Installation des .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="62a36-109">This tool can be used to install the .NET runtime only, it currently does not have the capability to install the .NET SDK.</span></span>

<span data-ttu-id="62a36-110">Nachdem Sie sich vergewissert haben, dass das .NET-Installationstool für Erweiterungsautoren Ihren Anforderungen entspricht, können Sie eine Abhängigkeit davon in Ihr [Erweiterungsmanifest](https://code.visualstudio.com/api/references/extension-manifest) eintragen und mit der Verwendung der Befehle beginnen, die wir mit der [VS Code-API](https://code.visualstudio.com/api/extension-guides/command#programmatically-executing-a-command) verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="62a36-110">Once you have verified that the .NET install tool for extension authors fits your needs, you can take a dependency on it in your [extension manifest](https://code.visualstudio.com/api/references/extension-manifest) and begin using the commands we expose with the [VS Code API](https://code.visualstudio.com/api/extension-guides/command#programmatically-executing-a-command).</span></span> <span data-ttu-id="62a36-111">Auf [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/commands.md) finden Sie die Liste der Befehle, die diese Erweiterung verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="62a36-111">You can find the list of commands this extension exposes on our [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/commands.md).</span></span>

<span data-ttu-id="62a36-112">Sehen Sie sich diese [Beispielerweiterung](https://github.com/dotnet/vscode-dotnet-runtime/tree/master/sample) an, um diese Schritte in Aktion zu sehen.</span><span class="sxs-lookup"><span data-stu-id="62a36-112">Check out this [sample extension](https://github.com/dotnet/vscode-dotnet-runtime/tree/master/sample) to see these steps in action.</span></span>

<span data-ttu-id="62a36-113">Weitere Beispiele finden Sie in diesen Open-Source-Erweiterungen, die dieses Tool zurzeit nutzen:</span><span class="sxs-lookup"><span data-stu-id="62a36-113">For more examples, check out these open source extensions that currently leverage this tool:</span></span>

- [<span data-ttu-id="62a36-114">Azure Resource Manager-Tools (ARM) für Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="62a36-114">Azure Resource Manager (ARM) Tools for Visual Studio Code</span></span>](https://github.com/microsoft/vscode-azurearmtools)

- [<span data-ttu-id="62a36-115">.NET Interactive Notebooks</span><span class="sxs-lookup"><span data-stu-id="62a36-115">.NET Interactive Notebooks</span></span>](https://github.com/dotnet/interactive/tree/main/src/dotnet-interactive-vscode)

## <a name="getting-started-end-users"></a><span data-ttu-id="62a36-116">Erste Schritte: Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="62a36-116">Getting started: end users</span></span>

<span data-ttu-id="62a36-117">Im Allgemeinen sollte eine Interaktion des Endbenutzers mit dem .NET-Installationstool für Erweiterungsautoren nicht nötig sein.</span><span class="sxs-lookup"><span data-stu-id="62a36-117">In general, the end user should not need to interact with the .NET install tool for extension authors at all.</span></span> <span data-ttu-id="62a36-118">Wenn Probleme mit der Erweiterung auftreten, besuchen Sie unsere [Problembehandlungsseite](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/troubleshooting.md), oder melden Sie ein Problem auf [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/issues).</span><span class="sxs-lookup"><span data-stu-id="62a36-118">If you are having problems with the extension, check out our [troubleshooting page](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/troubleshooting.md) or file an issue on our [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/issues).</span></span>
