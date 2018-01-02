---
title: '&lt;serviceHostingEnvironment&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a08df7c620065bb483d276e3ead2c179040f1c9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicehostingenvironmentgt"></a>&lt;serviceHostingEnvironment&gt;
Dieses Element definiert den Typ, der von der Diensthostingumgebung für einen bestimmten Transport instanziiert wird. Falls dieses Element leer ist, wird der Standardtyp verwendet. Dieses Element kann nur über die Anwendungskonfigurationsdatei bzw. die Computerkonfigurationsdatei verwendet werden.  
  
 \<System. ServiceModel >  
\<ServiceHostingEnvironment >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean" 
                           minFreeMemoryPercentageToActivateService="Integer" 
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String" service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String" transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|aspNetCompatibilityEnabled|Ein boolescher Wert, der angibt, ob der ASP.NET-Kompatibilitätsmodus für die aktuelle Anwendung aktiviert wurde. Die Standardeinstellung ist `false`.<br /><br /> Wenn dieses Attribut auf `true` festgelegt wird, fließen die Anforderungen an die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienste durch die ASP.NET-HTTP-Pipeline, und die Kommunikation über Nicht-HTTP-Protokolle wird untersagt. Weitere Informationen finden Sie unter [WCF-Dienste und ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).|  
|minFreeMemoryPercentageToActivateService|Eine ganze Zahl, welche die Mindestmenge des freien Arbeitsspeichers angibt, der auf dem System zur Verfügung stehen sollte, bevor ein [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienst aktiviert werden kann. **Vorsicht:** Festlegen dieses Attributs zusammen mit teilweiser Vertrauenswürdigkeit in der Datei "Web.config" ein [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Dienst führt zu einer <xref:System.Security.SecurityException> Wenn der Dienst ausgeführt wird.|  
|multipleSiteBindingsEnabled|Ein boolescher Wert, der angibt, ob mehrere IIS-Bindungen pro Website aktiviert sind.<br /><br /> IIS besteht aus Websites, die als Container für virtuelle Anwendungen fungieren, die virtuelle Verzeichnisse enthalten. Auf die Anwendung auf einer Website kann über eine oder mehrere IIS-Bindungen zugegriffen werden. IIS-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen. Das Bindungsprotokoll definiert das Schema, das für die Kommunikation verwendet wird, und die Bindungsinformationen dienen dem Zugriff auf die Website. Ein Beispiel für ein Bindungsprotokoll kann HTTP sein, wohingegen Bindungsinformationen eine IP-Adresse, einen Port, einen Hostheader usw. enthalten können.<br /><br /> IIS unterstützt die Angabe mehrerer IIS-Bindungen pro Website, was zu mehreren Basisadressen pro Schema führt. Ein unter einer Website gehosteter [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienst ermöglicht die Bindung zu nur einem baseAddress-Element pro Schema.<br /><br /> Um mehrere IIS-Bindungen pro Website für einen [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienst zu aktivieren, legen Sie dieses Attribut auf `true` fest. Beachten Sie, dass mehrere Bindungen pro Website nur für das HTTP-Protokoll unterstützt werden. Die Adresse der Endpunkte in der Konfigurationsdatei muss ein vollständiger URI sein.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<BaseAddressPrefixFilters >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|Eine Auflistung der Konfigurationselemente, die den Präfixfilter für die vom Diensthost verwendeten Basisadressen angeben.|  
|[\<ServiceActivations >](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceactivations.md)|Ein Konfigurationsabschnitt, der Aktivierungseinstellungen beschreibt.|  
|[\<TransportConfigurationTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|Eine Auflistung der Konfigurationselemente, die den Typ eines bestimmten Transports identifizieren.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|serviceModel|Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.|  
  
## <a name="remarks"></a>Hinweise  
 WCF-Dienste werden in gehosteten Anwendungsdomänen (AppDomain) standardmäßig zusammen mit ASP.NET ausgeführt. Selbst wenn WCF und ASP.NET in derselben AppDomain gleichzeitig ausgeführt werden können, werden die WCF-Anforderungen nicht standardmäßig von der ASP.NET-HTTP-Pipeline verarbeitet. Folglich stehen einige Elemente der ASP.NET-Anwendungsplattform nicht für WCF-Dienste zur Verfügung. Dazu gehören  
  
-   ASP.NET-Datei-/URL-Autorisierung  
  
-   ASP.NET-Identitätswechsel  
  
-   Cookiebasierter Sitzungszustand  
  
-   HttpContext.Current  
  
-   Pipeline-Erweiterbarkeit über benutzerdefiniertes HttpModule  
  
 Falls Ihre WCF-Dienste im ASP.NET-Kontext funktionieren müssen und nur über HTTP kommunizieren, können Sie den ASP.NET-Kompatibilitätsmodus von WCF verwenden. Dieser Modus wird aktiviert, wenn das `aspNetCompatibilityEnabled`-Attribut auf Anwendungsebene auf `true` festgelegt ist. Die Dienstimplementierungen müssen die Möglichkeit, im Kompatibilitätsmodus ausgeführt zu werden, mit der <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>-Klasse deklarieren. Wenn der Kompatibilitätsmodus aktiviert ist,  
  
-   wird vor der WCF-Autorisierung die ASP.NET-Datei-/URL-Autorisierung erzwungen. Eine Autorisierungsentscheidung basiert auf der Anforderungsidentität auf der Transportebene. Identitäten auf der Nachrichtenebene werden ignoriert.  
  
-   beginnen die WCF-Dienstvorgänge mit der Ausführung im ASP.NET-Identitätswechselkontext. Falls sowohl der ASP.NET-Identitätswechsel als auch der WCF-Identitätswechsel für einen bestimmten Dienst aktiviert sind, gilt der WCF-Identitätswechselkontext.  
  
-   kann HttpContext.Current im WCF-Dienstcode verwendet werden. Die Dienste werden daran gehindert, Nicht-HTTP-Endpunkte verfügbar zu machen.  
  
-   werden die WCF-Anforderungen von der ASP.NET-Pipeline verarbeitet. HttpModules, die für eingehende Anforderungen konfiguriert wurden, können ebenfalls WCF-Anforderungen verarbeiten. Dazu gehören ASP.NET-Plattformkomponenten (z.&#160;B. <xref:System.Web.SessionState.SessionStateModule>) sowie benutzerdefinierte Drittanbietermodule.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt, wie der ASP-Kompatibilitätsmodus aktiviert wird.  
  
## <a name="code"></a>Code  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [Hosting](../../../../../docs/framework/wcf/feature-details/hosting.md)  
 [WCF-Dienste und ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
