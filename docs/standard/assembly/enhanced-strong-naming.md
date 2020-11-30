---
title: Verbesserte starke Namen
description: Herkömmliche Signaturen mit starken Namen für Assemblys in .NET Framework haben Einschränkungen. Erfahren Sie mehr über verbesserte starke Namen.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies
- strong naming [.NET Framework], enhanced
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
ms.openlocfilehash: b9c690c77dafc247f7282c3f56384481efe53399
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731526"
---
# <a name="enhanced-strong-naming"></a><span data-ttu-id="c1f86-104">Verbesserte starke Namen</span><span class="sxs-lookup"><span data-stu-id="c1f86-104">Enhanced strong naming</span></span>

<span data-ttu-id="c1f86-105">Eine starke Namenssignatur ist ein Identitätsmechanismus in .NET Framework zum Identifizieren von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="c1f86-105">A strong name signature is an identity mechanism in the .NET Framework for identifying assemblies.</span></span> <span data-ttu-id="c1f86-106">In der Regel wird eine digitale Signatur mit öffentlichem Schlüssel verwendet, um die Integrität von Daten sicherzustellen, die von einem Absender (Signaturgeber) an einen Empfänger (Überprüfer) übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c1f86-106">It is a public-key digital signature that is typically used to verify the integrity of data being passed from an originator (signer) to a recipient (verifier).</span></span> <span data-ttu-id="c1f86-107">Diese Signatur wird als eindeutige Identität für eine Assembly verwendet und gewährleistet, dass Verweise auf die Assembly nicht mehrdeutig sind.</span><span class="sxs-lookup"><span data-stu-id="c1f86-107">This signature is used as a unique identity for an assembly and ensures that references to the assembly are not ambiguous.</span></span> <span data-ttu-id="c1f86-108">Die Assembly wird als Teil des Buildprozesses signiert und anschließend überprüft, wenn sie geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c1f86-108">The assembly is signed as part of the build process and then verified when it is loaded.</span></span>  
  
 <span data-ttu-id="c1f86-109">Starke Namenssignaturen helfen, bösartige Parteien daran zu hindern, eine Assembly zu manipulieren und sie anschließend mit dem Schlüssel des ursprünglichen Signaturgebers neu zu signieren.</span><span class="sxs-lookup"><span data-stu-id="c1f86-109">Strong name signatures help prevent malicious parties from tampering with an assembly and then re-signing the assembly with the original signer’s key.</span></span> <span data-ttu-id="c1f86-110">Allerdings enthalten Schlüssel mit starkem Namen weder zuverlässige Informationen zum Herausgeber, noch enthalten sie eine Zertifikatshierarchie.</span><span class="sxs-lookup"><span data-stu-id="c1f86-110">However, strong name keys don’t contain any reliable information about the publisher, nor do they contain a certificate hierarchy.</span></span> <span data-ttu-id="c1f86-111">Eine starke Namenssignatur garantiert nicht die Vertrauenswürdigkeit der Person, die die Assembly signiert hat, und gibt auch nicht an, ob diese Person ein legitimer Besitzer des Schlüssels war. Sie gibt nur an, dass der Besitzer des Schlüssels die Assembly signiert hat.</span><span class="sxs-lookup"><span data-stu-id="c1f86-111">A strong name signature does not guarantee the trustworthiness of the person who signed the assembly or indicate whether that person was a legitimate owner of the key; it indicates only that the owner of the key signed the assembly.</span></span> <span data-ttu-id="c1f86-112">Daher empfiehlt es sich nicht, eine starke Namenssignatur als Sicherheitsbestätigung für Code von Drittanbietern zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1f86-112">Therefore, we do not recommend using a strong name signature as a security validator for trusting third-party code.</span></span> <span data-ttu-id="c1f86-113">Zur Authentifizierung von Code wird Microsoft Authenticode empfohlen.</span><span class="sxs-lookup"><span data-stu-id="c1f86-113">Microsoft Authenticode is the recommended way to authenticate code.</span></span>  
  
## <a name="limitations-of-conventional-strong-names"></a><span data-ttu-id="c1f86-114">Beschränkungen der konventionellen starken Namen</span><span class="sxs-lookup"><span data-stu-id="c1f86-114">Limitations of conventional strong names</span></span>  

 <span data-ttu-id="c1f86-115">Die starke Benennungstechnologie aus den Vorgängerversionen von .NET Framework 4.5 hat folgende Nachteile:</span><span class="sxs-lookup"><span data-stu-id="c1f86-115">The strong naming technology used in versions before the .NET Framework 4.5 has the following shortcomings:</span></span>  
  
