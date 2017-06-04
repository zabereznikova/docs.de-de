---
title: "&lt;certificateValidation&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;certificateValidation&gt;
Steuert die Einstellungen, mit denen Token Ereignishandler verwenden, um Zertifikate zu überprüfen.  Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit seinem eigenen Validierungssteuerelement konfiguriert ist.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|certificateValidationMode|Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Validierung Wert, der den Modus angibt, der für das X.509\-Zertifikat zu verwenden.  Der Standardwert ist „PeerOrChainTrust“.  Um ein benutzerdefiniertes Validierungssteuerelement anzugeben, legen Sie dieses Attribut „Custom“ fest, und geben Sie das Validierungssteuerelement mithilfe des [\<certificateValidator\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)\-Elements an.  Optional.|  
|revocationMode|Ein Wert, der den <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> deaktivieren Sie den Modus angibt, der für das X.509\-Zertifikat zu verwenden.  Der Standardwert ist „Online“.  Optional.|  
|trustedStoreLocation|Ein Wert, der den <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509\-Zertifikatspeicher angibt.  Der Standardwert ist „LocalMachine“.  Optional.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<certificateValidator\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|Gibt einen benutzerdefinierten Typ zur Zertifikatsvalidierung an.  Dieser Typ wird nur verwendet, wenn das `certificateValidationMode`\-Attribut des [\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)\-Elements set „Custom“ ist.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt die Identität von Einstellungen auf Dienstebene auf.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt Konfiguration für eine Auflistung von Sicherheitstoken Ereignishandler bereit.|  
  
## Hinweise  
 Ein Element kann `<certificateValidation>` auf dem Servicelevel unter dem `<identityConfiguration>`\-Element oder in der Auflistung der Klassenhandler Sicherheitstoken angegeben werden, die unter dem Element `<securityTokenHandlerConfiguration>`.  Einstellungen für eine Auflistung von Token für die überschreiben, die auf dem Dienst angegeben werden.  Einige Token für validierungs Zertifikats bieten die Möglichkeit, Einstellungen in der Konfiguration anzugeben.  Einstellungen auf einzelnen Token handlern überschreiben die auf dem angegebenen Sicherheitstoken Klassenhandler und Servicelevel in der Auflistung.  
  
## Beispiel  
  
```  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```