---
title: "Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eb5adec17f834687038b729a475fbcc0e2311c01
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="c79ad-102">Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="c79ad-102">How to: Use the ASP.NET Role Provider with a Service</span></span>
<span data-ttu-id="c79ad-103">Der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Rollenanbieter (zusammen mit dem [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Mitgliedschaftsanbieter) ist eine Funktion für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Entwickler zum Erstellen von Websites, mit denen die Benutzer ein Konto auf einer Site erstellen können. Außerdem können ihnen Rollen für die Autorisierung zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c79ad-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider (in conjunction with the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider) is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="c79ad-104">Jeder Benutzer kann mit dieser Funktion ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden.</span><span class="sxs-lookup"><span data-stu-id="c79ad-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="c79ad-105">Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="c79ad-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="c79ad-106">Stattdessen kann jeder Benutzer, der seine Anmeldeinformationen (eine Kombination aus Benutzername/Kennwort) angibt, die Site und ihre Dienste nutzen.</span><span class="sxs-lookup"><span data-stu-id="c79ad-106">Instead, any user who supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="c79ad-107">Eine beispielanwendung finden Sie unter [Mitgliedschafts- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c79ad-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c79ad-108">die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Anbieter Mitgliedschaftsfunktion, finden Sie unter [Vorgehensweise: Verwenden Sie den ASP.NET-Mitgliedschaftsanbieter](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c79ad-108"> the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
 <span data-ttu-id="c79ad-109">Die Rollenanbieterfunktion verwendet eine SQL Server-Datenbank zum Speichern von Benutzerinformationen.</span><span class="sxs-lookup"><span data-stu-id="c79ad-109">The role provider feature uses a SQL Server database to store user information.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="c79ad-110">-Entwickler können diese Funktionen für Sicherheitszwecke nutzen.</span><span class="sxs-lookup"><span data-stu-id="c79ad-110"> developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="c79ad-111">Wenn sie in eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendung integriert sind, müssen die Benutzer der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientanwendung eine Kombination aus Benutzername/Kennwort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c79ad-111">When integrated into a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, users must supply a user name/password combination to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span> <span data-ttu-id="c79ad-112">Damit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Datenbank verwenden kann, müssen Sie eine Instanz der <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>-Klasse erstellen, ihre <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A>-Eigenschaft auf <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> festlegen und die Instanz zu der Verhaltensauflistung zum <xref:System.ServiceModel.ServiceHost> hinzufügen, der den Dienst hostet.</span><span class="sxs-lookup"><span data-stu-id="c79ad-112">To enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
### <a name="to-configure-the-role-provider"></a><span data-ttu-id="c79ad-113">So konfigurieren Sie den Rollenanbieter</span><span class="sxs-lookup"><span data-stu-id="c79ad-113">To configure the role provider</span></span>  
  
1.  <span data-ttu-id="c79ad-114">In der Datei "Web.config" unter der <`system.web`>-Element hinzufügen einer <`roleManager`> Element, und legen seine `enabled` -Attribut auf `true`.</span><span class="sxs-lookup"><span data-stu-id="c79ad-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2.  <span data-ttu-id="c79ad-115">Legen Sie das `defaultProvider`-Attribut auf `SqlRoleProvider` fest.</span><span class="sxs-lookup"><span data-stu-id="c79ad-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3.  <span data-ttu-id="c79ad-116">Als untergeordnetes Element der <`roleManager`>-Element hinzufügen einer <`providers`> Element.</span><span class="sxs-lookup"><span data-stu-id="c79ad-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4.  <span data-ttu-id="c79ad-117">Als untergeordnetes Element der <`providers`>-Element, Hinzufügen einer <`add`>-Element mit den folgenden Attributen auf die entsprechenden Werte festgelegt: `name`, `type`, `connectionStringName`, und `applicationName`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c79ad-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"   
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="c79ad-118">So konfigurieren Sie den Dienst für die Verwendung des Rollenanbieters</span><span class="sxs-lookup"><span data-stu-id="c79ad-118">To configure the service to use the role provider</span></span>  
  
1.  <span data-ttu-id="c79ad-119">In der Datei "Web.config" Hinzufügen einer [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Element.</span><span class="sxs-lookup"><span data-stu-id="c79ad-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="c79ad-120">Hinzufügen einer [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element auf der <`system.ServiceModel`> Element.</span><span class="sxs-lookup"><span data-stu-id="c79ad-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3.  <span data-ttu-id="c79ad-121">Hinzufügen einer [ \<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) auf der <`behaviors`> Element.</span><span class="sxs-lookup"><span data-stu-id="c79ad-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4.  <span data-ttu-id="c79ad-122">Hinzufügen einer [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Element, und legen die `name` -Attribut auf einen geeigneten Wert.</span><span class="sxs-lookup"><span data-stu-id="c79ad-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5.  <span data-ttu-id="c79ad-123">Hinzufügen einer [ \<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) auf der <`behavior`> Element.</span><span class="sxs-lookup"><span data-stu-id="c79ad-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6.  <span data-ttu-id="c79ad-124">Legen Sie das `principalPermissionMode`-Attribut auf `UseAspNetRoles` fest.</span><span class="sxs-lookup"><span data-stu-id="c79ad-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7.  <span data-ttu-id="c79ad-125">Legen Sie das `roleProviderName`-Attribut auf `SqlRoleProvider` fest.</span><span class="sxs-lookup"><span data-stu-id="c79ad-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="c79ad-126">Im folgenden Beispiel wird ein Fragment der Konfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c79ad-126">The following example shows a fragment of the configuration.</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c79ad-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c79ad-127">See Also</span></span>  
 [<span data-ttu-id="c79ad-128">Mitgliedschafts- und Rollenanbieter</span><span class="sxs-lookup"><span data-stu-id="c79ad-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 [<span data-ttu-id="c79ad-129">Vorgehensweise: Verwenden Sie den ASP.NET-Mitgliedschaftsanbieter</span><span class="sxs-lookup"><span data-stu-id="c79ad-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
