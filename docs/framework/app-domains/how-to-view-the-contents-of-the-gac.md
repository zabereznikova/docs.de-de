---
title: 'Vorgehensweise: Anzeigen der Inhalte des globalen Assemblycaches'
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c319c5f7c9bb808b2ce7ee10178722287e456339
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486429"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="c2ca3-102">Vorgehensweise: Anzeigen der Inhalte des globalen Assemblycaches</span><span class="sxs-lookup"><span data-stu-id="c2ca3-102">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="c2ca3-103">Verwenden Sie das [Global Assembly Cache-Tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md), um den Inhalt des globalen Assemblycaches (GAC) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c2ca3-103">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="c2ca3-104">Anzeigen der Assemblys im GAC</span><span class="sxs-lookup"><span data-stu-id="c2ca3-104">View the assemblies in the GAC</span></span>

<span data-ttu-id="c2ca3-105">Um eine Liste der Assemblys im globalen Assemblycache anzuzeigen, öffnen Sie die [Developer-Eingabeaufforderung für Visual Studio](../tools/developer-command-prompt-for-vs.md), und geben Sie dann den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="c2ca3-105">To view a list of the assemblies in the global assembly cache, open [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="c2ca3-106">- oder -</span><span class="sxs-lookup"><span data-stu-id="c2ca3-106">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="c2ca3-107">In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) das Anzeigen des globalen Assemblycaches im Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="c2ca3-107">In earlier versions of the .NET Framework, the [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="c2ca3-108">Seit .NET Framework 4 ist Shfusion.dll veraltet.</span><span class="sxs-lookup"><span data-stu-id="c2ca3-108">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2ca3-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2ca3-109">See also</span></span>

- [<span data-ttu-id="c2ca3-110">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="c2ca3-110">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="c2ca3-111">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="c2ca3-111">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
