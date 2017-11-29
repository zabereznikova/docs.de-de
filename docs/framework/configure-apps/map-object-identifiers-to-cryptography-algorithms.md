---
title: Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: dbfe394193925e38dad774d39d79ac813abef22a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen
Digitale Signaturen stellen Sie sicher, dass die Daten nicht manipuliert werden, wenn es von einem Programm zu einem anderen gesendet wird. In der Regel wird die digitale Signatur durch Anwenden einer mathematischen Funktion mit dem Hashwert der zu signierenden Daten berechnet. Beim Formatieren eines Hashwert zu signierenden anfügen einige Algorithmen für digitale Signaturen ein ASN. 1-Objektbezeichner (OID) als Teil des Formatierungsvorgangs an. Die OID identifiziert den Algorithmus, mit dem der Hashwert berechnet wurde. Sie können die Algorithmen für Objektbezeichner die kryptografischen Mechanismen zur Verwendung von benutzerdefinierten Algorithmen erweitern zuordnen. Im folgende Beispiel wird gezeigt, wie einen neuen Hashalgorithmus Objekt-ID zugeordnet.  
  
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
  
 Die [ \<OidEntry >-Element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) enthält zwei Attribute. Die **OID** Attribut ist die Objekt-ID zurück. Der **Name** Attribut ist der Wert der **Name** -Attribut aus der [ \<NameEntry > Element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md). Es muss eine Zuordnung eines Algorithmusnamens zu einer Klasse vorhanden sein, vor dem Bezeichner eines Objekts ein einfacher Name zugeordnet werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren kryptografischer Klassen](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
