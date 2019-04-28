---
title: <serviceAuthorization>-Element
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: 7099c5eca9cf28624153a705e4e16136628214a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670351"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="b5004-102">\<ServiceAuthorization >-Element</span><span class="sxs-lookup"><span data-stu-id="b5004-102">\<serviceAuthorization> element</span></span>
<span data-ttu-id="b5004-103">Gibt Einstellungen an, die den Zugriff auf Dienstvorgänge autorisieren.</span><span class="sxs-lookup"><span data-stu-id="b5004-103">Specifies settings that authorize access to service operations</span></span>  
  
 <span data-ttu-id="b5004-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b5004-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b5004-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b5004-105">\<behaviors></span></span>  
<span data-ttu-id="b5004-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b5004-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b5004-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b5004-107">\<behavior></span></span>  
<span data-ttu-id="b5004-108">\<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="b5004-108">\<serviceAuthorization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5004-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5004-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5004-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b5004-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b5004-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5004-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5004-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b5004-112">Attributes</span></span>  
  
|<span data-ttu-id="b5004-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="b5004-113">Attribute</span></span>|<span data-ttu-id="b5004-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5004-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b5004-115">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="b5004-115">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="b5004-116">Ein boolescher Wert, der angibt, ob alle Vorgänge im Dienst die Identität des Aufrufers annehmen.</span><span class="sxs-lookup"><span data-stu-id="b5004-116">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="b5004-117">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="b5004-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="b5004-118">Wenn ein bestimmter Dienstvorgang die Identität des Aufrufers annimmt, wird der Threadkontext zum Aufruferkontext geändert, bevor der angegebene Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b5004-118">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="b5004-119">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="b5004-119">principalPermissionMode</span></span>|<span data-ttu-id="b5004-120">Legt den Prinzipal fest, der verwendet wird, um Vorgänge auf dem Server auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b5004-120">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="b5004-121">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="b5004-121">Values include the following:</span></span><br /><br /> <span data-ttu-id="b5004-122">– None</span><span class="sxs-lookup"><span data-stu-id="b5004-122">-   None</span></span><br /><span data-ttu-id="b5004-123">-   UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="b5004-123">-   UseWindowsGroups</span></span><br /><span data-ttu-id="b5004-124">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="b5004-124">-   UseAspNetRoles</span></span><br /><span data-ttu-id="b5004-125">-Custom</span><span class="sxs-lookup"><span data-stu-id="b5004-125">-   Custom</span></span><br /><br /> <span data-ttu-id="b5004-126">Der Standardwert ist UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="b5004-126">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="b5004-127">Der Wert ist vom Typ <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="b5004-127">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="b5004-128">Weitere Informationen zur Verwendung dieses Attributs finden Sie unter [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="b5004-128">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="b5004-129">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="b5004-129">roleProviderName</span></span>|<span data-ttu-id="b5004-130">Eine Zeichenfolge, die den Namen des Rollenanbieters angibt, der Rolleninformationen für eine Windows Communication Foundation (WCF)-Anwendung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b5004-130">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="b5004-131">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b5004-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="b5004-132">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="b5004-132">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="b5004-133">Eine Zeichenfolge, die den Typ des Dienstautorisierungs-Managers angibt.</span><span class="sxs-lookup"><span data-stu-id="b5004-133">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="b5004-134">Weitere Informationen finden Sie unter <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="b5004-134">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5004-135">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5004-135">Child Elements</span></span>  
  
|<span data-ttu-id="b5004-136">Element</span><span class="sxs-lookup"><span data-stu-id="b5004-136">Element</span></span>|<span data-ttu-id="b5004-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5004-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5004-138">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="b5004-138">authorizationPolicies</span></span>|<span data-ttu-id="b5004-139">Enthält eine Auflistung der Autorisierungsrichtlinien-Typen, die mithilfe des `add`-Schlüsselworts hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="b5004-139">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="b5004-140">Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="b5004-140">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="b5004-141">Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b5004-141">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="b5004-142">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="b5004-142">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="b5004-143">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="b5004-143">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5004-144">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5004-144">Parent Elements</span></span>  
  
|<span data-ttu-id="b5004-145">Element</span><span class="sxs-lookup"><span data-stu-id="b5004-145">Element</span></span>|<span data-ttu-id="b5004-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5004-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5004-147">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b5004-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b5004-148">Enthält eine Auflistung der Einstellungen für das Verhalten eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="b5004-148">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5004-149">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5004-149">Remarks</span></span>  
 <span data-ttu-id="b5004-150">Dieser Abschnitt enthält Elemente, die die Autorisierung, benutzerspezifische Rollenanbieter und den Identitätswechsel beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="b5004-150">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="b5004-151">Das `principalPermissionMode`-Attribut gibt die Benutzergruppen an, mit denen die Verwendung einer geschützten Methode autorisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b5004-151">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="b5004-152">Der Standardwert lautet `UseWindowsGroups`. Er gibt an, das in Windows-Gruppen wie "Administratoren" oder "Benutzer" nach einer Identität gesucht wird, die versucht, auf eine Ressource zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b5004-152">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="b5004-153">Sie können auch angeben `UseAspNetRoles` einen benutzerdefinierten Rollenanbieter, der unter konfiguriert ist, verwenden die \<system.web > Element, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b5004-153">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="b5004-154">Im folgenden Code wird `roleProviderName` mit dem `principalPermissionMode`-Attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5004-154">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```  
  
 <span data-ttu-id="b5004-155">Ein ausführliches Beispiel für die Verwendung dieses Konfigurationselements finden Sie unter [Zugriff auf Dienstvorgänge autorisieren](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) und [Autorisierungsrichtlinie](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b5004-155">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5004-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5004-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="b5004-157">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="b5004-157">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b5004-158">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="b5004-158">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="b5004-159">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="b5004-159">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="b5004-160">Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse</span><span class="sxs-lookup"><span data-stu-id="b5004-160">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="b5004-161">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="b5004-161">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
