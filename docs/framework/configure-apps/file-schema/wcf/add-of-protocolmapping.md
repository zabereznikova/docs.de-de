---
title: '&lt;add&gt; von &lt;protocolMapping&gt;'
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: b9559a6921bdededf760f54f58abadb46612b174
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a>&lt;add&gt; von &lt;protocolMapping&gt;
Stellt eine standardprotokollzuordnung zwischen einem transportprotokollschema (z. B. http, net.tcp, net.pipe usw.) und einer Bindung Windows Communication Foundation (WCF) dar. Beim Erstellen von Standardendpunkten zur Laufzeit prüft [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] die konfigurierten Zuordnungen und wählt die für eine bestimmte Basisadresse zu verwendende Bindung.  
  
 \<system.serviceModel>  
\<ProtocolMapping >  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Bindung|Eine Zeichenfolge, die den Typ der Bindung angibt, die während der Standardendpunkterstellung für einen Endpunkt verwendet werden soll.|  
|bindingConfiguration|Eine Zeichenfolge, die den Namen des Bindungskonfigurationsabschnitts angibt, auf den verwiesen werden soll.|  
|scheme|Das für den Standardendpunkt zu verwendende Transportprotokollschema.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ProtocolMapping >](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Stellt einen Konfigurationsabschnitt zur Definition von standardprotokollzuordnungen zwischen transportprotokollschemas (z. B. http, net.tcp, net.pipe usw.) und Windows Communication Foundation (WCF)-Bindungen dar.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Konfigurationsbeispiel wird die Standardprotokollzuordnung in der Datei machine.config veranschaulicht. Sie können diese Standardzuordnung auf Computerebene überschreiben, indem Sie die Datei machine.config ändern. Wenn Sie sie lediglich innerhalb des Bereichs einer Anwendung überschreiben möchten, können Sie diesen Abschnitt innerhalb der Anwendungskonfigurationsdatei überschreiben und die Zuordnung für einzelne Protokollschemas ändern.  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
