---
title: "Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Kryptografische Algorithmen"
  - "Kryptografie, Zuordnen von Objektbezeichnern"
  - "Digitale Signaturen"
  - "Bezeichner, Zuordnen von Objektbezeichnern"
  - "Zuordnen von Objektbezeichnern"
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen
Durch digitale Signaturen wird sichergestellt, dass Daten nicht verfälscht werden, wenn sie von einem Programm zum anderen gesendet werden.  In der Regel wird die digitale Signatur durch die Anwendung einer mathematischen Funktion auf die Hashwerte der zu signierenden Daten berechnet.  Beim Formatieren eines zu signierenden Hashwerts hängen einige digitale Signaturalgorithmen einen ASN.1\-Objektbezeichner \(OID\) als Teil des Formatierungsvorgangs an.  Der OID erkennt den Algorithmus, der für die Berechnung des Hashwerts verwendet wurde.  Algorithmen lassen sich Objektbezeichnern zuordnen, um so die kryptografischen Mechanismen zur Verwendung von benutzerdefinierten Algorithmen zu erweitern.  Anhand des folgenden Beispiels wird gezeigt, wie ein Objektbezeichner einem neuen Hashalgorithmus zugeordnet wird.  
  
```  
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
  
 [\<oidEntry\>\-Element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) enthält zwei Attribute.  Das **OID**\-Attribut ist die Nummer des Objektbezeichners.  Das **name**\-Attribut ist der Wert des **name**\-Attributs von [\<nameEntry\>\-Element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).  Damit ein Objektbezeichner einem einfachen Namen zugeordnet werden kann, muss zunächst ein Algorithmusname einer Klasse zugeordnet werden.  
  
## Siehe auch  
 [Konfigurieren kryptografischer Klassen](../../../docs/framework/configure-apps/configure-cryptography-classes.md)   
 [Kryptografische Dienste](../../../docs/standard/security/cryptographic-services.md)