- <span data-ttu-id="c1f86-116">Die Schlüssel werden ständig attackiert, und durch verbesserte Techniken und Hardware ist es einfacher, einen privaten Schlüssel von einem öffentlichen abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c1f86-116">Keys are constantly under attack, and improved techniques and hardware make it easier to infer a private key from a public key.</span></span> <span data-ttu-id="c1f86-117">Zum Schutz gegen Angriffe sind größere Schlüssel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c1f86-117">To guard against attacks, larger keys are necessary.</span></span> <span data-ttu-id="c1f86-118">In .NET Framework-Versionen vor .NET Framework 4.5 können Signaturen mit einer beliebigen Schlüsselgröße (Standardgröße: 1.024 Bits) verwendet werden. Beim Signieren einer Assembly mit einem neuen Schlüssel werden jedoch alle Binärdateien beschädigt, die auf die ältere Identität der Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="c1f86-118">.NET Framework versions before the .NET Framework 4.5 provide the ability to sign with any size key (the default size is 1024 bits), but signing an assembly with a new key breaks all binaries that reference the older identity of the assembly.</span></span> <span data-ttu-id="c1f86-119">Daher ist es extrem schwierig, die Größe eines Signaturschlüssels zu aktualisieren, wenn Sie Kompatibilität beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="c1f86-119">Therefore, it is extremely difficult to upgrade the size of a signing key if you want to maintain compatibility.</span></span>  
  
- <span data-ttu-id="c1f86-120">Signierung mit starken Namen unterstützt nur den SHA-1-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="c1f86-120">Strong name signing supports only the SHA-1 algorithm.</span></span> <span data-ttu-id="c1f86-121">Es wurde kürzlich festgestellt, dass SHA-1 für die Sicherung von Hashing-Anwendungen unzureichend ist.</span><span class="sxs-lookup"><span data-stu-id="c1f86-121">SHA-1 has recently been found to be inadequate for secure hashing applications.</span></span> <span data-ttu-id="c1f86-122">Daher ist ein stärkerer Algorithmus (SHA-256 oder höher) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c1f86-122">Therefore, a stronger algorithm (SHA-256 or greater) is necessary.</span></span> <span data-ttu-id="c1f86-123">Es ist möglich, dass SHA-1 die FIPS-kompatible Position verliert, was zu Problemen für diejenigen führen würde, die sich entscheiden, nur FIPS-kompatible Software und Algorithmen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1f86-123">It is possible that SHA-1 will lose its FIPS-compliant standing, which would present problems for those who choose to use only FIPS-compliant software and algorithms.</span></span>  
  
## <a name="advantages-of-enhanced-strong-names"></a><span data-ttu-id="c1f86-124">Vorteile von verbesserten starken Namen</span><span class="sxs-lookup"><span data-stu-id="c1f86-124">Advantages of enhanced strong names</span></span>  

 <span data-ttu-id="c1f86-125">Die Hauptvorteile von erweiterten starken Namen sind Kompatibilität mit bereits vorhandenen starken Namen und die Möglichkeit, zu beanspruchen, dass eine Identität einer anderen entspricht:</span><span class="sxs-lookup"><span data-stu-id="c1f86-125">The main advantages of enhanced strong names are compatibility with pre-existing strong names and the ability to claim that one identity is equivalent to another:</span></span>  
  
- <span data-ttu-id="c1f86-126">Entwickler mit bereits vorhandenen signierten Assemblys können ihre Identitäten zu SHA-2-Algorithmen migrieren, wobei die Kompatibilität mit Assemblys, die auf alte Identitäten verweisen, beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="c1f86-126">Developers who have pre-existing signed assemblies can migrate their identities to the SHA-2 algorithms while maintaining compatibility with assemblies that reference the old identities.</span></span>  
  
- <span data-ttu-id="c1f86-127">Entwickler, die neue Assemblys erstellen und sich nicht mit vorhandenen starken Namenssignaturen befassen müssen, können die sichereren SHA-2-Algorithmen und die Assemblys wie gewohnt signieren.</span><span class="sxs-lookup"><span data-stu-id="c1f86-127">Developers who create new assemblies and are not concerned with pre-existing strong name signatures can use the more secure SHA-2 algorithms and sign the assemblies as they always have.</span></span>  
  
