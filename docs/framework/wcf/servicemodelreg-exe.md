---
title: ServiceModel Registration-Tool (ServiceModelReg.exe)
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: 5fab1a356cd035ed006bfe90d713e179907e0137
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a><span data-ttu-id="02ef6-102">ServiceModel Registration-Tool (ServiceModelReg.exe)</span><span class="sxs-lookup"><span data-stu-id="02ef6-102">ServiceModel Registration Tool (ServiceModelReg.exe)</span></span>
<span data-ttu-id="02ef6-103">Dieses Befehlszeilentool bietet die Möglichkeit, die Registrierung von WCF- und WF-Komponenten auf einem einzelnen Computer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="02ef6-103">This command-line tool provides the ability to manage the registration of WCF and WF components on a single machine.</span></span> <span data-ttu-id="02ef6-104">Unter normalen Umständen müssen Sie dieses Tool nicht verwenden, da WCF- und WF-Komponenten bei der Installation konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="02ef6-104">Under normal circumstances you should not need to use this tool as WCF and WF components are configured when installed.</span></span> <span data-ttu-id="02ef6-105">Wenn jedoch bei der Dienstaktivierung Probleme auftreten, können Sie versuchen, die Komponenten mithilfe dieses Tools zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="02ef6-105">But if you are experiencing problems with service activation, you can try to register the components using this tool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ef6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="02ef6-106">Syntax</span></span>  
  
