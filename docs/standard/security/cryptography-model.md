---
title: .Net-Kryptografiemodell
description: Überprüfen Sie die Implementierungen der üblichen Kryptografiealgorithmen in .net. Erfahren Sie mehr über das erweiterbare Kryptografiemodell der Objekt Vererbung, des streamentwurfs & Konfiguration.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], model
- encryption [.NET], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: f9ec08992cb8db8f81f11de661612e1b7d15131c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831116"
---
# <a name="net-cryptography-model"></a><span data-ttu-id="544f3-104">.Net-Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="544f3-104">.NET Cryptography Model</span></span>

<span data-ttu-id="544f3-105">.Net bietet Implementierungen von vielen standardmäßigen Kryptografiealgorithmen, und das .net-Kryptografiemodell ist erweiterbar.</span><span class="sxs-lookup"><span data-stu-id="544f3-105">.NET provides implementations of many standard cryptographic algorithms, and the .NET cryptography model is extensible.</span></span>

## <a name="object-inheritance"></a><span data-ttu-id="544f3-106">Objektvererbung</span><span class="sxs-lookup"><span data-stu-id="544f3-106">Object Inheritance</span></span>

<span data-ttu-id="544f3-107">Das Kryptografiesystem von .NET implementiert ein erweiterbares Muster der abgeleiteten Klassen Vererbung.</span><span class="sxs-lookup"><span data-stu-id="544f3-107">The .NET cryptography system implements an extensible pattern of derived class inheritance.</span></span> <span data-ttu-id="544f3-108">Die Hierarchie lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="544f3-108">The hierarchy is as follows:</span></span>

- <span data-ttu-id="544f3-109">Algorithmustypen Klasse, <xref:System.Security.Cryptography.SymmetricAlgorithm> z  <xref:System.Security.Cryptography.AsymmetricAlgorithm> . b <xref:System.Security.Cryptography.HashAlgorithm> ., oder.</span><span class="sxs-lookup"><span data-stu-id="544f3-109">Algorithm type class, such as <xref:System.Security.Cryptography.SymmetricAlgorithm>,  <xref:System.Security.Cryptography.AsymmetricAlgorithm>, or <xref:System.Security.Cryptography.HashAlgorithm>.</span></span> <span data-ttu-id="544f3-110">Diese Ebene ist abstrakt.</span><span class="sxs-lookup"><span data-stu-id="544f3-110">This level is abstract.</span></span>

- <span data-ttu-id="544f3-111">Algorithmusklasse, die von einer Algorithmustypklasse erbt; z. B. <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA> oder <xref:System.Security.Cryptography.ECDiffieHellman>.</span><span class="sxs-lookup"><span data-stu-id="544f3-111">Algorithm class that inherits from an algorithm type class; for example, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA>, or <xref:System.Security.Cryptography.ECDiffieHellman>.</span></span> <span data-ttu-id="544f3-112">Diese Ebene ist abstrakt.</span><span class="sxs-lookup"><span data-stu-id="544f3-112">This level is abstract.</span></span>

- <span data-ttu-id="544f3-113">Implementierung einer Algorithmusklasse, die von einer Algorithmusklasse erbt; z. B. <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> oder <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span><span class="sxs-lookup"><span data-stu-id="544f3-113">Implementation of an algorithm class that inherits from an algorithm class; for example, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider>, or <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="544f3-114">Diese Ebene ist vollständig implementiert.</span><span class="sxs-lookup"><span data-stu-id="544f3-114">This level is fully implemented.</span></span>

