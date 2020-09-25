---
title: <claimTypeRequirements> für <message>
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: e70b036fddbc706c8c16de9a0834140f600aa5ef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173795"
---
# <a name="claimtyperequirements-for-message"></a>\<claimTypeRequirements> für \<message>

Gibt eine Auflistung von erforderlichen Anspruchstypen an.  
  
 Die Auflistung wird vom Dienst verwendet, um erforderliche und optionale Ansprüche anzugeben, die sich in dem vom Client für den Dienstzugriff verwendeten ausgestellten Token befinden müssen. Der Dienst macht die erforderlichen Anspruchstypen in Metadaten verfügbar, wenn die WSDL-Veröffentlichung aktiviert wurde, aber WCF erfordert nicht, dass das ausgestellte Token die angegebenen Anspruchstypen enthält. Dienste, die versuchen, erforderliche Anspruchstypen durchzusetzen, sollten mit Autorisierungsrichtlinien verwendet werden.  
  
 Bei verbundenen Clients enthält diese Auflistung die Liste erforderlicher und optionaler Ansprüche, die an den Sicherheitstokendienst in der Clientanforderung für einen ausgestellten Token gesendet wird.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
