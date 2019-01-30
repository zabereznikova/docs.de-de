---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: d8f2b600b700a19cf587a6c8c4cc3f0e851edbd9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261279"
---
# <a name="contracttypenames"></a>\<contractTypeNames>
Ein Konfigurationsabschnitt, der eine Liste von Vertragstypnamen angibt, bei denen es sich um die Vertragsnamen der gesuchten Dienste handelt, sowie die Kriterien, die normalerweise beim Suchen nach einem Dienst verwendet werden. Wenn mehr als ein Vertragsname angegeben wird, antworten nur Dienstendpunkte, die ALLEN Verträgen entsprechen. Beachten Sie, dass in Windows Communication Foundation (WCF), ein Endpunkt nur als einen Vertrag unterstützen kann.  
  
 \<system.ServiceModel>  
\<standardEndpoints>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|Ein Vertragstypname ist eine Eigenschaft, die auf den Kriteriensatz verweist, der in der Regel beim Suchen nach einem Dienst verwendet wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<findCriteria>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird. Kriterien können in Suchkriterien (nach welchen Diensten soll gesucht werden, für die) gruppiert werden und Beendigungskriterien (wie lange soll die Suche dauern).|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
