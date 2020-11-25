---
title: Verwenden von starken Namen (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
ms.openlocfilehash: 7e431f3a41fadb7247f20d7ab9bb9120e827b0cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732293"
---
# <a name="strong-naming-unmanaged-api-reference"></a><span data-ttu-id="4f231-102">Verwenden von starken Namen (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="4f231-102">Strong Naming (Unmanaged API Reference)</span></span>

<span data-ttu-id="4f231-103">Die API für starke Namen ermöglicht es einem Client, die starke Namenssignierung für Assemblys zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4f231-103">The strong naming API enables a client to administer strong name signing for assemblies.</span></span>  
  
 <span data-ttu-id="4f231-104">Beim Signieren einer Assembly mit einem starken Namen wird der Datei, die das Assemblymanifest enthält, eine Verschlüsselung mit einem öffentlichen Schlüssel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4f231-104">Signing an assembly with a strong name adds a public key encryption to the file containing the assembly manifest.</span></span> <span data-ttu-id="4f231-105">Das Signieren mit starkem Namen gewährleistet die Eindeutigkeit der Namen, verhindert das Vortäuschen von Namen (Spoofing) und stellt Aufrufern beim Auflösen eines Verweises eine eindeutige Identität bereit.</span><span class="sxs-lookup"><span data-stu-id="4f231-105">Strong name signing helps verify name uniqueness, prevents name spoofing, and provides callers with a unique identity when a reference is resolved.</span></span> <span data-ttu-id="4f231-106">Mit einem starken Namen ist jedoch keine Vertrauensebene verknüpft.</span><span class="sxs-lookup"><span data-stu-id="4f231-106">However, no level of trust is associated with a strong name.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f231-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4f231-107">In This Section</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f231-108">All diese Funktionen sind ab .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="4f231-108">All of these functions have been deprecated starting with the .NET Framework 4.</span></span> <span data-ttu-id="4f231-109">Empfohlene Alternativen finden Sie in der [ICLRStrongName](../hosting/iclrstrongname-interface.md)-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4f231-109">For suggested alternatives, see the [ICLRStrongName](../hosting/iclrstrongname-interface.md) interface.</span></span>  
  
 [<span data-ttu-id="4f231-110">GetHashFromAssemblyFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-110">GetHashFromAssemblyFile Function</span></span>](gethashfromassemblyfile-function.md)  
 <span data-ttu-id="4f231-111">Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="4f231-111">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="4f231-112">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-112">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-113">GetHashFromAssemblyFileW-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-113">GetHashFromAssemblyFileW Function</span></span>](gethashfromassemblyfilew-function.md)  
 <span data-ttu-id="4f231-114">Ruft einen Hash der als Unicode-Zeichenfolge angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="4f231-114">Gets a hash of the assembly file specified as a Unicode string, using the specified hash algorithm.</span></span> <span data-ttu-id="4f231-115">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-115">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-116">GetHashFromBlob-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-116">GetHashFromBlob Function</span></span>](gethashfromblob-function.md)  
 <span data-ttu-id="4f231-117">Ruft einen Hash der Assembly unter der angegebenen Speicheradresse unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="4f231-117">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span> <span data-ttu-id="4f231-118">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-118">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-119">GetHashFromFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-119">GetHashFromFile Function</span></span>](gethashfromfile-function.md)  
 <span data-ttu-id="4f231-120">Generiert einen Hashwert für den Inhalt der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="4f231-120">Generates a hash over the contents of the specified file.</span></span>  <span data-ttu-id="4f231-121">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-121">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-122">GetHashFromFileW-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-122">GetHashFromFileW Function</span></span>](gethashfromfilew-function.md)  
 <span data-ttu-id="4f231-123">Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="4f231-123">Generates a hash over the contents of the file specified by a Unicode string.</span></span> <span data-ttu-id="4f231-124">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-124">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-125">GetHashFromHandle-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-125">GetHashFromHandle Function</span></span>](gethashfromhandle-function.md)  
 <span data-ttu-id="4f231-126">Generiert einen Hashwert für den Inhalt der Datei mit dem angegebenen Dateihandle unter Verwendung des angegebenen Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="4f231-126">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  <span data-ttu-id="4f231-127">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-127">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-128">StrongNameCompareAssemblies-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-128">StrongNameCompareAssemblies Function</span></span>](strongnamecompareassemblies-function.md)  
 <span data-ttu-id="4f231-129">Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4f231-129">Determines whether two assemblies differ only by their strong name signatures.</span></span> <span data-ttu-id="4f231-130">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-130">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-131">StrongNameErrorInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-131">StrongNameErrorInfo Function</span></span>](strongnameerrorinfo-function.md)  
 <span data-ttu-id="4f231-132">Ruft den letzten Fehlercode ab, der von einer der Funktionen mit starkem Namen ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="4f231-132">Gets the last error code that was raised by one of the strong name functions.</span></span>  
  
 [<span data-ttu-id="4f231-133">StrongNameFreeBuffer-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-133">StrongNameFreeBuffer Function</span></span>](strongnamefreebuffer-function.md)  
 <span data-ttu-id="4f231-134">Gibt Speicher frei, der bei einem vorherigen Aufruf einer Funktion für starke Namen wie [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) oder [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="4f231-134">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>   <span data-ttu-id="4f231-135">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-135">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-136">StrongNameGetBlob-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-136">StrongNameGetBlob Function</span></span>](strongnamegetblob-function.md)  
 <span data-ttu-id="4f231-137">Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse auf.</span><span class="sxs-lookup"><span data-stu-id="4f231-137">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span> <span data-ttu-id="4f231-138">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-138">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-139">StrongNameGetBlobFromImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-139">StrongNameGetBlobFromImage Function</span></span>](strongnamegetblobfromimage-function.md)  
 <span data-ttu-id="4f231-140">Ruft eine binäre Darstellung des Assemblyimages an der angegebenen Speicheradresse ab.</span><span class="sxs-lookup"><span data-stu-id="4f231-140">Gets a binary representation of the assembly image at the specified memory address.</span></span> <span data-ttu-id="4f231-141">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-141">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-142">StrongNameGetPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-142">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)  
 <span data-ttu-id="4f231-143">Ruft den öffentlichen Schlüssel aus einem privaten/öffentlichen Schlüsselpaar ab.</span><span class="sxs-lookup"><span data-stu-id="4f231-143">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="4f231-144">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-144">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-145">StrongNameHashSize-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-145">StrongNameHashSize Function</span></span>](strongnamehashsize-function.md)  
 <span data-ttu-id="4f231-146">Ruft mit dem angegebenen Hashalgorithmus die Puffergröße ab, die für einen Hash erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4f231-146">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  <span data-ttu-id="4f231-147">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-147">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-148">StrongNameKeyDelete-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-148">StrongNameKeyDelete Function</span></span>](strongnamekeydelete-function.md)  
 <span data-ttu-id="4f231-149">Löscht den angegebenen Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="4f231-149">Deletes the specified key container.</span></span> <span data-ttu-id="4f231-150">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-150">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-151">StrongNameKeyGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-151">StrongNameKeyGen Function</span></span>](strongnamekeygen-function.md)  
 <span data-ttu-id="4f231-152">Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.</span><span class="sxs-lookup"><span data-stu-id="4f231-152">Creates a new public/private key pair for strong name use.</span></span>  <span data-ttu-id="4f231-153">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-153">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-154">StrongNameKeyGenEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-154">StrongNameKeyGenEx Function</span></span>](strongnamekeygenex-function.md)  
 <span data-ttu-id="4f231-155">Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung von starken Namen.</span><span class="sxs-lookup"><span data-stu-id="4f231-155">Generates a new public/private key pair with the specified key size for strong name use.</span></span> <span data-ttu-id="4f231-156">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-156">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-157">StrongNameKeyInstall-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-157">StrongNameKeyInstall Function</span></span>](strongnamekeyinstall-function.md)  
 <span data-ttu-id="4f231-158">Importiert ein öffentliches/privates Schlüsselpaar in einen Container.</span><span class="sxs-lookup"><span data-stu-id="4f231-158">Imports a public/private key pair into a container.</span></span>  <span data-ttu-id="4f231-159">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-159">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-160">StrongNameSignatureGeneration-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-160">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)  
 <span data-ttu-id="4f231-161">Generiert eine Signatur mit starkem Namen für die angegebene Assembly.</span><span class="sxs-lookup"><span data-stu-id="4f231-161">Generates a strong name signature for the specified assembly.</span></span>   <span data-ttu-id="4f231-162">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-162">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-163">StrongNameSignatureGenerationEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-163">StrongNameSignatureGenerationEx Function</span></span>](strongnamesignaturegenerationex-function.md)  
 <span data-ttu-id="4f231-164">Generiert eine Signatur mit starkem Namen für die angegebene Assembly basierend auf den angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="4f231-164">Generates a strong name signature for the specified assembly, based on the specified flags.</span></span>    <span data-ttu-id="4f231-165">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-165">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-166">StrongNameSignatureSize-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-166">StrongNameSignatureSize Function</span></span>](strongnamesignaturesize-function.md)  
 <span data-ttu-id="4f231-167">Gibt die Größe der Signatur mit starkem Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="4f231-167">Returns the size of the strong name signature.</span></span> <span data-ttu-id="4f231-168">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-168">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-169">StrongNameSignatureVerification-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-169">StrongNameSignatureVerification Function</span></span>](strongnamesignatureverification-function.md)  
 <span data-ttu-id="4f231-170">Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die gemäß den angegebenen Flags überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="4f231-170">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span> <span data-ttu-id="4f231-171">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-171">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-172">StrongNameSignatureVerificationEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-172">StrongNameSignatureVerificationEx Function</span></span>](strongnamesignatureverificationex-function.md)  
 <span data-ttu-id="4f231-173">Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="4f231-173">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  <span data-ttu-id="4f231-174">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-174">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-175">StrongNameSignatureVerificationFromImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-175">StrongNameSignatureVerificationFromImage Function</span></span>](strongnamesignatureverificationfromimage-function.md)  
 <span data-ttu-id="4f231-176">Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist.</span><span class="sxs-lookup"><span data-stu-id="4f231-176">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span> <span data-ttu-id="4f231-177">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-177">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-178">StrongNameTokenFromAssembly-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-178">StrongNameTokenFromAssembly Function</span></span>](strongnametokenfromassembly-function.md)  
 <span data-ttu-id="4f231-179">Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="4f231-179">Creates a strong name token from the specified assembly file.</span></span>  <span data-ttu-id="4f231-180">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-180">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-181">StrongNameTokenFromAssemblyEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-181">StrongNameTokenFromAssemblyEx Function</span></span>](strongnametokenfromassemblyex-function.md)  
 <span data-ttu-id="4f231-182">Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel zurück.</span><span class="sxs-lookup"><span data-stu-id="4f231-182">Creates a strong name token from the specified assembly file, and returns the public key.</span></span> <span data-ttu-id="4f231-183">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-183">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-184">StrongNameTokenFromPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f231-184">StrongNameTokenFromPublicKey Function</span></span>](strongnametokenfrompublickey-function.md)  
 <span data-ttu-id="4f231-185">Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="4f231-185">Gets a token representing a public key.</span></span> <span data-ttu-id="4f231-186">Ab .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f231-186">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f231-187">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="4f231-187">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)  
 <span data-ttu-id="4f231-188">Stellt den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars im binären Format dar.</span><span class="sxs-lookup"><span data-stu-id="4f231-188">Represents the public key of a public/private key pair in binary format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f231-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f231-189">See also</span></span>

- [<span data-ttu-id="4f231-190">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f231-190">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="4f231-191">Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="4f231-191">Unmanaged API Reference</span></span>](../index.md)
