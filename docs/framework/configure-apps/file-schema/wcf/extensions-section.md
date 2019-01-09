---
title: '&lt;extensions&gt;-Abschnitt'
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 92dd3c528290344d9537c51fccf7c13c74c1984a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145314"
---
# <a name="ltextensionsgt-section"></a>&lt;extensions&gt;-Abschnitt
Dieser Konfigurationsabschnitt enthält eine Auflistung von Erweiterungen, mit deren Hilfe der Benutzer benutzerdefinierte Bindungen, Verhalten und andere Aspekte der Erweiterungen erstellen kann.  
  
\<system.ServiceModel>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
    </bindingExtensions>
    <behaviorExtensions>
    </behaviorExtensions>
    <bindingElementExtensions>
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<BehaviorExtensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md)|Dieser Abschnitt enthält Unterelemente mit Verhaltenserweiterungen, die es dem Benutzer ermöglichen, das Verhalten eines Diensts oder Endpunkts anzupassen.|  
|[\<BindingElementExtensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)|Dieser Abschnitt aktiviert die Verwendung eines benutzerdefinierten Elements für einen Computer oder eine Anwendungskonfigurationsdatei.|  
|[\<BindingExtensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingextensions.md)|Dieser Abschnitt enthält Unterelemente mit Bindungserweiterungen, die es dem Benutzer ermöglichen, Bindungen anzupassen.|  
|[\<EndpointExtensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointextensions.md)|Dieser Abschnitt enthält untergeordnete Elemente, die Standardendpunkte registrieren.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|system.ServiceModel|Das Stammelement aller WCF-Konfigurationselemente.|
