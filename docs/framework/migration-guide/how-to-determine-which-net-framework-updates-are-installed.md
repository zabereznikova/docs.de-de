---
title: 'Vorgehensweise: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes'
description: Erfahren Sie, wie Sie die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes ermitteln.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c69d4bb370087dddafbfed41cbfb1fef229677c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318971"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="1617b-103">Vorgehensweise: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes</span><span class="sxs-lookup"><span data-stu-id="1617b-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="1617b-104">In diesem Artikel wird gezeigt, wie Sie die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes ermitteln.</span><span class="sxs-lookup"><span data-stu-id="1617b-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="1617b-105">Alle in diesem Artikel gezeigten Techniken erfordern ein Konto mit Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="1617b-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="1617b-106">So ermitteln Sie mithilfe der Registrierung die installierten Updates</span><span class="sxs-lookup"><span data-stu-id="1617b-106">To find installed updates using the registry</span></span>

<span data-ttu-id="1617b-107">Die auf einem Computer installierten Sicherheitsupdates und Hotfixes für jede Version von .NET Framework werden in der Windows-Registrierung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1617b-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="1617b-108">Sie können diese Informationen mit dem Registrierungs-Editor (*regedit.exe*) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1617b-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="1617b-109">Öffnen Sie das Programm **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="1617b-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="1617b-110">Klicken Sie in Windows 8 und höheren Versionen mit der rechten Maustaste auf **Start** ![Screenshot des Logos der WINDOWS-TASTE.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1617b-110">In Windows 8 and later versions, right-click **Start** ![Screenshot of the Windows key logo.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="1617b-111">Geben Sie im Feld **Öffnen** den Namen **regedit.exe** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1617b-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="1617b-112">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:</span><span class="sxs-lookup"><span data-stu-id="1617b-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="1617b-113">Die installierten Updates werden unter Unterschlüsseln aufgeführt, die die für sie geltende .NET Framework-Version identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1617b-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="1617b-114">Jedes Update wird durch eine Knowledge Base (KB)-Nummer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1617b-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="1617b-115">Im Registrierungs-Editor werden die .NET Framework-Versionen und die installierten Updates für jede Version in verschiedenen Unterschlüsseln gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1617b-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="1617b-116">Informationen zum Ermitteln der installierten Versionsnummern finden Sie unter [Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen](how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="1617b-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="1617b-117">So ermitteln Sie mithilfe einer Registrierungsabfrage im Code die installierten Updates</span><span class="sxs-lookup"><span data-stu-id="1617b-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="1617b-118">Im folgenden Beispiel werden die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes programmgesteuert ermittelt:</span><span class="sxs-lookup"><span data-stu-id="1617b-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="1617b-119">Das Beispiel erzeugt eine Ausgabe, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="1617b-119">The example produces an output that's similar to the following one:</span></span>

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

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="1617b-120">So ermitteln Sie mithilfe einer Registrierungsabfrage in PowerShell die installierten Updates</span><span class="sxs-lookup"><span data-stu-id="1617b-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="1617b-121">Im folgenden Beispiel werden die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes mithilfe von PowerShell ermittelt:</span><span class="sxs-lookup"><span data-stu-id="1617b-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
$DotNetVersions = Get-ChildItem HKLM:\SOFTWARE\WOW6432Node\Microsoft\Updates | Where-Object {$_.name -like
 "*.NET Framework*"}

ForEach($Version in $DotNetVersions){
    
   $Updates = Get-ChildItem $Version.PSPath
    $Version.PSChildName
    ForEach ($Update in $Updates){
       $Update.PSChildName
       }
}
```

<span data-ttu-id="1617b-122">Das Beispiel erzeugt eine Ausgabe, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="1617b-122">The example produces an output that's similar to the following one:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1617b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1617b-123">See also</span></span>

- [<span data-ttu-id="1617b-124">Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen</span><span class="sxs-lookup"><span data-stu-id="1617b-124">How to: Determine which .NET Framework versions are installed</span></span>](how-to-determine-which-versions-are-installed.md)
- [<span data-ttu-id="1617b-125">Installieren von .NET Framework für Entwickler</span><span class="sxs-lookup"><span data-stu-id="1617b-125">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="1617b-126">Versionen und Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="1617b-126">Versions and dependencies</span></span>](versions-and-dependencies.md)
