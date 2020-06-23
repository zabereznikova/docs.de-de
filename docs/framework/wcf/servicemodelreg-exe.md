---
title: ServiceModel Registration-Tool (ServiceModelReg.exe)
description: Verwenden Sie dieses Befehlszeilen Tool, um die Registrierung von WCF-und WF-Komponenten auf einem einzelnen Computer zu verwalten, wenn Probleme bei der Dienst Aktivierung auftreten.
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: 347b1b8071abe7d8eb7e16ffd879c1fdb9825bc7
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245894"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a><span data-ttu-id="b33fa-103">ServiceModel Registration-Tool (ServiceModelReg.exe)</span><span class="sxs-lookup"><span data-stu-id="b33fa-103">ServiceModel Registration Tool (ServiceModelReg.exe)</span></span>
<span data-ttu-id="b33fa-104">Dieses Befehlszeilentool bietet die Möglichkeit, die Registrierung von WCF- und WF-Komponenten auf einem einzelnen Computer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b33fa-104">This command-line tool provides the ability to manage the registration of WCF and WF components on a single machine.</span></span> <span data-ttu-id="b33fa-105">Unter normalen Umständen müssen Sie dieses Tool nicht verwenden, da WCF- und WF-Komponenten bei der Installation konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b33fa-105">Under normal circumstances you should not need to use this tool as WCF and WF components are configured when installed.</span></span> <span data-ttu-id="b33fa-106">Wenn jedoch bei der Dienstaktivierung Probleme auftreten, können Sie versuchen, die Komponenten mithilfe dieses Tools zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="b33fa-106">But if you are experiencing problems with service activation, you can try to register the components using this tool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b33fa-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b33fa-107">Syntax</span></span>  
  
