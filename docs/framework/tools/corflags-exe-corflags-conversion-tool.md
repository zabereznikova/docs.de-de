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
ms.openlocfilehash: 63e70ae8cd110786ad7d2069088dbfdfde736a28
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846747"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="90a9d-102">CorFlags.exe (Konvertierungstool CorFlags)</span><span class="sxs-lookup"><span data-stu-id="90a9d-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="90a9d-103">Das Konvertierungstool „CorFlags“ ermöglicht das Konfigurieren des CorFlags-Abschnitts eines Headers eines portierbaren ausführbaren Images.</span><span class="sxs-lookup"><span data-stu-id="90a9d-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="90a9d-104">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="90a9d-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="90a9d-105">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="90a9d-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="90a9d-106">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="90a9d-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="90a9d-107">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="90a9d-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90a9d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="90a9d-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="90a9d-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="90a9d-109">Parameters</span></span>  
  
|<span data-ttu-id="90a9d-110">Erforderlicher Parameter</span><span class="sxs-lookup"><span data-stu-id="90a9d-110">Required parameter</span></span>|<span data-ttu-id="90a9d-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="90a9d-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="90a9d-112">Der Name der Assembly, für die CorFlags konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="90a9d-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="90a9d-113">Option</span><span class="sxs-lookup"><span data-stu-id="90a9d-113">Option</span></span>|<span data-ttu-id="90a9d-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="90a9d-114">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="90a9d-115">Legt das 32BITREQUIRED-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="90a9d-115">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="90a9d-116">Löscht das 32BITREQUIRED-Flag.</span><span class="sxs-lookup"><span data-stu-id="90a9d-116">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="90a9d-117">Legt das 32BITPREFERRED-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="90a9d-117">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="90a9d-118">Die App wird als 32-Bit-Prozess sogar auf 64-Bit-Plattformen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="90a9d-118">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="90a9d-119">Legen Sie dieses Flag nur auf EXE-Dateien fest.</span><span class="sxs-lookup"><span data-stu-id="90a9d-119">Set this flag only on EXE files.</span></span> <span data-ttu-id="90a9d-120">Wenn das Flag auf eine DLL-Datei festgelegt ist, kann die DLL in 64-Bit-Prozessen nicht geladen werden und eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="90a9d-120">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="90a9d-121">Eine EXE-Datei mit diesem Flag kann in einem 64-Bit-Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="90a9d-121">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="90a9d-122">Neues in .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="90a9d-122">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="90a9d-123">Löscht das 32BITPREFERRED-Flag.</span><span class="sxs-lookup"><span data-stu-id="90a9d-123">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="90a9d-124">Neues in .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="90a9d-124">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="90a9d-125">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="90a9d-125">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="90a9d-126">Erzwingt ein Update, auch wenn es sich um eine Assembly mit starkem Namen handelt.</span><span class="sxs-lookup"><span data-stu-id="90a9d-126">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="90a9d-127">**Wichtig:**  Nach dem Aktualisieren einer Assembly mit starkem Namen muss diese erneut signiert werden, bevor ihr Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="90a9d-127">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="90a9d-128">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="90a9d-128">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="90a9d-129">Legt das ILONLY-Flag fest.</span><span class="sxs-lookup"><span data-stu-id="90a9d-129">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="90a9d-130">Löscht das ILONLY-Flag.</span><span class="sxs-lookup"><span data-stu-id="90a9d-130">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="90a9d-131">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90a9d-131">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="90a9d-132">Setzt die CLR-Headerversion auf 2.0 zurück.</span><span class="sxs-lookup"><span data-stu-id="90a9d-132">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="90a9d-133">Aktualisiert die CLR-Headerversion auf 2.5.</span><span class="sxs-lookup"><span data-stu-id="90a9d-133">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="90a9d-134">**Hinweis**:  Assemblys können nur als systemeigener Code ausgeführt werden, wenn sie mindestens über die CLR-Headerversion 2.5 verfügen.</span><span class="sxs-lookup"><span data-stu-id="90a9d-134">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90a9d-135">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="90a9d-135">Remarks</span></span>  
 <span data-ttu-id="90a9d-136">Wenn keine Optionen angegeben sind, zeigt das Konvertierungstool CorFlags die Flags für die angegebene Assembly an.</span><span class="sxs-lookup"><span data-stu-id="90a9d-136">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a9d-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90a9d-137">See also</span></span>

- [<span data-ttu-id="90a9d-138">Extras</span><span class="sxs-lookup"><span data-stu-id="90a9d-138">Tools</span></span>](index.md)
- [<span data-ttu-id="90a9d-139">64-Bit-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="90a9d-139">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="90a9d-140">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="90a9d-140">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
