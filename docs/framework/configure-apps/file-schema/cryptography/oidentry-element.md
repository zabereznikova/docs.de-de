---
title: "&lt;oidEntry&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<oidEntry>-Element"
  - "oidEntry-Element"
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;oidEntry&gt;-Element
Ordnet einen ASN.1‑Objektbezeichner \(OID\) einem angezeigten Namen zu.  
  
## Syntax  
  
```  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|**OID**|Erforderliches Attribut.<br /><br /> Gibt den ASN.1 ‑OID an, der dem von der Klasse implementierten Algorithmus entspricht.|  
|**name**|Erforderliches Attribut.<br /><br /> Gibt den Wert des **name** \-Attribut im [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)\-Tag an.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`cryptographySettings`|Enthält Kryptografieeinstellungen.|  
|`mscorlib`|Enthält das `cryptographySettings`\-Element.|  
|`oidMap`|Enthält ASN.1‑OID\-Zuordnungen zu Klassen.|  
  
## Hinweise  
 ASN.1‑Objektbezeichner geben Algorithmen in bestimmten kryptografischen Formaten an.  Ordnen Sie für die Algorithmen, die Sie angeben möchten, Objektbezeichner angezeigten Namen zu.  Weitere Informationen über Objektbezeichner finden Sie in der MSDN Library.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie das Element **\<oidEntry\>** verwendet, um einer Hashwerts für den Hashalgorithmus RIPEMD\-160 an eine Implementierung dieses Hashalgorithmus zuzuordnen.  
  
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
 [Konfigurieren kryptografischer Klassen](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)   
 [Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)