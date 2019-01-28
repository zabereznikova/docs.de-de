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
ms.openlocfilehash: ae2efe619d9c6ebcf2c570b5a63d569faf3b3343
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690747"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="b4070-102">CorFlags.exe (Konvertierungstool CorFlags)</span><span class="sxs-lookup"><span data-stu-id="b4070-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="b4070-103">Das Konvertierungstool „CorFlags“ ermöglicht das Konfigurieren des CorFlags-Abschnitts eines Headers eines portierbaren ausführbaren Images.</span><span class="sxs-lookup"><span data-stu-id="b4070-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="b4070-104">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="b4070-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="b4070-105">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b4070-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="b4070-106">Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b4070-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="b4070-107">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b4070-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4070-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4070-108">Syntax</span></span>  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4070-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4070-109">Parameters</span></span>  
  
|<span data-ttu-id="b4070-110">Erforderlicher Parameter</span><span class="sxs-lookup"><span data-stu-id="b4070-110">Required parameter</span></span>|<span data-ttu-id="b4070-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4070-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="b4070-112">Der Name der Assembly, für die CorFlags konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b4070-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="b4070-113">Option</span><span class="sxs-lookup"><span data-stu-id="b4070-113">Option</span></span>|<span data-ttu-id="b4070-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4070-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b4070-115">**/32BIT[REQ]+**</span><span class="sxs-lookup"><span data-stu-id="b4070-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="b4070-116">Legt das 32BITREQUIRED-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="b4070-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="b4070-117">**/32BIT[REQ]-**</span><span class="sxs-lookup"><span data-stu-id="b4070-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="b4070-118">Löscht das 32BITREQUIRED-Flag.</span><span class="sxs-lookup"><span data-stu-id="b4070-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="b4070-119">**/32BITPREF+**</span><span class="sxs-lookup"><span data-stu-id="b4070-119">**/32BITPREF+**</span></span>|<span data-ttu-id="b4070-120">Legt das 32BITPREFERRED-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="b4070-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="b4070-121">Die App wird als 32-Bit-Prozess sogar auf 64-Bit-Plattformen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b4070-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="b4070-122">Legen Sie dieses Flag nur auf EXE-Dateien fest.</span><span class="sxs-lookup"><span data-stu-id="b4070-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="b4070-123">Wenn das Flag auf eine DLL-Datei festgelegt ist, kann die DLL in 64-Bit-Prozessen nicht geladen werden und eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b4070-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="b4070-124">Eine EXE-Datei mit diesem Flag kann in einem 64-Bit-Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="b4070-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="b4070-125">Neu im [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4070-125">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="b4070-126">**/32BITPREF-**</span><span class="sxs-lookup"><span data-stu-id="b4070-126">**/32BITPREF-**</span></span>|<span data-ttu-id="b4070-127">Löscht das 32BITPREFERRED-Flag.</span><span class="sxs-lookup"><span data-stu-id="b4070-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="b4070-128">Neu im [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4070-128">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="b4070-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="b4070-129">**/?**</span></span>|<span data-ttu-id="b4070-130">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="b4070-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="b4070-131">**/Force**</span><span class="sxs-lookup"><span data-stu-id="b4070-131">**/Force**</span></span>|<span data-ttu-id="b4070-132">Erzwingt ein Update, auch wenn es sich um eine Assembly mit starkem Namen handelt.</span><span class="sxs-lookup"><span data-stu-id="b4070-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="b4070-133">**Wichtig:**  Nach dem Aktualisieren einer Assembly mit starkem Namen muss diese erneut signiert werden, bevor ihr Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b4070-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="b4070-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="b4070-134">**/help**</span></span>|<span data-ttu-id="b4070-135">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="b4070-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="b4070-136">**/ILONLY+**</span><span class="sxs-lookup"><span data-stu-id="b4070-136">**/ILONLY+**</span></span>|<span data-ttu-id="b4070-137">Legt das ILONLY-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="b4070-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="b4070-138">**/ILONLY-**</span><span class="sxs-lookup"><span data-stu-id="b4070-138">**/ILONLY-**</span></span>|<span data-ttu-id="b4070-139">Löscht das ILONLY-Flag.</span><span class="sxs-lookup"><span data-stu-id="b4070-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="b4070-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="b4070-140">**/nologo**</span></span>|<span data-ttu-id="b4070-141">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b4070-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="b4070-142">**/RevertCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="b4070-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="b4070-143">Setzt die CLR-Headerversion auf 2.0 zurück.</span><span class="sxs-lookup"><span data-stu-id="b4070-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="b4070-144">**/UpgradeCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="b4070-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="b4070-145">Aktualisiert die CLR-Headerversion auf 2.5.</span><span class="sxs-lookup"><span data-stu-id="b4070-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="b4070-146">**Hinweis**:  Assemblys können nur als systemeigener Code ausgeführt werden, wenn sie mindestens über die CLR-Headerversion 2.5 verfügen.</span><span class="sxs-lookup"><span data-stu-id="b4070-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4070-147">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4070-147">Remarks</span></span>  
 <span data-ttu-id="b4070-148">Wenn keine Optionen angegeben sind, zeigt das Konvertierungstool CorFlags die Flags für die angegebene Assembly an.</span><span class="sxs-lookup"><span data-stu-id="b4070-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4070-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4070-149">See also</span></span>
- [<span data-ttu-id="b4070-150">Extras</span><span class="sxs-lookup"><span data-stu-id="b4070-150">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="b4070-151">64-Bit-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b4070-151">64-bit Applications</span></span>](../../../docs/framework/64-bit-apps.md)
- [<span data-ttu-id="b4070-152">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="b4070-152">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
