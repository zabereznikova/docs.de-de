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
ms.openlocfilehash: 6a868f62c6a327012a6225b86bf0103d178d6ab7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921167"
---
# <a name="cryptoclass-element"></a>\<cryptoClass-> Element
Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element [\<nameEntry>](nameentry-element.md) zugeordnet ist.  
  
 \<configuration>  
\<mscorlib>  
\<cryptographySettings>  
\<cryptoNameMapping>  
\<cryptoClasses>  
\<cryptoClass>  
  
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
 Im folgenden Beispiel wird gezeigt, wie das  **\<cryptoClass >** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren. Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode übergeben und <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> die-Methode verwenden `MyCryptoRSAClass` , um ein-Objekt zurückzugeben.  
  
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
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
- [Konfigurieren kryptografischer Klassen](../../configure-cryptography-classes.md)
