---
title: "Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 88fc7658af3d82a21931b697e3a66a15b32be16b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="8758b-102">Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="8758b-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="8758b-103">Wird von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ein Webdienst gehostet, kann der Autorisierungs-Manager in die Anwendung integriert werden, um dem Dienst Autorisierung zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="8758b-103">When [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="8758b-104">Der Autorisierungs-Manager ermöglicht einem Anwendungsentwickler das Definieren einzelner Vorgänge, die zum Bilden von Aufgaben zusammengruppiert werden können.</span><span class="sxs-lookup"><span data-stu-id="8758b-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="8758b-105">Ein Administrator kann anschließend Rollen für das Ausführen bestimmter Aufgaben oder einzelner Vorgänge autorisieren.</span><span class="sxs-lookup"><span data-stu-id="8758b-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="8758b-106">Vom Autorisierungs-Manager wird ein Verwaltungstool als Microsoft Management Console (MMC)-Snap-in für die Verwaltung von Rollen, Aufgaben, Vorgängen und Benutzern zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="8758b-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="8758b-107">Administratoren konfigurieren für den Autorisierungs-Manager einen Richtlinienspeicher in einer XML-Datei, in Active Directory oder in einem ADAM (Active Directory Application Mode)-Speicher.</span><span class="sxs-lookup"><span data-stu-id="8758b-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="8758b-108">Der Autorisierungs-Manager wird durch Konfigurieren des [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Rollenanbieters des Autorisierungs-Managers für die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendung, die als Host für den Webdienst fungiert, in die Anwendung integriert.</span><span class="sxs-lookup"><span data-stu-id="8758b-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider for the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application that is hosting the Web service.</span></span> <span data-ttu-id="8758b-109">Wie andere [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Rollenanbieter wird der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Rollenanbieter des Autorisierungs-Managers mithilfe des <`providers`>-Elements konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8758b-109">Like other [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role providers, the Authorization Manager [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="8758b-110">Das folgende Codebeispiel ist ein Teil einer Konfigurationsdatei für einen Webdienst, der den Autorisierungs-Manager in die Anwendung integriert.</span><span class="sxs-lookup"><span data-stu-id="8758b-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"   
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="8758b-111">Integrieren einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Rollenanbieter mit einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Anwendung finden Sie unter [wie: Verwenden des ASP.NET-Rollenanbieters bei einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="8758b-111"> integrating an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="8758b-112">Verwenden des Autorisierungs-Manager mit [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], finden Sie unter [Vorgehensweise: verwenden Autorisierungs-Manager (AzMan) mit ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=71303).</span><span class="sxs-lookup"><span data-stu-id="8758b-112"> using Authorization Manager with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=71303).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8758b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8758b-113">See Also</span></span>  
 [<span data-ttu-id="8758b-114">Vorgehensweise: Verwenden des ASP.NET-Rollenanbieters bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="8758b-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
