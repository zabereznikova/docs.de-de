---
title: 'Vorgehensweise: Anzeigen der Inhalte des globalen Assemblycaches'
description: Informationen zum Aufrufen der Inhalte des globalen Assemblycache in .NET mithilfe des Global Assembly Cache-Tools (gacutil.exe).
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
ms.openlocfilehash: 4d775efc073f3aad745eff7a7707efdec06172c2
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104685"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="60112-103">Vorgehensweise: Anzeigen der Inhalte des globalen Assemblycaches</span><span class="sxs-lookup"><span data-stu-id="60112-103">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="60112-104">Verwenden Sie das [Global Assembly Cache-Tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md), um den Inhalt des globalen Assemblycaches (GAC) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="60112-104">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="60112-105">Anzeigen der Assemblys im GAC</span><span class="sxs-lookup"><span data-stu-id="60112-105">View the assemblies in the GAC</span></span>

<span data-ttu-id="60112-106">Um eine Liste der Assemblys im globalen Assemblycache anzuzeigen, öffnen Sie die [Developer-Eingabeaufforderung für Visual Studio](../tools/developer-command-prompt-for-vs.md), und geben Sie dann den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="60112-106">To view a list of the assemblies in the global assembly cache, open [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="60112-107">- oder -</span><span class="sxs-lookup"><span data-stu-id="60112-107">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="60112-108">In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) das Anzeigen des globalen Assemblycaches im Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="60112-108">In earlier versions of the .NET Framework, the [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="60112-109">Seit .NET Framework 4 ist Shfusion.dll veraltet.</span><span class="sxs-lookup"><span data-stu-id="60112-109">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="60112-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60112-110">See also</span></span>

- [<span data-ttu-id="60112-111">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="60112-111">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="60112-112">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="60112-112">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
