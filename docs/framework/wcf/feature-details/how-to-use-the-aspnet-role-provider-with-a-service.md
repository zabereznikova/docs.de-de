---
title: 'Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 8f3fadc60645ef81d2683c63fda0ddd5bf24c982
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047242"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="5ef30-102">Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="5ef30-102">How to: Use the ASP.NET Role Provider with a Service</span></span>
<span data-ttu-id="5ef30-103">Der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Rollenanbieter (zusammen mit dem [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Mitgliedschaftsanbieter) ist eine Funktion für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Entwickler zum Erstellen von Websites, mit denen die Benutzer ein Konto auf einer Site erstellen können. Außerdem können ihnen Rollen für die Autorisierung zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="5ef30-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider (in conjunction with the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider) is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="5ef30-104">Jeder Benutzer kann mit dieser Funktion ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden.</span><span class="sxs-lookup"><span data-stu-id="5ef30-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="5ef30-105">Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="5ef30-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="5ef30-106">Stattdessen kann jeder Benutzer, der seine Anmeldeinformationen (eine Kombination aus Benutzername/Kennwort) angibt, die Site und ihre Dienste nutzen.</span><span class="sxs-lookup"><span data-stu-id="5ef30-106">Instead, any user who supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="5ef30-107">Eine beispielanwendung finden Sie unter [Mitgliedschafts- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="5ef30-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="5ef30-108">Weitere Informationen zu den [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -mitgliedschaftsanbieterfunktion finden Sie unter [Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="5ef30-108">For more information about the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
 <span data-ttu-id="5ef30-109">Die Rollenanbieterfunktion verwendet eine SQL Server-Datenbank zum Speichern von Benutzerinformationen.</span><span class="sxs-lookup"><span data-stu-id="5ef30-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="5ef30-110">Windows Communication Foundation (WCF)-Entwickler können diese Funktionen für Sicherheitszwecke nutzen.</span><span class="sxs-lookup"><span data-stu-id="5ef30-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="5ef30-111">Wenn in einer WCF-Anwendung integriert, müssen Benutzer über eine Kombination aus Benutzername und Kennwort an die WCF-Clientanwendung angeben.</span><span class="sxs-lookup"><span data-stu-id="5ef30-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="5ef30-112">Um WCF zur Verwendung der Datenbank zu aktivieren, müssen Sie erstellen eine Instanz von der <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> Klasse, legen dessen <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> Eigenschaft <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, und fügen Sie die Instanz, auf die Auflistung von Verhaltensweisen, die die <xref:System.ServiceModel.ServiceHost> , die den Dienst hostet.</span><span class="sxs-lookup"><span data-stu-id="5ef30-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
### <a name="to-configure-the-role-provider"></a><span data-ttu-id="5ef30-113">So konfigurieren Sie den Rollenanbieter</span><span class="sxs-lookup"><span data-stu-id="5ef30-113">To configure the role provider</span></span>  
  
1. <span data-ttu-id="5ef30-114">In der Datei "Web.config" unter der <`system.web`>-Element hinzufügen einer <`roleManager`> Element, und legen seine `enabled` -Attribut auf `true`.</span><span class="sxs-lookup"><span data-stu-id="5ef30-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="5ef30-115">Legen Sie das `defaultProvider`-Attribut auf `SqlRoleProvider` fest.</span><span class="sxs-lookup"><span data-stu-id="5ef30-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="5ef30-116">Als untergeordnetes Element der <`roleManager`>-Element hinzufügen einer <`providers`> Element.</span><span class="sxs-lookup"><span data-stu-id="5ef30-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="5ef30-117">Als untergeordnetes Element der <`providers`>-Element, Hinzufügen einer <`add`>-Element mit den folgenden Attributen festgelegt wird, auf die entsprechenden Werte: `name`, `type`, `connectionStringName`, und `applicationName`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ef30-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="5ef30-118">So konfigurieren Sie den Dienst für die Verwendung des Rollenanbieters</span><span class="sxs-lookup"><span data-stu-id="5ef30-118">To configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="5ef30-119">In der Datei "Web.config" Hinzufügen einer [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Element.</span><span class="sxs-lookup"><span data-stu-id="5ef30-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="5ef30-120">Hinzufügen einer [ \<Verhaltensweisen >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element, das <`system.ServiceModel`> Element.</span><span class="sxs-lookup"><span data-stu-id="5ef30-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="5ef30-121">Hinzufügen einer [ \<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) auf der <`behaviors`> Element.</span><span class="sxs-lookup"><span data-stu-id="5ef30-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="5ef30-122">Hinzufügen einer [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Element, und legen die `name` -Attribut auf einen geeigneten Wert.</span><span class="sxs-lookup"><span data-stu-id="5ef30-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="5ef30-123">Hinzufügen einer [ \<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) auf der <`behavior`> Element.</span><span class="sxs-lookup"><span data-stu-id="5ef30-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="5ef30-124">Legen Sie das `principalPermissionMode`-Attribut auf `UseAspNetRoles` fest.</span><span class="sxs-lookup"><span data-stu-id="5ef30-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="5ef30-125">Legen Sie das `roleProviderName`-Attribut auf `SqlRoleProvider` fest.</span><span class="sxs-lookup"><span data-stu-id="5ef30-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="5ef30-126">Im folgenden Beispiel wird ein Fragment der Konfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5ef30-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ef30-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ef30-127">See also</span></span>

- [<span data-ttu-id="5ef30-128">Mitgliedschafts- und Rollenanbieter</span><span class="sxs-lookup"><span data-stu-id="5ef30-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="5ef30-129">Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="5ef30-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
