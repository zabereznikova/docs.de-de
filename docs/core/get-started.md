---
title: Erste Schritte mit .NET Core
description: Lernen Sie verschiedene Ressourcen kennen, um zu erfahren, wie Sie .NET Core-Anwendungen unter Windows, Linux und macOS erstellen können.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 0968d9db1dbfbdc8c586328ee8e02315f17950b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714398"
---
# <a name="get-started-with-net-core"></a>Erste Schritte mit .NET Core

Dieser Artikel enthält Informationen zu den ersten Schritten mit .NET Core. .NET Core kann unter Windows, Linux und macOS installiert werden. Außerdem können Sie in Ihrem bevorzugten Text-Editor programmieren und plattformübergreifende Bibliotheken und Anwendungen erstellen.

Wenn Sie nicht sicher sind, was .NET Core ist oder in welcher Beziehung es zu anderen .NET-Technologien steht, sollten Sie mit [What is .NET (Was ist .NET)](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) beginnen. Einfach ausgedrückt, ist .NET Core eine plattformübergreifende Open-Source-Implementierung von .NET.

## <a name="create-an-application"></a>Erstellen einer Anwendung

Laden Sie das [.NET Core SDK](https://dotnet.microsoft.com/download) auf Ihrem Computer herunter, und installieren Sie es.

Als Nächstes öffnen Sie ein Terminal, z.B. **PowerShell**, die **Eingabeaufforderung** oder die **Bash**. Geben Sie die folgenden `dotnet`-Befehle ein, um eine C#-Anwendung zu erstellen und zu veröffentlichen:

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

Die folgende Ausgabe wird angezeigt:

```console
Hello World!
```

Herzlichen Glückwunsch! Sie haben eine einfache .NET Core-Anwendung erstellt. Sie können auch [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (nur Windows) oder [Visual Studio für Mac](./tutorials/using-on-mac-vs.md) (nur macOS) verwenden, um eine .NET Core-Anwendung zu erstellen.

## <a name="tutorials"></a>Lernprogramme

Steigen Sie in die Entwicklung von .NET Core-Anwendungen ein, indem Sie diese schrittweisen Tutorials durcharbeiten:

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

- [Erstellen Ihrer ersten .NET Core-Konsolenanwendung in Visual Studio 2019](./tutorials/with-visual-studio.md)
- [Erstellen einer Klassenbibliothek mit .NET Standard in Visual Studio](./tutorials/library-with-visual-studio.md)
- [Erste Schritte mit .NET Core unter Verwendung der .NET Core-CLI](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| ![Kamerasymbol für Video](./media/video-icon.png "Video ansehen") | Sehen Sie sich das Video [Vorgehensweise: Installieren und Verwenden von Visual Studio Code und .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) auf Channel 9 an. |
| ![Kamerasymbol für Video](./media/video-icon.png "Video ansehen") | Sehen Sie sich das Video [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) auf YouTube an. |

Eine Liste der unterstützten Windows-Versionen finden Sie im Artikel [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?pivots=os-windows).

# <a name="linux"></a>[Linux](#tab/linux)

Steigen Sie in die Entwicklung von .NET Core-Anwendungen ein, indem Sie diese schrittweisen Tutorials durcharbeiten:

- [Erste Schritte mit .NET Core unter Verwendung der Befehlszeile](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| ![Kamerasymbol für Video](./media/video-icon.png "Video ansehen") | Sehen Sie sich ein Video zu den [ersten Schritte mit Visual Studio Code mit C# und .NET Core unter Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) an. |

Eine Liste der unterstützten Linux-Distributionen und -Versionen finden Sie im Artikel [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?pivots=os-linux).

# <a name="macos"></a>[macOS](#tab/macos)

Steigen Sie in die Entwicklung von .NET Core-Anwendungen ein, indem Sie diese schrittweisen Tutorials durcharbeiten:

- [Erste Schritte mit .NET Core unter macOS mithilfe von Visual Studio Code](./tutorials/using-on-macos.md)
- [Erste Schritte mit .NET Core unter Verwendung der Befehlszeile](./tutorials/cli-create-console-app.md)
- [Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac](./tutorials/using-on-mac-vs.md)
- [Erstellen einer vollständigen .NET Core-Lösung unter macOS mit Visual Studio für Mac](./tutorials/using-on-mac-vs-full-solution.md)

|   |   |
|---|---|
| ![Kamerasymbol für Video](media/video-icon.png "Video ansehen") | Sehen Sie sich ein Video zu den [ersten Schritte mit Visual Studio Code mit C# und .NET Core unter macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac) an. |

Eine Liste der unterstützten OS X-/macOS-Versionen finden Sie im Artikel [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?pivots=os-macos).

---
