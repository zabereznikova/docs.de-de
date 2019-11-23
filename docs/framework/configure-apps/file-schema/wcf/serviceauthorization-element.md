---
title: <serviceAuthorization>-Element
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834021"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="f2084-102">\<ServiceAuthorization >-Element</span><span class="sxs-lookup"><span data-stu-id="f2084-102">\<serviceAuthorization> element</span></span>

<span data-ttu-id="f2084-103">Gibt Einstellungen an, die den Zugriff auf Dienstvorgänge autorisieren.</span><span class="sxs-lookup"><span data-stu-id="f2084-103">Specifies settings that authorize access to service operations</span></span>

<span data-ttu-id="f2084-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2084-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f2084-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f2084-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f2084-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhalten**](behaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="f2084-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="f2084-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**serviceverhaltensweisen**](servicebehaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="f2084-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="f2084-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**Verhalten >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f2084-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="f2084-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ServiceAuthorization >**</span><span class="sxs-lookup"><span data-stu-id="f2084-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f2084-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2084-110">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="f2084-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f2084-111">Attributes and elements</span></span>

<span data-ttu-id="f2084-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und übergeordnete Elemente beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f2084-112">The following sections describe attributes, child elements, and parent elements:</span></span>

### <a name="attributes"></a><span data-ttu-id="f2084-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="f2084-113">Attributes</span></span>

|<span data-ttu-id="f2084-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="f2084-114">Attribute</span></span>|<span data-ttu-id="f2084-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2084-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f2084-116">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="f2084-116">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="f2084-117">Ein boolescher Wert, der angibt, ob alle Vorgänge im Dienst die Identität des Aufrufers annehmen.</span><span class="sxs-lookup"><span data-stu-id="f2084-117">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="f2084-118">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="f2084-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="f2084-119">Wenn ein bestimmter Dienstvorgang die Identität des Aufrufers annimmt, wird der Threadkontext zum Aufruferkontext geändert, bevor der angegebene Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f2084-119">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="f2084-120">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="f2084-120">principalPermissionMode</span></span>|<span data-ttu-id="f2084-121">Legt den Prinzipal fest, der verwendet wird, um Vorgänge auf dem Server auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f2084-121">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="f2084-122">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="f2084-122">Values include the following:</span></span><br /><br /> <span data-ttu-id="f2084-123">-None</span><span class="sxs-lookup"><span data-stu-id="f2084-123">-   None</span></span><br /><span data-ttu-id="f2084-124">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="f2084-124">-   UseWindowsGroups</span></span><br /><span data-ttu-id="f2084-125">-Useaspnettroles</span><span class="sxs-lookup"><span data-stu-id="f2084-125">-   UseAspNetRoles</span></span><br /><span data-ttu-id="f2084-126">-Benutzer definiert</span><span class="sxs-lookup"><span data-stu-id="f2084-126">-   Custom</span></span><br /><br /> <span data-ttu-id="f2084-127">Der Standardwert ist UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="f2084-127">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="f2084-128">Der Wert ist vom Typ <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="f2084-128">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="f2084-129">Weitere Informationen zur Verwendung dieses Attributs finden Sie unter Gewusst [wie: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="f2084-129">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="f2084-130">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="f2084-130">roleProviderName</span></span>|<span data-ttu-id="f2084-131">Eine Zeichenfolge, die den Namen des Rollenanbieters angibt, der Rolleninformationen für eine Windows Communication Foundation (WCF)-Anwendung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f2084-131">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="f2084-132">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f2084-132">The default is an empty string.</span></span>|  
|<span data-ttu-id="f2084-133">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="f2084-133">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="f2084-134">Eine Zeichenfolge, die den Typ des Dienstautorisierungs-Managers angibt.</span><span class="sxs-lookup"><span data-stu-id="f2084-134">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="f2084-135">Weitere Informationen finden Sie unter <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="f2084-135">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="f2084-136">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2084-136">Child elements</span></span>

|<span data-ttu-id="f2084-137">Element</span><span class="sxs-lookup"><span data-stu-id="f2084-137">Element</span></span>|<span data-ttu-id="f2084-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2084-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2084-139">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="f2084-139">authorizationPolicies</span></span>|<span data-ttu-id="f2084-140">Enthält eine Auflistung der Autorisierungsrichtlinien-Typen, die mithilfe des `add`-Schlüsselworts hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="f2084-140">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="f2084-141">Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="f2084-141">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="f2084-142">Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f2084-142">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="f2084-143">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="f2084-143">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="f2084-144">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="f2084-144">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  

### <a name="parent-elements"></a><span data-ttu-id="f2084-145">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2084-145">Parent elements</span></span>

|<span data-ttu-id="f2084-146">Element</span><span class="sxs-lookup"><span data-stu-id="f2084-146">Element</span></span>|<span data-ttu-id="f2084-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2084-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2084-148">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f2084-148">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f2084-149">Enthält eine Auflistung der Einstellungen für das Verhalten eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="f2084-149">Contains a collection of settings for the behavior of a service.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="f2084-150">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2084-150">Remarks</span></span>

<span data-ttu-id="f2084-151">Dieser Abschnitt enthält Elemente, die die Autorisierung, benutzerspezifische Rollenanbieter und den Identitätswechsel beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="f2084-151">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
<span data-ttu-id="f2084-152">Das `principalPermissionMode`-Attribut gibt die Benutzergruppen an, mit denen die Verwendung einer geschützten Methode autorisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f2084-152">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="f2084-153">Der Standardwert lautet `UseWindowsGroups`. Er gibt an, das in Windows-Gruppen wie "Administratoren" oder "Benutzer" nach einer Identität gesucht wird, die versucht, auf eine Ressource zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f2084-153">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="f2084-154">Sie können auch angeben, `UseAspNetRoles` einen benutzerdefinierten Rollen Anbieter verwenden möchten, der unter dem \<System. Web >-Element konfiguriert ist, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f2084-154">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code:</span></span>

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
  
<span data-ttu-id="f2084-155">Der folgende Code zeigt die `roleProviderName`, die mit dem Attribut `principalPermissionMode` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="f2084-155">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute:</span></span>
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

<span data-ttu-id="f2084-156">Ein ausführliches Beispiel für die Verwendung dieses Konfigurations Elements finden Sie unter [Autorisieren des Zugriffs auf Dienst Vorgänge](../../../wcf/samples/authorizing-access-to-service-operations.md) und [Autorisierungs Richtlinien](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f2084-156">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f2084-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2084-157">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="f2084-158">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="f2084-158">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f2084-159">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="f2084-159">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="f2084-160">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="f2084-160">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="f2084-161">Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse</span><span class="sxs-lookup"><span data-stu-id="f2084-161">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="f2084-162">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="f2084-162">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
