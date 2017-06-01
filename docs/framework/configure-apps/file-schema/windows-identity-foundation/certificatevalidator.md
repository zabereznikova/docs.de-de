---
title: "&lt;certificateValidator&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;certificateValidator&gt;
Gibt einen benutzerdefinierten Typ zur Zertifikatsvalidierung.  Dieser Typ wird verwendet, wenn nur die `certificateValidationMode` \-Attribut des der [\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) Element auf "Custom" festgelegt ist.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|type|Gibt einen benutzerdefinierten Typ, der von abgeleitet wird die <xref:System.IdentityModel.Selectors.X509CertificateValidator> Klasse.  Festlegen der `certificateValidationMode` \-Attribut des der [\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) Element auf "Custom" verwenden.  Weitere Informationen zum Angeben der `type` \-Attribut, finden Sie unter [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).  Optional.|  
  
### Untergeordnete Elemente  
 None  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Steuert die Einstellungen, die Tokenhandler verwenden, um Zertifikate zu überprüfen.|  
  
## Beispiel  
  
```  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```