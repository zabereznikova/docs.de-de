---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 38d123a53b344ff1e4d781115093d0d1de5ae679
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69926462"
---
# \<authorizationPolicies>
<span data-ttu-id="190ff-101">Dieser Konfigurationsabschnitt enthält eine Auflistung der Autorisierungsrichtlinien-Typen, die mithilfe des `add`-Schlüsselworts hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="190ff-101">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="190ff-102">Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="190ff-102">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="190ff-103">Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="190ff-103">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="190ff-104">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="190ff-104">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="190ff-105">Weitere Informationen zur Funktionsweise von Autorisierungs Richtlinien finden Sie unter <xref:System.IdentityModel.Policy.IAuthorizationPolicy> und [Autorisierungs Richtlinien](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="190ff-105">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="190ff-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="190ff-106">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="190ff-107">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="190ff-107">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="190ff-108">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="190ff-108">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="190ff-109">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="190ff-109">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
