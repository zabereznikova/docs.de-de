---
title: 'Vorgehensweise: ermitteln, welche .NET Framework-Sicherheit-Updates und Hotfixes installiert sind'
description: Informationen Sie zum bestimmen, welche .NET Framework-Sicherheit-Updates und Hotfixes auf einem Computer installiert sind.
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c35705470a8e1b553eca2ca0c68d3b8b9b3f6fa6
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="90893-103">Vorgehensweise: ermitteln, welche .NET Framework-Sicherheit-Updates und Hotfixes installiert sind</span><span class="sxs-lookup"><span data-stu-id="90893-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="90893-104">Diesem Artikel erfahren Sie, wie Sie herausfinden, welche .NET Framework-Sicherheitsupdates und Hotfixes auf einem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="90893-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="90893-105">Die Techniken, die in diesem Artikel angezeigten erfordern ein Konto mit Administratorrechten aus.</span><span class="sxs-lookup"><span data-stu-id="90893-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="90893-106">Suchen Sie installierte Updates mithilfe der Registrierung</span><span class="sxs-lookup"><span data-stu-id="90893-106">To find installed updates using the registry</span></span>

<span data-ttu-id="90893-107">Die installierten Sicherheitsupdates und Hotfixes für jede Version von .NET Framework auf einem Computer installiert sind, werden in der Windows-Registrierung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="90893-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="90893-108">Sie können den Registrierungs-Editor (*regedit.exe*) Programm zum Anzeigen dieser Informationen.</span><span class="sxs-lookup"><span data-stu-id="90893-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="90893-109">Öffnen Sie das Programm **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="90893-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="90893-110">In Windows 8 und höher, mit der Maustaste **starten** ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), und wählen Sie dann **ausführen**.</span><span class="sxs-lookup"><span data-stu-id="90893-110">In Windows 8 and later versions, right-click **Start** ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="90893-111">In der **öffnen** geben **Regedit** , und wählen Sie **OK**.</span><span class="sxs-lookup"><span data-stu-id="90893-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="90893-112">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:</span><span class="sxs-lookup"><span data-stu-id="90893-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="90893-113">Die installierten Updates werden unter Unterschlüsseln aufgeführt, die die für sie geltende .NET Framework-Version identifizieren.</span><span class="sxs-lookup"><span data-stu-id="90893-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="90893-114">Jedes Update wird durch eine Knowledge Base (KB)-Nummer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="90893-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="90893-115">Im Registrierungs-Editor werden die .NET Framework-Versionen und die installierten Updates für jede Version in verschiedenen Unterschlüsseln gespeichert.</span><span class="sxs-lookup"><span data-stu-id="90893-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="90893-116">Informationen zum Ermitteln der installierten Versionsnummern finden Sie unter [wie: bestimmen, welche .NET Framework-Versionen installiert sind](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="90893-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="90893-117">Um installierten Updates durch Abfragen der Registrierungs im code</span><span class="sxs-lookup"><span data-stu-id="90893-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="90893-118">Im folgende Beispiel ermittelt programmgesteuert die .NET Framework-Sicherheitsupdates und Hotfixes, die auf einem Computer installiert sind:</span><span class="sxs-lookup"><span data-stu-id="90893-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="90893-119">Das Beispiel führt eine Ausgabe, die mit dem folgenden ähnlich ist:</span><span class="sxs-lookup"><span data-stu-id="90893-119">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="90893-120">Um installierten Updates durch Abfragen der Registrierungs in PowerShell</span><span class="sxs-lookup"><span data-stu-id="90893-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="90893-121">Das folgende Beispiel zeigt, wie bestimmt wird, die .NET Framework-Sicherheitsupdates und Hotfixes, die mithilfe von PowerShell auf einem Computer installiert sind:</span><span class="sxs-lookup"><span data-stu-id="90893-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
 Get-ChildItem "HKLM:SOFTWARE\Wow6432Node\Microsoft\Updates\*" -Recurse | Where-Object {$_.name -like
 "*.NET Framework*"}
```

<span data-ttu-id="90893-122">Das Beispiel führt eine Ausgabe, die mit dem folgenden ähnlich ist:</span><span class="sxs-lookup"><span data-stu-id="90893-122">The example produces an output that's similar to the following one:</span></span>

```console
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Client Profile


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y


    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Extended


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y
```

## <a name="see-also"></a><span data-ttu-id="90893-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90893-123">See also</span></span>

[<span data-ttu-id="90893-124">Vorgehensweise: bestimmen, welche .NET Framework-Versionen installiert sind</span><span class="sxs-lookup"><span data-stu-id="90893-124">How to: Determine which .NET Framework versions are installed</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[<span data-ttu-id="90893-125">Installieren Sie .NET Framework für Entwickler</span><span class="sxs-lookup"><span data-stu-id="90893-125">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)  
[<span data-ttu-id="90893-126">Versionen und-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="90893-126">Versions and dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
