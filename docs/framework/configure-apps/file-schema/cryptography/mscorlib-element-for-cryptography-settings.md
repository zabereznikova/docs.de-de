---
title: "&lt;mscorlib&gt;-Element f&#252;r Kryptografieklassen | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<mscorlib>-Element"
  - "mscorlib-Element"
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;mscorlib&gt;-Element f&#252;r Kryptografieklassen
Enthält [\<cryptographySettings\>\-Element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).  
  
## Syntax  
  
```  
  
      <mscorlib>   
</mscorlib>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`cryptographySettings`|Enthält Kryptografieeinstellungen.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie das Element **\<mscorlib\>**, um eine mehr zu verweisen verwendet und die Laufzeit zu konfigurieren.  Sie können dann die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=fullName>\-Methode übergeben und mithilfe der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>\-Methode ein `MyCryptoRSAClass`\-Objekt zurückgeben.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>   
 <xref:System.Security.Cryptography>   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Schema für Kryptografieeinstellungen](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)   
 [Konfigurieren kryptografischer Klassen](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)