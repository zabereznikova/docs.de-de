---
title: ServiceModel Registration-Tool (ServiceModelReg.exe)
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: a6f65ccc6caa0a7e496e7de8c83259ab48903753
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183105"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a><span data-ttu-id="b4706-102">ServiceModel Registration-Tool (ServiceModelReg.exe)</span><span class="sxs-lookup"><span data-stu-id="b4706-102">ServiceModel Registration Tool (ServiceModelReg.exe)</span></span>
<span data-ttu-id="b4706-103">Dieses Befehlszeilentool bietet die Möglichkeit, die Registrierung von WCF- und WF-Komponenten auf einem einzelnen Computer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b4706-103">This command-line tool provides the ability to manage the registration of WCF and WF components on a single machine.</span></span> <span data-ttu-id="b4706-104">Unter normalen Umständen müssen Sie dieses Tool nicht verwenden, da WCF- und WF-Komponenten bei der Installation konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b4706-104">Under normal circumstances you should not need to use this tool as WCF and WF components are configured when installed.</span></span> <span data-ttu-id="b4706-105">Wenn jedoch bei der Dienstaktivierung Probleme auftreten, können Sie versuchen, die Komponenten mithilfe dieses Tools zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="b4706-105">But if you are experiencing problems with service activation, you can try to register the components using this tool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4706-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4706-106">Syntax</span></span>  
  
