---
title: Verbesserte starke Namen
ms.date: 03/30/2017
helpviewer_keywords:
- strong-named assemblies
- strong naming [.NET Framework], enhanced
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf4a8df87cd507f2bfb17086e83dc8374a22fe71
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746890"
---
# <a name="enhanced-strong-naming"></a><span data-ttu-id="992de-102">Verbesserte starke Namen</span><span class="sxs-lookup"><span data-stu-id="992de-102">Enhanced Strong Naming</span></span>
<span data-ttu-id="992de-103">Eine starke Namenssignatur ist ein Identitätsmechanismus in .NET Framework zum Identifizieren von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="992de-103">A strong name signature is an identity mechanism in the .NET Framework for identifying assemblies.</span></span> <span data-ttu-id="992de-104">In der Regel wird eine digitale Signatur mit öffentlichem Schlüssel verwendet, um die Integrität von Daten sicherzustellen, die von einem Absender (Signaturgeber) an einen Empfänger (Überprüfer) übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="992de-104">It is a public-key digital signature that is typically used to verify the integrity of data being passed from an originator (signer) to a recipient (verifier).</span></span> <span data-ttu-id="992de-105">Diese Signatur wird als eindeutige Identität für eine Assembly verwendet und gewährleistet, dass Verweise auf die Assembly nicht mehrdeutig sind.</span><span class="sxs-lookup"><span data-stu-id="992de-105">This signature is used as a unique identity for an assembly and ensures that references to the assembly are not ambiguous.</span></span> <span data-ttu-id="992de-106">Die Assembly wird als Teil des Buildprozesses signiert und anschließend überprüft, wenn sie geladen wird.</span><span class="sxs-lookup"><span data-stu-id="992de-106">The assembly is signed as part of the build process and then verified when it is loaded.</span></span>  
  
 <span data-ttu-id="992de-107">Starke Namenssignaturen helfen, bösartige Parteien daran zu hindern, eine Assembly zu manipulieren und sie anschließend mit dem Schlüssel des ursprünglichen Signaturgebers neu zu signieren.</span><span class="sxs-lookup"><span data-stu-id="992de-107">Strong name signatures help prevent malicious parties from tampering with an assembly and then re-signing the assembly with the original signer’s key.</span></span> <span data-ttu-id="992de-108">Allerdings enthalten Schlüssel mit starkem Namen weder zuverlässige Informationen zum Herausgeber, noch enthalten sie eine Zertifikatshierarchie.</span><span class="sxs-lookup"><span data-stu-id="992de-108">However, strong name keys don’t contain any reliable information about the publisher, nor do they contain a certificate hierarchy.</span></span> <span data-ttu-id="992de-109">Eine starke Namenssignatur garantiert nicht die Vertrauenswürdigkeit der Person, die die Assembly signiert hat, und gibt auch nicht an, ob diese Person ein legitimer Besitzer des Schlüssels war. Sie gibt nur an, dass der Besitzer des Schlüssels die Assembly signiert hat.</span><span class="sxs-lookup"><span data-stu-id="992de-109">A strong name signature does not guarantee the trustworthiness of the person who signed the assembly or indicate whether that person was a legitimate owner of the key; it indicates only that the owner of the key signed the assembly.</span></span> <span data-ttu-id="992de-110">Daher empfiehlt es sich nicht, eine starke Namenssignatur als Sicherheitsbestätigung für Code von Drittanbietern zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="992de-110">Therefore, we do not recommend using a strong name signature as a security validator for trusting third-party code.</span></span> <span data-ttu-id="992de-111">Zur Authentifizierung von Code wird Microsoft Authenticode empfohlen.</span><span class="sxs-lookup"><span data-stu-id="992de-111">Microsoft Authenticode is the recommended way to authenticate code.</span></span>  
  
