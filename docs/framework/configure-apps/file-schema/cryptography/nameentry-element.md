---
title: '&lt;NameEntry&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1bffb72e7c68d10e2c0edd5ec3cb9bcff10cbc0a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltnameentrygt-element"></a>&lt;NameEntry&gt; Element
Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.  
  
 \<configuration>  
\<"mscorlib" >  
\<CryptographySettings >  
\<CryptoNameMapping >  
\<NameEntry >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**name**|Erforderliches Attribut.<br /><br /> Gibt den Anzeigenamen des Algorithmus, den die Kryptografieklasse implementiert.|  
|**class**|Erforderliches Attribut.<br /><br /> Gibt den Wert für die **Namen** Attribut in der [ \<CryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) Element.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.web`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
  
## <a name="remarks"></a>Hinweise  
 Die **Namen** Attribut kann den Namen einer abstrakten Klassen der <xref:System.Security.Cryptography> Namespace. Beim Aufrufen der **erstellen** Methode in einer abstrakten Kryptografieklasse, Name der abstrakten Klasse wird zum Übergeben der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> Methode. **CreateFromName** gibt eine Instanz des Typs, angegeben durch die **Klasse** Attribut. Wenn die **Namen** -Attribut ist ein Kurzname wie z. B. RSA, können Sie diesen Namen beim Aufrufen der **CreateFromName** Methode.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die  **\<NameEntry >** Element auf eine kryptografischen Klasse verweisen und die Laufzeit zu konfigurieren. Sie können dann die Zeichenfolge "RSA" übergeben, um die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.  
  
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
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)  
 [Konfigurieren kryptografischer Klassen](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