<span data-ttu-id="544f3-115">Mit diesem Muster abgeleiteter Klassen können Sie einen neuen Algorithmus oder eine neue Implementierung eines vorhandenen Algorithmus hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="544f3-115">This pattern of derived classes lets you add a new algorithm or a new implementation of an existing algorithm.</span></span> <span data-ttu-id="544f3-116">Möchten Sie z. B. einen neuen Algorithmus für einen öffentlichem Schlüssel erstellen, würden Sie von der <xref:System.Security.Cryptography.AsymmetricAlgorithm>-Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="544f3-116">For example, to create a new public-key algorithm, you would inherit from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class.</span></span> <span data-ttu-id="544f3-117">Um eine neue Implementierung eines bestimmten Algorithmus zu erstellen, würden Sie eine nicht abstrakte abgeleitete Klasse dieses Algorithmus erstellen.</span><span class="sxs-lookup"><span data-stu-id="544f3-117">To create a new implementation of a specific algorithm, you would create a non-abstract derived class of that algorithm.</span></span>

## <a name="how-algorithms-are-implemented-in-net"></a><span data-ttu-id="544f3-118">Implementierung von Algorithmen in .net</span><span class="sxs-lookup"><span data-stu-id="544f3-118">How Algorithms Are Implemented in .NET</span></span>

<span data-ttu-id="544f3-119">Als ein Beispiel für die verschiedenen Implementierungen eines Algorithmus können Sie sich symmetrische Algorithmen ansehen.</span><span class="sxs-lookup"><span data-stu-id="544f3-119">As an example of the different implementations available for an algorithm, consider symmetric algorithms.</span></span> <span data-ttu-id="544f3-120">Die Basis für alle symmetrischen Algorithmen ist <xref:System.Security.Cryptography.SymmetricAlgorithm> , die von, und anderen geerbt wird, die <xref:System.Security.Cryptography.Aes> <xref:System.Security.Cryptography.TripleDES> nicht mehr empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="544f3-120">The base for all symmetric algorithms is <xref:System.Security.Cryptography.SymmetricAlgorithm>, which is inherited by <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.TripleDES>, and others that are no longer recommended.</span></span>

<span data-ttu-id="544f3-121"><xref:System.Security.Cryptography.Aes> wird von <xref:System.Security.Cryptography.AesCryptoServiceProvider> , <xref:System.Security.Cryptography.AesCng> und geerbt <xref:System.Security.Cryptography.AesManaged> .</span><span class="sxs-lookup"><span data-stu-id="544f3-121"><xref:System.Security.Cryptography.Aes> is inherited by <xref:System.Security.Cryptography.AesCryptoServiceProvider>, <xref:System.Security.Cryptography.AesCng>, and <xref:System.Security.Cryptography.AesManaged>.</span></span>

<span data-ttu-id="544f3-122">In .NET Framework unter Windows:</span><span class="sxs-lookup"><span data-stu-id="544f3-122">In .NET Framework on Windows:</span></span>

* <span data-ttu-id="544f3-123">`*CryptoServiceProvider` Algorithmusklassen, wie z <xref:System.Security.Cryptography.AesCryptoServiceProvider> . b., sind Wrapper für die Windows Cryptography API (CAPI)-Implementierung eines Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="544f3-123">`*CryptoServiceProvider` algorithm classes, such as <xref:System.Security.Cryptography.AesCryptoServiceProvider>, are wrappers around the Windows Cryptography API (CAPI) implementation of an algorithm.</span></span>
* <span data-ttu-id="544f3-124">`*Cng` Algorithmusklassen, wie z <xref:System.Security.Cryptography.ECDiffieHellmanCng> . b., sind Wrapper um die CNG-Implementierung (Cryptography Next Generation) von Windows.</span><span class="sxs-lookup"><span data-stu-id="544f3-124">`*Cng` algorithm classes, such as <xref:System.Security.Cryptography.ECDiffieHellmanCng>, are wrappers around the Windows Cryptography Next Generation (CNG) implementation.</span></span>
* <span data-ttu-id="544f3-125">`*Managed` Klassen, wie z <xref:System.Security.Cryptography.AesManaged> . b., werden vollständig in verwaltetem Code geschrieben.</span><span class="sxs-lookup"><span data-stu-id="544f3-125">`*Managed` classes, such as <xref:System.Security.Cryptography.AesManaged>, are written entirely in managed code.</span></span> <span data-ttu-id="544f3-126">`*Managed` Implementierungen sind nicht durch die Federal Information Processing Standards (fps) zertifiziert und möglicherweise langsamer als die `*CryptoServiceProvider` `*Cng` Wrapper Klassen und.</span><span class="sxs-lookup"><span data-stu-id="544f3-126">`*Managed` implementations are not certified by the Federal Information Processing Standards (FIPS), and may be slower than the `*CryptoServiceProvider` and `*Cng` wrapper classes.</span></span>

