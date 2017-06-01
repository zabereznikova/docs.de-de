---
title: "&lt;oidMap&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<oidMap>-Element"
  - "oidMap-Element"
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;oidMap&gt;-Element
Enthält ASN.1‑OID\-Zuordnungen zu Klassen.  
  
## Syntax  
  
```  
<oidMap>   
</oidMap>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<oidEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|Ordnet einen ASN.1‑OID einem angezeigten Namen zu.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`cryptographySettings`|Enthält Kryptografieeinstellungen.|  
|`mscorlib`|Enthält das `cryptographySettings` \-Element.|  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie das Element **\<oidMap\>** verwendet, um eine Zuordnung eines OID für den Hashalgorithmus RIPEMD\-160 an eine Implementierung dieses Hashalgorithmus an.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## Siehe auch  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Schema für Kryptografieeinstellungen](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)   
 [Konfigurieren kryptografischer Klassen](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)   
 [Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)