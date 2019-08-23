---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 38d123a53b344ff1e4d781115093d0d1de5ae679
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926462"
---
# <a name="authorizationpolicies"></a><span data-ttu-id="f951b-101">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="f951b-101">\<authorizationPolicies></span></span>
<span data-ttu-id="f951b-102">Dieser Konfigurationsabschnitt enthält eine Auflistung der Autorisierungsrichtlinien-Typen, die mithilfe des `add`-Schlüsselworts hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="f951b-102">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="f951b-103">Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="f951b-103">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="f951b-104">Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f951b-104">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="f951b-105">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="f951b-105">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="f951b-106">Weitere Informationen zur Funktionsweise von Autorisierungs Richtlinien finden <xref:System.IdentityModel.Policy.IAuthorizationPolicy> Sie unter und [Autorisierungs Richtlinien](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f951b-106">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f951b-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f951b-107">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="f951b-108">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="f951b-108">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="f951b-109">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="f951b-109">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="f951b-110">\<add></span><span class="sxs-lookup"><span data-stu-id="f951b-110">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="f951b-111">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="f951b-111">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
