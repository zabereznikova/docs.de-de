---
title: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes
description: Erfahren Sie, wie Sie die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes ermitteln.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
ms.openlocfilehash: 5c7bf48d5786530a9bcb69fb7cf605ac2c80a4eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181269"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="00da4-103">Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes</span><span class="sxs-lookup"><span data-stu-id="00da4-103">How to determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="00da4-104">In diesem Artikel wird gezeigt, wie Sie die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes ermitteln.</span><span class="sxs-lookup"><span data-stu-id="00da4-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="00da4-105">Alle in diesem Artikel gezeigten Techniken erfordern ein Konto mit Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="00da4-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="use-registry-editor"></a><span data-ttu-id="00da4-106">Verwenden des Registrierungs-Editors</span><span class="sxs-lookup"><span data-stu-id="00da4-106">Use Registry Editor</span></span>

<span data-ttu-id="00da4-107">Die auf einem Computer installierten Sicherheitsupdates und Hotfixes für jede Version von .NET Framework werden in der Windows-Registrierung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="00da4-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="00da4-108">Sie können diese Informationen mit dem Registrierungs-Editor (*regedit.exe*) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="00da4-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="00da4-109">Öffnen Sie das Programm **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="00da4-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="00da4-110">Klicken Sie in Windows 8 und höheren Versionen mit der rechten Maustaste auf **Start** ![Screenshot des Logos der WINDOWS-TASTE.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="00da4-110">In Windows 8 and later versions, right-click **Start** ![Screenshot of the Windows key logo.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="00da4-111">Geben Sie im Feld **Öffnen** den Namen **regedit.exe** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="00da4-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="00da4-112">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:</span><span class="sxs-lookup"><span data-stu-id="00da4-112">In the Registry Editor, open the following subkey:</span></span>

     <span data-ttu-id="00da4-113">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates**</span><span class="sxs-lookup"><span data-stu-id="00da4-113">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates**</span></span>

     <span data-ttu-id="00da4-114">Die installierten Updates werden unter Unterschlüsseln aufgeführt, die die für sie geltende .NET Framework-Version identifizieren.</span><span class="sxs-lookup"><span data-stu-id="00da4-114">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="00da4-115">Jedes Update wird durch eine Knowledge Base (KB)-Nummer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="00da4-115">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="00da4-116">Im Registrierungs-Editor werden die .NET Framework-Versionen und die installierten Updates für jede Version in verschiedenen Unterschlüsseln gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00da4-116">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="00da4-117">Informationen zum Ermitteln der installierten Versionsnummern finden Sie unter [Gewusst wie: Bestimmen der installierten .NET Framework-Versionen](how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="00da4-117">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="query-the-registry-using-code"></a><span data-ttu-id="00da4-118">Abfragen der Registrierung mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="00da4-118">Query the registry using code</span></span>

<span data-ttu-id="00da4-119">Im folgenden Beispiel werden die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes programmgesteuert ermittelt:</span><span class="sxs-lookup"><span data-stu-id="00da4-119">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="00da4-120">Das Beispiel erzeugt eine Ausgabe, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="00da4-120">The example produces an output that's similar to the following one:</span></span>

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

## <a name="use-powershell-to-query-the-registry"></a><span data-ttu-id="00da4-121">Abfragen der Registrierung mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="00da4-121">Use PowerShell to query the registry</span></span>

<span data-ttu-id="00da4-122">Im folgenden Beispiel werden die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes mithilfe von PowerShell ermittelt:</span><span class="sxs-lookup"><span data-stu-id="00da4-122">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

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

<span data-ttu-id="00da4-123">Das Beispiel erzeugt eine Ausgabe, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="00da4-123">The example produces an output that's similar to the following one:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="00da4-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00da4-124">See also</span></span>

- [<span data-ttu-id="00da4-125">Gewusst wie: Bestimmen der installierten .NET Framework-Versionen</span><span class="sxs-lookup"><span data-stu-id="00da4-125">How to: Determine which .NET Framework versions are installed</span></span>](how-to-determine-which-versions-are-installed.md)
- [<span data-ttu-id="00da4-126">Installieren von.NET Framework für Entwickler</span><span class="sxs-lookup"><span data-stu-id="00da4-126">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="00da4-127">Versionen und Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="00da4-127">Versions and dependencies</span></span>](versions-and-dependencies.md)
