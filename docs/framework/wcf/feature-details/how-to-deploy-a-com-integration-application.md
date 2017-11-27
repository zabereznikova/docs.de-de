---
title: 'Vorgehensweise: Bereitstellung einer COM+-Integrationsanwendung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7d6d9103c2d36de81392858fedc249be9f7ae94f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-deploy-a-com-integration-application"></a><span data-ttu-id="b36f9-102">Vorgehensweise: Bereitstellung einer COM+-Integrationsanwendung</span><span class="sxs-lookup"><span data-stu-id="b36f9-102">How to: Deploy a COM+ Integration Application</span></span>
<span data-ttu-id="b36f9-103">Sobald Sie eine COM+-Integrationsanwendung geschrieben haben, möchten Sie diese auf einem anderen Computer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b36f9-103">Once you have written a COM+ integration application, you may want to deploy it on another machine.</span></span> <span data-ttu-id="b36f9-104">In diesem Thema wird beschrieben, wie eine COM+-Integrationsanwendung von einem Computer auf einen anderen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="b36f9-104">This topic describes how to move a COM+ integration application from one machine to another.</span></span>  
  
### <a name="moving-a-com-hosted-integration-app"></a><span data-ttu-id="b36f9-105">Verschieben einer COM+-gehosteten Integrationsanwendung</span><span class="sxs-lookup"><span data-stu-id="b36f9-105">Moving a COM+ hosted Integration App</span></span>  
  
1.  <span data-ttu-id="b36f9-106">Stellen Sie sicher, dass [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auf beiden Computern installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b36f9-106">Ensure that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is installed on both machines.</span></span>  
  
2.  <span data-ttu-id="b36f9-107">Exportieren Sie die Anwendung von Computer A.</span><span class="sxs-lookup"><span data-stu-id="b36f9-107">Export the application from machine A.</span></span>  
  
3.  <span data-ttu-id="b36f9-108">Importieren Sie die Anwendung auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="b36f9-108">Import the application on machine B.</span></span>  
  
4.  <span data-ttu-id="b36f9-109">Richten Sie das Stammverzeichnis der Anwendung ein.</span><span class="sxs-lookup"><span data-stu-id="b36f9-109">Set the Application Root Directory.</span></span> <span data-ttu-id="b36f9-110">Gemäß der Konventionen ist dies %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span><span class="sxs-lookup"><span data-stu-id="b36f9-110">By convention, this is %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span></span>  
  
5.  <span data-ttu-id="b36f9-111">Kopieren Sie die Dateien Application.config und Application.manifest aus dem Stammverzeichnis der Anwendung auf dem Computer A in das Stammverzeichnis der Anwendung auf dem Computer B.</span><span class="sxs-lookup"><span data-stu-id="b36f9-111">Copy the Application.config and Application.manifest files from the application root directory on machine A to the application root directory on machine B.</span></span>  
  
6.  <span data-ttu-id="b36f9-112">Bearbeiten Sie die Adressen der Dienstendpunkte in der Datei Application.config auf Computer B, um den entsprechenden Computer zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b36f9-112">Edit the service endpoint addresses in the Application.config file on machine B to identify the appropriate machine.</span></span> <span data-ttu-id="b36f9-113">Beispiel: Ändern Sie http://machineA/MyService in http://machineB/MyService.</span><span class="sxs-lookup"><span data-stu-id="b36f9-113">For example, change http://machineA/MyService to http://machineB/MyService.</span></span>  
  
### <a name="moving-a-web-hosted-integration-application"></a><span data-ttu-id="b36f9-114">Verschieben einer im Internet gehosteten Integrationsanwendung</span><span class="sxs-lookup"><span data-stu-id="b36f9-114">Moving a Web-hosted integration application</span></span>  
  
1.  <span data-ttu-id="b36f9-115">Stellen Sie sicher, dass [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auf beiden Computern installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b36f9-115">Ensure that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is installed on both machines.</span></span>  
  
2.  <span data-ttu-id="b36f9-116">Exportieren Sie die Anwendung von Computer A.</span><span class="sxs-lookup"><span data-stu-id="b36f9-116">Export the application from machine A.</span></span>  
  
3.  <span data-ttu-id="b36f9-117">Importieren Sie die Anwendung auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="b36f9-117">Import the application on machine B.</span></span>  
  
4.  <span data-ttu-id="b36f9-118">Erstellen Sie einen IIS-vroot auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="b36f9-118">Create an IIS vroot on machine B.</span></span>  
  
5.  <span data-ttu-id="b36f9-119">Kopieren Sie die .svc-Datei (Komponentenname.svc) und die Datei Web.config vom vroot auf dem Computer A in das neu erstellte vroot auf Computer B.</span><span class="sxs-lookup"><span data-stu-id="b36f9-119">Copy the .svc file (componentName.svc) and the Web.config file from the vroot on machine A to the newly created vroot on machine B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b36f9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b36f9-120">See Also</span></span>  
 [<span data-ttu-id="b36f9-121">Integrieren von COM+-Anwendungen (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="b36f9-121">Integrating with COM+ Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)  
 [<span data-ttu-id="b36f9-122">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="b36f9-122">How to: Configure COM+ Service Settings</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)  
 [<span data-ttu-id="b36f9-123">Vorgehensweise: Verwenden Sie das COM+ Service Model Configuration-Tool</span><span class="sxs-lookup"><span data-stu-id="b36f9-123">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
