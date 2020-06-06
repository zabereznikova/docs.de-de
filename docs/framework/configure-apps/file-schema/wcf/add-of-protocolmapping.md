---
title: <add> von <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 6197d01665d49a7c97ac9e44251abf15faf80a8f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850378"
---
# <a name="add-of-protocolmapping"></a>\<add> von \<protocolMapping>
Stellt eine Standardprotokoll Zuordnung zwischen einem Transportprotokoll Schema (z. b. http, net. TCP, net. Pipe usw.) und einer Windows Communication Foundation (WCF)-Bindung dar. Beim Erstellen von Standard Endpunkten zur Laufzeit prüft WCF die konfigurierten Zuordnungen und entscheidet, welche Bindung für eine bestimmte basierte Adresse verwendet werden soll.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|binding|Eine Zeichenfolge, die den Typ der Bindung angibt, die während der Standardendpunkterstellung für einen Endpunkt verwendet werden soll.|  
|bindingConfiguration|Eine Zeichenfolge, die den Namen des Bindungskonfigurationsabschnitts angibt, auf den verwiesen werden soll.|  
|scheme|Das für den Standardendpunkt zu verwendende Transportprotokollschema.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|Stellt einen Konfigurations Abschnitt zum Definieren von Standardprotokoll Zuordnungen zwischen Transportprotokoll Schemas (z. b. http, net. TCP, net. Pipe usw.) und Windows Communication Foundation (WCF)-Bindungen dar.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Konfigurationsbeispiel wird die Standardprotokollzuordnung in der Datei machine.config veranschaulicht. Sie können diese Standardzuordnung auf Computerebene überschreiben, indem Sie die Datei machine.config ändern. Wenn Sie sie lediglich innerhalb des Bereichs einer Anwendung überschreiben möchten, können Sie diesen Abschnitt innerhalb der Anwendungskonfigurationsdatei überschreiben und die Zuordnung für einzelne Protokollschemas ändern.  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
