---
title: '&lt;OidEntry&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: db209bac487ccbb98f7f0aeb272f51169e7a0148
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltoidentrygt-element"></a>&lt;OidEntry&gt; Element
Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.  
  
 \<configuration>  
\<"mscorlib" >  
\<CryptographySettings >  
\<OidMap >  
\<OidEntry >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**OID**|Erforderliches Attribut.<br /><br /> Gibt die ASN. 1-OID für den Algorithmus, der von der Klasse implementiert.|  
|**name**|Erforderliches Attribut.<br /><br /> Gibt den Wert für die **Namen** Attribut in der [ \<NameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) Tag.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`cryptographySettings`|Enthält Kryptografieeinstellungen.|  
|`mscorlib`|Enthält die `cryptographySettings` Element.|  
|`oidMap`|Enthält die ASN. 1-Objekt-ID (OID)-Zuordnungen von Klassen.|  
  
## <a name="remarks"></a>Hinweise  
 ASN. 1-Objektbezeichner identifizieren, in einigen Formaten kryptografischen Algorithmen. Ordnen Sie Objektbezeichner Anzeigenamen für die Algorithmen, die Sie ermitteln möchten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die  **\<OidEntry >** -Element einen Objektbezeichner für die RIPEMD-160-Hashalgorithmus zu einer Implementierung dieses Hashalgorithmus zuordnen.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)  
 [Konfigurieren kryptografischer Klassen](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