```  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a><span data-ttu-id="02ef6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02ef6-107">Remarks</span></span>  
 <span data-ttu-id="02ef6-108">Das Tool befindet sich an folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="02ef6-108">The tool can be found in the following location:</span></span>  
  
 <span data-ttu-id="02ef6-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span><span class="sxs-lookup"><span data-stu-id="02ef6-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02ef6-110">Wenn die ServiceModel-Registrierungstool ausgeführt wird, auf [!INCLUDE[wv](../../../includes/wv-md.md)], **Windows-Features** Dialogfeld möglicherweise nicht berücksichtigen, die die **Windows Communication Foundation-HTTP-Aktivierung** Option "unter" **Microsoft .NET Framework 3.0** eingeschaltet ist.</span><span class="sxs-lookup"><span data-stu-id="02ef6-110">When the ServiceModel Registration Tool is run on [!INCLUDE[wv](../../../includes/wv-md.md)], the **Windows Features** dialog may not reflect that the **Windows Communication Foundation HTTP Activation** option under **Microsoft .NET Framework 3.0** is turned on.</span></span> <span data-ttu-id="02ef6-111">Die **Windows-Features** Dialogfeld zugegriffen werden kann, indem Sie auf **starten**, klicken Sie dann auf **ausführen** und geben dann **OptionalFeatures**.</span><span class="sxs-lookup"><span data-stu-id="02ef6-111">The **Windows Features** dialog can be accessed by clicking **Start**, then click **Run** and then typing **OptionalFeatures**.</span></span>  
  
 <span data-ttu-id="02ef6-112">Die folgenden Tabellen beschreiben die Optionen, die mit ServiceModelReg.exe verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="02ef6-112">The following tables describe the options that can be used with ServiceModelReg.exe.</span></span>  
  
|<span data-ttu-id="02ef6-113">Option</span><span class="sxs-lookup"><span data-stu-id="02ef6-113">Option</span></span>|<span data-ttu-id="02ef6-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02ef6-114">Description</span></span>|  
|------------|-----------------|  
|`-ia`|<span data-ttu-id="02ef6-115">Installiert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="02ef6-115">Installs all WCF and WF components.</span></span>|  
|`-ua`|<span data-ttu-id="02ef6-116">Deinstalliert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="02ef6-116">Uninstalls all WCF and WF components.</span></span>|  
|`-r`|<span data-ttu-id="02ef6-117">Repariert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="02ef6-117">Repairs all WCF and WF components.</span></span>|  
|`-i`|<span data-ttu-id="02ef6-118">Installiert mit -c angegebene WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="02ef6-118">Installs WCF and WF components specified with –c.</span></span>|  
|`-u`|<span data-ttu-id="02ef6-119">Deinstalliert mit -c angegebene WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="02ef6-119">Uninstalls WCF and WF components specified with –c.</span></span>|  
|`-c`|<span data-ttu-id="02ef6-120">Installiert oder deinstalliert eine Komponente:</span><span class="sxs-lookup"><span data-stu-id="02ef6-120">Installs or uninstalls a component:</span></span><br /><br /> <span data-ttu-id="02ef6-121">-Httpnamespace – HTTP-Namespace Reservierung</span><span class="sxs-lookup"><span data-stu-id="02ef6-121">-   httpnamespace – HTTP Namespace Reservation</span></span><br /><span data-ttu-id="02ef6-122">-Tcpportsharing – TCP-Portfreigabedienst</span><span class="sxs-lookup"><span data-stu-id="02ef6-122">-   tcpportsharing – TCP port sharing service</span></span><br /><span data-ttu-id="02ef6-123">-Tcpactivation – TCP-Aktivierungsdienst (die auf .NET 4 Client Profile nicht unterstützt)</span><span class="sxs-lookup"><span data-stu-id="02ef6-123">-   tcpactivation – TCP activation service (unsupported on .NET 4 Client Profile)</span></span><br /><span data-ttu-id="02ef6-124">-Namedpipeactivation – Named Pipe Activation Service (nicht auf .NET 4-Clientprofil unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02ef6-124">-   namedpipeactivation – Named pipe activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="02ef6-125">-der Msmqactivation – MSMQ-Aktivierungsdienst (nicht auf .NET 4-Clientprofil unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02ef6-125">-   msmqactivation – MSMQ activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="02ef6-126">-Etw-ETW-Ablaufverfolgung ereignismanifesten (Windows Vista oder höher)</span><span class="sxs-lookup"><span data-stu-id="02ef6-126">-   etw – ETW event tracing manifests (Windows Vista or later)</span></span>|  
|`-q`|<span data-ttu-id="02ef6-127">Stiller Modus (nur Protokollierung von Anzeigefehlern)</span><span class="sxs-lookup"><span data-stu-id="02ef6-127">Quiet mode (only display error logging)</span></span>|  
|`-v`|<span data-ttu-id="02ef6-128">Ausführlicher Modus.</span><span class="sxs-lookup"><span data-stu-id="02ef6-128">Verbose mode.</span></span>|  
|`-nologo`|<span data-ttu-id="02ef6-129">Die Copyright- und Bannermeldung werden unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="02ef6-129">Suppresses the copyright and banner message.</span></span>|  
|`-?`|<span data-ttu-id="02ef6-130">Zeigt Hilfetext an.</span><span class="sxs-lookup"><span data-stu-id="02ef6-130">Displays help text</span></span>|  
  
## <a name="fixing-the-fileloadexception-error"></a><span data-ttu-id="02ef6-131">Beheben des FileLoadException-Fehlers</span><span class="sxs-lookup"><span data-stu-id="02ef6-131">Fixing the FileLoadException Error</span></span>  
 <span data-ttu-id="02ef6-132">Wenn Sie frühere Versionen von WCF auf dem Computer installiert haben, erhalten Sie eventuell eine `FileLoadFoundException` Fehler, wenn Sie das ServiceModelReg-Tool zum Registrieren einer neuen Installations ausführen.</span><span class="sxs-lookup"><span data-stu-id="02ef6-132">If you installed previous versions of WCF on your machine, you may get a `FileLoadFoundException` error when you run the ServiceModelReg tool to register a new installation.</span></span> <span data-ttu-id="02ef6-133">Dies kann auch auftreten, wenn Sie Dateien von der vorherigen Installation manuell entfernt haben, aber die machine.config-Einstellungen unverändert gelassen haben.</span><span class="sxs-lookup"><span data-stu-id="02ef6-133">This can happen even if you have manually removed files from the previous install, but left the machine.config settings intact.</span></span>  
  
 <span data-ttu-id="02ef6-134">Die Fehlermeldung lautet ungefähr folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="02ef6-134">The error message is similar to the following.</span></span>  
  
```  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 <span data-ttu-id="02ef6-135">Die Meldung sollte angeben, dass die System.ServiceModel Version&#160;2.0.0.0-Assembly mit einer frühen CTP (Customer Technology Preview)-Version installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="02ef6-135">You should note from the error message that the System.ServiceModel Version 2.0.0.0 assembly was installed by an early Customer Technology Preview (CTP) release.</span></span> <span data-ttu-id="02ef6-136">Die aktuelle Version der System.ServiceModel-Assembly lautet jedoch 3.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="02ef6-136">The current version of the System.ServiceModel assembly released is 3.0.0.0 instead.</span></span> <span data-ttu-id="02ef6-137">Daher wird dieses Problem gefunden, wenn Sie möchten, die offizielle WCF-Version auf einem Computer installieren, denen eine frühe CTP-Version von WCF installiert, jedoch nicht vollständig deinstalliert wurde.</span><span class="sxs-lookup"><span data-stu-id="02ef6-137">Therefore, this issue is encountered when you want to install the official WCF release on a machine where an early CTP release of WCF was installed, but not completely uninstalled.</span></span>  
  
 <span data-ttu-id="02ef6-138">ServiceModelReg.exe kann keine vorherigen Versionseinträge bereinigen und die Einträge der neuen Version nicht registrieren.</span><span class="sxs-lookup"><span data-stu-id="02ef6-138">ServiceModelReg.exe cannot clean up prior version entries, nor can it register the new version's entries.</span></span> <span data-ttu-id="02ef6-139">Die einzige Problemumgehung ist die manuelle Bearbeitung von machine.config. Sie finden diese Datei am folgenden Speicherort.</span><span class="sxs-lookup"><span data-stu-id="02ef6-139">The only workaround is to manually edit machine.config. You can locate this file at the following location.</span></span>  
  
```  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config   
```  
  
 <span data-ttu-id="02ef6-140">Wenn Sie WCF auf einem 64-Bit-Computer ausführen, sollten Sie auch die gleiche Datei an diesem Speicherort bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="02ef6-140">If you are running WCF on a 64-bit machine, you should also edit the same file at this location.</span></span>  
  
```  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config   
```  
  
 <span data-ttu-id="02ef6-141">Suchen Sie die XML-Knoten in dieser Datei, die auf verweisen "System.ServiceModel, Version = 2.0.0.0", löschen Sie diese und alle untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="02ef6-141">Locate any XML nodes in this file that refer to "System.ServiceModel, Version=2.0.0.0", delete them and any child nodes.</span></span> <span data-ttu-id="02ef6-142">Speichern Sie die Datei, und führen Sie ServiceModelReg.exe erneut aus, um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="02ef6-142">Save the file and re-run ServiceModelReg.exe resolves this problem.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="02ef6-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="02ef6-143">Examples</span></span>  
 <span data-ttu-id="02ef6-144">In den folgenden Beispielen wird gezeigt, wie die häufigsten Optionen des Tools ServiceModelReg.exe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02ef6-144">The following examples show how to use the most common options of the ServiceModelReg.exe tool.</span></span>  
  
```  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