```console  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a><span data-ttu-id="b33fa-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b33fa-108">Remarks</span></span>  
 <span data-ttu-id="b33fa-109">Das Tool befindet sich an folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="b33fa-109">The tool can be found in the following location:</span></span>  
  
 <span data-ttu-id="b33fa-110">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b33fa-110">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span></span>\  
  
> [!NOTE]
> <span data-ttu-id="b33fa-111">Wenn das Service Model-Registrierungs Tool unter Windows Vista ausgeführt wird, zeigt das Dialogfeld **Windows-Features** möglicherweise nicht an, dass die **Windows Communication Foundation http-Aktivierungs** Option unter **Microsoft .NET Framework 3,0** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b33fa-111">When the ServiceModel Registration Tool is run on Windows Vista, the **Windows Features** dialog may not reflect that the **Windows Communication Foundation HTTP Activation** option under **Microsoft .NET Framework 3.0** is turned on.</span></span> <span data-ttu-id="b33fa-112">Sie können auf das Dialogfeld " **Windows-Features** " zugreifen, indem Sie auf **Start**und dann auf **Ausführen** klicken und dann **OptionalFeatures**eingeben.</span><span class="sxs-lookup"><span data-stu-id="b33fa-112">The **Windows Features** dialog can be accessed by clicking **Start**, then click **Run** and then typing **OptionalFeatures**.</span></span>  
  
 <span data-ttu-id="b33fa-113">Die folgenden Tabellen beschreiben die Optionen, die mit ServiceModelReg.exe verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b33fa-113">The following tables describe the options that can be used with ServiceModelReg.exe.</span></span>  
  
|<span data-ttu-id="b33fa-114">Option</span><span class="sxs-lookup"><span data-stu-id="b33fa-114">Option</span></span>|<span data-ttu-id="b33fa-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b33fa-115">Description</span></span>|  
|------------|-----------------|  
|`-ia`|<span data-ttu-id="b33fa-116">Installiert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b33fa-116">Installs all WCF and WF components.</span></span>|  
|`-ua`|<span data-ttu-id="b33fa-117">Deinstalliert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b33fa-117">Uninstalls all WCF and WF components.</span></span>|  
|`-r`|<span data-ttu-id="b33fa-118">Repariert alle WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b33fa-118">Repairs all WCF and WF components.</span></span>|  
|`-i`|<span data-ttu-id="b33fa-119">Installiert mit -c angegebene WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b33fa-119">Installs WCF and WF components specified with –c.</span></span>|  
|`-u`|<span data-ttu-id="b33fa-120">Deinstalliert mit -c angegebene WCF- und WF-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b33fa-120">Uninstalls WCF and WF components specified with –c.</span></span>|  
|`-c`|<span data-ttu-id="b33fa-121">Installiert oder deinstalliert eine Komponente:</span><span class="sxs-lookup"><span data-stu-id="b33fa-121">Installs or uninstalls a component:</span></span><br /><br /> <span data-ttu-id="b33fa-122">-httpnamespace – HTTP-Namespace Reservierung</span><span class="sxs-lookup"><span data-stu-id="b33fa-122">-   httpnamespace – HTTP Namespace Reservation</span></span><br /><span data-ttu-id="b33fa-123">-tcpportsharing – TCP-Port Freigabe Dienst</span><span class="sxs-lookup"><span data-stu-id="b33fa-123">-   tcpportsharing – TCP port sharing service</span></span><br /><span data-ttu-id="b33fa-124">-tcpactivations – TCP-Aktivierungs Dienst (für .NET 4 Client Profile nicht unterstützt)</span><span class="sxs-lookup"><span data-stu-id="b33fa-124">-   tcpactivation – TCP activation service (unsupported on .NET 4 Client Profile)</span></span><br /><span data-ttu-id="b33fa-125">-namedpipeactivations – Named Pipe-Aktivierungs Dienst (für .NET 4 Client Profile nicht unterstützt)</span><span class="sxs-lookup"><span data-stu-id="b33fa-125">-   namedpipeactivation – Named pipe activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="b33fa-126">-der MsmqActivation – MSMQ-Aktivierungs Dienst (für .NET 4 Client Profile nicht unterstützt)</span><span class="sxs-lookup"><span data-stu-id="b33fa-126">-   msmqactivation – MSMQ activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="b33fa-127">-etw – ETW-Ereignis Ablauf Verfolgungs Manifeste (Windows Vista oder höher)</span><span class="sxs-lookup"><span data-stu-id="b33fa-127">-   etw – ETW event tracing manifests (Windows Vista or later)</span></span>|  
|`-q`|<span data-ttu-id="b33fa-128">Stiller Modus (nur Protokollierung von Anzeigefehlern)</span><span class="sxs-lookup"><span data-stu-id="b33fa-128">Quiet mode (only display error logging)</span></span>|  
|`-v`|<span data-ttu-id="b33fa-129">Ausführlicher Modus.</span><span class="sxs-lookup"><span data-stu-id="b33fa-129">Verbose mode.</span></span>|  
|`-nologo`|<span data-ttu-id="b33fa-130">Die Copyright- und Bannermeldung werden unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="b33fa-130">Suppresses the copyright and banner message.</span></span>|  
|`-?`|<span data-ttu-id="b33fa-131">Zeigt Hilfetext an.</span><span class="sxs-lookup"><span data-stu-id="b33fa-131">Displays help text</span></span>|  
  
## <a name="fixing-the-fileloadexception-error"></a><span data-ttu-id="b33fa-132">Beheben des FileLoadException-Fehlers</span><span class="sxs-lookup"><span data-stu-id="b33fa-132">Fixing the FileLoadException Error</span></span>  
 <span data-ttu-id="b33fa-133">Wenn Sie frühere Versionen von WCF auf dem Computer installiert haben, erhalten Sie möglicherweise einen `FileLoadFoundException` Fehler, wenn Sie das Service Model reg-Tool ausführen, um eine neue Installation zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="b33fa-133">If you installed previous versions of WCF on your machine, you may get a `FileLoadFoundException` error when you run the ServiceModelReg tool to register a new installation.</span></span> <span data-ttu-id="b33fa-134">Dies kann auch auftreten, wenn Sie Dateien von der vorherigen Installation manuell entfernt haben, aber die machine.config-Einstellungen unverändert gelassen haben.</span><span class="sxs-lookup"><span data-stu-id="b33fa-134">This can happen even if you have manually removed files from the previous install, but left the machine.config settings intact.</span></span>  
  
 <span data-ttu-id="b33fa-135">Die Fehlermeldung lautet ungefähr folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="b33fa-135">The error message is similar to the following.</span></span>  
  
```console  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 <span data-ttu-id="b33fa-136">Die Meldung sollte angeben, dass die System.ServiceModel Version&#160;2.0.0.0-Assembly mit einem frühen CTP (Customer Technology Preview)-Release installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b33fa-136">You should note from the error message that the System.ServiceModel Version 2.0.0.0 assembly was installed by an early Customer Technology Preview (CTP) release.</span></span> <span data-ttu-id="b33fa-137">Die aktuelle Version der System.ServiceModel-Assembly lautet jedoch 3.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="b33fa-137">The current version of the System.ServiceModel assembly released is 3.0.0.0 instead.</span></span> <span data-ttu-id="b33fa-138">Dieses Problem ist daher aufgetreten, wenn Sie die offizielle WCF-Version auf einem Computer installieren möchten, auf dem eine frühe CTP-Version von WCF installiert, aber nicht vollständig deinstalliert wurde.</span><span class="sxs-lookup"><span data-stu-id="b33fa-138">Therefore, this issue is encountered when you want to install the official WCF release on a machine where an early CTP release of WCF was installed, but not completely uninstalled.</span></span>  
  
 <span data-ttu-id="b33fa-139">ServiceModelReg.exe kann keine vorherigen Versionseinträge bereinigen und die Einträge der neuen Version nicht registrieren.</span><span class="sxs-lookup"><span data-stu-id="b33fa-139">ServiceModelReg.exe cannot clean up prior version entries, nor can it register the new version's entries.</span></span> <span data-ttu-id="b33fa-140">Die einzige Problem Umgehung besteht darin, machine.config manuell zu bearbeiten. Sie finden diese Datei am folgenden Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b33fa-140">The only workaround is to manually edit machine.config. You can locate this file at the following location.</span></span>  
  
```console  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config
```  
  
 <span data-ttu-id="b33fa-141">Wenn Sie WCF auf einem 64-Bit-Computer ausführen, sollten Sie auch dieselbe Datei an diesem Speicherort bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b33fa-141">If you are running WCF on a 64-bit machine, you should also edit the same file at this location.</span></span>  
  
```console  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config
```  
  
 <span data-ttu-id="b33fa-142">Suchen Sie alle XML-Knoten in dieser Datei, die auf "System. Service Model, Version = 2.0.0.0" verweisen, löschen Sie Sie und alle untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="b33fa-142">Locate any XML nodes in this file that refer to "System.ServiceModel, Version=2.0.0.0", delete them and any child nodes.</span></span> <span data-ttu-id="b33fa-143">Speichern Sie die Datei, und führen Sie ServiceModelReg.exe erneut aus, um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b33fa-143">Save the file and re-run ServiceModelReg.exe resolves this problem.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b33fa-144">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b33fa-144">Examples</span></span>  
 <span data-ttu-id="b33fa-145">In den folgenden Beispielen wird gezeigt, wie die häufigsten Optionen des Tools ServiceModelReg.exe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b33fa-145">The following examples show how to use the most common options of the ServiceModelReg.exe tool.</span></span>  
  
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
