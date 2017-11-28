---
title: Storeadm.exe (Isolated Storage-Tool)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d9ae6b007fe32dfbef973105311ba929cc247e6b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="storeadmexe-isolated-storage-tool"></a><span data-ttu-id="a42ad-102">Storeadm.exe (Isolated Storage-Tool)</span><span class="sxs-lookup"><span data-stu-id="a42ad-102">Storeadm.exe (Isolated Storage Tool)</span></span>
<span data-ttu-id="a42ad-103">Das Isolated Storage-Tool listet alle vorhandenen Speicher des aktuellen Benutzers auf oder löscht diese.</span><span class="sxs-lookup"><span data-stu-id="a42ad-103">The Isolated Storage tool lists or removes all existing stores for the current user.</span></span>  
  
 <span data-ttu-id="a42ad-104">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="a42ad-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="a42ad-105">Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung (oder die Visual Studio-Eingabeaufforderung in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="a42ad-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="a42ad-106">Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="a42ad-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="a42ad-107">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a42ad-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a42ad-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a42ad-108">Syntax</span></span>  
  
```  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a42ad-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="a42ad-109">Parameters</span></span>  
  
|<span data-ttu-id="a42ad-110">Option</span><span class="sxs-lookup"><span data-stu-id="a42ad-110">Option</span></span>|<span data-ttu-id="a42ad-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a42ad-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a42ad-112">**-h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="a42ad-112">**/h**[**elp**]</span></span>|<span data-ttu-id="a42ad-113">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="a42ad-113">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="a42ad-114">**/list**</span><span class="sxs-lookup"><span data-stu-id="a42ad-114">**/list**</span></span>|<span data-ttu-id="a42ad-115">Zeigt sämtliche vorhandenen Speicher des aktuellen Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="a42ad-115">Displays all existing stores for the current user.</span></span> <span data-ttu-id="a42ad-116">Dies schließt die Speicher für alle von diesem Benutzer ausgeführten Anwendungen oder Assemblys ein.</span><span class="sxs-lookup"><span data-stu-id="a42ad-116">This includes the stores for all applications or assemblies executed by this user.</span></span>|  
|<span data-ttu-id="a42ad-117">**/machine**</span><span class="sxs-lookup"><span data-stu-id="a42ad-117">**/machine**</span></span>|<span data-ttu-id="a42ad-118">Wählt den Computerspeicher aus.</span><span class="sxs-lookup"><span data-stu-id="a42ad-118">Selects the machine store.</span></span> <span data-ttu-id="a42ad-119">Verwenden Sie diese Option zusammen mit der **/list**-Option oder der **/remove**-Option, um anzugeben, dass die Aktion auf den Computerspeicher angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a42ad-119">Use this option with the **/list** or **/remove** option to specify that the action should apply to the machine store.</span></span><br /><br /> <span data-ttu-id="a42ad-120">Neu in .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="a42ad-120">New in the .NET Framework 2.0</span></span>|  
|<span data-ttu-id="a42ad-121">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="a42ad-121">**/quiet**</span></span>|<span data-ttu-id="a42ad-122">Gibt den stillen Modus an. Dies unterdrückt die Ausgabe von Informationen und zeigt nur Fehlermeldungen an.</span><span class="sxs-lookup"><span data-stu-id="a42ad-122">Specifies quiet mode; suppresses informational output so that only error messages appear.</span></span>|  
|<span data-ttu-id="a42ad-123">**/remove**</span><span class="sxs-lookup"><span data-stu-id="a42ad-123">**/remove**</span></span>|<span data-ttu-id="a42ad-124">Entfernt alle vorhandenen Speicher des aktuellen Benutzers dauerhaft.</span><span class="sxs-lookup"><span data-stu-id="a42ad-124">Permanently removes all existing stores for the current user.</span></span>|  
|<span data-ttu-id="a42ad-125">**/roaming**</span><span class="sxs-lookup"><span data-stu-id="a42ad-125">**/roaming**</span></span>|<span data-ttu-id="a42ad-126">Wählt den Roamingspeicher aus.</span><span class="sxs-lookup"><span data-stu-id="a42ad-126">Selects the roaming store.</span></span> <span data-ttu-id="a42ad-127">Verwenden Sie diese Option zusammen mit der **/list**-Option oder der **/remove**-Option, um anzugeben, dass die Aktion auf den Roamingspeicher angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a42ad-127">Use this option with the **/list** or **/remove** options to specify that the action should apply to the roaming store.</span></span>|  
|<span data-ttu-id="a42ad-128">**/?**</span><span class="sxs-lookup"><span data-stu-id="a42ad-128">**/?**</span></span>|<span data-ttu-id="a42ad-129">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="a42ad-129">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a42ad-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a42ad-130">Remarks</span></span>  
 <span data-ttu-id="a42ad-131">Wird "Storeadm.exe" ohne Angabe von Optionen von der Befehlszeile aus ausgeführt, werden Syntax und Optionen für das Tool angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a42ad-131">Running Storeadm.exe from the command line without specifying any options displays the syntax and options for the tool.</span></span>  
  
 <span data-ttu-id="a42ad-132">Die **/list**-Option und die **/remove**-Option werden in der Regel nicht gleichzeitig verwendet. Wenn jedoch zwei oder mehr Optionen angegeben sind, erfolgt deren Verarbeitung in der Reihenfolge ihrer Eingabe in die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="a42ad-132">The **/list** and **/remove** options are typically used one at a time; however, if two or more options are specified they will be performed in the order in which they appear on the command line.</span></span>  
  
 <span data-ttu-id="a42ad-133">Anwendungen bieten die Wahl, in einen von zwei Speichern für einen Benutzer oder in den Computerspeicher zu speichern:</span><span class="sxs-lookup"><span data-stu-id="a42ad-133">Applications have a choice of saving to one of two stores for a user or to the machine store:</span></span>  
  
-   <span data-ttu-id="a42ad-134">Der lokale Speicher befindet sich an einem Speicherort, der (unter Windows 2000 und höher) kein Roaming zulässt, selbst wenn Benutzerdatenroaming für den Benutzer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a42ad-134">The local store exists in a location that is guaranteed not to roam (on Windows 2000 and later) even if user data roaming is enabled for the user.</span></span>  
  
-   <span data-ttu-id="a42ad-135">Der Roamingspeicher befindet sich an einem Speicherort, der Roaming ermöglicht, sofern über die Windows NT-Verwaltung das Roaming von Benutzerdaten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a42ad-135">The roaming store exists in a location that is able to roam, but can only do so if roaming is enabled for the user via Windows NT administration.</span></span>  
  
-   <span data-ttu-id="a42ad-136">Der Computerspeicher wird von allen Benutzern eines Computers gemeinsam genutzt und unter einem allgemeinen Verzeichnis auf dem jeweiligen Computer angelegt.</span><span class="sxs-lookup"><span data-stu-id="a42ad-136">The machine store is common to all users on a machine and is stored under a common directory on that machine.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a42ad-137">Der Computerspeicher ist ein neues Feature in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="a42ad-137">The machine store is new in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="a42ad-138">Ob Roaming für den Benutzer tatsächlich aktiviert ist, wirkt sich nicht auf die Verwaltung von "Storeadm.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="a42ad-138">Whether roaming is actually enabled for the user does not affect the administration of Storeadm.exe.</span></span> <span data-ttu-id="a42ad-139">Wenn das Tool ohne Optionen ausgeführt wird, werden sämtliche Aktionen auf den lokalen Speicher angewendet.</span><span class="sxs-lookup"><span data-stu-id="a42ad-139">Running the tool without any options applies all actions to the local store.</span></span> <span data-ttu-id="a42ad-140">Wird das Tool mit der **/roaming**-Option ausgeführt, werden alle Aktionen auf den Speicher angewendet, der Roaming zulässt.</span><span class="sxs-lookup"><span data-stu-id="a42ad-140">Running the tool with the **/roaming** option applies all actions to the store that is able to roam.</span></span> <span data-ttu-id="a42ad-141">Wenn das Tool mit der **/machine**-Option ausgeführt wird, werden sämtliche Aktionen auf den Computerspeicher angewendet.</span><span class="sxs-lookup"><span data-stu-id="a42ad-141">Running the tool with the **/machine** option applies all actions to the machine store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a42ad-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a42ad-142">See Also</span></span>  
 [<span data-ttu-id="a42ad-143">Extras</span><span class="sxs-lookup"><span data-stu-id="a42ad-143">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="a42ad-144">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="a42ad-144">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="a42ad-145">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="a42ad-145">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