```console  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a><span data-ttu-id="b4706-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b4706-107">Remarks</span></span>  
 <span data-ttu-id="b4706-108">Das Tool befindet sich an folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="b4706-108">The tool can be found in the following location:</span></span>  
  
 <span data-ttu-id="b4706-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b4706-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span></span>\  
  
> [!NOTE]
> <span data-ttu-id="b4706-110">Wenn das ServiceModel-Registrierungstool unter Windows Vista ausgeführt wird, spiegelt das Dialogfeld **Windows-Features** möglicherweise nicht wider, dass die **HTTP-Aktivierungsoption** von Windows Communication Foundation unter **Microsoft .NET Framework 3.0** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b4706-110">When the ServiceModel Registration Tool is run on Windows Vista, the **Windows Features** dialog may not reflect that the **Windows Communication Foundation HTTP Activation** option under **Microsoft .NET Framework 3.0** is turned on.</span></span> <span data-ttu-id="b4706-111">Auf das Dialogfeld **Windows-Features** kann zugegriffen werden, indem Sie auf **Start**klicken, dann auf **Ausführen** klicken und dann **OptionalFeatures**eingeben.</span><span class="sxs-lookup"><span data-stu-id="b4706-111">The **Windows Features** dialog can be accessed by clicking **Start**, then click **Run** and then typing **OptionalFeatures**.</span></span>  
  
 <span data-ttu-id="b4706-112">Die folgenden Tabellen beschreiben die Optionen, die mit ServiceModelReg.exe verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b4706-112">The following tables describe the options that can be used with ServiceModelReg.exe.</span></span>  
  
|<span data-ttu-id="b4706-113">Option</span><span class="sxs-lookup"><span data-stu-id="b4706-113">Option</span></span>|<span data-ttu-id="b4706-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4706-114">Description</span></span>|  
|------------|-----------------|  
|`-ia`|<span data-ttu-id="b4706-115">Installiert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b4706-115">Installs all WCF and WF components.</span></span>|  
|`-ua`|<span data-ttu-id="b4706-116">Deinstalliert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b4706-116">Uninstalls all WCF and WF components.</span></span>|  
|`-r`|<span data-ttu-id="b4706-117">Repariert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b4706-117">Repairs all WCF and WF components.</span></span>|  
|`-i`|<span data-ttu-id="b4706-118">Installiert mit -c angegebene WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b4706-118">Installs WCF and WF components specified with –c.</span></span>|  
|`-u`|<span data-ttu-id="b4706-119">Deinstalliert mit -c angegebene WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b4706-119">Uninstalls WCF and WF components specified with –c.</span></span>|  
|`-c`|<span data-ttu-id="b4706-120">Installiert oder deinstalliert eine Komponente:</span><span class="sxs-lookup"><span data-stu-id="b4706-120">Installs or uninstalls a component:</span></span><br /><br /> <span data-ttu-id="b4706-121">- httpnamespace – HTTP-Namespace-Reservierung</span><span class="sxs-lookup"><span data-stu-id="b4706-121">-   httpnamespace – HTTP Namespace Reservation</span></span><br /><span data-ttu-id="b4706-122">- tcpportsharing – TCP-Port-Sharing-Dienst</span><span class="sxs-lookup"><span data-stu-id="b4706-122">-   tcpportsharing – TCP port sharing service</span></span><br /><span data-ttu-id="b4706-123">- tcpactivation – TCP-Aktivierungsdienst (nicht unterstützt auf .NET 4 Client Profil)</span><span class="sxs-lookup"><span data-stu-id="b4706-123">-   tcpactivation – TCP activation service (unsupported on .NET 4 Client Profile)</span></span><br /><span data-ttu-id="b4706-124">- namedpipeactivation – Named Pipe-Aktivierungsdienst (nicht unterstützt im .NET 4-Clientprofil</span><span class="sxs-lookup"><span data-stu-id="b4706-124">-   namedpipeactivation – Named pipe activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="b4706-125">- msmqactivation – MSMQ-Aktivierungsdienst (nicht unterstützt im .NET 4-Clientprofil</span><span class="sxs-lookup"><span data-stu-id="b4706-125">-   msmqactivation – MSMQ activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="b4706-126">- etw – ETW-Ereignisablaufverfolgungsmanifeste (Windows Vista oder höher)</span><span class="sxs-lookup"><span data-stu-id="b4706-126">-   etw – ETW event tracing manifests (Windows Vista or later)</span></span>|  
|`-q`|<span data-ttu-id="b4706-127">Stiller Modus (nur Protokollierung von Anzeigefehlern)</span><span class="sxs-lookup"><span data-stu-id="b4706-127">Quiet mode (only display error logging)</span></span>|  
|`-v`|<span data-ttu-id="b4706-128">Ausführlicher Modus.</span><span class="sxs-lookup"><span data-stu-id="b4706-128">Verbose mode.</span></span>|  
|`-nologo`|<span data-ttu-id="b4706-129">Die Copyright- und Bannermeldung werden unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="b4706-129">Suppresses the copyright and banner message.</span></span>|  
|`-?`|<span data-ttu-id="b4706-130">Zeigt Hilfetext an.</span><span class="sxs-lookup"><span data-stu-id="b4706-130">Displays help text</span></span>|  
  
## <a name="fixing-the-fileloadexception-error"></a><span data-ttu-id="b4706-131">Beheben des FileLoadException-Fehlers</span><span class="sxs-lookup"><span data-stu-id="b4706-131">Fixing the FileLoadException Error</span></span>  
 <span data-ttu-id="b4706-132">Wenn Sie frühere Versionen von WCF auf Ihrem `FileLoadFoundException` Computer installiert haben, wird möglicherweise eine Fehlermeldung angezeigt, wenn Sie das ServiceModelReg-Tool ausführen, um eine neue Installation zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="b4706-132">If you installed previous versions of WCF on your machine, you may get a `FileLoadFoundException` error when you run the ServiceModelReg tool to register a new installation.</span></span> <span data-ttu-id="b4706-133">Dies kann auch auftreten, wenn Sie Dateien von der vorherigen Installation manuell entfernt haben, aber die machine.config-Einstellungen unverändert gelassen haben.</span><span class="sxs-lookup"><span data-stu-id="b4706-133">This can happen even if you have manually removed files from the previous install, but left the machine.config settings intact.</span></span>  
  
 <span data-ttu-id="b4706-134">Die Fehlermeldung lautet ungefähr folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="b4706-134">The error message is similar to the following.</span></span>  
  
```console  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 <span data-ttu-id="b4706-135">Die Meldung sollte angeben, dass die System.ServiceModel Version&#160;2.0.0.0-Assembly mit einem frühen CTP (Customer Technology Preview)-Release installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b4706-135">You should note from the error message that the System.ServiceModel Version 2.0.0.0 assembly was installed by an early Customer Technology Preview (CTP) release.</span></span> <span data-ttu-id="b4706-136">Die aktuelle Version der System.ServiceModel-Assembly lautet jedoch 3.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="b4706-136">The current version of the System.ServiceModel assembly released is 3.0.0.0 instead.</span></span> <span data-ttu-id="b4706-137">Daher tritt dieses Problem auf, wenn Sie die offizielle WCF-Version auf einem Computer installieren möchten, auf dem eine frühe CTP-Version von WCF installiert, aber nicht vollständig deinstalliert wurde.</span><span class="sxs-lookup"><span data-stu-id="b4706-137">Therefore, this issue is encountered when you want to install the official WCF release on a machine where an early CTP release of WCF was installed, but not completely uninstalled.</span></span>  
  
 <span data-ttu-id="b4706-138">ServiceModelReg.exe kann keine vorherigen Versionseinträge bereinigen und die Einträge der neuen Version nicht registrieren.</span><span class="sxs-lookup"><span data-stu-id="b4706-138">ServiceModelReg.exe cannot clean up prior version entries, nor can it register the new version's entries.</span></span> <span data-ttu-id="b4706-139">Die einzige Problemumgehung besteht darin, machine.config manuell zu bearbeiten. Sie können diese Datei an folgendem Speicherort finden.</span><span class="sxs-lookup"><span data-stu-id="b4706-139">The only workaround is to manually edit machine.config. You can locate this file at the following location.</span></span>  
  
```console  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config
```  
  
 <span data-ttu-id="b4706-140">Wenn Sie WCF auf einem 64-Bit-Computer ausführen, sollten Sie dieselbe Datei auch an diesem Speicherort bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b4706-140">If you are running WCF on a 64-bit machine, you should also edit the same file at this location.</span></span>  
  
```console  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config
```  
  
 <span data-ttu-id="b4706-141">Suchen Sie alle XML-Knoten in dieser Datei, die auf "System.ServiceModel, Version=2.0.0.0" verweisen, löschen Sie sie und alle untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="b4706-141">Locate any XML nodes in this file that refer to "System.ServiceModel, Version=2.0.0.0", delete them and any child nodes.</span></span> <span data-ttu-id="b4706-142">Speichern Sie die Datei, und führen Sie ServiceModelReg.exe erneut aus, um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b4706-142">Save the file and re-run ServiceModelReg.exe resolves this problem.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b4706-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b4706-143">Examples</span></span>  
 <span data-ttu-id="b4706-144">In den folgenden Beispielen wird gezeigt, wie die häufigsten Optionen des Tools ServiceModelReg.exe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4706-144">The following examples show how to use the most common options of the ServiceModelReg.exe tool.</span></span>  
  
```console  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
