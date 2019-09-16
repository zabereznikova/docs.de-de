---
title: CorFlags.exe (Konvertierungstool CorFlags)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4228da6efe22091c86de95d846c14f504d51457f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851284"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="3cc21-102">CorFlags.exe (Konvertierungstool CorFlags)</span><span class="sxs-lookup"><span data-stu-id="3cc21-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="3cc21-103">Das Konvertierungstool „CorFlags“ ermöglicht das Konfigurieren des CorFlags-Abschnitts eines Headers eines portierbaren ausführbaren Images.</span><span class="sxs-lookup"><span data-stu-id="3cc21-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="3cc21-104">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="3cc21-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="3cc21-105">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3cc21-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="3cc21-106">Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="3cc21-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="3cc21-107">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3cc21-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc21-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="3cc21-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cc21-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="3cc21-109">Parameters</span></span>  
  
|<span data-ttu-id="3cc21-110">Erforderlicher Parameter</span><span class="sxs-lookup"><span data-stu-id="3cc21-110">Required parameter</span></span>|<span data-ttu-id="3cc21-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3cc21-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="3cc21-112">Der Name der Assembly, für die CorFlags konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3cc21-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="3cc21-113">Option</span><span class="sxs-lookup"><span data-stu-id="3cc21-113">Option</span></span>|<span data-ttu-id="3cc21-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3cc21-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3cc21-115">**/32BIT[REQ]+**</span><span class="sxs-lookup"><span data-stu-id="3cc21-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="3cc21-116">Legt das 32BITREQUIRED-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="3cc21-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="3cc21-117">**/32BIT[REQ]-**</span><span class="sxs-lookup"><span data-stu-id="3cc21-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="3cc21-118">Löscht das 32BITREQUIRED-Flag.</span><span class="sxs-lookup"><span data-stu-id="3cc21-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="3cc21-119">**/32BITPREF+**</span><span class="sxs-lookup"><span data-stu-id="3cc21-119">**/32BITPREF+**</span></span>|<span data-ttu-id="3cc21-120">Legt das 32BITPREFERRED-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="3cc21-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="3cc21-121">Die App wird als 32-Bit-Prozess sogar auf 64-Bit-Plattformen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3cc21-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="3cc21-122">Legen Sie dieses Flag nur auf EXE-Dateien fest.</span><span class="sxs-lookup"><span data-stu-id="3cc21-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="3cc21-123">Wenn das Flag auf eine DLL-Datei festgelegt ist, kann die DLL in 64-Bit-Prozessen nicht geladen werden und eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3cc21-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="3cc21-124">Eine EXE-Datei mit diesem Flag kann in einem 64-Bit-Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="3cc21-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="3cc21-125">Neues in .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="3cc21-125">New in the .NET Framework 4.5.</span></span>|  
|<span data-ttu-id="3cc21-126">**/32BITPREF-**</span><span class="sxs-lookup"><span data-stu-id="3cc21-126">**/32BITPREF-**</span></span>|<span data-ttu-id="3cc21-127">Löscht das 32BITPREFERRED-Flag.</span><span class="sxs-lookup"><span data-stu-id="3cc21-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="3cc21-128">Neues in .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="3cc21-128">New in the .NET Framework 4.5.</span></span>|  
|<span data-ttu-id="3cc21-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="3cc21-129">**/?**</span></span>|<span data-ttu-id="3cc21-130">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="3cc21-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="3cc21-131">**/Force**</span><span class="sxs-lookup"><span data-stu-id="3cc21-131">**/Force**</span></span>|<span data-ttu-id="3cc21-132">Erzwingt ein Update, auch wenn es sich um eine Assembly mit starkem Namen handelt.</span><span class="sxs-lookup"><span data-stu-id="3cc21-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="3cc21-133">**Wichtig:**  Nach dem Aktualisieren einer Assembly mit starkem Namen muss diese erneut signiert werden, bevor ihr Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3cc21-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="3cc21-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="3cc21-134">**/help**</span></span>|<span data-ttu-id="3cc21-135">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="3cc21-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="3cc21-136">**/ILONLY+**</span><span class="sxs-lookup"><span data-stu-id="3cc21-136">**/ILONLY+**</span></span>|<span data-ttu-id="3cc21-137">Legt das ILONLY-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="3cc21-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="3cc21-138">**/ILONLY-**</span><span class="sxs-lookup"><span data-stu-id="3cc21-138">**/ILONLY-**</span></span>|<span data-ttu-id="3cc21-139">Löscht das ILONLY-Flag.</span><span class="sxs-lookup"><span data-stu-id="3cc21-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="3cc21-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="3cc21-140">**/nologo**</span></span>|<span data-ttu-id="3cc21-141">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3cc21-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="3cc21-142">**/RevertCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="3cc21-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="3cc21-143">Setzt die CLR-Headerversion auf 2.0 zurück.</span><span class="sxs-lookup"><span data-stu-id="3cc21-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="3cc21-144">**/UpgradeCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="3cc21-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="3cc21-145">Aktualisiert die CLR-Headerversion auf 2.5.</span><span class="sxs-lookup"><span data-stu-id="3cc21-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="3cc21-146">**Hinweis**:  Assemblys können nur als systemeigener Code ausgeführt werden, wenn sie mindestens über die CLR-Headerversion 2.5 verfügen.</span><span class="sxs-lookup"><span data-stu-id="3cc21-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cc21-147">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="3cc21-147">Remarks</span></span>  
 <span data-ttu-id="3cc21-148">Wenn keine Optionen angegeben sind, zeigt das Konvertierungstool CorFlags die Flags für die angegebene Assembly an.</span><span class="sxs-lookup"><span data-stu-id="3cc21-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cc21-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cc21-149">See also</span></span>

- [<span data-ttu-id="3cc21-150">Extras</span><span class="sxs-lookup"><span data-stu-id="3cc21-150">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="3cc21-151">64-Bit-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="3cc21-151">64-bit Applications</span></span>](../../../docs/framework/64-bit-apps.md)
- [<span data-ttu-id="3cc21-152">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="3cc21-152">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