## <a name="limitations-of-conventional-strong-names"></a><span data-ttu-id="992de-112">Beschränkungen der konventionellen starken Namen</span><span class="sxs-lookup"><span data-stu-id="992de-112">Limitations of Conventional Strong Names</span></span>  
 <span data-ttu-id="992de-113">Die starke Benennungstechnologie, die in Versionen vor [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] verwendet wird, hat folgende Nachteile:</span><span class="sxs-lookup"><span data-stu-id="992de-113">The strong naming technology used in versions before the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] has the following shortcomings:</span></span>  
  
-   <span data-ttu-id="992de-114">Die Schlüssel werden ständig attackiert, und durch verbesserte Techniken und Hardware ist es einfacher, einen privaten Schlüssel von einem öffentlichen abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="992de-114">Keys are constantly under attack, and improved techniques and hardware make it easier to infer a private key from a public key.</span></span> <span data-ttu-id="992de-115">Zum Schutz gegen Angriffe sind größere Schlüssel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="992de-115">To guard against attacks, larger keys are necessary.</span></span> <span data-ttu-id="992de-116">.NET Framework-Versionen vor [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] bieten die Möglichkeit, mit einem beliebigen Größenschlüssel zu signieren (die Standardgröße ist 1024 Bit), das Signieren einer Assembly mit einem neuen Schlüssel bricht jedoch alle Binärdateien, die auf die ältere Identität der Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="992de-116">.NET Framework versions before the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] provide the ability to sign with any size key (the default size is 1024 bits), but signing an assembly with a new key breaks all binaries that reference the older identity of the assembly.</span></span> <span data-ttu-id="992de-117">Daher ist es extrem schwierig, die Größe eines Signaturschlüssels zu aktualisieren, wenn Sie Kompatibilität beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="992de-117">Therefore, it is extremely difficult to upgrade the size of a signing key if you want to maintain compatibility.</span></span>  
  
-   <span data-ttu-id="992de-118">Signierung mit starken Namen unterstützt nur den SHA-1-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="992de-118">Strong name signing supports only the SHA-1 algorithm.</span></span> <span data-ttu-id="992de-119">Es wurde kürzlich festgestellt, dass SHA-1 für die Sicherung von Hashing-Anwendungen unzureichend ist.</span><span class="sxs-lookup"><span data-stu-id="992de-119">SHA-1 has recently been found to be inadequate for secure hashing applications.</span></span> <span data-ttu-id="992de-120">Daher ist ein stärkerer Algorithmus (SHA-256 oder höher) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="992de-120">Therefore, a stronger algorithm (SHA-256 or greater) is necessary.</span></span> <span data-ttu-id="992de-121">Es ist möglich, dass SHA-1 die FIPS-kompatible Position verliert, was zu Problemen für diejenigen führen würde, die sich entscheiden, nur FIPS-kompatible Software und Algorithmen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="992de-121">It is possible that SHA-1 will lose its FIPS-compliant standing, which would present problems for those who choose to use only FIPS-compliant software and algorithms.</span></span>  
  
## <a name="advantages-of-enhanced-strong-names"></a><span data-ttu-id="992de-122">Vorteile von erweiterten starken Namen</span><span class="sxs-lookup"><span data-stu-id="992de-122">Advantages of Enhanced Strong Names</span></span>  
 <span data-ttu-id="992de-123">Die Hauptvorteile von erweiterten starken Namen sind Kompatibilität mit bereits vorhandenen starken Namen und die Möglichkeit, zu beanspruchen, dass eine Identität einer anderen entspricht:</span><span class="sxs-lookup"><span data-stu-id="992de-123">The main advantages of enhanced strong names are compatibility with pre-existing strong names and the ability to claim that one identity is equivalent to another:</span></span>  
  
-   <span data-ttu-id="992de-124">Entwickler mit bereits vorhandenen signierten Assemblys können ihre Identitäten zu SHA-2-Algorithmen migrieren, wobei die Kompatibilität mit Assemblys, die auf alte Identitäten verweisen, beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="992de-124">Developers who have pre-existing signed assemblies can migrate their identities to the SHA-2 algorithms while maintaining compatibility with assemblies that reference the old identities.</span></span>  
  
