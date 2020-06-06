---
title: <serviceAuthorization>-Element
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "71834021"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="4100d-102">\<serviceAuthorization>-Element</span><span class="sxs-lookup"><span data-stu-id="4100d-102">\<serviceAuthorization> element</span></span>

<span data-ttu-id="4100d-103">Gibt Einstellungen an, die den Zugriff auf Dienstvorgänge autorisieren.</span><span class="sxs-lookup"><span data-stu-id="4100d-103">Specifies settings that authorize access to service operations</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**  

## <a name="syntax"></a><span data-ttu-id="4100d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4100d-104">Syntax</span></span>

```xml
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4100d-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4100d-105">Attributes and elements</span></span>

<span data-ttu-id="4100d-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und übergeordnete Elemente beschrieben:</span><span class="sxs-lookup"><span data-stu-id="4100d-106">The following sections describe attributes, child elements, and parent elements:</span></span>

### <a name="attributes"></a><span data-ttu-id="4100d-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="4100d-107">Attributes</span></span>

|<span data-ttu-id="4100d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="4100d-108">Attribute</span></span>|<span data-ttu-id="4100d-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4100d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4100d-110">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="4100d-110">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="4100d-111">Ein boolescher Wert, der angibt, ob alle Vorgänge im Dienst die Identität des Aufrufers annehmen.</span><span class="sxs-lookup"><span data-stu-id="4100d-111">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="4100d-112">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="4100d-112">The default is `false`.</span></span><br /><br /> <span data-ttu-id="4100d-113">Wenn ein bestimmter Dienstvorgang die Identität des Aufrufers annimmt, wird der Threadkontext zum Aufruferkontext geändert, bevor der angegebene Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4100d-113">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="4100d-114">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="4100d-114">principalPermissionMode</span></span>|<span data-ttu-id="4100d-115">Legt den Prinzipal fest, der verwendet wird, um Vorgänge auf dem Server auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4100d-115">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="4100d-116">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="4100d-116">Values include the following:</span></span><br /><br /> <span data-ttu-id="4100d-117">-None</span><span class="sxs-lookup"><span data-stu-id="4100d-117">-   None</span></span><br /><span data-ttu-id="4100d-118">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="4100d-118">-   UseWindowsGroups</span></span><br /><span data-ttu-id="4100d-119">-Useaspnettroles</span><span class="sxs-lookup"><span data-stu-id="4100d-119">-   UseAspNetRoles</span></span><br /><span data-ttu-id="4100d-120">-Benutzer definiert</span><span class="sxs-lookup"><span data-stu-id="4100d-120">-   Custom</span></span><br /><br /> <span data-ttu-id="4100d-121">Der Standardwert ist UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="4100d-121">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="4100d-122">Der Wert ist vom Typ <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="4100d-122">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="4100d-123">Weitere Informationen zur Verwendung dieses Attributs finden Sie unter Gewusst [wie: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="4100d-123">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="4100d-124">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="4100d-124">roleProviderName</span></span>|<span data-ttu-id="4100d-125">Eine Zeichenfolge, die den Namen des Rollenanbieters angibt, der Rolleninformationen für eine Windows Communication Foundation (WCF)-Anwendung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="4100d-125">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="4100d-126">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4100d-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="4100d-127">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="4100d-127">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="4100d-128">Eine Zeichenfolge, die den Typ des Dienstautorisierungs-Managers angibt.</span><span class="sxs-lookup"><span data-stu-id="4100d-128">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="4100d-129">Weitere Informationen finden Sie unter <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="4100d-129">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="4100d-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4100d-130">Child elements</span></span>

|<span data-ttu-id="4100d-131">Element</span><span class="sxs-lookup"><span data-stu-id="4100d-131">Element</span></span>|<span data-ttu-id="4100d-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4100d-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4100d-133">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="4100d-133">authorizationPolicies</span></span>|<span data-ttu-id="4100d-134">Enthält eine Auflistung der Autorisierungsrichtlinien-Typen, die mithilfe des `add`-Schlüsselworts hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="4100d-134">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="4100d-135">Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="4100d-135">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="4100d-136">Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4100d-136">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="4100d-137">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="4100d-137">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="4100d-138">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="4100d-138">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  

### <a name="parent-elements"></a><span data-ttu-id="4100d-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4100d-139">Parent elements</span></span>

|<span data-ttu-id="4100d-140">Element</span><span class="sxs-lookup"><span data-stu-id="4100d-140">Element</span></span>|<span data-ttu-id="4100d-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4100d-141">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4100d-142">Enthält eine Auflistung der Einstellungen für das Verhalten eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="4100d-142">Contains a collection of settings for the behavior of a service.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="4100d-143">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4100d-143">Remarks</span></span>

<span data-ttu-id="4100d-144">Dieser Abschnitt enthält Elemente, die die Autorisierung, benutzerspezifische Rollenanbieter und den Identitätswechsel beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="4100d-144">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
<span data-ttu-id="4100d-145">Das `principalPermissionMode`-Attribut gibt die Benutzergruppen an, mit denen die Verwendung einer geschützten Methode autorisiert wird.</span><span class="sxs-lookup"><span data-stu-id="4100d-145">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="4100d-146">Der Standardwert lautet `UseWindowsGroups`. Er gibt an, das in Windows-Gruppen wie "Administratoren" oder "Benutzer" nach einer Identität gesucht wird, die versucht, auf eine Ressource zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4100d-146">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="4100d-147">Sie können auch angeben, `UseAspNetRoles` dass ein benutzerdefinierter Rollen Anbieter verwendet werden soll, der unter dem-Element konfiguriert ist \<system.web> , wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4100d-147">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code:</span></span>

```xml
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```
  
<span data-ttu-id="4100d-148">Der folgende Code zeigt, wie `roleProviderName` mit dem-Attribut verwendet wird `principalPermissionMode` :</span><span class="sxs-lookup"><span data-stu-id="4100d-148">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute:</span></span>
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

<span data-ttu-id="4100d-149">Ein ausführliches Beispiel für die Verwendung dieses Konfigurations Elements finden Sie unter [Autorisieren des Zugriffs auf Dienst Vorgänge](../../../wcf/samples/authorizing-access-to-service-operations.md) und [Autorisierungs Richtlinien](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4100d-149">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4100d-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4100d-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="4100d-151">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="4100d-151">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="4100d-152">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="4100d-152">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="4100d-153">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="4100d-153">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="4100d-154">Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse</span><span class="sxs-lookup"><span data-stu-id="4100d-154">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="4100d-155">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4100d-155">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
