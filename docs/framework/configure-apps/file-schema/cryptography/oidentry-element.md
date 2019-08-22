---
title: <oidEntry>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: 013994e36c4c63410a753967cbac92c38783ae62
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659589"
---
# <a name="oidentry-element"></a>\<oidEntry-> Element
Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.  
  
 \<configuration>  
\<mscorlib>  
\<cryptographySettings>  
\<oidMap>  
\<oidEntry>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**OID**|Erforderliches Attribut.<br /><br /> Gibt die ASN. 1-OID an, die dem von der Klasse implementierten Algorithmus entspricht.|  
|**name**|Erforderliches Attribut.<br /><br /> Gibt den Wert für das **Name** -Attribut im [ \<nameEntry->](nameentry-element.md) -Tag an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`cryptographySettings`|Enthält Kryptografieeinstellungen.|  
|`mscorlib`|Enthält das `cryptographySettings` -Element.|  
|`oidMap`|Enthält ASN. 1 objektbezeichnermappings (OID) zu Klassen.|  
  
## <a name="remarks"></a>Hinweise  
 ASN. 1-Objekt Bezeichner erkennen Algorithmen in einigen kryptografieformaten. Ordnen Sie den anzeigen Amen für die Algorithmen, die Sie identifizieren möchten, Objekt Bezeichner zu.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie mit dem  **\<Element oidEntry >** ein Objekt Bezeichner für den RIPEMD-160-Hash Algorithmus einer Implementierung dieses Hash Algorithmus zugeordnet wird.  
  
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

- [Konfigurationsdateischema](../index.md)
- [Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](index.md)
- [Cryptographic Services](../../../../../docs/standard/security/cryptographic-services.md)
- [Konfigurieren kryptografischer Klassen](../../configure-cryptography-classes.md)
- [Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen](../../map-object-identifiers-to-cryptography-algorithms.md)
