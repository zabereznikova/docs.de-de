---
title: '&lt;policyImporter&gt;'
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 22d90ff9d0cd5325300cf42437836f075cbf8c31
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148486"
---
# <a name="ltpolicyimportergt"></a>&lt;policyImporter&gt;
Gibt einen Richtlinienimporter an, der den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuert.  
  
 \<system.ServiceModel>  
\<Client >  
\<Metadaten >  
\<PolicyImporters >  
\<PolicyImporter >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`type`|Der Typ dieses Elements.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<PolicyImporters >](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.|  
  
## <a name="remarks"></a>Hinweise  
 Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfunktionen gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Funktionen implementiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [WCF-Clientkonfiguration](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [Clients](../../../../../docs/framework/wcf/feature-details/clients.md)
