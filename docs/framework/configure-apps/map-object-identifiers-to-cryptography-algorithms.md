---
title: Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d23fc48a53ee47aacfc290b52887b800ce37477f
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48036858"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen
Digitale Signaturen stellen Sie sicher, dass Daten nicht manipuliert werden, wenn er von einem Programm auf einen anderen gesendet wird. In der Regel wird die digitale Signatur berechnet, indem Sie die Anwendung einer mathematischen Funktion mit dem Hashwert der zu signierenden Daten. Bei der Formatierung eines Hashwert, signiert werden, fügen Sie einige Algorithmen für digitale Signaturen ein ASN. 1-Objektbezeichner (OID) als Teil der Formatierungsvorgang. Die OID identifiziert den Algorithmus, der mit der Hashwert berechnet wurde. Sie können die kryptografischen Mechanismen zur Verwendung von benutzerdefinierten Algorithmen erweitern die Objekt-IDs Algorithmen zuordnen. Das folgende Beispiel zeigt, wie Sie einen neuen Hashalgorithmus Objekt-ID zuordnen.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 Die [ \<OidEntry >-Element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) enthält zwei Attribute. Die **OID** -Attribut ist die Objektkennnummer. Die **Namen** Attribut ist der Wert des der **Namen** -Attribut aus der [ \<NameEntry > Element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md). Es muss eine Zuordnung eines Algorithmusnamens zu einer Klasse vorhanden sein, bevor eine Objekt-ID ein einfacher Name zugeordnet werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren kryptografischer Klassen](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
