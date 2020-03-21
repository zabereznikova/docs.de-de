---
title: 'Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: ddfedeb2491998f64ab241ceba303d50d0714351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184767"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="ab17c-102">Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="ab17c-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="ab17c-103">Der ASP.NET Rollenanbieter (in Verbindung mit dem ASP.NET Mitgliedschaftsanbieter) ist eine Funktion, die es ASP.NET Entwicklern ermöglicht, Websites zu erstellen, die es Benutzern ermöglichen, ein Konto mit einer Website zu erstellen und Rollen für Autorisierungszwecke zugewiesen zu werden.</span><span class="sxs-lookup"><span data-stu-id="ab17c-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="ab17c-104">Jeder Benutzer kann mit dieser Funktion ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden.</span><span class="sxs-lookup"><span data-stu-id="ab17c-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="ab17c-105">Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="ab17c-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="ab17c-106">Stattdessen kann jeder Benutzer, der seine Anmeldeinformationen (die Kombination benutzername/password) bereitstellt, die Website und ihre Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab17c-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="ab17c-107">Eine Beispielanwendung finden Sie unter [Mitgliedschaft und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ab17c-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="ab17c-108">Weitere Informationen zur Funktion des ASP.NET Mitgliedschaftsanbieters finden Sie unter [Gewusst wie: Verwenden des ASP.NET Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ab17c-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="ab17c-109">Die Rollenanbieterfunktion verwendet eine SQL Server-Datenbank zum Speichern von Benutzerinformationen.</span><span class="sxs-lookup"><span data-stu-id="ab17c-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="ab17c-110">Windows Communication Foundation (WCF)-Entwickler können diese Funktionen aus Sicherheitsgründen nutzen.</span><span class="sxs-lookup"><span data-stu-id="ab17c-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="ab17c-111">Wenn benutzerin eine WCF-Anwendung integriert ist, müssen sie der WCF-Clientanwendung eine Kombination aus Benutzername und Kennwort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ab17c-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="ab17c-112">Damit WCF die Datenbank verwenden kann, müssen <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> Sie eine <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> Instanz <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>der Klasse erstellen, ihre Eigenschaft auf <xref:System.ServiceModel.ServiceHost> festlegen und die Instanz der Auflistung von Verhaltensweisen hinzufügen, die den Dienst hostet.</span><span class="sxs-lookup"><span data-stu-id="ab17c-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="ab17c-113">Konfigurieren des Rollenanbieters</span><span class="sxs-lookup"><span data-stu-id="ab17c-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="ab17c-114">Fügen Sie in der Datei Web.config unter `system.web` `roleManager` dem <>-Element ein <>-Element hinzu, und legen Sie dessen `enabled` Attribut auf fest. `true`</span><span class="sxs-lookup"><span data-stu-id="ab17c-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="ab17c-115">Legen Sie das `defaultProvider`-Attribut auf `SqlRoleProvider` fest.</span><span class="sxs-lookup"><span data-stu-id="ab17c-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="ab17c-116">Fügen Sie als `roleManager` untergeordnetes Element zum `providers` <>-Element ein <>-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="ab17c-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="ab17c-117">Fügen Sie als `providers` untergeordnetes Element zum `add` <>-Element ein <>-Element hinzu, wobei die folgenden Attribute auf die entsprechenden Werte `name`festgelegt sind: , `type`, `connectionStringName`und `applicationName`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ab17c-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="ab17c-118">Konfigurieren des Dienstes für die Verwendung des Rollenanbieters</span><span class="sxs-lookup"><span data-stu-id="ab17c-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="ab17c-119">Fügen Sie in der Datei Web.config ein [ \<system.serviceModel->-Element](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="ab17c-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="ab17c-120">Fügen [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Sie dem <`system.ServiceModel`>-Element ein Verhalten>Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="ab17c-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="ab17c-121">Fügen Sie dem <`behaviors`>-Element einen [ \<serviceBehaviors->](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="ab17c-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="ab17c-122">Fügen [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Sie ein Verhalten `name`>Element hinzu, und legen Sie das Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="ab17c-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="ab17c-123">Fügen Sie dem <`behavior`>-Element einen [ \<serviceAuthorization->](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="ab17c-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="ab17c-124">Legen Sie das `principalPermissionMode`-Attribut auf `UseAspNetRoles` fest.</span><span class="sxs-lookup"><span data-stu-id="ab17c-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="ab17c-125">Legen Sie das `roleProviderName`-Attribut auf `SqlRoleProvider` fest.</span><span class="sxs-lookup"><span data-stu-id="ab17c-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="ab17c-126">Im folgenden Beispiel wird ein Fragment der Konfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ab17c-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ab17c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab17c-127">See also</span></span>

- [<span data-ttu-id="ab17c-128">Mitgliedschafts- und Rollenanbieter</span><span class="sxs-lookup"><span data-stu-id="ab17c-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="ab17c-129">Gewusst wie: Verwenden des ASP.NET-Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="ab17c-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