## <a name="use-enhanced-strong-names"></a><span data-ttu-id="c1f86-128">Verwenden von verbesserten starken Namen</span><span class="sxs-lookup"><span data-stu-id="c1f86-128">Use enhanced strong names</span></span>  

 <span data-ttu-id="c1f86-129">Schlüssel mit starkem Namen bestehen aus einem Signaturschlüssel und einem Identitätsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="c1f86-129">Strong name keys consist of a signature key and an identity key.</span></span> <span data-ttu-id="c1f86-130">Die Assembly wird mit dem Signaturschlüssel signiert und durch den Identitätsschlüssel identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c1f86-130">The assembly is signed with the signature key and is identified by the identity key.</span></span> <span data-ttu-id="c1f86-131">Vor .NET Framework 4.5 waren diese beiden Schlüssel identisch.</span><span class="sxs-lookup"><span data-stu-id="c1f86-131">Prior to the .NET Framework 4.5, these two keys were identical.</span></span> <span data-ttu-id="c1f86-132">Ab .NET Framework 4.5 wird der gleiche Identitätsschlüssel wie in früheren .NET Framework-Versionen verwendet, der Signaturschlüssel wird jedoch durch einen stärkeren Hashalgorithmus verbessert.</span><span class="sxs-lookup"><span data-stu-id="c1f86-132">Starting with the .NET Framework 4.5, the identity key remains the same as in earlier .NET Framework versions, but the signature key is enhanced with a stronger hash algorithm.</span></span> <span data-ttu-id="c1f86-133">Außerdem wird der Signaturschlüssel mit dem Identitätsschlüssels signiert, um eine Gegensignatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c1f86-133">In addition, the signature key is signed with the identity key to create a counter-signature.</span></span>  
  
 <span data-ttu-id="c1f86-134">Mithilfe des <xref:System.Reflection.AssemblySignatureKeyAttribute>-Attributs können die Assemblymetadaten den bereits vorhandenen öffentlichen Schlüssel für die Assemblyidentität verwenden, wodurch alte Assemblyverweise weiterhin funktionieren.</span><span class="sxs-lookup"><span data-stu-id="c1f86-134">The <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute enables the assembly metadata to use the pre-existing public key for assembly identity, which allows old assembly references to continue to work.</span></span>  <span data-ttu-id="c1f86-135">Das <xref:System.Reflection.AssemblySignatureKeyAttribute>-Attribut verwendet die Gegensignatur, um sicherzustellen, dass der Besitzer des neuen Signaturschlüssels auch der Besitzer des alten Identitätsschlüssels ist.</span><span class="sxs-lookup"><span data-stu-id="c1f86-135">The <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute uses the counter-signature to ensure that the owner of the new signature key is also the owner of the old identity key.</span></span>  
  
### <a name="sign-with-sha-2-without-key-migration"></a><span data-ttu-id="c1f86-136">Signieren einer Assembly mit SHA-2 ohne Schlüsselmigration</span><span class="sxs-lookup"><span data-stu-id="c1f86-136">Sign with SHA-2, without key migration</span></span>  

 <span data-ttu-id="c1f86-137">Führen Sie die folgenden Befehle über eine Eingabeaufforderung aus, um eine Assembly zu signieren, ohne die Signatur eines starken Namens zu migrieren:</span><span class="sxs-lookup"><span data-stu-id="c1f86-137">Run the following commands from a command prompt to sign an assembly without migrating a strong name signature:</span></span>  
  
1. <span data-ttu-id="c1f86-138">Generieren Sie den neuen Identitätsschlüssels (falls erforderlich).</span><span class="sxs-lookup"><span data-stu-id="c1f86-138">Generate the new identity key (if necessary).</span></span>  
  
    ```console  
    sn -k IdentityKey.snk  
    ```  
  
