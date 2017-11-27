---
title: "&lt;\"mscorlib\"&gt; -Element für Kryptografieeinstellungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 992e62575dccae3f68df27fb7dd027dceab91ffc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltmscorlibgt-element-for-cryptography-settings"></a>&lt;"mscorlib"&gt; -Element für Kryptografieeinstellungen
Enthält die [ \<CryptographySettings >-Element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).  
  
 \<configuration>  
\<"mscorlib" >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`cryptographySettings`|Enthält Kryptografieeinstellungen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die  **\<"mscorlib" >** Element auf eine kryptografischen Klasse verweisen und die Laufzeit zu konfigurieren. Sie können dann die Zeichenfolge "RSA" übergeben, um die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>  
 <xref:System.Security.Cryptography>  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)  
 [Konfigurieren kryptografischer Klassen](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
