---
title: CorFlags.exe (Konvertierungstool CorFlags)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
caps.latest.revision: 17
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 80fb48fc86d3010020a0a8a79bb2b4b7a6275368
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="a6d6e-102">CorFlags.exe (Konvertierungstool CorFlags)</span><span class="sxs-lookup"><span data-stu-id="a6d6e-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="a6d6e-103">Das Konvertierungstool „CorFlags“ ermöglicht das Konfigurieren des CorFlags-Abschnitts eines Headers eines portierbaren ausführbaren Images.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="a6d6e-104">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="a6d6e-105">Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung (oder die Visual Studio-Eingabeaufforderung in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="a6d6e-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="a6d6e-106">Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="a6d6e-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="a6d6e-107">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a6d6e-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6d6e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6d6e-108">Syntax</span></span>  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6d6e-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6d6e-109">Parameters</span></span>  
  
|<span data-ttu-id="a6d6e-110">Erforderlicher Parameter</span><span class="sxs-lookup"><span data-stu-id="a6d6e-110">Required parameter</span></span>|<span data-ttu-id="a6d6e-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6d6e-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="a6d6e-112">Der Name der Assembly, für die CorFlags konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="a6d6e-113">Option</span><span class="sxs-lookup"><span data-stu-id="a6d6e-113">Option</span></span>|<span data-ttu-id="a6d6e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6d6e-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a6d6e-115">**/32BIT[REQ]+**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="a6d6e-116">Legt das 32BITREQUIRED-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="a6d6e-117">**/32BIT[REQ]-**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="a6d6e-118">Löscht das 32BITREQUIRED-Flag.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="a6d6e-119">**/32BITPREF+**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-119">**/32BITPREF+**</span></span>|<span data-ttu-id="a6d6e-120">Legt das 32BITPREFERRED-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="a6d6e-121">Die App wird als 32-Bit-Prozess sogar auf 64-Bit-Plattformen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="a6d6e-122">Legen Sie dieses Flag nur auf EXE-Dateien fest.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="a6d6e-123">Wenn das Flag auf eine DLL-Datei festgelegt ist, kann die DLL in 64-Bit-Prozessen nicht geladen werden und eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="a6d6e-124">Eine EXE-Datei mit diesem Flag kann in einem 64-Bit-Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="a6d6e-125">Neu im [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6d6e-125">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="a6d6e-126">**/32BITPREF-**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-126">**/32BITPREF-**</span></span>|<span data-ttu-id="a6d6e-127">Löscht das 32BITPREFERRED-Flag.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="a6d6e-128">Neu im [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6d6e-128">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="a6d6e-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-129">**/?**</span></span>|<span data-ttu-id="a6d6e-130">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="a6d6e-131">**/Force**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-131">**/Force**</span></span>|<span data-ttu-id="a6d6e-132">Erzwingt ein Update, auch wenn es sich um eine Assembly mit starkem Namen handelt.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="a6d6e-133">**Wichtig**: Nach dem Aktualisieren einer Assembly mit starkem Namen muss diese erneut signiert werden, bevor ihr Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="a6d6e-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-134">**/help**</span></span>|<span data-ttu-id="a6d6e-135">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="a6d6e-136">**/ILONLY+**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-136">**/ILONLY+**</span></span>|<span data-ttu-id="a6d6e-137">Legt das ILONLY-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="a6d6e-138">**/ILONLY-**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-138">**/ILONLY-**</span></span>|<span data-ttu-id="a6d6e-139">Löscht das ILONLY-Flag.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="a6d6e-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-140">**/nologo**</span></span>|<span data-ttu-id="a6d6e-141">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="a6d6e-142">**/RevertCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="a6d6e-143">Setzt die CLR-Headerversion auf 2.0 zurück.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="a6d6e-144">**/UpgradeCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="a6d6e-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="a6d6e-145">Aktualisiert die CLR-Headerversion auf 2.5.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="a6d6e-146">**Wichtig**: Assemblys können nur als nativer Code ausgeführt werden, wenn sie mindestens über die CLR-Headerversion 2.5 verfügen.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6d6e-147">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6d6e-147">Remarks</span></span>  
 <span data-ttu-id="a6d6e-148">Wenn keine Optionen angegeben sind, zeigt das Konvertierungstool CorFlags die Flags für die angegebene Assembly an.</span><span class="sxs-lookup"><span data-stu-id="a6d6e-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d6e-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6d6e-149">See Also</span></span>  
 <span data-ttu-id="a6d6e-150">[Tools](../../../docs/framework/tools/index.md) </span><span class="sxs-lookup"><span data-stu-id="a6d6e-150">[Tools](../../../docs/framework/tools/index.md) </span></span>  
 <span data-ttu-id="a6d6e-151">[64-Bit-Anwendungen](../../../docs/framework/64-bit-apps.md) </span><span class="sxs-lookup"><span data-stu-id="a6d6e-151">[64-bit Applications](../../../docs/framework/64-bit-apps.md) </span></span>  
 [<span data-ttu-id="a6d6e-152">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="a6d6e-152">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

