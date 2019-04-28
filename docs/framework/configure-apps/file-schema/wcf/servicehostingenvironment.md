---
title: <serviceHostingEnvironment>
ms.date: 03/30/2017
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
ms.openlocfilehash: 24cf36aba81b5bb31eaac475361e2d07bc6f8b12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788400"
---
# <a name="servicehostingenvironment"></a>\<serviceHostingEnvironment>
Dieses Element definiert den Typ, der von der Diensthostingumgebung für einen bestimmten Transport instanziiert wird. Falls dieses Element leer ist, wird der Standardtyp verwendet. Dieses Element kann nur über die Anwendungskonfigurationsdatei bzw. die Computerkonfigurationsdatei verwendet werden.  
  
 \<system.ServiceModel>  
\<ServiceHostingEnvironment>  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|aspNetCompatibilityEnabled|Ein boolescher Wert, der angibt, ob der ASP.NET-Kompatibilitätsmodus für die aktuelle Anwendung aktiviert wurde. Die Standardeinstellung ist `false`.<br /><br /> Wenn dieses Attribut festgelegt ist, um `true`, Anforderungen an Windows Communication Foundation (WCF)-Dienste über die ASP.NET HTTP-Pipeline zu übertragen und Kommunikation über nicht-HTTP-Protokolle ist nicht zulässig. Weitere Informationen finden Sie unter [WCF-Dienste und ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).|  
|minFreeMemoryPercentageToActivateService|Eine ganze Zahl, die die Mindestmenge des freien Speichers gibt an, die auf dem System verfügbar sein sollen, bevor ein WCF-Dienst aktiviert werden kann. **Vorsicht**:  Durch Angeben dieses Attributs zusammen mit teilweiser Vertrauenswürdigkeit in der Datei "Web.config" von einem WCF-Dienst führt zu einem <xref:System.Security.SecurityException> Wenn der Dienst ausgeführt wird.|  
|multipleSiteBindingsEnabled|Ein boolescher Wert, der angibt, ob mehrere IIS-Bindungen pro Website aktiviert sind.<br /><br /> IIS besteht aus Websites, die als Container für virtuelle Anwendungen fungieren, die virtuelle Verzeichnisse enthalten. Auf die Anwendung auf einer Website kann über eine oder mehrere IIS-Bindungen zugegriffen werden. IIS-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen. Das Bindungsprotokoll definiert das Schema, das für die Kommunikation verwendet wird, und die Bindungsinformationen dienen dem Zugriff auf die Website. Ein Beispiel für ein Bindungsprotokoll kann HTTP sein, wohingegen Bindungsinformationen eine IP-Adresse, einen Port, einen Hostheader usw. enthalten können.<br /><br /> IIS unterstützt die Angabe mehrerer IIS-Bindungen pro Website, was zu mehreren Basisadressen pro Schema führt. Allerdings kann ein Windows Communication Foundation (WCF)-Dienst unter einer Website gehosteter Bindung an nur einem BaseAddress-Element pro Schema.<br /><br /> Um mehrere IIS-Bindungen pro Website für einen Windows Communication Foundation (WCF)-Dienst zu aktivieren, legen Sie dieses Attribut auf `true`. Beachten Sie, dass mehrere Bindungen pro Website nur für das HTTP-Protokoll unterstützt werden. Die Adresse der Endpunkte in der Konfigurationsdatei muss ein vollständiger URI sein.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|Eine Auflistung der Konfigurationselemente, die den Präfixfilter für die vom Diensthost verwendeten Basisadressen angeben.|  
|[\<serviceActivations>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceactivations.md)|Ein Konfigurationsabschnitt, der Aktivierungseinstellungen beschreibt.|  
|[\<transportConfigurationTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|Eine Auflistung der Konfigurationselemente, die den Typ eines bestimmten Transports identifizieren.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|serviceModel|Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.|  
  
## <a name="remarks"></a>Hinweise  
 WCF-Dienste werden in gehosteten Anwendungsdomänen (AppDomain) standardmäßig zusammen mit ASP.NET ausgeführt. Selbst wenn WCF und ASP.NET in derselben AppDomain gleichzeitig ausgeführt werden können, werden die WCF-Anforderungen nicht standardmäßig von der ASP.NET-HTTP-Pipeline verarbeitet. Folglich stehen einige Elemente der ASP.NET-Anwendungsplattform nicht für WCF-Dienste zur Verfügung. Dazu gehören  
  
- ASP.NET-Datei-/URL-Autorisierung  
  
- ASP.NET-Identitätswechsel  
  
- Cookiebasierter Sitzungszustand  
  
- HttpContext.Current  
  
- Pipeline-Erweiterbarkeit über benutzerdefiniertes HttpModule  
  
 Falls Ihre WCF-Dienste im ASP.NET-Kontext funktionieren müssen und nur über HTTP kommunizieren, können Sie den ASP.NET-Kompatibilitätsmodus von WCF verwenden. Dieser Modus wird aktiviert, wenn das `aspNetCompatibilityEnabled`-Attribut auf Anwendungsebene auf `true` festgelegt ist. Die Dienstimplementierungen müssen die Möglichkeit, im Kompatibilitätsmodus ausgeführt zu werden, mit der <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>-Klasse deklarieren. Wenn der Kompatibilitätsmodus aktiviert ist,  
  
- wird vor der WCF-Autorisierung die ASP.NET-Datei-/URL-Autorisierung erzwungen. Eine Autorisierungsentscheidung basiert auf der Anforderungsidentität auf der Transportebene. Identitäten auf der Nachrichtenebene werden ignoriert.  
  
- beginnen die WCF-Dienstvorgänge mit der Ausführung im ASP.NET-Identitätswechselkontext. Falls sowohl der ASP.NET-Identitätswechsel als auch der WCF-Identitätswechsel für einen bestimmten Dienst aktiviert sind, gilt der WCF-Identitätswechselkontext.  
  
- kann HttpContext.Current im WCF-Dienstcode verwendet werden. Die Dienste werden daran gehindert, Nicht-HTTP-Endpunkte verfügbar zu machen.  
  
- werden die WCF-Anforderungen von der ASP.NET-Pipeline verarbeitet. HttpModules, die für eingehende Anforderungen konfiguriert wurden, können ebenfalls WCF-Anforderungen verarbeiten. Dazu gehören ASP.NET-Plattformkomponenten (z.&amp;#160;B. <xref:System.Web.SessionState.SessionStateModule>) sowie benutzerdefinierte Drittanbietermodule.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt, wie der ASP-Kompatibilitätsmodus aktiviert wird.  
  
## <a name="code"></a>Code  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [Hosting](../../../../../docs/framework/wcf/feature-details/hosting.md)
- [WCF-Dienste und ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
