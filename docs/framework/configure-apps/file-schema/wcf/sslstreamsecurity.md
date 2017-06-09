---
title: "&lt;sslStreamSecurity&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
caps.latest.revision: 11
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 11
---
# &lt;sslStreamSecurity&gt;
Stellt ein benutzerdefiniertes binding\-Element dar, das die Channelsicherheit unter Verwendung eines SSL\-Datenstroms unterstützt.  
  
## Syntax  
  
```  
  
<sslStreamSecurity requireClientCertificate="Boolean"  
      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|requireClientCertificate|Ein boolescher Wert, der angibt, ob ein Clientzertifikat für diese Bindung erforderlich ist.  Die Standardeinstellung ist `false`.|  
|sslProtocols|Ein SslProtocols Enum\-Flagwert, der angibt, welche SslProtocols unterstützt werden.  Der Standardwert ist Ssl3&#124;Tls&#124;Tls11&#124;Tls12.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindung\>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)