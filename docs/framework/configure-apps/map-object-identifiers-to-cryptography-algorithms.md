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
ms.openlocfilehash: e035ff04a70a441f7f64bbc230ba6d8036fb2ace
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130610"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="4ac8d-102">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="4ac8d-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="4ac8d-103">Digitale Signaturen stellen Sie sicher, dass Daten nicht manipuliert werden, wenn er von einem Programm auf einen anderen gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="4ac8d-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="4ac8d-104">In der Regel wird die digitale Signatur berechnet, indem Sie die Anwendung einer mathematischen Funktion mit dem Hashwert der zu signierenden Daten.</span><span class="sxs-lookup"><span data-stu-id="4ac8d-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="4ac8d-105">Bei der Formatierung eines Hashwert, signiert werden, fügen Sie einige Algorithmen für digitale Signaturen ein ASN. 1-Objektbezeichner (OID) als Teil der Formatierungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="4ac8d-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="4ac8d-106">Die OID identifiziert den Algorithmus, der mit der Hashwert berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="4ac8d-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="4ac8d-107">Sie können die kryptografischen Mechanismen zur Verwendung von benutzerdefinierten Algorithmen erweitern die Objekt-IDs Algorithmen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="4ac8d-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="4ac8d-108">Das folgende Beispiel zeigt, wie Sie einen neuen Hashalgorithmus Objekt-ID zuordnen.</span><span class="sxs-lookup"><span data-stu-id="4ac8d-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
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
  
 <span data-ttu-id="4ac8d-109">Die [ \<OidEntry >-Element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) enthält zwei Attribute.</span><span class="sxs-lookup"><span data-stu-id="4ac8d-109">The [\<oidEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="4ac8d-110">Die **OID** -Attribut ist die Objektkennnummer.</span><span class="sxs-lookup"><span data-stu-id="4ac8d-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="4ac8d-111">Die **Namen** Attribut ist der Wert des der **Namen** -Attribut aus der [ \<NameEntry > Element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8d-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="4ac8d-112">Es muss eine Zuordnung eines Algorithmusnamens zu einer Klasse vorhanden sein, bevor eine Objekt-ID ein einfacher Name zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4ac8d-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ac8d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ac8d-113">See also</span></span>

- [<span data-ttu-id="4ac8d-114">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="4ac8d-114">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="4ac8d-115">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="4ac8d-115">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
