---
title: "&lt;cryptographySettings&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<cryptographySettings>-Element"
  - "cryptographySettings-Element"
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;cryptographySettings&gt;-Element
Enthält Kryptografieeinstellungen.  
  
## Syntax  
  
```  
  
      <cryptographySettings>   
</crytopgraphySettings>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<CryptoNameMapping\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|Enthält Zuordnungen von Klassen zu angezeigten Namen.|  
|[\<oidMap\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|Enthält ASN.1‑OID\-Zuordnungen zu Klassen.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`mscorlib`|Enthält das `cryptographySettings`\-Element.|  
  
## Beispiel  
 Das folgende Beispiel wie mit dem **\<cryptographySettings\>** Kryptographienamenzuordnungen Element, und OID\-Zuordnungen zu enthalten.  In diesem Beispiel wird die Laufzeit so konfiguriert, dass [System.Security.Cryptography.HashAlgorithm.Create](frlrfSystemSecurityCryptographyHashAlgorithmClassCreateTopic) ein `MyHashClass`\-Objekt zurückgibt und die `MyCryptoClass`\-Klasse dem Objektbezeichner 1.3.36.3.2.1 zugeordnet wird.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## Siehe auch  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Schema für Kryptografieeinstellungen](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)