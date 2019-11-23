---
title: <nameEntry>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: a339638587f8b544bbc1b0073553f6232ce09694
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699778"
---
# <a name="nameentry-element"></a>\<nameEntry > Element
Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<mscorlib->** ](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<nameEntry >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**name**|Erforderliches Attribut.<br /><br /> Gibt den anzeigen amen des von der Kryptografieklasse implementierten Algorithmus an.|  
|**Klasse**|Erforderliches Attribut.<br /><br /> Gibt den Wert für das **Name** -Attribut im [\<cryptoClass >](cryptoclass-element.md) -Element an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.web`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
  
## <a name="remarks"></a>Hinweise  
 Das **Name** -Attribut kann der Name einer der abstrakten Klassen sein, die im <xref:System.Security.Cryptography>-Namespace gefunden werden. Wenn Sie die **Create** -Methode für eine abstrakte Kryptografieklasse aufzurufen, wird der abstrakte Klassenname an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>-Methode weitergegeben. " **Kreatefromname** " gibt eine Instanz des Typs zurück, der durch das **Class** -Attribut angegeben wird. Wenn das **Name** -Attribut ein Kurzname ist (z. b. RSA), können Sie diesen Namen verwenden, wenn Sie die **CreateFromName** -Methode aufrufen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das **\<nameEntry >** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren. Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>-Methode übergeben und die <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>-Methode verwenden, um ein `MyCryptoRSAClass`-Objekt zurückzugeben.  
  
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

- [Konfigurationsdateischema](../index.md)
- [Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](index.md)
- [Kryptografische Dienste](../../../../standard/security/cryptographic-services.md)
- [Konfigurieren kryptografischer Klassen](../../configure-cryptography-classes.md)
