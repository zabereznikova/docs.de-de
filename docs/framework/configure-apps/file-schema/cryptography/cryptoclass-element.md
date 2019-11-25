---
title: <cryptoClass>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: 4872fbd6fa043902e8c69f158bee5d0c915ec83a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088664"
---
# <a name="cryptoclass-element"></a>\<cryptoClass >-Element
Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element [\<nameEntry>](nameentry-element.md) zugeordnet ist.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<mscorlib->** ](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping**](cryptonamemapping-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**cryptoClasses**](cryptoclasses-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptoClass >**

## <a name="syntax"></a>Syntax  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`customClassName`|Erforderliches Attribut.<br /><br /> Enthält die Informationen für die Kryptografieklasse. Verwenden Sie dieses Attribut, um einen Kurznamen für die Klasse anzugeben. Sie müssen eine Zeichenfolge angeben, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`cryptoClasses`|Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element [\<nameEntry>](nameentry-element.md) zugeordnet sind.|  
|`cryptographySettings`|Enthält Kryptografieeinstellungen.|  
|`cryptoNameMapping`|Enthält die Zuordnung von Klassen zu den Anzeigenamen.|  
|`mscorlib`|Enthält das Element [\<cryptographySettings>](cryptographysettings-element.md).|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das **\<cryptoClass >** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren. Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>-Methode übergeben und die <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>-Methode verwenden, um ein `MyCryptoRSAClass`-Objekt zurückzugeben.  
  
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
