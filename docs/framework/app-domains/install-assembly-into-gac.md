---
title: 'Vorgehensweise: Installieren einer Assembly im globalen Assemblycache'
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: 64878a795a7c5b790c8991064e32b82505685c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155562"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="f9b0d-102">Vorgehensweise: Installieren einer Assembly im globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="f9b0d-102">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="f9b0d-103">Im globalen Assemblycache (GAC) werden Assemblys gespeichert, die von mehreren Anwendungen gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-103">The global assembly cache (GAC) stores assemblies that several applications share.</span></span> <span data-ttu-id="f9b0d-104">Installieren Sie eine Assembly mit einer der folgenden Komponenten in den [globalen Assemblycache](gac.md):</span><span class="sxs-lookup"><span data-stu-id="f9b0d-104">Install an assembly into the [global assembly cache](gac.md) with one of the following components:</span></span>

- [<span data-ttu-id="f9b0d-105">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="f9b0d-105">Windows Installer</span></span>](#windows-installer)
- [<span data-ttu-id="f9b0d-106">Tool für globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="f9b0d-106">Global Assembly Cache tool</span></span>](#global-assembly-cache-tool)

> [!IMPORTANT]
> <span data-ttu-id="f9b0d-107">Sie können nur Assemblys mit starkem Namen im globalen Assemblycache installieren.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-107">You can install only strong-named assemblies into the global assembly cache.</span></span> <span data-ttu-id="f9b0d-108">Informationen zum Erstellen von Assemblys mit starkem Namen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="f9b0d-108">For information about how to create a strong-named assembly, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="f9b0d-109">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="f9b0d-109">Windows Installer</span></span>

<span data-ttu-id="f9b0d-110">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), das Windows-Installationsmodul, stellt das empfohlene Verfahren zum Hinzufügen von Assemblys zum globalen Assemblycache dar.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-110">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="f9b0d-111">Der Windows Installer bietet neben einem Verweiszähler für Assemblys im globalen Assemblycache noch weitere Vorteile.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-111">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="f9b0d-112">Verwenden Sie die [WiX-Toolseterweiterung für Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension), um ein Installationspaket für Windows Installer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-112">To create an installer package for Windows Installer, use the [WiX toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="f9b0d-113">Tool für globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="f9b0d-113">Global Assembly Cache tool</span></span>

<span data-ttu-id="f9b0d-114">Mit dem [.NET-Hilfsprogramm für den globalen Assemblycache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) können Sie dem globalen Assemblycache Assemblys hinzufügen und sich dessen Inhalt anzeigen lassen.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-114">You can use the [.NET Global Assembly Cache utility (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f9b0d-115">Die *gacutil.exe* ist nur für Entwicklungszwecke vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-115">*Gacutil.exe* is for development purposes only.</span></span> <span data-ttu-id="f9b0d-116">Verwenden Sie die ausführbare Datei nicht zum Installieren von Produktionsassemblys in den globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-116">Don't use it to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="f9b0d-117">Die Syntax zur Verwendung der *gacutil.exe* zum Installieren einer Assembly im GAC lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f9b0d-117">The syntax for using *gacutil.exe* to install an assembly in the GAC is as follows:</span></span>

```cmd
gacutil -i <assembly name>
```

<span data-ttu-id="f9b0d-118">In diesem Befehl bezeichnet *\<Assemblyname>* den Namen der Assembly, die im globalen Assemblycache installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-118">In this command, *\<assembly name>* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="f9b0d-119">Wenn *gacutil.exe* sich nicht in Ihrem Systempfad befindet, verwenden Sie die [Developer-Eingabeaufforderung für VS *\<Version>* ](../tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f9b0d-119">If *gacutil.exe* isn't in your system path, use the [Developer command prompt for VS *\<version>*](../tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="f9b0d-120">Im folgenden Beispiel wird eine Assembly mit dem Dateinamen *hello.dll* im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-120">The following example installs an assembly with the file name *hello.dll* into the global assembly cache.</span></span>

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="f9b0d-121">In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung *Shfusion.dll* das Installieren von Assemblys durch Verschieben in den Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-121">In earlier versions of the .NET Framework, the *Shfusion.dll* Windows shell extension let you install assemblies by dragging them to File Explorer.</span></span> <span data-ttu-id="f9b0d-122">Die *Shfusion.dll* ist seit .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="f9b0d-122">Beginning with .NET Framework 4, *Shfusion.dll* is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9b0d-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9b0d-123">See also</span></span>

- [<span data-ttu-id="f9b0d-124">Arbeiten mit Assemblys und dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="f9b0d-124">Work with assemblies and the global assembly cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="f9b0d-125">How to: Entfernen einer Assembly aus dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="f9b0d-125">How to: Remove an assembly from the global assembly cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="f9b0d-126">Gacutil.exe (Tool für globalen Assemblycache)</span><span class="sxs-lookup"><span data-stu-id="f9b0d-126">Gacutil.exe (Global Assembly Cache tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="f9b0d-127">How to: Signieren einer Assembly mit einem starken Namen</span><span class="sxs-lookup"><span data-stu-id="f9b0d-127">How to: Sign an assembly with a strong name</span></span>](../../standard/assembly/sign-strong-name.md)
