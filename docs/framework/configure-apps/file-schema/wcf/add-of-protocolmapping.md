---
title: "&lt;add&gt; von &lt;protocolMapping&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;add&gt; von &lt;protocolMapping&gt;
Stellt eine Standardprotokollzuordnung zwischen einem Transportprotokollschema \(z. B. http, net.tcp, net.pipe usw.\) und einer [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Bindung dar.  Beim Erstellen von Standardendpunkten zur Laufzeit prüft [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] die konfigurierten Zuordnungen und wählt die für eine bestimmte Basisadresse zu verwendende Bindung.  
  
## Syntax  
  
```vb  
  
<protocolMapping>  
    <add binding="String”  
         bindingConfiguration="String”  
         scheme="http/net.msmq/net.pipe/net.tcp"/>  
</protocolMapping>  
  
```  
  
```csharp  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Element|Beschreibung|  
|-------------|------------------|  
|Bindung|Eine Zeichenfolge, die den Typ der Bindung angibt, die während der Standardendpunkterstellung für einen Endpunkt verwendet werden soll.|  
|bindingConfiguration|Eine Zeichenfolge, die den Namen des Bindungskonfigurationsabschnitts angibt, auf den verwiesen werden soll.|  
|scheme|Das für den Standardendpunkt zu verwendende Transportprotokollschema.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<protocolMapping\>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Stellt einen Konfigurationsabschnitt zur Definition von Standardprotokollzuordnungen zwischen Transportprotokollschemas \(z. B. http, net.tcp, net.pipe usw.\) und [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Bindungen dar.|  
  
## Beispiel  
 Im folgenden Konfigurationsbeispiel wird die Standardprotokollzuordnung in der Datei machine.config veranschaulicht.  Sie können diese Standardzuordnung auf Computerebene überschreiben, indem Sie die Datei machine.config ändern.  Wenn Sie sie lediglich innerhalb des Bereichs einer Anwendung überschreiben möchten, können Sie diesen Abschnitt innerhalb der Anwendungskonfigurationsdatei überschreiben und die Zuordnung für einzelne Protokollschemas ändern.  
  
```  
  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
  
```  
  
## Siehe auch  
 [System.ServiceModel.Configuration.ProtocolMappingSection](assetId:///System.ServiceModel.Configuration.ProtocolMappingSection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.ServiceModel.Configuration.ProtocolMappingElement](assetId:///System.ServiceModel.Configuration.ProtocolMappingElement?qualifyHint=False&amp;autoUpgrade=True)