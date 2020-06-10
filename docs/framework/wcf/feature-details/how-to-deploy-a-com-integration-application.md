---
title: 'Vorgehensweise: Bereitstellung einer COM+-Integrationsanwendung'
ms.date: 03/30/2017
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
ms.openlocfilehash: b4ae7f730296d54debc1cf2971b61e5700503430
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595426"
---
# <a name="how-to-deploy-a-com-integration-application"></a><span data-ttu-id="99314-102">Vorgehensweise: Bereitstellung einer COM+-Integrationsanwendung</span><span class="sxs-lookup"><span data-stu-id="99314-102">How to: Deploy a COM+ Integration Application</span></span>
<span data-ttu-id="99314-103">Sobald Sie eine COM+-Integrationsanwendung geschrieben haben, möchten Sie diese auf einem anderen Computer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="99314-103">Once you have written a COM+ integration application, you may want to deploy it on another machine.</span></span> <span data-ttu-id="99314-104">In diesem Thema wird beschrieben, wie eine COM+-Integrationsanwendung von einem Computer auf einen anderen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="99314-104">This topic describes how to move a COM+ integration application from one machine to another.</span></span>  
  
### <a name="moving-a-com-hosted-integration-app"></a><span data-ttu-id="99314-105">Verschieben einer COM+-gehosteten Integrationsanwendung</span><span class="sxs-lookup"><span data-stu-id="99314-105">Moving a COM+ hosted Integration App</span></span>  
  
1. <span data-ttu-id="99314-106">Stellen Sie sicher, dass auf beiden Computern WCF installiert ist.</span><span class="sxs-lookup"><span data-stu-id="99314-106">Ensure that WCF is installed on both machines.</span></span>  
  
2. <span data-ttu-id="99314-107">Exportieren Sie die Anwendung von Computer A.</span><span class="sxs-lookup"><span data-stu-id="99314-107">Export the application from machine A.</span></span>  
  
3. <span data-ttu-id="99314-108">Importieren Sie die Anwendung auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="99314-108">Import the application on machine B.</span></span>  
  
4. <span data-ttu-id="99314-109">Richten Sie das Stammverzeichnis der Anwendung ein.</span><span class="sxs-lookup"><span data-stu-id="99314-109">Set the Application Root Directory.</span></span> <span data-ttu-id="99314-110">Gemäß der Konventionen ist dies %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span><span class="sxs-lookup"><span data-stu-id="99314-110">By convention, this is %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span></span>  
  
5. <span data-ttu-id="99314-111">Kopieren Sie die Dateien Application.config und Application.manifest aus dem Stammverzeichnis der Anwendung auf dem Computer A in das Stammverzeichnis der Anwendung auf dem Computer B.</span><span class="sxs-lookup"><span data-stu-id="99314-111">Copy the Application.config and Application.manifest files from the application root directory on machine A to the application root directory on machine B.</span></span>  
  
6. <span data-ttu-id="99314-112">Bearbeiten Sie die Adressen der Dienstendpunkte in der Datei Application.config auf Computer B, um den entsprechenden Computer zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="99314-112">Edit the service endpoint addresses in the Application.config file on machine B to identify the appropriate machine.</span></span> <span data-ttu-id="99314-113">Ändern Sie beispielsweise `http://machineA/MyService` in `http://machineB/MyService`.</span><span class="sxs-lookup"><span data-stu-id="99314-113">For example, change `http://machineA/MyService` to `http://machineB/MyService`.</span></span>  
  
### <a name="moving-a-web-hosted-integration-application"></a><span data-ttu-id="99314-114">Verschieben einer im Internet gehosteten Integrationsanwendung</span><span class="sxs-lookup"><span data-stu-id="99314-114">Moving a Web-hosted integration application</span></span>  
  
1. <span data-ttu-id="99314-115">Stellen Sie sicher, dass auf beiden Computern WCF installiert ist.</span><span class="sxs-lookup"><span data-stu-id="99314-115">Ensure that WCF is installed on both machines.</span></span>  
  
2. <span data-ttu-id="99314-116">Exportieren Sie die Anwendung von Computer A.</span><span class="sxs-lookup"><span data-stu-id="99314-116">Export the application from machine A.</span></span>  
  
3. <span data-ttu-id="99314-117">Importieren Sie die Anwendung auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="99314-117">Import the application on machine B.</span></span>  
  
4. <span data-ttu-id="99314-118">Erstellen Sie einen IIS-vroot auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="99314-118">Create an IIS vroot on machine B.</span></span>  
  
5. <span data-ttu-id="99314-119">Kopieren Sie die .svc-Datei (Komponentenname.svc) und die Datei Web.config vom vroot auf dem Computer A in das neu erstellte vroot auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="99314-119">Copy the .svc file (componentName.svc) and the Web.config file from the vroot on machine A to the newly created vroot on machine B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99314-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99314-120">See also</span></span>

- [<span data-ttu-id="99314-121">Übersicht über die Integration von com+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="99314-121">Integrating with COM+ Applications Overview</span></span>](integrating-with-com-plus-applications-overview.md)
- [<span data-ttu-id="99314-122">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="99314-122">How to: Configure COM+ Service Settings</span></span>](how-to-configure-com-service-settings.md)
- [<span data-ttu-id="99314-123">Vorgehensweise: Verwenden des COM+-Dienstmodell-Konfigurationstools</span><span class="sxs-lookup"><span data-stu-id="99314-123">How to: Use the COM+ Service Model Configuration Tool</span></span>](how-to-use-the-com-service-model-configuration-tool.md)
