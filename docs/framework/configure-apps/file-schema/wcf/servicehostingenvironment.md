---
title: <serviceHostingEnvironment>
ms.date: 03/30/2017
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
ms.openlocfilehash: 5a7043064593fa329618510d15baeb87da432652
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167097"
---
# \<serviceHostingEnvironment>

Dieses Element definiert den Typ, der von der Diensthostingumgebung für einen bestimmten Transport instanziiert wird. Falls dieses Element leer ist, wird der Standardtyp verwendet. Dieses Element kann nur über die Anwendungskonfigurationsdatei bzw. die Computerkonfigurationsdatei verwendet werden.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceHostingEnvironment>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean"
                           minFreeMemoryPercentageToActivateService="Integer"
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|aspNetCompatibilityEnabled|Ein boolescher Wert, der angibt, ob der ASP.NET-Kompatibilitätsmodus für die aktuelle Anwendung aktiviert wurde. Der Standardwert lautet `false`.<br /><br /> Wenn dieses Attribut auf festgelegt ist `true` , werden Anforderungen an Windows Communication Foundation (WCF)-Dienste über die ASP.NET-HTTP-Pipeline geleitet, und die Kommunikation über nicht-HTTP-Protokolle ist unzulässig. Weitere Informationen finden Sie unter [WCF-Dienste und ASP.net](../../../wcf/feature-details/wcf-services-and-aspnet.md).|  
|minFreeMemoryPercentageToActivateService|Eine ganze Zahl, die den minimalen freien Speicherplatz angibt, der für das System verfügbar sein sollte, bevor ein WCF-Dienst aktiviert werden kann. **Vorsicht:**  Wenn Sie dieses Attribut zusammen mit teilweiser Vertrauenswürdigkeit in der web.config-Datei eines WCF-dienstanweises angeben, führt dies zu einer, <xref:System.Security.SecurityException> Wenn der Dienst ausgeführt wird.|  
|multipleSiteBindingsEnabled|Ein boolescher Wert, der angibt, ob mehrere IIS-Bindungen pro Website aktiviert sind.<br /><br /> IIS besteht aus Websites, die als Container für virtuelle Anwendungen fungieren, die virtuelle Verzeichnisse enthalten. Auf die Anwendung auf einer Website kann über eine oder mehrere IIS-Bindungen zugegriffen werden. IIS-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen. Das Bindungsprotokoll definiert das Schema, das für die Kommunikation verwendet wird, und die Bindungsinformationen dienen dem Zugriff auf die Website. Ein Beispiel für ein Bindungsprotokoll kann HTTP sein, wohingegen Bindungsinformationen eine IP-Adresse, einen Port, einen Hostheader usw. enthalten können.<br /><br /> IIS unterstützt die Angabe mehrerer IIS-Bindungen pro Website, was zu mehreren Basisadressen pro Schema führt. Ein Windows Communication Foundation (WCF)-Dienst, der unter einer Site gehostet wird, ermöglicht jedoch nur das Binden an eine BaseAddress pro Schema.<br /><br /> Um mehrere IIS-Bindungen pro Website für einen Windows Communication Foundation (WCF)-Dienst zu aktivieren, legen Sie dieses Attribut auf fest `true` . Beachten Sie, dass mehrere Bindungen pro Website nur für das HTTP-Protokoll unterstützt werden. Die Adresse der Endpunkte in der Konfigurationsdatei muss ein vollständiger URI sein.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters>](baseaddressprefixfilters.md)|Eine Auflistung der Konfigurationselemente, die den Präfixfilter für die vom Diensthost verwendeten Basisadressen angeben.|  
|[\<serviceActivations>](serviceactivations.md)|Ein Konfigurationsabschnitt, der Aktivierungseinstellungen beschreibt.|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|Eine Auflistung der Konfigurationselemente, die den Typ eines bestimmten Transports identifizieren.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|serviceModel|Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.|  
  
## <a name="remarks"></a>Bemerkungen  

 WCF-Dienste werden in gehosteten Anwendungsdomänen (AppDomain) standardmäßig zusammen mit ASP.NET ausgeführt. Selbst wenn WCF und ASP.NET in derselben AppDomain gleichzeitig ausgeführt werden können, werden die WCF-Anforderungen nicht standardmäßig von der ASP.NET-HTTP-Pipeline verarbeitet. Folglich stehen einige Elemente der ASP.NET-Anwendungsplattform nicht für WCF-Dienste zur Verfügung. Dies sind:  
  
- ASP.NET-Datei-/URL-Autorisierung  
  
- ASP.NET-Identitätswechsel  
  
- Cookiebasierter Sitzungszustand  
  
- HttpContext.Current  
  
- Pipeline-Erweiterbarkeit über benutzerdefiniertes HttpModule  
  
 Falls Ihre WCF-Dienste im ASP.NET-Kontext funktionieren müssen und nur über HTTP kommunizieren, können Sie den ASP.NET-Kompatibilitätsmodus von WCF verwenden. Dieser Modus wird aktiviert, wenn das `aspNetCompatibilityEnabled`-Attribut auf Anwendungsebene auf `true` festgelegt ist. Die Dienstimplementierungen müssen die Möglichkeit, im Kompatibilitätsmodus ausgeführt zu werden, mit der <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>-Klasse deklarieren. Wenn der Kompatibilitätsmodus aktiviert ist,  
  
- wird vor der WCF-Autorisierung die ASP.NET-Datei-/URL-Autorisierung erzwungen. Eine Autorisierungsentscheidung basiert auf der Anforderungsidentität auf der Transportebene. Identitäten auf der Nachrichtenebene werden ignoriert.  
  
- beginnen die WCF-Dienstvorgänge mit der Ausführung im ASP.NET-Identitätswechselkontext. Falls sowohl der ASP.NET-Identitätswechsel als auch der WCF-Identitätswechsel für einen bestimmten Dienst aktiviert sind, gilt der WCF-Identitätswechselkontext.  
  
- kann HttpContext.Current im WCF-Dienstcode verwendet werden. Die Dienste werden daran gehindert, Nicht-HTTP-Endpunkte verfügbar zu machen.  
  
- werden die WCF-Anforderungen von der ASP.NET-Pipeline verarbeitet. HttpModules, die für eingehende Anforderungen konfiguriert wurden, können ebenfalls WCF-Anforderungen verarbeiten. Dazu gehören ASP.NET-Plattformkomponenten (z.&#160;B. <xref:System.Web.SessionState.SessionStateModule>) sowie benutzerdefinierte Drittanbietermodule.  
  
## <a name="example"></a>Beispiel  

 Das folgende Codebeispiel zeigt, wie der ASP-Kompatibilitätsmodus aktiviert wird.  
  
## <a name="code"></a>Code  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [Hosting](../../../wcf/feature-details/hosting.md)
- [WCF-Dienste und ASP.NET](../../../wcf/feature-details/wcf-services-and-aspnet.md)
