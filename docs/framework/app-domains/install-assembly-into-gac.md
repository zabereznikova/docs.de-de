---
title: 'Vorgehensweise: Installieren einer Assembly im globalen Assemblycache'
description: Installieren Sie eine Assembly im globalen Assemblycache (Global Assembly Cache, GAC) in .NET, damit sie von mehreren Anwendungen gemeinsam genutzt werden kann. Verwenden Sie den Windows Installer oder das GAC-Hilfsprogramm.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: 08a5475d74327265f28b65676ae56be15afb57d3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104668"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="547eb-104">Vorgehensweise: Installieren einer Assembly im globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="547eb-104">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="547eb-105">Im globalen Assemblycache (GAC) werden Assemblys gespeichert, die von mehreren Anwendungen gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="547eb-105">The global assembly cache (GAC) stores assemblies that several applications share.</span></span> <span data-ttu-id="547eb-106">Installieren Sie eine Assembly mit einer der folgenden Komponenten in den [globalen Assemblycache](gac.md):</span><span class="sxs-lookup"><span data-stu-id="547eb-106">Install an assembly into the [global assembly cache](gac.md) with one of the following components:</span></span>

- [<span data-ttu-id="547eb-107">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="547eb-107">Windows Installer</span></span>](#windows-installer)
- [<span data-ttu-id="547eb-108">Tool für globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="547eb-108">Global Assembly Cache tool</span></span>](#global-assembly-cache-tool)

> [!IMPORTANT]
> <span data-ttu-id="547eb-109">Sie können nur Assemblys mit starkem Namen im globalen Assemblycache installieren.</span><span class="sxs-lookup"><span data-stu-id="547eb-109">You can install only strong-named assemblies into the global assembly cache.</span></span> <span data-ttu-id="547eb-110">Informationen zum Erstellen von Assemblys mit starkem Namen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="547eb-110">For information about how to create a strong-named assembly, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="547eb-111">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="547eb-111">Windows Installer</span></span>

<span data-ttu-id="547eb-112">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), das Windows-Installationsmodul, stellt das empfohlene Verfahren zum Hinzufügen von Assemblys zum globalen Assemblycache dar.</span><span class="sxs-lookup"><span data-stu-id="547eb-112">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="547eb-113">Der Windows Installer bietet neben einem Verweiszähler für Assemblys im globalen Assemblycache noch weitere Vorteile.</span><span class="sxs-lookup"><span data-stu-id="547eb-113">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="547eb-114">Verwenden Sie die [WiX-Toolseterweiterung für Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension), um ein Installationspaket für Windows Installer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="547eb-114">To create an installer package for Windows Installer, use the [WiX toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="547eb-115">Tool für globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="547eb-115">Global Assembly Cache tool</span></span>

<span data-ttu-id="547eb-116">Mit dem [.NET-Hilfsprogramm für den globalen Assemblycache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) können Sie dem globalen Assemblycache Assemblys hinzufügen und sich dessen Inhalt anzeigen lassen.</span><span class="sxs-lookup"><span data-stu-id="547eb-116">You can use the [.NET Global Assembly Cache utility (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="547eb-117">Die *gacutil.exe* ist nur für Entwicklungszwecke vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="547eb-117">*Gacutil.exe* is for development purposes only.</span></span> <span data-ttu-id="547eb-118">Verwenden Sie die ausführbare Datei nicht zum Installieren von Produktionsassemblys in den globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="547eb-118">Don't use it to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="547eb-119">Die Syntax zur Verwendung der *gacutil.exe* zum Installieren einer Assembly im GAC lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="547eb-119">The syntax for using *gacutil.exe* to install an assembly in the GAC is as follows:</span></span>

```cmd
gacutil -i <assembly name>
```

<span data-ttu-id="547eb-120">In diesem Befehl bezeichnet *\<assembly name>* den Namen der Assembly, die im globalen Assemblycache installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="547eb-120">In this command, *\<assembly name>* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="547eb-121">Wenn *gacutil.exe* sich nicht auf Ihrem Systempfad befindet, verwenden Sie die [Developer-Eingabeaufforderung für Visual Studio *\<version>* ](../tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="547eb-121">If *gacutil.exe* isn't in your system path, use the [Developer command prompt for VS *\<version>*](../tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="547eb-122">Im folgenden Beispiel wird eine Assembly mit dem Dateinamen *hello.dll* im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="547eb-122">The following example installs an assembly with the file name *hello.dll* into the global assembly cache.</span></span>

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="547eb-123">In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung *Shfusion.dll* das Installieren von Assemblys durch Verschieben in den Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="547eb-123">In earlier versions of the .NET Framework, the *Shfusion.dll* Windows shell extension let you install assemblies by dragging them to File Explorer.</span></span> <span data-ttu-id="547eb-124">Die *Shfusion.dll* ist seit .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="547eb-124">Beginning with .NET Framework 4, *Shfusion.dll* is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="547eb-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="547eb-125">See also</span></span>

- [<span data-ttu-id="547eb-126">Arbeiten mit Assemblys und dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="547eb-126">Work with assemblies and the global assembly cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="547eb-127">How to: Entfernen einer Assembly aus dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="547eb-127">How to: Remove an assembly from the global assembly cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="547eb-128">Gacutil.exe (Tool für globalen Assemblycache)</span><span class="sxs-lookup"><span data-stu-id="547eb-128">Gacutil.exe (Global Assembly Cache tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="547eb-129">How to: Signieren einer Assembly mit einem starken Namen</span><span class="sxs-lookup"><span data-stu-id="547eb-129">How to: Sign an assembly with a strong name</span></span>](../../standard/assembly/sign-strong-name.md)
