---
title: "&lt;nameEntry&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<nameEntry>-Element"
  - "nameEntry-Element"
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;nameEntry&gt;-Element
Ordnet einen Klassennamen einem angezeigten Algorithmusnamen zu, wodurch eine Klasse viele angezeigte Namen aufweisen kann.  
  
## Syntax  
  
```  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|**name**|Erforderliches Attribut.<br /><br /> Gibt den angezeigten Namen des Algorithmus an, den die Kryptografieklasse implementiert.|  
|**class**|Erforderliches Attribut.<br /><br /> Gibt den Wert des **name** \-Attribut im [\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)\-Element an.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.web`|Gibt das Stammelement für den ASP.NET\-Konfigurationsabschnitt an.|  
  
## Hinweise  
 Das **name**\-Attribut kann der Name einer der abstrakten Klassen im <xref:System.Security.Cryptography>\-Namespace sein.  Wenn die **Create**\-Methode in einer abstrakten Kryptografieklasse aufgerufen wird, wird der Name der abstrakten Klasse an die [Security.CryptoConfig.CreateFromName](frlrfSystemSecurityCryptographyCryptoConfigClassCreateFromNameTopic)\-Methode übergeben.  **CreateFromName** gibt eine Instanz des Typs zurück, der durch das **class**\-Attribut angegeben wird.  Wenn das **name**\-Attribut ein Kurzname ist, z. B. RSA, können Sie den Namen beim Aufrufen der **CreateFromName**\-Methode verwenden.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie das Element **\<nameEntry\>**, um eine mehr zu verweisen verwendet und die Laufzeit zu konfigurieren.  Sie können dann die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=fullName>\-Methode übergeben und mithilfe der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>\-Methode ein `MyCryptoRSAClass`\-Objekt zurückgeben.  
  
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
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Schema für Kryptografieeinstellungen](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)   
 [Konfigurieren kryptografischer Klassen](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)