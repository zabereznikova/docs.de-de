---
title: 'Vorgehensweise: Bereitstellung einer COM+-Integrationsanwendung'
ms.date: 03/30/2017
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
ms.openlocfilehash: 872d0f0c84c1ac0ea96a87ed24a386bb9bedcf85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490138"
---
# <a name="how-to-deploy-a-com-integration-application"></a><span data-ttu-id="d15c3-102">Vorgehensweise: Bereitstellung einer COM+-Integrationsanwendung</span><span class="sxs-lookup"><span data-stu-id="d15c3-102">How to: Deploy a COM+ Integration Application</span></span>
<span data-ttu-id="d15c3-103">Sobald Sie eine COM+-Integrationsanwendung geschrieben haben, möchten Sie diese auf einem anderen Computer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d15c3-103">Once you have written a COM+ integration application, you may want to deploy it on another machine.</span></span> <span data-ttu-id="d15c3-104">In diesem Thema wird beschrieben, wie eine COM+-Integrationsanwendung von einem Computer auf einen anderen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="d15c3-104">This topic describes how to move a COM+ integration application from one machine to another.</span></span>  
  
### <a name="moving-a-com-hosted-integration-app"></a><span data-ttu-id="d15c3-105">Verschieben einer COM+-gehosteten Integrationsanwendung</span><span class="sxs-lookup"><span data-stu-id="d15c3-105">Moving a COM+ hosted Integration App</span></span>  
  
1.  <span data-ttu-id="d15c3-106">Stellen Sie sicher, dass WCF auf beiden Computern installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d15c3-106">Ensure that WCF is installed on both machines.</span></span>  
  
2.  <span data-ttu-id="d15c3-107">Exportieren Sie die Anwendung von Computer A.</span><span class="sxs-lookup"><span data-stu-id="d15c3-107">Export the application from machine A.</span></span>  
  
3.  <span data-ttu-id="d15c3-108">Importieren Sie die Anwendung auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="d15c3-108">Import the application on machine B.</span></span>  
  
4.  <span data-ttu-id="d15c3-109">Richten Sie das Stammverzeichnis der Anwendung ein.</span><span class="sxs-lookup"><span data-stu-id="d15c3-109">Set the Application Root Directory.</span></span> <span data-ttu-id="d15c3-110">Gemäß der Konventionen ist dies %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span><span class="sxs-lookup"><span data-stu-id="d15c3-110">By convention, this is %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span></span>  
  
5.  <span data-ttu-id="d15c3-111">Kopieren Sie die Dateien Application.config und Application.manifest aus dem Stammverzeichnis der Anwendung auf dem Computer A in das Stammverzeichnis der Anwendung auf dem Computer B.</span><span class="sxs-lookup"><span data-stu-id="d15c3-111">Copy the Application.config and Application.manifest files from the application root directory on machine A to the application root directory on machine B.</span></span>  
  
6.  <span data-ttu-id="d15c3-112">Bearbeiten Sie die Adressen der Dienstendpunkte in der Datei Application.config auf Computer B, um den entsprechenden Computer zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d15c3-112">Edit the service endpoint addresses in the Application.config file on machine B to identify the appropriate machine.</span></span> <span data-ttu-id="d15c3-113">Ändern Sie beispielsweise http://machineA/MyService zu http://machineB/MyService.</span><span class="sxs-lookup"><span data-stu-id="d15c3-113">For example, change http://machineA/MyService to http://machineB/MyService.</span></span>  
  
### <a name="moving-a-web-hosted-integration-application"></a><span data-ttu-id="d15c3-114">Verschieben einer im Internet gehosteten Integrationsanwendung</span><span class="sxs-lookup"><span data-stu-id="d15c3-114">Moving a Web-hosted integration application</span></span>  
  
1.  <span data-ttu-id="d15c3-115">Stellen Sie sicher, dass WCF auf beiden Computern installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d15c3-115">Ensure that WCF is installed on both machines.</span></span>  
  
2.  <span data-ttu-id="d15c3-116">Exportieren Sie die Anwendung von Computer A.</span><span class="sxs-lookup"><span data-stu-id="d15c3-116">Export the application from machine A.</span></span>  
  
3.  <span data-ttu-id="d15c3-117">Importieren Sie die Anwendung auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="d15c3-117">Import the application on machine B.</span></span>  
  
4.  <span data-ttu-id="d15c3-118">Erstellen Sie einen IIS-vroot auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="d15c3-118">Create an IIS vroot on machine B.</span></span>  
  
5.  <span data-ttu-id="d15c3-119">Kopieren Sie die .svc-Datei (Komponentenname.svc) und die Datei Web.config vom vroot auf dem Computer A in das neu erstellte vroot auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="d15c3-119">Copy the .svc file (componentName.svc) and the Web.config file from the vroot on machine A to the newly created vroot on machine B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d15c3-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d15c3-120">See Also</span></span>  
 [<span data-ttu-id="d15c3-121">Übersicht über die Integration von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d15c3-121">Integrating with COM+ Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)  
 [<span data-ttu-id="d15c3-122">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="d15c3-122">How to: Configure COM+ Service Settings</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)  
 [<span data-ttu-id="d15c3-123">Vorgehensweise: Verwenden des COM+-Dienstmodell-Konfigurationstools</span><span class="sxs-lookup"><span data-stu-id="d15c3-123">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
