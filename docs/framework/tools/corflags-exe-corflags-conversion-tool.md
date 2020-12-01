---
title: CorFlags.exe (Konvertierungstool CorFlags)
description: Hier erfahren Sie mehr über das CorFlags-Konvertierungstool „CorFlags.exe“. Dieses Tool ermöglicht das Konfigurieren des CorFlags-Abschnitts eines portierbaren und ausführbaren Imageheaders.
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: 3f9f2a71a7a33de13264ce60fa7ff6ea5832aace
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247186"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="782b0-104">CorFlags.exe (Konvertierungstool CorFlags)</span><span class="sxs-lookup"><span data-stu-id="782b0-104">CorFlags.exe (CorFlags Conversion Tool)</span></span>

<span data-ttu-id="782b0-105">Das Konvertierungstool „CorFlags“ ermöglicht das Konfigurieren des CorFlags-Abschnitts eines Headers eines portierbaren ausführbaren Images.</span><span class="sxs-lookup"><span data-stu-id="782b0-105">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="782b0-106">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="782b0-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="782b0-107">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="782b0-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="782b0-108">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="782b0-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="782b0-109">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="782b0-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="782b0-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="782b0-110">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="782b0-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="782b0-111">Parameters</span></span>  
  
|<span data-ttu-id="782b0-112">Erforderlicher Parameter</span><span class="sxs-lookup"><span data-stu-id="782b0-112">Required parameter</span></span>|<span data-ttu-id="782b0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="782b0-113">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="782b0-114">Der Name der Assembly, für die CorFlags konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="782b0-114">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="782b0-115">Option</span><span class="sxs-lookup"><span data-stu-id="782b0-115">Option</span></span>|<span data-ttu-id="782b0-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="782b0-116">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="782b0-117">Legt das 32BITREQUIRED-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="782b0-117">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="782b0-118">Löscht das 32BITREQUIRED-Flag.</span><span class="sxs-lookup"><span data-stu-id="782b0-118">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="782b0-119">Legt das 32BITPREFERRED-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="782b0-119">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="782b0-120">Die App wird als 32-Bit-Prozess sogar auf 64-Bit-Plattformen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="782b0-120">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="782b0-121">Legen Sie dieses Flag nur auf EXE-Dateien fest.</span><span class="sxs-lookup"><span data-stu-id="782b0-121">Set this flag only on EXE files.</span></span> <span data-ttu-id="782b0-122">Wenn das Flag auf eine DLL-Datei festgelegt ist, kann die DLL in 64-Bit-Prozessen nicht geladen werden und eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="782b0-122">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="782b0-123">Eine EXE-Datei mit diesem Flag kann in einem 64-Bit-Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="782b0-123">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="782b0-124">Neues in .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="782b0-124">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="782b0-125">Löscht das 32BITPREFERRED-Flag.</span><span class="sxs-lookup"><span data-stu-id="782b0-125">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="782b0-126">Neues in .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="782b0-126">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="782b0-127">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="782b0-127">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="782b0-128">Erzwingt ein Update, auch wenn es sich um eine Assembly mit starkem Namen handelt.</span><span class="sxs-lookup"><span data-stu-id="782b0-128">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="782b0-129">**Wichtig:**  Nach dem Aktualisieren einer Assembly mit starkem Namen muss diese erneut signiert werden, bevor ihr Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="782b0-129">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="782b0-130">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="782b0-130">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="782b0-131">Legt das ILONLY-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="782b0-131">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="782b0-132">Löscht das ILONLY-Flag.</span><span class="sxs-lookup"><span data-stu-id="782b0-132">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="782b0-133">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="782b0-133">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="782b0-134">Setzt die CLR-Headerversion auf 2.0 zurück.</span><span class="sxs-lookup"><span data-stu-id="782b0-134">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="782b0-135">Aktualisiert die CLR-Headerversion auf 2.5.</span><span class="sxs-lookup"><span data-stu-id="782b0-135">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="782b0-136">**Hinweis**:  Assemblys können nur als systemeigener Code ausgeführt werden, wenn sie mindestens über die CLR-Headerversion 2.5 verfügen.</span><span class="sxs-lookup"><span data-stu-id="782b0-136">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="782b0-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="782b0-137">Remarks</span></span>  

 <span data-ttu-id="782b0-138">Wenn keine Optionen angegeben sind, zeigt das Konvertierungstool CorFlags die Flags für die angegebene Assembly an.</span><span class="sxs-lookup"><span data-stu-id="782b0-138">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782b0-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="782b0-139">See also</span></span>

- [<span data-ttu-id="782b0-140">Extras</span><span class="sxs-lookup"><span data-stu-id="782b0-140">Tools</span></span>](index.md)
- [<span data-ttu-id="782b0-141">64-Bit-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="782b0-141">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="782b0-142">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="782b0-142">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
