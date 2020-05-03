---
title: 'Vorgehensweise: Entfernen einer Assembly aus dem globalen Assemblycache'
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- global assembly cache, removing assemblies
- strong-named assemblies, global assembly cache
- removing assemblies from global assembly cache
- deleting assemblies in global assembly cache
- Global Assembly Cache tool
- GAC (global assembly cache), removing assemblies
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
ms.openlocfilehash: c7d85222f35a61154e3eec70d8c9dad2ca6a32f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119857"
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a><span data-ttu-id="bd021-102">Vorgehensweise: Entfernen einer Assembly aus dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="bd021-102">How to: Remove an Assembly from the Global Assembly Cache</span></span>

<span data-ttu-id="bd021-103">Es gibt zwei Möglichkeiten, eine Assembly aus dem globalen Assemblycache (GAC) zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="bd021-103">There are two ways to remove an assembly from the global assembly cache (GAC):</span></span>

- <span data-ttu-id="bd021-104">Durch Verwenden des [Global Assembly Cache-Tools (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md).</span><span class="sxs-lookup"><span data-stu-id="bd021-104">By using the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md).</span></span> <span data-ttu-id="bd021-105">Diese Option können Sie zum Deinstallieren von Assemblys verwenden, die Sie beim Entwickeln und Testen im GAC platziert haben.</span><span class="sxs-lookup"><span data-stu-id="bd021-105">You can use this option to uninstall assemblies that you've placed in the GAC during development and testing.</span></span>

- <span data-ttu-id="bd021-106">Mithilfe von [Windows Installer](/windows/desktop/Msi/windows-installer-portal).</span><span class="sxs-lookup"><span data-stu-id="bd021-106">By using [Windows Installer](/windows/desktop/Msi/windows-installer-portal).</span></span> <span data-ttu-id="bd021-107">Diese Option für das Deinstallieren von Assemblys sollten Sie für Produktionssysteme und dann verwenden, wenn Sie Installationspakete testen.</span><span class="sxs-lookup"><span data-stu-id="bd021-107">You should use this option to uninstall assemblies when testing installation packages and for production systems.</span></span>

## <a name="removing-an-assembly-with-gacutilexe"></a><span data-ttu-id="bd021-108">Entfernen einer Assembly mit "Gacutil.exe"</span><span class="sxs-lookup"><span data-stu-id="bd021-108">Removing an assembly with Gacutil.exe</span></span>

<span data-ttu-id="bd021-109">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="bd021-109">At the command prompt, type the following command:</span></span>

<span data-ttu-id="bd021-110">**gacutil -u** \<*Assemblyname*></span><span class="sxs-lookup"><span data-stu-id="bd021-110">**gacutil –u** \<*assembly name*></span></span>

<span data-ttu-id="bd021-111">In diesem Befehl ist *Assemblyname* der Name der Assembly, die aus dem globalen Assemblycache entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bd021-111">In this command, *assembly name* is the name of the assembly to remove from the global assembly cache.</span></span>

> [!WARNING]
> <span data-ttu-id="bd021-112">Sie sollten "Gacutil.exe" nicht verwenden, um Assemblys auf Produktionssystemen zu entfernen, denn es besteht die Möglichkeit, dass die Assembly für einige Anwendungen weiterhin erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="bd021-112">You should not use Gacutil.exe to remove assemblies on production systems because of the possibility that the assembly may still be required by some application.</span></span> <span data-ttu-id="bd021-113">Stattdessen sollten Sie den Windows Installer verwenden, der einen Verweiszähler für jede Assembly verwaltet, die er im GAC installiert.</span><span class="sxs-lookup"><span data-stu-id="bd021-113">Instead, you should use the Windows Installer, which maintains a reference count for each assembly it installs in the GAC.</span></span>

<span data-ttu-id="bd021-114">Im folgenden Beispiel wird die Assembly `hello.dll` aus dem globalen Assemblycache entfernt:</span><span class="sxs-lookup"><span data-stu-id="bd021-114">The following example removes an assembly named `hello.dll` from the global assembly cache:</span></span>

```console
gacutil -u hello
```

## <a name="removing-an-assembly-with-windows-installer"></a><span data-ttu-id="bd021-115">Entfernen einer Assembly mit Windows Installer</span><span class="sxs-lookup"><span data-stu-id="bd021-115">Removing an assembly with Windows Installer</span></span>

<span data-ttu-id="bd021-116">Wählen Sie in der **Systemsteuerung** in **Programme und Funktionen** die Anwendung aus, die Sie deinstallieren möchten.</span><span class="sxs-lookup"><span data-stu-id="bd021-116">From the **Programs and Features** app in **Control Panel**, select the app that you want to uninstall.</span></span> <span data-ttu-id="bd021-117">Wenn das Installationspaket Assemblys im GAC platziert hat, werden diese von Windows Installer entfernt, sofern sie nicht von einer anderen Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd021-117">If the installation package placed assemblies in the GAC, Windows Installer will remove them if they are not used by another application.</span></span>

> [!NOTE]
> <span data-ttu-id="bd021-118">Windows Installer verwaltet einen Verweiszähler für Assemblys, die im GAC installiert sind.</span><span class="sxs-lookup"><span data-stu-id="bd021-118">Windows Installer maintains a reference count for assemblies installed in the GAC.</span></span> <span data-ttu-id="bd021-119">Eine Assembly wird nur dann aus dem GAC entfernt, wenn ihr Verweiszähler gleich null wird, wodurch angegeben ist, dass sie von keiner der Anwendungen verwendet wird, die über ein Windows Installer-Paket installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bd021-119">An assembly is removed from the GAC only when its reference count reaches zero, which indicates that it is not used by any application installed by a Windows Installer package.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd021-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd021-120">See also</span></span>

- [<span data-ttu-id="bd021-121">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="bd021-121">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="bd021-122">How to: Installieren einer Assembly im globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="bd021-122">How to: Install an Assembly into the Global Assembly Cache</span></span>](install-assembly-into-gac.md)
- [<span data-ttu-id="bd021-123">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="bd021-123">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
