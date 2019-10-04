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
# <a name="serviceauthorization-element"></a><span data-ttu-id="54b6d-102">\<serviceauthorization > Element</span><span class="sxs-lookup"><span data-stu-id="54b6d-102">\<serviceAuthorization> element</span></span>

<span data-ttu-id="54b6d-103">Gibt Einstellungen an, die den Zugriff auf Dienstvorgänge autorisieren.</span><span class="sxs-lookup"><span data-stu-id="54b6d-103">Specifies settings that authorize access to service operations</span></span>

<span data-ttu-id="54b6d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="54b6d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="54b6d-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="54b6d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="54b6d-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<verhaltensweisen >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="54b6d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="54b6d-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<serviceverhaltensweisen >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="54b6d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="54b6d-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0behavior >** ](behavior-of-servicebehaviors.md)1</span><span class="sxs-lookup"><span data-stu-id="54b6d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\</span></span>
<span data-ttu-id="54b6d-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1serviceauthorization >**</span><span class="sxs-lookup"><span data-stu-id="54b6d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="54b6d-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="54b6d-110">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="54b6d-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="54b6d-111">Attributes and elements</span></span>

<span data-ttu-id="54b6d-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und übergeordnete Elemente beschrieben:</span><span class="sxs-lookup"><span data-stu-id="54b6d-112">The following sections describe attributes, child elements, and parent elements:</span></span>

### <a name="attributes"></a><span data-ttu-id="54b6d-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="54b6d-113">Attributes</span></span>

