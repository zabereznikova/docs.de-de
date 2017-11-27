---
title: '&lt;add&gt; von &lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5166f7859bb3e914de8313de08427cda9bc06d6f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltserviceactivationsgt"></a>&lt;add&gt; von &lt;serviceActivations&gt;
Ein Konfigurationselement, das Ihnen ermöglicht, virtuelle Dienstaktivierungseinstellungen zu definieren, die Ihren [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Diensttypen entsprechen. Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.  
  
 \<System. ServiceModel >  
\<ServiceHostingEnvironment >  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|factory|Eine Zeichenfolge, die den CLR-Typnamen der Factory angibt, die ein Dienstaktivierungselement generiert.|  
|service|Der ServiceType, der den Dienst implementiert (entweder der vollqualifizierte Typname oder der kurze Typname, falls im Ordner "App_Code" enthalten).|  
|relativeAddress|Die relative Adresse innerhalb der aktuellen IIS-Anwendung, z. B. "Service.svc". In WCF 4.0 muss diese relative Adresse eine der gültigen Dateierweiterungen (.svc, .xamlx, …) enthalten. Für relativeUrl muss keine physische Datei vorhanden sein.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ServiceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Ein Konfigurationsabschnitt, der Aktivierungseinstellungen beschreibt.|  
  
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
 <xref:System.ServiceModel.Configuration.ServiceActivationElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
