---
ms.openlocfilehash: f9000b19997201c2d3de0643669f9029ff1ca31c
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567944"
---
### <a name="envelopedcms-defaults-to-aes-256-encryption"></a><span data-ttu-id="d6705-101">EnvelopedCms verwendet standardmäßig AES-256-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="d6705-101">EnvelopedCms defaults to AES-256 encryption</span></span>

<span data-ttu-id="d6705-102">Der von `EnvelopedCms` verwendete symmetrische Standardverschlüsselungsalgorithmus hat sich von TripleDES in AES-256 geändert.</span><span class="sxs-lookup"><span data-stu-id="d6705-102">The default symmetric encryption algorithm used by `EnvelopedCms` has changed from TripleDES to AES-256.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d6705-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="d6705-103">Change description</span></span>

<span data-ttu-id="d6705-104">Wenn in .NET Core Vorschau 7 und früheren Versionen <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> zum Verschlüsseln von Daten verwendet wird, ohne einen symmetrischen Verschlüsselungsalgorithmus über eine Konstruktorüberladung anzugeben, wurden die Daten mit dem TripleDES/3DES/3DES/3DEA/DES3-EDE-Algorithmus verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="d6705-104">In .NET Core Preview 7 and earlier versions, when <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> is used to encrypt data without specifying a symmetric encryption algorithm via a constructor overload, the data was encrypted with the TripleDES/3DES/3DEA/DES3-EDE algorithm.</span></span>

<span data-ttu-id="d6705-105">Ab . NET Core 3.0 Vorschau 8 (über Version 4.6.0 des NuGet-Pakets [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/)) wurde der Standardalgorithmus in AES-256 geändert, um die Algorithmen zu modernisieren und die Sicherheit von Standardoptionen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d6705-105">Starting with .NET Core 3.0 Preview 8 (via version 4.6.0 of the [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) NuGet package), the default algorithm has been changed to AES-256 for algorithm modernization and to improve the security of default options.</span></span> <span data-ttu-id="d6705-106">Wenn ein Nachrichtenempfängerzertifikat über einen öffentlichen Diffie-Hellman-Schlüssel (Nicht-EC) verfügt, kann die Verschlüsselung mit einer <xref:System.Security.Cryptography.CryptographicException> aufgrund von Einschränkungen der zugrunde liegenden Plattform fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="d6705-106">If a message recipient certificate has a (non-EC) Diffie-Hellman public key, the encryption operation may fail with a <xref:System.Security.Cryptography.CryptographicException> due to limitations in the underlying platform.</span></span>

<span data-ttu-id="d6705-107">Im folgenden Beispielcode werden die Daten mit TripleDES verschlüsselt, wenn die Ausführung unter .NET Core 3.0 Vorschau 7 oder früher erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d6705-107">In the following sample code, the data is encrypted with TripleDES if running on .NET Core 3.0 Preview 7 or earlier.</span></span> <span data-ttu-id="d6705-108">Wenn die Ausführung unter .NET Core 3.0 Vorschau 8 oder höher erfolgt, wird für die Verschlüsselung AES-256 verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6705-108">If running on .NET Core 3.0 Preview 8 or later, it is encrypted with AES-256.</span></span>

```csharp
EnvelopedCms cms = new EnvelopedCms(content);
cms.Encrypt(recipient);
return cms.Encode();
```

#### <a name="version-introduced"></a><span data-ttu-id="d6705-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d6705-109">Version introduced</span></span>

<span data-ttu-id="d6705-110">3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="d6705-110">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d6705-111">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="d6705-111">Recommended action</span></span>

<span data-ttu-id="d6705-112">Wenn Sie von der Änderung negativ betroffen sind, können Sie die TripleDES-Verschlüsselung wiederherstellen, indem Sie den Bezeichner des Verschlüsselungsalgorithmus in einem <xref:System.Security.Cryptography.Pkcs.EnvelopedCms>-Konstruktor explizit angeben, der einen Parameter vom Typ <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier> enthält, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="d6705-112">If you are negatively impacted by the change, you can restore TripleDES encryption by explicitly specifying the encryption algorithm identifier in an <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> constructor that includes a parameter of type <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>, such as:</span></span>

```csharp
Oid tripleDesOid = new Oid("1.2.840.113549.3.7", null);
AlgorithmIdentifier tripleDesIdentifier = new AlgorithmIdentifier(tripleDesOid);
EnvelopedCms cms = new EnvelopedCms(content, tripleDesIdentifier);

cms.Encrypt(recipient);
return cms.Encode()l
```

#### <a name="category"></a><span data-ttu-id="d6705-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="d6705-113">Category</span></span>

<span data-ttu-id="d6705-114">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="d6705-114">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d6705-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d6705-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor(System.Security.Cryptography.Pkcs.ContentInfo)`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)`

-->
