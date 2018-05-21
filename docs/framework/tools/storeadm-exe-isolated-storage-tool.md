---
title: Storeadm.exe (Isolated Storage-Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c9b8d0680a50d9945bef0d03d10e45750fc49a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="storeadmexe-isolated-storage-tool"></a><span data-ttu-id="ef2f2-102">Storeadm.exe (Isolated Storage-Tool)</span><span class="sxs-lookup"><span data-stu-id="ef2f2-102">Storeadm.exe (Isolated Storage Tool)</span></span>
<span data-ttu-id="ef2f2-103">Das Isolated Storage-Tool listet alle vorhandenen Speicher des aktuellen Benutzers auf oder löscht diese.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-103">The Isolated Storage tool lists or removes all existing stores for the current user.</span></span>  
  
 <span data-ttu-id="ef2f2-104">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="ef2f2-105">Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung (oder die Visual Studio-Eingabeaufforderung in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="ef2f2-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="ef2f2-106">Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="ef2f2-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="ef2f2-107">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ef2f2-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef2f2-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef2f2-108">Syntax</span></span>  
  
```  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef2f2-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="ef2f2-109">Parameters</span></span>  
  
|<span data-ttu-id="ef2f2-110">Option</span><span class="sxs-lookup"><span data-stu-id="ef2f2-110">Option</span></span>|<span data-ttu-id="ef2f2-111">description</span><span class="sxs-lookup"><span data-stu-id="ef2f2-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ef2f2-112">**-h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="ef2f2-112">**/h**[**elp**]</span></span>|<span data-ttu-id="ef2f2-113">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-113">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="ef2f2-114">**/list**</span><span class="sxs-lookup"><span data-stu-id="ef2f2-114">**/list**</span></span>|<span data-ttu-id="ef2f2-115">Zeigt sämtliche vorhandenen Speicher des aktuellen Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-115">Displays all existing stores for the current user.</span></span> <span data-ttu-id="ef2f2-116">Dies schließt die Speicher für alle von diesem Benutzer ausgeführten Anwendungen oder Assemblys ein.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-116">This includes the stores for all applications or assemblies executed by this user.</span></span>|  
|<span data-ttu-id="ef2f2-117">**/machine**</span><span class="sxs-lookup"><span data-stu-id="ef2f2-117">**/machine**</span></span>|<span data-ttu-id="ef2f2-118">Wählt den Computerspeicher aus.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-118">Selects the machine store.</span></span> <span data-ttu-id="ef2f2-119">Verwenden Sie diese Option zusammen mit der **/list**-Option oder der **/remove**-Option, um anzugeben, dass die Aktion auf den Computerspeicher angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-119">Use this option with the **/list** or **/remove** option to specify that the action should apply to the machine store.</span></span><br /><br /> <span data-ttu-id="ef2f2-120">Neu in .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="ef2f2-120">New in the .NET Framework 2.0</span></span>|  
|<span data-ttu-id="ef2f2-121">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="ef2f2-121">**/quiet**</span></span>|<span data-ttu-id="ef2f2-122">Gibt den stillen Modus an. Dies unterdrückt die Ausgabe von Informationen und zeigt nur Fehlermeldungen an.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-122">Specifies quiet mode; suppresses informational output so that only error messages appear.</span></span>|  
|<span data-ttu-id="ef2f2-123">**/remove**</span><span class="sxs-lookup"><span data-stu-id="ef2f2-123">**/remove**</span></span>|<span data-ttu-id="ef2f2-124">Entfernt alle vorhandenen Speicher des aktuellen Benutzers dauerhaft.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-124">Permanently removes all existing stores for the current user.</span></span>|  
|<span data-ttu-id="ef2f2-125">**/roaming**</span><span class="sxs-lookup"><span data-stu-id="ef2f2-125">**/roaming**</span></span>|<span data-ttu-id="ef2f2-126">Wählt den Roamingspeicher aus.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-126">Selects the roaming store.</span></span> <span data-ttu-id="ef2f2-127">Verwenden Sie diese Option zusammen mit der **/list**-Option oder der **/remove**-Option, um anzugeben, dass die Aktion auf den Roamingspeicher angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-127">Use this option with the **/list** or **/remove** options to specify that the action should apply to the roaming store.</span></span>|  
|<span data-ttu-id="ef2f2-128">**/?**</span><span class="sxs-lookup"><span data-stu-id="ef2f2-128">**/?**</span></span>|<span data-ttu-id="ef2f2-129">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-129">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef2f2-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef2f2-130">Remarks</span></span>  
 <span data-ttu-id="ef2f2-131">Wird "Storeadm.exe" ohne Angabe von Optionen von der Befehlszeile aus ausgeführt, werden Syntax und Optionen für das Tool angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-131">Running Storeadm.exe from the command line without specifying any options displays the syntax and options for the tool.</span></span>  
  
 <span data-ttu-id="ef2f2-132">Die **/list**-Option und die **/remove**-Option werden in der Regel nicht gleichzeitig verwendet. Wenn jedoch zwei oder mehr Optionen angegeben sind, erfolgt deren Verarbeitung in der Reihenfolge ihrer Eingabe in die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-132">The **/list** and **/remove** options are typically used one at a time; however, if two or more options are specified they will be performed in the order in which they appear on the command line.</span></span>  
  
 <span data-ttu-id="ef2f2-133">Anwendungen bieten die Wahl, in einen von zwei Speichern für einen Benutzer oder in den Computerspeicher zu speichern:</span><span class="sxs-lookup"><span data-stu-id="ef2f2-133">Applications have a choice of saving to one of two stores for a user or to the machine store:</span></span>  
  
-   <span data-ttu-id="ef2f2-134">Der lokale Speicher befindet sich an einem Speicherort, der (unter Windows 2000 und höher) kein Roaming zulässt, selbst wenn Benutzerdatenroaming für den Benutzer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-134">The local store exists in a location that is guaranteed not to roam (on Windows 2000 and later) even if user data roaming is enabled for the user.</span></span>  
  
-   <span data-ttu-id="ef2f2-135">Der Roamingspeicher befindet sich an einem Speicherort, der Roaming ermöglicht, sofern über die Windows NT-Verwaltung das Roaming von Benutzerdaten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-135">The roaming store exists in a location that is able to roam, but can only do so if roaming is enabled for the user via Windows NT administration.</span></span>  
  
-   <span data-ttu-id="ef2f2-136">Der Computerspeicher wird von allen Benutzern eines Computers gemeinsam genutzt und unter einem allgemeinen Verzeichnis auf dem jeweiligen Computer angelegt.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-136">The machine store is common to all users on a machine and is stored under a common directory on that machine.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef2f2-137">Der Computerspeicher ist ein neues Feature in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-137">The machine store is new in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="ef2f2-138">Ob Roaming für den Benutzer tatsächlich aktiviert ist, wirkt sich nicht auf die Verwaltung von "Storeadm.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-138">Whether roaming is actually enabled for the user does not affect the administration of Storeadm.exe.</span></span> <span data-ttu-id="ef2f2-139">Wenn das Tool ohne Optionen ausgeführt wird, werden sämtliche Aktionen auf den lokalen Speicher angewendet.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-139">Running the tool without any options applies all actions to the local store.</span></span> <span data-ttu-id="ef2f2-140">Wird das Tool mit der **/roaming**-Option ausgeführt, werden alle Aktionen auf den Speicher angewendet, der Roaming zulässt.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-140">Running the tool with the **/roaming** option applies all actions to the store that is able to roam.</span></span> <span data-ttu-id="ef2f2-141">Wenn das Tool mit der **/machine**-Option ausgeführt wird, werden sämtliche Aktionen auf den Computerspeicher angewendet.</span><span class="sxs-lookup"><span data-stu-id="ef2f2-141">Running the tool with the **/machine** option applies all actions to the machine store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef2f2-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef2f2-142">See Also</span></span>  
 [<span data-ttu-id="ef2f2-143">Extras</span><span class="sxs-lookup"><span data-stu-id="ef2f2-143">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="ef2f2-144">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="ef2f2-144">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="ef2f2-145">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="ef2f2-145">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
