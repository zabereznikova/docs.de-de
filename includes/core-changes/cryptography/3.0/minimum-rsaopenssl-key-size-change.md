---
ms.openlocfilehash: b5b724afefcce69df706f2bea0b1612db653af03
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274798"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a><span data-ttu-id="f1086-101">Die Mindestgröße für die Generierung von RSAOpenSsl-Schlüsseln wurde heraufgesetzt</span><span class="sxs-lookup"><span data-stu-id="f1086-101">Minimum size for RSAOpenSsl key generation has increased</span></span>

<span data-ttu-id="f1086-102">Die Mindestgröße für das Erstellen neuer RSA-Schlüssel unter Linux wurde von 384 Bit auf 512 Bit heraufgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f1086-102">The minimum size for generating new RSA keys on Linux has increased from 384-bit to 512-bit.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f1086-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="f1086-103">Change description</span></span>

<span data-ttu-id="f1086-104">Mit .NET Core 3.0 wurde die mindestens erforderliche Schlüsselgröße, die von der `LegalKeySizes`-Eigenschaft auf RSA-Instanzen von <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A> und <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A> unter Linux gemeldet wird, von 384 auf 512 erhöht.</span><span class="sxs-lookup"><span data-stu-id="f1086-104">Starting with .NET Core 3.0, the minimum legal key size reported by the `LegalKeySizes` property on RSA instances from <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A>, and <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A> on Linux has increased from 384 to 512.</span></span>

<span data-ttu-id="f1086-105">Infolgedessen ist in . NET Core 2.2 und früheren Versionen ein Methodenaufruf wie `RSA.Create(384)` erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="f1086-105">As a result, in .NET Core 2.2 and earlier versions, a method call such as `RSA.Create(384)` succeeds.</span></span> <span data-ttu-id="f1086-106">In .NET Core 3.0 und höheren Versionen löst der Methodenaufruf `RSA.Create(384)` eine Ausnahme aus, die anzeigt, dass die Größe zu klein ist.</span><span class="sxs-lookup"><span data-stu-id="f1086-106">In .NET Core 3.0 and later versions, the method call `RSA.Create(384)` throws an exception indicating the size is too small.</span></span>

<span data-ttu-id="f1086-107">Diese Änderung wurde vorgenommen, weil für OpenSSL (Software zum Durchführen der kryptografischen Vorgänge unter Linux) der Mindestwert von Version 1.0.2 zu Version 1.1.0 erhöht wurde.</span><span class="sxs-lookup"><span data-stu-id="f1086-107">This change was made because OpenSSL, which performs the cryptographic operations on Linux, raised its minimum between versions 1.0.2 and 1.1.0.</span></span> <span data-ttu-id="f1086-108">.NET Core 3.0 zieht OpenSSL 1.1.x 1.0.x vor, und die mindestens gemeldete Version wurde erhöht, um dieser neuen höheren Abhängigkeitseinschränkung Rechnung zu tragen.</span><span class="sxs-lookup"><span data-stu-id="f1086-108">.NET Core 3.0 prefers OpenSSL 1.1.x to 1.0.x, and the minimum reported version was raised to reflect this new higher dependency limitation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f1086-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f1086-109">Version introduced</span></span>

<span data-ttu-id="f1086-110">3.0</span><span class="sxs-lookup"><span data-stu-id="f1086-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f1086-111">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="f1086-111">Recommended action</span></span>

<span data-ttu-id="f1086-112">Wenn Sie eine der betroffenen APIs aufzurufen, stellen Sie sicher, dass die Größe der generierten Schlüssel nicht kleiner ist als der Anbietermindestwert.</span><span class="sxs-lookup"><span data-stu-id="f1086-112">If you call any of the affected APIs, ensure that the size of any generated keys is not less than the provider minimum.</span></span>

> [!NOTE]
> <span data-ttu-id="f1086-113">384-Bit-RSA wird bereits als unsicher angesehen (ebenso wie 512-Bit-RSA).</span><span class="sxs-lookup"><span data-stu-id="f1086-113">384-bit RSA is already considered insecure (as is 512-bit RSA).</span></span> <span data-ttu-id="f1086-114">Moderne Empfehlungen (z.B. [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)) schlagen 2048-Bit als Mindestgröße für neu generierte Schlüssel vor.</span><span class="sxs-lookup"><span data-stu-id="f1086-114">Modern recommendations, such as [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), suggest 2048-bit as the minimum size for newly generated keys.</span></span>

#### <a name="category"></a><span data-ttu-id="f1086-115">Kategorie</span><span class="sxs-lookup"><span data-stu-id="f1086-115">Category</span></span>

<span data-ttu-id="f1086-116">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="f1086-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f1086-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f1086-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A>

<!--
### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`

-->