-   <span data-ttu-id="992de-125">Entwickler, die neue Assemblys erstellen und sich nicht mit vorhandenen starken Namenssignaturen befassen müssen, können die sichereren SHA-2-Algorithmen und die Assemblys wie gewohnt signieren.</span><span class="sxs-lookup"><span data-stu-id="992de-125">Developers who create new assemblies and are not concerned with pre-existing strong name signatures can use the more secure SHA-2 algorithms and sign the assemblies as they always have.</span></span>  
  
## <a name="using-enhanced-strong-names"></a><span data-ttu-id="992de-126">Verwenden von verbesserten starken Namen</span><span class="sxs-lookup"><span data-stu-id="992de-126">Using Enhanced Strong Names</span></span>  
 <span data-ttu-id="992de-127">Schlüssel mit starkem Namen bestehen aus einem Signaturschlüssel und einem Identitätsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="992de-127">Strong name keys consist of a signature key and an identity key.</span></span> <span data-ttu-id="992de-128">Die Assembly wird mit dem Signaturschlüssel signiert und durch den Identitätsschlüssel identifiziert.</span><span class="sxs-lookup"><span data-stu-id="992de-128">The assembly is signed with the signature key and is identified by the identity key.</span></span> <span data-ttu-id="992de-129">Vor [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] waren diese beiden Schlüssel identisch.</span><span class="sxs-lookup"><span data-stu-id="992de-129">Prior to the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], these two keys were identical.</span></span> <span data-ttu-id="992de-130">Ab [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] bleibt der Identitätsschlüssel gleich wie in früheren .NET Framework-Versionen, der Signaturschlüssel wird jedoch durch einen stärkeren Hashalgorithmus verbessert.</span><span class="sxs-lookup"><span data-stu-id="992de-130">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], the identity key remains the same as in earlier .NET Framework versions, but the signature key is enhanced with a stronger hash algorithm.</span></span> <span data-ttu-id="992de-131">Außerdem wird der Signaturschlüssel mit dem Identitätsschlüssels signiert, um eine Gegensignatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="992de-131">In addition, the signature key is signed with the identity key to create a counter-signature.</span></span>  
  
 <span data-ttu-id="992de-132">Mithilfe des <xref:System.Reflection.AssemblySignatureKeyAttribute>-Attributs können die Assemblymetadaten den bereits vorhandenen öffentlichen Schlüssel für die Assemblyidentität verwenden, wodurch alte Assemblyverweise weiterhin funktionieren.</span><span class="sxs-lookup"><span data-stu-id="992de-132">The <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute enables the assembly metadata to use the pre-existing public key for assembly identity, which allows old assembly references to continue to work.</span></span>  <span data-ttu-id="992de-133">Das <xref:System.Reflection.AssemblySignatureKeyAttribute>-Attribut verwendet die Gegensignatur, um sicherzustellen, dass der Besitzer des neuen Signaturschlüssels auch der Besitzer des alten Identitätsschlüssels ist.</span><span class="sxs-lookup"><span data-stu-id="992de-133">The <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute uses the counter-signature to ensure that the owner of the new signature key is also the owner of the old identity key.</span></span>  
  
### <a name="signing-with-sha-2-without-key-migration"></a><span data-ttu-id="992de-134">Signieren mit SHA-2, ohne Schlüsselmigration</span><span class="sxs-lookup"><span data-stu-id="992de-134">Signing with SHA-2, Without Key Migration</span></span>  
 <span data-ttu-id="992de-135">Führen Sie die folgenden Befehle in einem Eingabeaufforderungsfenster aus, um eine Assembly zu signieren, ohne eine starke Namenssignatur zu migrieren:</span><span class="sxs-lookup"><span data-stu-id="992de-135">Run the following commands from a Command Prompt window to sign an assembly without migrating a strong name signature:</span></span>  
  