<span data-ttu-id="544f3-127">In .net Core und .net 5 und höheren Versionen sind alle Implementierungsklassen ( `*CryptoServiceProvider` , `*Managed` und `*Cng` ) Wrapper für die Betriebssystem Algorithmen (OS).</span><span class="sxs-lookup"><span data-stu-id="544f3-127">In .NET Core and .NET 5 and later versions, all implementation classes (`*CryptoServiceProvider`, `*Managed`, and `*Cng`) are wrappers for the operating system (OS) algorithms.</span></span> <span data-ttu-id="544f3-128">Wenn die Betriebssystem Algorithmen mit der Verwendung von "fps" zertifiziert sind, werden von .net mit der Verwendung von "PPS"</span><span class="sxs-lookup"><span data-stu-id="544f3-128">If the OS algorithms are FIPS-certified, then .NET uses FIPS-certified algorithms.</span></span> <span data-ttu-id="544f3-129">Weitere Informationen finden Sie unter [plattformübergreifende Kryptographie](cross-platform-cryptography.md).</span><span class="sxs-lookup"><span data-stu-id="544f3-129">For more information, see [Cross-Platform Cryptography](cross-platform-cryptography.md).</span></span>

<span data-ttu-id="544f3-130">In den meisten Fällen ist es nicht erforderlich, direkt auf eine algorithmusimplementierungs Klasse zu verweisen, z `AesCryptoServiceProvider` . b..</span><span class="sxs-lookup"><span data-stu-id="544f3-130">In most cases, you don't need to directly reference an algorithm implementation class, such as `AesCryptoServiceProvider`.</span></span> <span data-ttu-id="544f3-131">Die Methoden und Eigenschaften, die Sie in der Regel benötigen, sind in der Basis Algorithmusklasse, z `Aes` . b.</span><span class="sxs-lookup"><span data-stu-id="544f3-131">The methods and properties you typically need are on the base algorithm class, such as `Aes`.</span></span> <span data-ttu-id="544f3-132">Erstellen Sie eine Instanz einer Standard Implementierungs Klasse, indem Sie eine Factorymethode für die basisalgorithmusklasse verwenden, und verweisen Sie auf die basisalgorithmusklasse.</span><span class="sxs-lookup"><span data-stu-id="544f3-132">Create an instance of a default implementation class by using a factory method on the base algorithm class, and refer to the base algorithm class.</span></span> <span data-ttu-id="544f3-133">Sehen Sie sich beispielsweise die hervorgehobene Codezeile im folgenden Beispiel an:</span><span class="sxs-lookup"><span data-stu-id="544f3-133">For example, see the highlighted line of code in the following example:</span></span>

:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs" highlight="16":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb" highlight="12":::

## <a name="cryptographic-configuration"></a><span data-ttu-id="544f3-134">Kryptografische Konfiguration</span><span class="sxs-lookup"><span data-stu-id="544f3-134">Cryptographic Configuration</span></span>

