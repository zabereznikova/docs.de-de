---
title: '&lt;clear&gt; von &lt;claimTypeRequirements&gt;'
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 1e77e3c978c1e385aec983d5e2d4bea64697c43e
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145288"
---
# <a name="ltcleargt-of-ltclaimtyperequirementsgt-element"></a>&lt;clear&gt; von &lt;claimTypeRequirements&gt;
Gibt an, dass alle Anspruchstypen in den verbundenen Anmeldeinformationen entfernt werden sollen. Dadurch wird sichergestellt, dass die Auflistung beim Starten leer ist.  
  
 \<system.ServiceModel>  
\<bindings>  
\<wsFederatedBinding>  
\<binding>  
\<Sicherheit >  
\<Meldung >  
\<ClaimTypeRequirements >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|Gibt eine Auflistung von erforderlichen Anspruchstypen an. Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.<br /><br /> In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest. Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen. Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