1.  <span data-ttu-id="992de-136">Generieren Sie den neuen Identitätsschlüssels (falls erforderlich).</span><span class="sxs-lookup"><span data-stu-id="992de-136">Generate the new identity key (if necessary).</span></span>  
  
    ```  
    sn -k IdentityKey.snk  
    ```  
  
2.  <span data-ttu-id="992de-137">Extrahieren Sie den öffentlichen Identitätsschlüssel, und geben Sie an, dass ein SHA-2-Algorithmus beim Signieren mit diesem Schlüssel verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="992de-137">Extract the identity public key, and specify that a SHA-2 algorithm should be used when signing with this key.</span></span>  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3.  <span data-ttu-id="992de-138">Führen Sie eine verzögerte Signierung der Assembly mit der öffentlichen Identitätsschlüsseldatei durch.</span><span class="sxs-lookup"><span data-stu-id="992de-138">Delay-sign the assembly with the identity public key file.</span></span>  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4.  <span data-ttu-id="992de-139">Signieren Sie die Assembly mit dem vollständigen Identitätsschlüsselpaar erneut.</span><span class="sxs-lookup"><span data-stu-id="992de-139">Re-sign the assembly with the full identity key pair.</span></span>  
  
    ```  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### <a name="signing-with-sha-2-with-key-migration"></a><span data-ttu-id="992de-140">Signieren mit SHA-2, mit Schlüsselmigration</span><span class="sxs-lookup"><span data-stu-id="992de-140">Signing with SHA-2, with Key Migration</span></span>  
 <span data-ttu-id="992de-141">Führen Sie die folgenden Befehle in einem Eingabeaufforderungsfenster aus, um eine Assembly mit einer migrierten starken Namenssignatur zu signieren.</span><span class="sxs-lookup"><span data-stu-id="992de-141">Run the following commands from a Command Prompt window to sign an assembly with a migrated strong name signature.</span></span>  
  
1.  <span data-ttu-id="992de-142">Generieren Sie ein Identitäts- und Signaturschlüsselpaar (falls erforderlich).</span><span class="sxs-lookup"><span data-stu-id="992de-142">Generate an identity and signature key pair (if necessary).</span></span>  
  
    ```  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2.  <span data-ttu-id="992de-143">Extrahieren Sie den öffentlichen Signaturschlüssel, und geben Sie an, dass ein SHA-2-Algorithmus beim Signieren mit diesem Schlüssel verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="992de-143">Extract the signature public key, and specify that a SHA-2 algorithm should be used when signing with this key.</span></span>  
  
    ```  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3.  <span data-ttu-id="992de-144">Extrahieren Sie den öffentlichen Identitätsschlüssel, der den Hashalgorithmus bestimmt, der eine Gegensignatur generiert.</span><span class="sxs-lookup"><span data-stu-id="992de-144">Extract the identity public key, which determines the hash algorithm that generates a counter-signature.</span></span>  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4.  <span data-ttu-id="992de-145">Generieren Sie die Parameter für ein <xref:System.Reflection.AssemblySignatureKeyAttribute>-Attribut, und fügen Sie das Attribut an die Assembly an.</span><span class="sxs-lookup"><span data-stu-id="992de-145">Generate the parameters for a <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute, and attach the attribute to the assembly.</span></span>  
  
    ```  
    sn -ac IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  
  
5.  <span data-ttu-id="992de-146">Führen Sie eine verzögerte Signierung der Assembly mit dem öffentlichen Identitätsschlüssel durch.</span><span class="sxs-lookup"><span data-stu-id="992de-146">Delay-sign the assembly with the identity public key.</span></span>  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
6.  <span data-ttu-id="992de-147">Führen Sie eine vollständige Signatur der Assembly mit dem Signaturschlüsselpaar durch.</span><span class="sxs-lookup"><span data-stu-id="992de-147">Fully sign the assembly with the signature key pair.</span></span>  
  
    ```  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="992de-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="992de-148">See Also</span></span>  
 [<span data-ttu-id="992de-149">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="992de-149">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
