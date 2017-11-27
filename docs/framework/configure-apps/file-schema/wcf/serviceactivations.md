---
title: '&lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a4f05b8164c0920893ea5b379017b1eb91f1b37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltserviceactivationsgt"></a>&lt;serviceActivations&gt;
Ein Konfigurationselement, das Ihnen ermöglicht, Einstellungen zur Definition virtueller Dienstaktivierungseinstellungen hinzuzufügen, die Ihren [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Diensttypen entsprechen. Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.  
  
 \<System. ServiceModel >  
\<ServiceHostingEnvironment >  
\<ServiceActivations >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|Fügt ein Konfigurationselement hinzu, das die Aktivierung einer Dienstanwendung angibt.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ServiceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.|  
  
## <a name="remarks"></a>Hinweise  
 Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei web.config konfiguriert werden.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 Mit dieser Konfiguration können Sie das GreetingService-Element aktivieren, ohne eine SVC-Datei zu verwenden.  
  
 Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt. Sie müssen das `web.config`-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren. Außerdem ist `serviceHostingEnvironment` ein machinetoApplication-vererbbarer Abschnitt. Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.  
  
 Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll. Sie erfordert Erweiterungen im relatativeAddress-Element, z. B. .svc, .xoml oder .xamlx. Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren. Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC-Registrierungen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
