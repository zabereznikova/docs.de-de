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
ms.openlocfilehash: a5aebac2d392d4540581dfe7c7afff0819968ac0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69912540"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="8082b-102">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="8082b-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="8082b-103">Digitale Signaturen stellen sicher, dass die Daten nicht manipuliert werden, wenn Sie von einem Programm an ein anderes gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="8082b-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="8082b-104">In der Regel wird die digitale Signatur berechnet, indem eine mathematische Funktion auf den Hash der zu Signier enden Daten angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8082b-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="8082b-105">Beim Formatieren eines zu Signier enden Hashwerts fügen einige digitale Signatur Algorithmen einen ASN. 1-Objekt Bezeichner (OID) als Teil des Formatierungs Vorgangs an.</span><span class="sxs-lookup"><span data-stu-id="8082b-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="8082b-106">Die OID identifiziert den Algorithmus, der zum Berechnen des Hashwerts verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8082b-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="8082b-107">Sie können einem Objekt Bezeichner Algorithmen zuordnen, um den Kryptografiemechanismus so zu erweitern, dass benutzerdefinierte Algorithmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8082b-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="8082b-108">Im folgenden Beispiel wird gezeigt, wie ein Objekt Bezeichner einem neuen Hash Algorithmus zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="8082b-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
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
  
 <span data-ttu-id="8082b-109">Das- [ \<oidEntry> Element](./file-schema/cryptography/oidentry-element.md) enthält zwei Attribute.</span><span class="sxs-lookup"><span data-stu-id="8082b-109">The [\<oidEntry> element](./file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="8082b-110">Das **OID** -Attribut ist die Nummer des Objekt Bezeichners.</span><span class="sxs-lookup"><span data-stu-id="8082b-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="8082b-111">Das **Name** -Attribut ist der Wert des **Name** -Attributs aus dem- [ \<nameEntry> Element](./file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="8082b-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="8082b-112">Es muss eine Zuordnung von einem Algorithmusnamen zu einer Klasse vorhanden sein, bevor ein Objekt Bezeichner einem einfachen Namen zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8082b-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8082b-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8082b-113">See also</span></span>

- [<span data-ttu-id="8082b-114">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="8082b-114">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
- [<span data-ttu-id="8082b-115">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="8082b-115">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
