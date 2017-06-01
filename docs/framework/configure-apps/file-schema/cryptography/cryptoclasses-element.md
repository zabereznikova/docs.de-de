---
title: "&lt;cryptoClasses&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<cryptoClasses>-Element"
  - "cryptoClasses-Element"
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# &lt;cryptoClasses&gt;-Element
Enthält eine Liste von kryptografischen Klassen, die eine Zuordnung in einen Anzeigenamen im [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)\-Element verfügen.  
  
## Syntax  
  
```  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|Enthält eine mehr, die eine Zuordnung in einen Anzeigenamen im **\<nameEntry\>**\-Element verfügt.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`cryptographySettings`|Enthält Kryptografieeinstellungen.|  
|`cryptoNameMapping`|Enthält Zuordnungen von Klassen zu angezeigten Namen.|  
|`mscorlib`|Enthält das `cryptographySettings`\-Element.|  
  
## Beispiel  
 Das folgende Beispiel wie mit dem **\<cryptoClass\>**\-Element, eine mehr verweisen und die Laufzeit zu konfigurieren.  Sie können dann die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=fullName>\-Methode übergeben und mithilfe der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>\-Methode ein `MyCryptoRSAClass`\-Objekt zurückgeben.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Security.Cryptography>   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Schema für Kryptografieeinstellungen](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)   
 [System.Security.Cryptography.CryptoConfig.CreateFromName](frlrfSystemSecurityCryptographyCryptoConfigClassCreateFromNameTopic)   
 [Konfigurieren kryptografischer Klassen](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)