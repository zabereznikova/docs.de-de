---
title: 'Gewusst wie: Bestimmen der installierten .NET Framework-Updates'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ba734dd3a9585b52b96cb2d27743da6190961126
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-determine-which-net-framework-updates-are-installed"></a><span data-ttu-id="a734b-102">Gewusst wie: Bestimmen der installierten .NET Framework-Updates</span><span class="sxs-lookup"><span data-stu-id="a734b-102">How to: Determine Which .NET Framework Updates Are Installed</span></span>
<span data-ttu-id="a734b-103">Die installierten Updates für jede auf einem Computer installierten Version von .NET Framework werden in der Windows-Registrierung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a734b-103">The installed updates for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="a734b-104">Sie können diese Informationen mit dem Registrierungs-Editor (regedit.exe) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a734b-104">You can use the Registry Editor (regedit.exe) to view this information.</span></span>  
  
 <span data-ttu-id="a734b-105">Im Registrierungs-Editor werden die .NET Framework-Versionen und die installierten Updates für jede Version in verschiedenen Unterschlüsseln gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a734b-105">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="a734b-106">Informationen zum Ermitteln der installierten Versionsnummern finden Sie unter [Gewusst wie: Bestimmen der installierten .NET Framework-Versionen](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="a734b-106">For information about detecting the installed version numbers, see [How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span> <span data-ttu-id="a734b-107">Informationen zum Installieren von .NET Framework finden Sie unter [Install the .NET Framework for developers (Installieren von .NET Framework für Entwickler)](../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="a734b-107">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
### <a name="to-find-installed-updates"></a><span data-ttu-id="a734b-108">So suchen Sie installierte Updates</span><span class="sxs-lookup"><span data-stu-id="a734b-108">To find installed updates</span></span>  
  
1.  <span data-ttu-id="a734b-109">Öffnen Sie das Programm **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="a734b-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="a734b-110">Öffnen Sie in Windows 8 und höher die Startseite, und geben Sie den Namen ein.</span><span class="sxs-lookup"><span data-stu-id="a734b-110">In Windows 8 and higher open the Start screen and type the name.</span></span> <span data-ttu-id="a734b-111">In früheren Versionen von Windows wählen Sie im **Startmenü** **Ausführen** aus, und geben Sie dann in das Feld **Öffnen** den Wert **regedit.exe** ein.</span><span class="sxs-lookup"><span data-stu-id="a734b-111">In earlier versions of Windows, on the **Start** menu, choose **Run** and then, in the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="a734b-112">Sie müssen über Administratorrechte verfügen, um regedit.exe ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="a734b-112">You must have administrative credentials to run regedit.exe.</span></span>  
  
2.  <span data-ttu-id="a734b-113">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:</span><span class="sxs-lookup"><span data-stu-id="a734b-113">In the Registry Editor, open the following subkey:</span></span>  
  
     <span data-ttu-id="a734b-114">HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates</span><span class="sxs-lookup"><span data-stu-id="a734b-114">HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates</span></span>  
  
     <span data-ttu-id="a734b-115">Die installierten Updates werden unter Unterschlüsseln aufgeführt, die die für sie geltende .NET Framework-Version identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a734b-115">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="a734b-116">Jedes Update wird durch eine Knowledge Base (KB)-Nummer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a734b-116">Each update is identified by a Knowledge Base (KB) number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a734b-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a734b-117">Example</span></span>  
 <span data-ttu-id="a734b-118">Der folgende Code ermittelt programmgesteuert die auf einem Computer installierten .NET Framework-Updates.</span><span class="sxs-lookup"><span data-stu-id="a734b-118">The following code programmatically determines the .NET Framework updates that are installed on a computer.</span></span> <span data-ttu-id="a734b-119">Sie müssen über Administratorrechte verfügen, um dieses Beispiel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="a734b-119">You must have administrative credentials to run this example.</span></span>  
  
 [!code-csharp[ListUpdates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs#1)]
 [!code-vb[ListUpdates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb#1)]  
  
 <span data-ttu-id="a734b-120">Das Beispiel führt zu einer Ausgabe, die der folgenden Ausgabe ähnelt:</span><span class="sxs-lookup"><span data-stu-id="a734b-120">The example produces output that's similar to the following:</span></span>  
  
```  
Microsoft .NET Framework 3.5 SP1  
  KB953595  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB953595)  
  SP1  
    KB2657424  Security Update for Microsoft .NET Framework 3.5 SP1 (KB2657424)  
    KB958484  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB958484)  
    KB963707  Update for Microsoft .NET Framework 3.5 SP1 (KB963707)  
Microsoft .NET Framework 4 Client Profile  
  KB2160841  Security Update for Microsoft .NET Framework 4 Client Profile (KB2160841)  
  KB2446708  Security Update for Microsoft .NET Framework 4 Client Profile (KB2446708)  
  KB2468871  Update for Microsoft .NET Framework 4 Client Profile (KB2468871)  
  KB2478663  Security Update for Microsoft .NET Framework 4 Client Profile (KB2478663)  
  KB2518870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2518870)  
  KB2533523  Update for Microsoft .NET Framework 4 Client Profile (KB2533523)  
  KB2539636  Security Update for Microsoft .NET Framework 4 Client Profile (KB2539636)  
  KB2572078  Security Update for Microsoft .NET Framework 4 Client Profile (KB2572078)  
  KB2633870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2633870)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Client Profile (KB2656351)  
Microsoft .NET Framework 4 Extended  
  KB2416472  Security Update for Microsoft .NET Framework 4 Extended (KB2416472)  
  KB2468871  Update for Microsoft .NET Framework 4 Extended (KB2468871)  
  KB2487367  Security Update for Microsoft .NET Framework 4 Extended (KB2487367)  
  KB2533523  Update for Microsoft .NET Framework 4 Extended (KB2533523)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Extended (KB2656351)  
```  
  
## <a name="see-also"></a><span data-ttu-id="a734b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a734b-121">See also</span></span>

<span data-ttu-id="a734b-122">[Gewusst wie: Bestimmen der installierten .NET Framework-Versionen](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) </span><span class="sxs-lookup"><span data-stu-id="a734b-122">[How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) </span></span>  
<span data-ttu-id="a734b-123">[Installieren von .NET Framework](../../../docs/framework/install/guide-for-developers.md) </span><span class="sxs-lookup"><span data-stu-id="a734b-123">[Installing the .NET Framework](../../../docs/framework/install/guide-for-developers.md) </span></span>  
[<span data-ttu-id="a734b-124">Versionen und Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="a734b-124">Versions and Dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
