---
title: Erste Schritte mit .NET Core
description: Suchen Sie Ressourcen, um zu erfahren, wie Sie .NET Core-Anwendungen auf Windows, Linux und Mac OS erstellen können.
author: thraka
ms.author: adegeo
ms.date: 09/19/2019
ms.openlocfilehash: 89db6d79336c01315983133d9041904d88cba301
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884253"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="cdfe4-103">Erste Schritte mit .NET Core</span><span class="sxs-lookup"><span data-stu-id="cdfe4-103">Get started with .NET Core</span></span>

<span data-ttu-id="cdfe4-104">Dieser Artikel enthält Informationen zu den ersten Schritten mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="cdfe4-105">.NET Core kann unter Windows, Linux und macOS installiert werden.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="cdfe4-106">Außerdem können Sie in Ihrem bevorzugten Text-Editor programmieren und plattformübergreifende Bibliotheken und Anwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span> 

<span data-ttu-id="cdfe4-107">Wenn Sie nicht sicher sind, was .NET Core ist oder in welcher Beziehung es zu anderen .NET-Technologien steht, sollten Sie mit [What is .NET (Was ist .NET)](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) beginnen.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="cdfe4-108">Einfach ausgedrückt, ist .NET Core eine plattformübergreifende Open-Source-Implementierung von .NET.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="cdfe4-109">Erstellen einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="cdfe4-109">Create an application</span></span>

<span data-ttu-id="cdfe4-110">Laden Sie das [.NET Core SDK](https://dotnet.microsoft.com/download) auf Ihrem Computer herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="cdfe4-111">Als Nächstes öffnen Sie ein Terminal, z.B. **PowerShell**, die **Eingabeaufforderung** oder die **Bash**.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="cdfe4-112">Geben Sie die folgenden `dotnet`-Befehle ein, um eine C#-Anwendung zu erstellen und zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="cdfe4-112">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="cdfe4-113">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cdfe4-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="cdfe4-114">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="cdfe4-114">Congratulations!</span></span> <span data-ttu-id="cdfe4-115">Sie haben eine einfache .NET Core-Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="cdfe4-116">Sie können auch [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (nur Windows) oder [Visual Studio für Mac](tutorials/using-on-mac-vs.md) (nur macOS) verwenden, um eine .NET Core-Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-116">You can also use [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="cdfe4-117">Tutorials</span><span class="sxs-lookup"><span data-stu-id="cdfe4-117">Tutorials</span></span>

<span data-ttu-id="cdfe4-118">Die folgenden ausführlichen Tutorials helfen Ihnen beim Einstieg in das Entwickeln von .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-118">You can get started developing .NET Core applications by following these step-by-step tutorials.</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="cdfe4-119">Windows</span><span class="sxs-lookup"><span data-stu-id="cdfe4-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="cdfe4-120">Erstellen einer „Hallo Welt“-Anwendung in C# mit .NET Core in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="cdfe4-120">Build a C# "Hello World" Application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="cdfe4-121">Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="cdfe4-121">Build a C# class library with .NET Core in Visual Studio 2017.</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="cdfe4-122">Erstellen einer „Hallo Welt“-Anwendung in Visual Basic mit .NET Core in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="cdfe4-122">Build a Visual Basic "Hello World" application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-with-visual-studio.md)
- [<span data-ttu-id="cdfe4-123">Erstellen einer Klassenbibliothek mit Visual Basic und .NET Core in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="cdfe4-123">Build a class library with Visual Basic and .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-library-with-visual-studio.md)  
- <span data-ttu-id="cdfe4-124">Sehen Sie sich ein Video zum [Installieren und Verwenden von Visual Studio Code und .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) an.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-124">Watch a video on [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span></span>
- <span data-ttu-id="cdfe4-125">Sehen Sie sich ein Video zum [Installieren und Verwenden von Visual Studio 2017 und .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/) an.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-125">Watch a video on [how to install and use Visual Studio 2017 and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span></span>
- [<span data-ttu-id="cdfe4-126">Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="cdfe4-126">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)

<span data-ttu-id="cdfe4-127">Eine Liste der unterstützten Windows-Versionen finden Sie im Artikel [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="cdfe4-127">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-windows) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="cdfe4-128">Linux</span><span class="sxs-lookup"><span data-stu-id="cdfe4-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="cdfe4-129">Die folgenden ausführlichen Tutorials helfen Ihnen beim Einstieg in das Entwickeln von .NET Core-Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="cdfe4-129">You can get started developing .NET Core application by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="cdfe4-130">Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="cdfe4-130">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)
- <span data-ttu-id="cdfe4-131">Sehen Sie sich ein Video zu den [ersten Schritte mit Visual Studio Code mit C# und .NET Core unter Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) an.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-131">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

<span data-ttu-id="cdfe4-132">Eine Liste der unterstützten Linux-Distributionen und -Versionen finden Sie im Artikel [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?tabs=netcore30&pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="cdfe4-132">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-linux) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="cdfe4-133">macOS</span><span class="sxs-lookup"><span data-stu-id="cdfe4-133">macOS</span></span>](#tab/macos)

<span data-ttu-id="cdfe4-134">Die folgenden ausführlichen Tutorials helfen Ihnen beim Einstieg in das Entwickeln von .NET Core-Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="cdfe4-134">You can get started developing .NET Core application by following these step-by-step tutorials:</span></span>

- <span data-ttu-id="cdfe4-135">Sehen Sie sich ein Video zu den [ersten Schritte mit Visual Studio Code mit C# und .NET Core unter macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac) an.</span><span class="sxs-lookup"><span data-stu-id="cdfe4-135">Watch a video on [Getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span>
- [<span data-ttu-id="cdfe4-136">Erste Schritte mit .NET Core unter Mac OS</span><span class="sxs-lookup"><span data-stu-id="cdfe4-136">Getting started with .NET Core on macOS, using Visual Studio Code.</span></span>](tutorials/using-on-macos.md)
- [<span data-ttu-id="cdfe4-137">Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="cdfe4-137">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)
- [<span data-ttu-id="cdfe4-138">Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="cdfe4-138">Getting started with .NET Core on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs.md)
- [<span data-ttu-id="cdfe4-139">Erstellen einer vollständigen .NET Core-Lösung unter macOS mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="cdfe4-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs-full-solution.md)

<span data-ttu-id="cdfe4-140">Eine Liste der unterstützten OS X-/macOS-Versionen finden Sie im Artikel [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?tabs=netcore30&pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="cdfe4-140">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-macos) article for a list of the supported OS X / macOS versions.</span></span>

---
