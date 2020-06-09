---
title: 'Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 45eeda046e877b4379d7d0e5edd90fac305f5e44
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595296"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="65efc-102">Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="65efc-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="65efc-103">Der ASP.NET-Rollen Anbieter (in Verbindung mit dem ASP.net-Mitgliedschafts Anbieter) ist ein Feature, mit dem ASP.NET-Entwickler Websites erstellen können, die Benutzern das Erstellen eines Kontos mit einer Website und das Zuweisen von Rollen zu Autorisierungs Zwecken ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="65efc-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="65efc-104">Jeder Benutzer kann mit dieser Funktion ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden.</span><span class="sxs-lookup"><span data-stu-id="65efc-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="65efc-105">Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="65efc-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="65efc-106">Stattdessen kann jeder Benutzer, der seine Anmelde Informationen (die Kombination aus Benutzername und Kennwort) bereitstellt, die Website und seine Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="65efc-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="65efc-107">Eine Beispielanwendung finden Sie unter [Mitgliedschaft und Rollen Anbieter](../samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="65efc-107">For a sample application, see [Membership and Role Provider](../samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="65efc-108">Weitere Informationen zur ASP.net-Mitgliedschafts Anbieter Funktion finden Sie unter Gewusst [wie: Verwenden des ASP.net-Mitgliedschafts Anbieters](how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="65efc-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="65efc-109">Die Rollenanbieterfunktion verwendet eine SQL Server-Datenbank zum Speichern von Benutzerinformationen.</span><span class="sxs-lookup"><span data-stu-id="65efc-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="65efc-110">Windows Communication Foundation (WCF)-Entwickler können diese Features aus Sicherheitsgründen nutzen.</span><span class="sxs-lookup"><span data-stu-id="65efc-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="65efc-111">Wenn Benutzer in eine WCF-Anwendung integriert sind, müssen Sie der WCF-Client Anwendung eine Kombination aus Benutzername und Kennwort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="65efc-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="65efc-112">Um WCF die Verwendung der Datenbank zu ermöglichen, müssen Sie eine Instanz der- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> Klasse erstellen, deren- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> Eigenschaft auf festlegen <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> und die-Instanz der Auflistung von Verhalten hinzufügen, die <xref:System.ServiceModel.ServiceHost> den-Dienst gehostet.</span><span class="sxs-lookup"><span data-stu-id="65efc-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="65efc-113">Konfigurieren des Rollen Anbieters</span><span class="sxs-lookup"><span data-stu-id="65efc-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="65efc-114">Fügen Sie in der Datei Web. config unter dem < `system.web` >-Element ein < `roleManager` >-Element hinzu, und legen Sie dessen- `enabled` Attribut auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="65efc-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="65efc-115">Legen Sie das `defaultProvider`-Attribut auf `SqlRoleProvider` fest.</span><span class="sxs-lookup"><span data-stu-id="65efc-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="65efc-116">Fügen Sie als untergeordnetes Element des <`roleManager`>-Elements ein <`providers`>-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="65efc-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="65efc-117">Fügen Sie als untergeordnetes Element des <`providers`>-Elements ein <`add`> Element mit den folgenden Attributen hinzu, die auf die entsprechenden Werte festgelegt sind: `name` , `type` , `connectionStringName` und `applicationName` , wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="65efc-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="65efc-118">Konfigurieren Sie den Dienst für die Verwendung des Rollen Anbieters.</span><span class="sxs-lookup"><span data-stu-id="65efc-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="65efc-119">Fügen Sie in der Datei Web. config ein- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="65efc-119">In the Web.config file, add a [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="65efc-120">Fügen Sie [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) dem <>-Element ein-Element hinzu `system.ServiceModel` .</span><span class="sxs-lookup"><span data-stu-id="65efc-120">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="65efc-121">Fügen Sie ein- [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) Element zum <`behaviors`>-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="65efc-121">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="65efc-122">Fügen Sie ein [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) -Element hinzu, und legen Sie das- `name` Attribut auf einen geeigneten Wert fest</span><span class="sxs-lookup"><span data-stu-id="65efc-122">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="65efc-123">Fügen Sie ein- [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) Element zum <`behavior`>-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="65efc-123">Add a [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="65efc-124">Legen Sie das `principalPermissionMode`-Attribut auf `UseAspNetRoles` fest.</span><span class="sxs-lookup"><span data-stu-id="65efc-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="65efc-125">Legen Sie das `roleProviderName`-Attribut auf `SqlRoleProvider` fest.</span><span class="sxs-lookup"><span data-stu-id="65efc-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="65efc-126">Im folgenden Beispiel wird ein Fragment der Konfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="65efc-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65efc-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65efc-127">See also</span></span>

- [<span data-ttu-id="65efc-128">Mitgliedschafts- und Rollenanbieter</span><span class="sxs-lookup"><span data-stu-id="65efc-128">Membership and Role Provider</span></span>](../samples/membership-and-role-provider.md)
- [<span data-ttu-id="65efc-129">Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="65efc-129">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)