2. <span data-ttu-id="c1f86-139">Extrahieren Sie den öffentlichen Identitätsschlüssel, und geben Sie an, dass ein SHA-2-Algorithmus beim Signieren mit diesem Schlüssel verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c1f86-139">Extract the identity public key, and specify that a SHA-2 algorithm should be used when signing with this key.</span></span>  
  
    ```console  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3. <span data-ttu-id="c1f86-140">Führen Sie eine verzögerte Signierung der Assembly mit der öffentlichen Identitätsschlüsseldatei durch.</span><span class="sxs-lookup"><span data-stu-id="c1f86-140">Delay-sign the assembly with the identity public key file.</span></span>  
  
    ```console  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4. <span data-ttu-id="c1f86-141">Signieren Sie die Assembly mit dem vollständigen Identitätsschlüsselpaar erneut.</span><span class="sxs-lookup"><span data-stu-id="c1f86-141">Re-sign the assembly with the full identity key pair.</span></span>  
  
    ```console  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### <a name="sign-with-sha-2-with-key-migration"></a><span data-ttu-id="c1f86-142">Signieren einer Assembly mit SHA-2 und Schlüsselmigration</span><span class="sxs-lookup"><span data-stu-id="c1f86-142">Sign with SHA-2, with key migration</span></span>  

 <span data-ttu-id="c1f86-143">Führen Sie die folgenden Befehle über eine Eingabeaufforderung aus, um eine Assembly zu signieren und dabei eine migrierte Signatur eines starken Namens zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1f86-143">Run the following commands from a command prompt to sign an assembly with a migrated strong name signature.</span></span>  
  
1. <span data-ttu-id="c1f86-144">Generieren Sie ein Identitäts- und Signaturschlüsselpaar (falls erforderlich).</span><span class="sxs-lookup"><span data-stu-id="c1f86-144">Generate an identity and signature key pair (if necessary).</span></span>  
  
    ```console  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2. <span data-ttu-id="c1f86-145">Extrahieren Sie den öffentlichen Signaturschlüssel, und geben Sie an, dass ein SHA-2-Algorithmus beim Signieren mit diesem Schlüssel verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c1f86-145">Extract the signature public key, and specify that a SHA-2 algorithm should be used when signing with this key.</span></span>  
  
    ```console  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3. <span data-ttu-id="c1f86-146">Extrahieren Sie den öffentlichen Identitätsschlüssel, der den Hashalgorithmus bestimmt, der eine Gegensignatur generiert.</span><span class="sxs-lookup"><span data-stu-id="c1f86-146">Extract the identity public key, which determines the hash algorithm that generates a counter-signature.</span></span>  
  
    ```console  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4. <span data-ttu-id="c1f86-147">Generieren Sie die Parameter für ein <xref:System.Reflection.AssemblySignatureKeyAttribute>-Attribut, und fügen Sie das Attribut an die Assembly an.</span><span class="sxs-lookup"><span data-stu-id="c1f86-147">Generate the parameters for a <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute, and attach the attribute to the assembly.</span></span>  
  
    ```console  
    sn -a IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  

    <span data-ttu-id="c1f86-148">Dadurch wird eine Ausgabe erzeugt, die der Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="c1f86-148">This produces output similar to the following.</span></span>

    ```output
    Information for key migration attribute.
    (System.Reflection.AssemblySignatureKeyAttribute):
    publicKey=
    002400000c80000094000000060200000024000052534131000400000100010005a3a81ac0a519
    d96244a9c589fc147c7d403e40ccf184fc290bdd06c7339389a76b738e255a2bce1d56c3e7e936
    e4fc87d45adc82ca94c716b50a65d39d373eea033919a613e4341c66863cb2dc622bcb541762b4
    3893434d219d1c43f07e9c83fada2aed400b9f6e44ff05e3ecde6c2827830b8f43f7ac8e3270a3
    4d153cdd

    counterSignature=
    e3cf7c211678c4d1a7b8fb20276c894ab74c29f0b5a34de4d61e63d4a997222f78cdcbfe4c91eb
    e1ddf9f3505a32edcb2a76f34df0450c4f61e376b70fa3cdeb7374b1b8e2078b121e2ee6e8c6a8
    ed661cc35621b4af53ac29c9e41738f199a81240e8fd478c887d1a30729d34e954a97cddce66e3
    ae5fec2c682e57b7442738
    ```

    <span data-ttu-id="c1f86-149">Diese Ausgabe kann dann in ein AssemblySignatureKeyAttribute transformiert werden.</span><span class="sxs-lookup"><span data-stu-id="c1f86-149">This output can then be transformed into an AssemblySignatureKeyAttribute.</span></span>

    ```csharp
    [assembly:System.Reflection.AssemblySignatureKeyAttribute(
    "002400000c80000094000000060200000024000052534131000400000100010005a3a81ac0a519d96244a9c589fc147c7d403e40ccf184fc290bdd06c7339389a76b738e255a2bce1d56c3e7e936e4fc87d45adc82ca94c716b50a65d39d373eea033919a613e4341c66863cb2dc622bcb541762b43893434d219d1c43f07e9c83fada2aed400b9f6e44ff05e3ecde6c2827830b8f43f7ac8e3270a34d153cdd",
    "e3cf7c211678c4d1a7b8fb20276c894ab74c29f0b5a34de4d61e63d4a997222f78cdcbfe4c91ebe1ddf9f3505a32edcb2a76f34df0450c4f61e376b70fa3cdeb7374b1b8e2078b121e2ee6e8c6a8ed661cc35621b4af53ac29c9e41738f199a81240e8fd478c887d1a30729d34e954a97cddce66e3ae5fec2c682e57b7442738"
    )]
    ```
  
5. <span data-ttu-id="c1f86-150">Führen Sie eine verzögerte Signierung der Assembly mit dem öffentlichen Identitätsschlüssel durch.</span><span class="sxs-lookup"><span data-stu-id="c1f86-150">Delay-sign the assembly with the identity public key.</span></span>  
  
    ```console  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
6. <span data-ttu-id="c1f86-151">Führen Sie eine vollständige Signatur der Assembly mit dem Signaturschlüsselpaar durch.</span><span class="sxs-lookup"><span data-stu-id="c1f86-151">Fully sign the assembly with the signature key pair.</span></span>  
  
    ```console  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c1f86-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1f86-152">See also</span></span>

- [<span data-ttu-id="c1f86-153">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="c1f86-153">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
