---
title: Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen
description: Weitere Informationen finden Sie unterzuordnen eines Objekt Bezeichners (OID) zu einem Kryptografiealgorithmus in .NET mithilfe der Elemente "oidEntry" und "nameEntry" in einer XML-Konfigurationsdatei.
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
ms.openlocfilehash: e22510014071455b83ba28cd82690b5ecdce9bc9
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85142003"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen
Digitale Signaturen stellen sicher, dass die Daten nicht manipuliert werden, wenn Sie von einem Programm an ein anderes gesendet werden. In der Regel wird die digitale Signatur berechnet, indem eine mathematische Funktion auf den Hash der zu Signier enden Daten angewendet wird. Beim Formatieren eines zu Signier enden Hashwerts fügen einige digitale Signatur Algorithmen einen ASN. 1-Objekt Bezeichner (OID) als Teil des Formatierungs Vorgangs an. Die OID identifiziert den Algorithmus, der zum Berechnen des Hashwerts verwendet wurde. Sie können einem Objekt Bezeichner Algorithmen zuordnen, um den Kryptografiemechanismus so zu erweitern, dass benutzerdefinierte Algorithmen verwendet werden. Im folgenden Beispiel wird gezeigt, wie ein Objekt Bezeichner einem neuen Hash Algorithmus zugeordnet wird.  
  
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
  
 Das- [ \<oidEntry> Element](./file-schema/cryptography/oidentry-element.md) enthält zwei Attribute. Das **OID** -Attribut ist die Nummer des Objekt Bezeichners. Das **Name** -Attribut ist der Wert des **Name** -Attributs aus dem- [ \<nameEntry> Element](./file-schema/cryptography/nameentry-element.md). Es muss eine Zuordnung von einem Algorithmusnamen zu einer Klasse vorhanden sein, bevor ein Objekt Bezeichner einem einfachen Namen zugeordnet werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren kryptografischer Klassen](configure-cryptography-classes.md)
- [Kryptografiedienste](../../standard/security/cryptographic-services.md)