|<span data-ttu-id="54b6d-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="54b6d-114">Attribute</span></span>|<span data-ttu-id="54b6d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54b6d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54b6d-116">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="54b6d-116">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="54b6d-117">Ein boolescher Wert, der angibt, ob alle Vorgänge im Dienst die Identität des Aufrufers annehmen.</span><span class="sxs-lookup"><span data-stu-id="54b6d-117">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="54b6d-118">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="54b6d-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="54b6d-119">Wenn ein bestimmter Dienstvorgang die Identität des Aufrufers annimmt, wird der Threadkontext zum Aufruferkontext geändert, bevor der angegebene Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="54b6d-119">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="54b6d-120">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="54b6d-120">principalPermissionMode</span></span>|<span data-ttu-id="54b6d-121">Legt den Prinzipal fest, der verwendet wird, um Vorgänge auf dem Server auszuführen.</span><span class="sxs-lookup"><span data-stu-id="54b6d-121">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="54b6d-122">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="54b6d-122">Values include the following:</span></span><br /><br /> <span data-ttu-id="54b6d-123">-None</span><span class="sxs-lookup"><span data-stu-id="54b6d-123">-   None</span></span><br /><span data-ttu-id="54b6d-124">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="54b6d-124">-   UseWindowsGroups</span></span><br /><span data-ttu-id="54b6d-125">-Useaspnettroles</span><span class="sxs-lookup"><span data-stu-id="54b6d-125">-   UseAspNetRoles</span></span><br /><span data-ttu-id="54b6d-126">-Benutzer definiert</span><span class="sxs-lookup"><span data-stu-id="54b6d-126">-   Custom</span></span><br /><br /> <span data-ttu-id="54b6d-127">Der Standardwert ist UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="54b6d-127">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="54b6d-128">Der Wert ist vom Typ <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="54b6d-128">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="54b6d-129">Weitere Informationen zur Verwendung dieses Attributs finden Sie unter [gewusst wie: Beschränken Sie den Zugriff mit der PrincipalPermissionAttribute-Klasse @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="54b6d-129">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="54b6d-130">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="54b6d-130">roleProviderName</span></span>|<span data-ttu-id="54b6d-131">Eine Zeichenfolge, die den Namen des Rollenanbieters angibt, der Rolleninformationen für eine Windows Communication Foundation (WCF)-Anwendung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="54b6d-131">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="54b6d-132">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="54b6d-132">The default is an empty string.</span></span>|  
|<span data-ttu-id="54b6d-133">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="54b6d-133">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="54b6d-134">Eine Zeichenfolge, die den Typ des Dienstautorisierungs-Managers angibt.</span><span class="sxs-lookup"><span data-stu-id="54b6d-134">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="54b6d-135">Weitere Informationen finden Sie unter <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="54b6d-135">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="54b6d-136">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54b6d-136">Child elements</span></span>

|<span data-ttu-id="54b6d-137">Element</span><span class="sxs-lookup"><span data-stu-id="54b6d-137">Element</span></span>|<span data-ttu-id="54b6d-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54b6d-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="54b6d-139">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="54b6d-139">authorizationPolicies</span></span>|<span data-ttu-id="54b6d-140">Enthält eine Auflistung der Autorisierungsrichtlinien-Typen, die mithilfe des `add`-Schlüsselworts hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="54b6d-140">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="54b6d-141">Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="54b6d-141">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="54b6d-142">Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="54b6d-142">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="54b6d-143">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="54b6d-143">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="54b6d-144">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="54b6d-144">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  

### <a name="parent-elements"></a><span data-ttu-id="54b6d-145">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54b6d-145">Parent elements</span></span>

|<span data-ttu-id="54b6d-146">Element</span><span class="sxs-lookup"><span data-stu-id="54b6d-146">Element</span></span>|<span data-ttu-id="54b6d-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54b6d-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54b6d-148">\<behavior></span><span class="sxs-lookup"><span data-stu-id="54b6d-148">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="54b6d-149">Enthält eine Auflistung der Einstellungen für das Verhalten eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="54b6d-149">Contains a collection of settings for the behavior of a service.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="54b6d-150">Hinweise</span><span class="sxs-lookup"><span data-stu-id="54b6d-150">Remarks</span></span>

<span data-ttu-id="54b6d-151">Dieser Abschnitt enthält Elemente, die die Autorisierung, benutzerspezifische Rollenanbieter und den Identitätswechsel beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="54b6d-151">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
<span data-ttu-id="54b6d-152">Das `principalPermissionMode`-Attribut gibt die Benutzergruppen an, mit denen die Verwendung einer geschützten Methode autorisiert wird.</span><span class="sxs-lookup"><span data-stu-id="54b6d-152">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="54b6d-153">Der Standardwert lautet `UseWindowsGroups`. Er gibt an, das in Windows-Gruppen wie "Administratoren" oder "Benutzer" nach einer Identität gesucht wird, die versucht, auf eine Ressource zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="54b6d-153">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="54b6d-154">Sie können auch `UseAspNetRoles` angeben, um einen benutzerdefinierten Rollen Anbieter zu verwenden, der unter dem @no__t -1System. Web >-Element konfiguriert ist, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="54b6d-154">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code:</span></span>

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
  
<span data-ttu-id="54b6d-155">Der folgende Code zeigt den `roleProviderName`-Wert, der mit dem `principalPermissionMode`-Attribut verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="54b6d-155">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute:</span></span>
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

<span data-ttu-id="54b6d-156">Ein ausführliches Beispiel für die Verwendung dieses Konfigurations Elements finden Sie unter [Autorisieren des Zugriffs auf Dienst Vorgänge](../../../wcf/samples/authorizing-access-to-service-operations.md) und [Autorisierungs Richtlinien](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="54b6d-156">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="54b6d-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54b6d-157">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="54b6d-158">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="54b6d-158">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="54b6d-159">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="54b6d-159">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- <span data-ttu-id="54b6d-160">[Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="54b6d-160">[How to: Create a Custom Authorization Manager for a Service](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)</span></span>
- <span data-ttu-id="54b6d-161">[Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="54b6d-161">[How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)</span></span>
- [<span data-ttu-id="54b6d-162">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="54b6d-162">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
