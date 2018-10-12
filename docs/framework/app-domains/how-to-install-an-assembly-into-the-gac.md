---
title: Installieren einer Assembly im globalen Assemblycache
ms.date: 09/20/2018
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d365ac77fe6cd7fc4fca36705729ec12b06d6830
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2018
ms.locfileid: "46584580"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="b5ea7-102">Gewusst wie: Installieren einer Assembly im globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="b5ea7-102">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="b5ea7-103">Es gibt zwei Möglichkeiten, eine Assembly mit starkem Namen im globalen Assemblycache (GAC) zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b5ea7-103">There are two ways to install a strong-named assembly into the global assembly cache (GAC).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5ea7-104">Nur Assemblys mit starkem Namen können im GAC installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b5ea7-104">Only strong-named assemblies can be installed into the GAC.</span></span> <span data-ttu-id="b5ea7-105">Informationen zum Erstellen einer Assembly mit starkem Namen finden Sie unter [How to: Sign an Assembly with a Strong Name (Vorgehensweise: Signieren einer Assembly mit einem starken Namen)](how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="b5ea7-105">For information about how to create a strong-named assembly, see [How to: Sign an Assembly with a Strong Name](how-to-sign-an-assembly-with-a-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="b5ea7-106">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="b5ea7-106">Windows Installer</span></span>

<span data-ttu-id="b5ea7-107">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), das Windows-Installationsmodul, stellt das empfohlene Verfahren zum Hinzufügen von Assemblys zum globalen Assemblycache dar.</span><span class="sxs-lookup"><span data-stu-id="b5ea7-107">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="b5ea7-108">Der Windows Installer bietet neben einem Verweiszähler für Assemblys im globalen Assemblycache noch weitere Vorteile.</span><span class="sxs-lookup"><span data-stu-id="b5ea7-108">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="b5ea7-109">Sie können die [WiX-Toolseterweiterung für Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension) verwenden, um ein Installationspaket für Windows Installer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b5ea7-109">You can use the [WiX Toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension) to create an installer package for Windows Installer.</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="b5ea7-110">Globaler Assemblycache-Tool</span><span class="sxs-lookup"><span data-stu-id="b5ea7-110">Global assembly cache tool</span></span>

<span data-ttu-id="b5ea7-111">Mit dem [Globaler Assemblycache-Tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) können Sie Assemblys mit starkem Namen zum globalen Assemblycache hinzufügen und sich dessen Inhalt anzeigen lassen.</span><span class="sxs-lookup"><span data-stu-id="b5ea7-111">You can use the [Global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add strong-named assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b5ea7-112">Gacutil.exe ist Entwicklungszwecken vorbehalten und nicht für die Installation von Produktionsassemblys im globalen Assemblycache vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b5ea7-112">Gacutil.exe is only for development purposes and should not be used to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="b5ea7-113">Die Syntax für gacutil lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b5ea7-113">The syntax for gacutil is as follows:</span></span>

```shell
gacutil -i <assembly name>
```

<span data-ttu-id="b5ea7-114">In diesem Befehl bezeichnet *Assemblyname* den Namen der Assembly, die im globalen Assemblycache installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5ea7-114">In this command, *assembly name* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="b5ea7-115">Im folgenden Beispiel wird eine Assembly mit dem Dateinamen `hello.dll` im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="b5ea7-115">The following example installs an assembly with the file name `hello.dll` into the global assembly cache.</span></span>

```shell
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="b5ea7-116">In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung „Shfusion.dll“ das Installieren von Assemblys durch Ziehen in **Datei-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="b5ea7-116">In earlier versions of the .NET Framework, the Shfusion.dll Windows shell extension enabled you to install assemblies by dragging them in **File Explorer**.</span></span> <span data-ttu-id="b5ea7-117">Seit .NET Framework 4 ist Shfusion.dll veraltet.</span><span class="sxs-lookup"><span data-stu-id="b5ea7-117">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5ea7-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5ea7-118">See also</span></span>

- [<span data-ttu-id="b5ea7-119">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="b5ea7-119">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="b5ea7-120">Gewusst wie: Entfernen einer Assembly aus dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="b5ea7-120">How to: Remove an Assembly from the Global Assembly Cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="b5ea7-121">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="b5ea7-121">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="b5ea7-122">Vorgehensweise: Signieren einer Assembly mit einem starken Namen</span><span class="sxs-lookup"><span data-stu-id="b5ea7-122">How to: Sign an Assembly with a Strong Name</span></span>](how-to-sign-an-assembly-with-a-strong-name.md)