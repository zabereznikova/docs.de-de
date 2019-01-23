---
title: '&lt;authorizationPolicies&gt;'
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 7648c221a61efb99b4dc486f9b4d121439632c63
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519553"
---
# <a name="ltauthorizationpoliciesgt"></a><span data-ttu-id="c8034-102">&lt;authorizationPolicies&gt;</span><span class="sxs-lookup"><span data-stu-id="c8034-102">&lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="c8034-103">Dieser Konfigurationsabschnitt enthält eine Auflistung der Autorisierungsrichtlinien-Typen, die mithilfe des `add`-Schlüsselworts hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="c8034-103">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="c8034-104">Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="c8034-104">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="c8034-105">Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c8034-105">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="c8034-106">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="c8034-106">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="c8034-107">Weitere Informationen zur Funktionsweise einer Autorisierungsrichtlinie finden Sie unter <xref:System.IdentityModel.Policy.IAuthorizationPolicy> und [Autorisierungsrichtlinie](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="c8034-107">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8034-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8034-108">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="c8034-109">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="c8034-109">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="c8034-110">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="c8034-110">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="c8034-111">\<add></span><span class="sxs-lookup"><span data-stu-id="c8034-111">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="c8034-112">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c8034-112">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
