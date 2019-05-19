---
title: 'Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 778af929b4cfc96ce0683d304be5f8fb87a0e47b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880201"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="97ba9-102">Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="97ba9-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="97ba9-103">Wenn ASP.NET auf einen Webdienst hostet, können Sie die Autorisierungs-Manager bei der Anwendung Autorisierung für den Dienst zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="97ba9-103">When ASP.NET hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="97ba9-104">Der Autorisierungs-Manager ermöglicht einem Anwendungsentwickler das Definieren einzelner Vorgänge, die zum Bilden von Aufgaben zusammengruppiert werden können.</span><span class="sxs-lookup"><span data-stu-id="97ba9-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="97ba9-105">Ein Administrator kann anschließend Rollen für das Ausführen bestimmter Aufgaben oder einzelner Vorgänge autorisieren.</span><span class="sxs-lookup"><span data-stu-id="97ba9-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="97ba9-106">Vom Autorisierungs-Manager wird ein Verwaltungstool als Microsoft Management Console (MMC)-Snap-in für die Verwaltung von Rollen, Aufgaben, Vorgängen und Benutzern zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="97ba9-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="97ba9-107">Administratoren konfigurieren für den Autorisierungs-Manager einen Richtlinienspeicher in einer XML-Datei, in Active Directory oder in einem ADAM (Active Directory Application Mode)-Speicher.</span><span class="sxs-lookup"><span data-stu-id="97ba9-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="97ba9-108">Autorisierungs-Manager ist in der Anwendung integriert, konfigurieren Sie den ASP.NET-Rollenanbieter Autorisierungs-Manager für die ASP.NET-Anwendung, die den Webdienst hostet.</span><span class="sxs-lookup"><span data-stu-id="97ba9-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager ASP.NET role provider for the ASP.NET application that is hosting the Web service.</span></span> <span data-ttu-id="97ba9-109">Wie andere ASP.NET-Rollenanbietern der Autorisierungs-Manager ASP.NET-Rollenanbieter erfolgt über die <`providers`> Element.</span><span class="sxs-lookup"><span data-stu-id="97ba9-109">Like other ASP.NET role providers, the Authorization Manager ASP.NET role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="97ba9-110">Das folgende Codebeispiel ist ein Teil einer Konfigurationsdatei für einen Webdienst, der den Autorisierungs-Manager in die Anwendung integriert.</span><span class="sxs-lookup"><span data-stu-id="97ba9-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
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
  
 <span data-ttu-id="97ba9-111">Weitere Informationen zu einer WCF-Anwendung ein ASP.NET-Rollenanbieter integrieren, finden Sie unter [Vorgehensweise: Verwenden des ASP.NET-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="97ba9-111">For more information about integrating an ASP.NET role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="97ba9-112">Weitere Informationen zur Verwendung des Autorisierungs-Manager mit ASP.NET finden Sie unter [Vorgehensweise: Use Authorization Manager (AzMan) mit ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).</span><span class="sxs-lookup"><span data-stu-id="97ba9-112">For more information about using Authorization Manager with ASP.NET, see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ba9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97ba9-113">See also</span></span>

- [<span data-ttu-id="97ba9-114">Vorgehensweise: Verwenden des ASP.NET-Rollenanbieters mit einem Dienst</span><span class="sxs-lookup"><span data-stu-id="97ba9-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
