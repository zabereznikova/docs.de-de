---
title: ServiceModel Registration-Tool (ServiceModelReg.exe)
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: 5fab1a356cd035ed006bfe90d713e179907e0137
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051779"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a><span data-ttu-id="9f4ef-102">ServiceModel Registration-Tool (ServiceModelReg.exe)</span><span class="sxs-lookup"><span data-stu-id="9f4ef-102">ServiceModel Registration Tool (ServiceModelReg.exe)</span></span>
<span data-ttu-id="9f4ef-103">Dieses Befehlszeilentool bietet die Möglichkeit, die Registrierung von WCF- und WF-Komponenten auf einem einzelnen Computer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-103">This command-line tool provides the ability to manage the registration of WCF and WF components on a single machine.</span></span> <span data-ttu-id="9f4ef-104">Unter normalen Umständen müssen Sie dieses Tool nicht verwenden, da WCF- und WF-Komponenten bei der Installation konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-104">Under normal circumstances you should not need to use this tool as WCF and WF components are configured when installed.</span></span> <span data-ttu-id="9f4ef-105">Wenn jedoch bei der Dienstaktivierung Probleme auftreten, können Sie versuchen, die Komponenten mithilfe dieses Tools zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-105">But if you are experiencing problems with service activation, you can try to register the components using this tool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f4ef-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f4ef-106">Syntax</span></span>  
  