<span data-ttu-id="544f3-135">Mithilfe der Kryptografiekonfiguration können Sie eine bestimmte Implementierung eines Algorithmus in einen Algorithmusnamen auflösen und so die Erweiterbarkeit der .net-Kryptografieklassen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="544f3-135">Cryptographic configuration lets you resolve a specific implementation of an algorithm to an algorithm name, allowing extensibility of the .NET cryptography classes.</span></span> <span data-ttu-id="544f3-136">Sie können Ihre eigene Hardware- oder Softwareimplementierung eines Algorithmus hinzufügen und die Implementierung dem von Ihnen gewählten Algorithmusnamen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="544f3-136">You can add your own hardware or software implementation of an algorithm and map the implementation to the algorithm name of your choice.</span></span> <span data-ttu-id="544f3-137">Ist in der Konfigurationsdatei kein Algorithmus angegeben, werden die Standardeinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="544f3-137">If an algorithm is not specified in the configuration file, the default settings are used.</span></span>

## <a name="choosing-an-algorithm"></a><span data-ttu-id="544f3-138">Auswählen eines Algorithmus</span><span class="sxs-lookup"><span data-stu-id="544f3-138">Choosing an Algorithm</span></span>

<span data-ttu-id="544f3-139">Sie können einen Algorithmus für unterschiedliche Zwecke wählen: z. B. für Datenintegrität, für Datenschutz oder zum Generieren eines Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="544f3-139">You can select an algorithm for different reasons: for example, for data integrity, for data privacy, or to generate a key.</span></span> <span data-ttu-id="544f3-140">Symmetrische und Hashalgorithmen sind dazu vorgesehen, Daten entweder aus Integritätsgründen (Schutz vor Änderungen) oder aus Datenschutzgründen (Schutz vor Anzeigen) zu schützen.</span><span class="sxs-lookup"><span data-stu-id="544f3-140">Symmetric and hash algorithms are intended for protecting data for either integrity reasons (protect from change) or privacy reasons (protect from viewing).</span></span> <span data-ttu-id="544f3-141">Hashalgorithmen werden hauptsächlich für die Datenintegrität verwendet.</span><span class="sxs-lookup"><span data-stu-id="544f3-141">Hash algorithms are used primarily for data integrity.</span></span>

<span data-ttu-id="544f3-142">Es folgt eine Liste empfohlener Algorithmen nach Anwendung:</span><span class="sxs-lookup"><span data-stu-id="544f3-142">Here is a list of recommended algorithms by application:</span></span>

- <span data-ttu-id="544f3-143">Datenschutz:</span><span class="sxs-lookup"><span data-stu-id="544f3-143">Data privacy:</span></span>
  - <xref:System.Security.Cryptography.Aes>
- <span data-ttu-id="544f3-144">Datenintegrität:</span><span class="sxs-lookup"><span data-stu-id="544f3-144">Data integrity:</span></span>
  - <xref:System.Security.Cryptography.HMACSHA256>
  - <xref:System.Security.Cryptography.HMACSHA512>
- <span data-ttu-id="544f3-145">Digitale Signatur:</span><span class="sxs-lookup"><span data-stu-id="544f3-145">Digital signature:</span></span>
  - <xref:System.Security.Cryptography.ECDsa>
  - <xref:System.Security.Cryptography.RSA>
- <span data-ttu-id="544f3-146">Schlüsselaustausch:</span><span class="sxs-lookup"><span data-stu-id="544f3-146">Key exchange:</span></span>
  - <xref:System.Security.Cryptography.ECDiffieHellman>
  - <xref:System.Security.Cryptography.RSA>
- <span data-ttu-id="544f3-147">Zufallszahlengenerierung:</span><span class="sxs-lookup"><span data-stu-id="544f3-147">Random number generation:</span></span>
  - <xref:System.Security.Cryptography.RandomNumberGenerator.Create%2A?displayProperty=nameWithType>
- <span data-ttu-id="544f3-148">Generieren eines Schlüssels aus einem Kennwort:</span><span class="sxs-lookup"><span data-stu-id="544f3-148">Generating a key from a password:</span></span>
  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a><span data-ttu-id="544f3-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="544f3-149">See also</span></span>

- [<span data-ttu-id="544f3-150">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="544f3-150">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="544f3-151">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="544f3-151">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="544f3-152">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="544f3-152">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
