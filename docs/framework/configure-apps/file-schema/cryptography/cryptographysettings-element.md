---
title: <cryptographySettings>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: ca0a9a4b37f28eb03f58de4fd9b120cb7e654e0c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088646"
---
# <a name="cryptographysettings-element"></a>\<> Element "cryptographySettings"
Enthält Kryptografieeinstellungen.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<mscorlib->** ](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptographySettings >**

## <a name="syntax"></a>Syntax  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<cryptoNameMapping >](cryptonamemapping-element.md)|Enthält die Zuordnung von Klassen zu den Anzeigenamen.|  
|[\<oidmap >](oidmap-element.md)|Enthält ASN. 1 objektbezeichnermappings (OID) zu Klassen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`mscorlib`|Enthält das `cryptographySettings` Element.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das **\<cryptographySettings >** -Element verwendet wird, um kryptografienamenszuordnungen und OID-Zuordnungen zu enthalten. In diesem Beispiel wird die Laufzeit so konfiguriert, dass <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> ein `MyHashClass`-Objekt zurückgibt, und die `MyCryptoClass`-Klasse wird dem Objekt Bezeichner 1.3.36.2.1 zugeordnet.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema](../index.md)
- [Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](index.md)
- [Kryptografische Dienste](../../../../standard/security/cryptographic-services.md)
