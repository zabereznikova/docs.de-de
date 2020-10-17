---
title: Erste Schritte mit .NET
description: Hier erhalten Sie Informationen zum Erstellen einer Hallo Welt-.NET-App.
author: adegeo
ms.author: adegeo
ms.date: 09/29/2020
ms.custom: vs-dotnet
ms.openlocfilehash: 6ad2b96e668c52ee80b707e31a63eac2433f3c9e
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756090"
---
# <a name="get-started-with-net"></a>Erste Schritte mit .NET

In diesem Artikel erfahren Sie, wie Sie eine Hallo Welt-.NET-App erstellen und ausführen.

Wenn Sie unsicher sind, was .NET ist, beginnen Sie zunächst mit der [.NET-Einführung](introduction.md).

## <a name="create-an-application"></a>Erstellen einer Anwendung

Laden Sie zuerst das [.NET SDK](https://dotnet.microsoft.com/download/dotnet-core) auf Ihren Computer herunter, und installieren Sie es.

Als Nächstes öffnen Sie ein Terminal, z.B. **PowerShell**, die **Eingabeaufforderung** oder die **Bash**. Geben Sie die folgenden `dotnet`-Befehle ein, um eine C#-Anwendung zu erstellen und auszuführen:

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

Die folgende Ausgabe wird angezeigt:

```output
Hello World!
```

Herzlichen Glückwunsch! Sie haben eine einfache .NET-Anwendung erstellt.

## <a name="next-steps"></a>Nächste Schritte

Beginnen Sie mit dem Entwickeln von .NET-Anwendungen. Sehen Sie sich dazu ein [detailliertes Tutorial](../standard/get-started.md) oder [Videos zu den ersten Schritten mit .NET](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) auf YouTube an.