```  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a><span data-ttu-id="9f4ef-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f4ef-107">Remarks</span></span>  
 <span data-ttu-id="9f4ef-108">Das Tool befindet sich an folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="9f4ef-108">The tool can be found in the following location:</span></span>  
  
 <span data-ttu-id="9f4ef-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span><span class="sxs-lookup"><span data-stu-id="9f4ef-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f4ef-110">Wenn die ServiceModel-Registrierungstool ausgeführt wird [!INCLUDE[wv](../../../includes/wv-md.md)], **Windows Features** Dialogfeld u. u. nicht wiedergegeben, die die **Windows Communication Foundation-HTTP-Aktivierung** Option **Microsoft .NET Framework 3.0** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-110">When the ServiceModel Registration Tool is run on [!INCLUDE[wv](../../../includes/wv-md.md)], the **Windows Features** dialog may not reflect that the **Windows Communication Foundation HTTP Activation** option under **Microsoft .NET Framework 3.0** is turned on.</span></span> <span data-ttu-id="9f4ef-111">Die **Windows Features** Dialogfeld zugegriffen werden kann, indem Sie auf **starten**, klicken Sie dann auf **ausführen** und geben dann **OptionalFeatures**.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-111">The **Windows Features** dialog can be accessed by clicking **Start**, then click **Run** and then typing **OptionalFeatures**.</span></span>  
  
 <span data-ttu-id="9f4ef-112">Die folgenden Tabellen beschreiben die Optionen, die mit ServiceModelReg.exe verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-112">The following tables describe the options that can be used with ServiceModelReg.exe.</span></span>  
  
|<span data-ttu-id="9f4ef-113">Option</span><span class="sxs-lookup"><span data-stu-id="9f4ef-113">Option</span></span>|<span data-ttu-id="9f4ef-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f4ef-114">Description</span></span>|  
|------------|-----------------|  
|`-ia`|<span data-ttu-id="9f4ef-115">Installiert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-115">Installs all WCF and WF components.</span></span>|  
|`-ua`|<span data-ttu-id="9f4ef-116">Deinstalliert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-116">Uninstalls all WCF and WF components.</span></span>|  
|`-r`|<span data-ttu-id="9f4ef-117">Repariert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-117">Repairs all WCF and WF components.</span></span>|  
|`-i`|<span data-ttu-id="9f4ef-118">Installiert mit -c angegebene WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-118">Installs WCF and WF components specified with –c.</span></span>|  
|`-u`|<span data-ttu-id="9f4ef-119">Deinstalliert mit -c angegebene WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-119">Uninstalls WCF and WF components specified with –c.</span></span>|  
|`-c`|<span data-ttu-id="9f4ef-120">Installiert oder deinstalliert eine Komponente:</span><span class="sxs-lookup"><span data-stu-id="9f4ef-120">Installs or uninstalls a component:</span></span><br /><br /> <span data-ttu-id="9f4ef-121">-Httpnamespace – HTTP-Namespace-Reservierung</span><span class="sxs-lookup"><span data-stu-id="9f4ef-121">-   httpnamespace – HTTP Namespace Reservation</span></span><br /><span data-ttu-id="9f4ef-122">-Tcpportsharing – TCP-Portfreigabedienst</span><span class="sxs-lookup"><span data-stu-id="9f4ef-122">-   tcpportsharing – TCP port sharing service</span></span><br /><span data-ttu-id="9f4ef-123">-Tcpactivation – TCP-Aktivierungsdienst (die für .NET 4 Client Profile nicht unterstützt)</span><span class="sxs-lookup"><span data-stu-id="9f4ef-123">-   tcpactivation – TCP activation service (unsupported on .NET 4 Client Profile)</span></span><br /><span data-ttu-id="9f4ef-124">-Namedpipeactivation – Named Pipe Activation Service (für .NET 4 Client Profile nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f4ef-124">-   namedpipeactivation – Named pipe activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="9f4ef-125">-der Msmqactivation – MSMQ-Aktivierungsdienst (für .NET 4 Client Profile nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f4ef-125">-   msmqactivation – MSMQ activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="9f4ef-126">-Etw-ETW-ereignisablaufverfolgungsmanifeste (Windows Vista oder höher)</span><span class="sxs-lookup"><span data-stu-id="9f4ef-126">-   etw – ETW event tracing manifests (Windows Vista or later)</span></span>|  
|`-q`|<span data-ttu-id="9f4ef-127">Stiller Modus (nur Protokollierung von Anzeigefehlern)</span><span class="sxs-lookup"><span data-stu-id="9f4ef-127">Quiet mode (only display error logging)</span></span>|  
|`-v`|<span data-ttu-id="9f4ef-128">Ausführlicher Modus.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-128">Verbose mode.</span></span>|  
|`-nologo`|<span data-ttu-id="9f4ef-129">Die Copyright- und Bannermeldung werden unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-129">Suppresses the copyright and banner message.</span></span>|  
|`-?`|<span data-ttu-id="9f4ef-130">Zeigt Hilfetext an.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-130">Displays help text</span></span>|  
  
## <a name="fixing-the-fileloadexception-error"></a><span data-ttu-id="9f4ef-131">Beheben des FileLoadException-Fehlers</span><span class="sxs-lookup"><span data-stu-id="9f4ef-131">Fixing the FileLoadException Error</span></span>  
 <span data-ttu-id="9f4ef-132">Wenn Sie frühere Versionen von WCF auf Ihrem Computer installiert haben, erhalten Sie eventuell eine `FileLoadFoundException` Fehler, wenn Sie das ServiceModelReg-Tool zum Registrieren einer neuen Installations ausführen.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-132">If you installed previous versions of WCF on your machine, you may get a `FileLoadFoundException` error when you run the ServiceModelReg tool to register a new installation.</span></span> <span data-ttu-id="9f4ef-133">Dies kann auch auftreten, wenn Sie Dateien von der vorherigen Installation manuell entfernt haben, aber die machine.config-Einstellungen unverändert gelassen haben.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-133">This can happen even if you have manually removed files from the previous install, but left the machine.config settings intact.</span></span>  
  
 <span data-ttu-id="9f4ef-134">Die Fehlermeldung lautet ungefähr folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="9f4ef-134">The error message is similar to the following.</span></span>  
  
```  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 <span data-ttu-id="9f4ef-135">Die Meldung sollte angeben, dass die System.ServiceModel Version&amp;#160;2.0.0.0-Assembly mit einem frühen CTP (Customer Technology Preview)-Release installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-135">You should note from the error message that the System.ServiceModel Version 2.0.0.0 assembly was installed by an early Customer Technology Preview (CTP) release.</span></span> <span data-ttu-id="9f4ef-136">Die aktuelle Version der System.ServiceModel-Assembly lautet jedoch 3.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-136">The current version of the System.ServiceModel assembly released is 3.0.0.0 instead.</span></span> <span data-ttu-id="9f4ef-137">Aus diesem Grund dieses Problem tritt auf, wenn Sie der offiziellen Veröffentlichung von WCF auf einem Computer zu installieren, in eine frühere CTP-Version von WCF installiert wurde, aber nicht vollständig deinstalliert wurde, möchten.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-137">Therefore, this issue is encountered when you want to install the official WCF release on a machine where an early CTP release of WCF was installed, but not completely uninstalled.</span></span>  
  
 <span data-ttu-id="9f4ef-138">ServiceModelReg.exe kann keine vorherigen Versionseinträge bereinigen und die Einträge der neuen Version nicht registrieren.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-138">ServiceModelReg.exe cannot clean up prior version entries, nor can it register the new version's entries.</span></span> <span data-ttu-id="9f4ef-139">Die einzige Problemumgehung ist die manuelle Bearbeitung von machine.config. Sie finden diese Datei am folgenden Speicherort.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-139">The only workaround is to manually edit machine.config. You can locate this file at the following location.</span></span>  
  
```  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config   
```  
  
 <span data-ttu-id="9f4ef-140">Wenn Sie WCF auf einem 64-Bit-Computer ausführen, sollten Sie auch die gleiche Datei an diesem Speicherort bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-140">If you are running WCF on a 64-bit machine, you should also edit the same file at this location.</span></span>  
  
```  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config   
```  
  
 <span data-ttu-id="9f4ef-141">Suchen von XML-Knoten in dieser Datei, die auf "System.ServiceModel, Version = 2.0.0.0", löschen Sie diese und alle untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-141">Locate any XML nodes in this file that refer to "System.ServiceModel, Version=2.0.0.0", delete them and any child nodes.</span></span> <span data-ttu-id="9f4ef-142">Speichern Sie die Datei, und führen Sie ServiceModelReg.exe erneut aus, um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-142">Save the file and re-run ServiceModelReg.exe resolves this problem.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9f4ef-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9f4ef-143">Examples</span></span>  
 <span data-ttu-id="9f4ef-144">In den folgenden Beispielen wird gezeigt, wie die häufigsten Optionen des Tools ServiceModelReg.exe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f4ef-144">The following examples show how to use the most common options of the ServiceModelReg.exe tool.</span></span>  
  
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
