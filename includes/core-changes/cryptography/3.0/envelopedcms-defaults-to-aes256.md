---
ms.openlocfilehash: e0cdcce9b8c7d591925b08635e3354dadaf22b7b
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556025"
---
### <a name="envelopedcms-defaults-to-aes-256-encryption"></a>EnvelopedCms verwendet standardmäßig AES-256-Verschlüsselung

Der von `EnvelopedCms` verwendete symmetrische Standardverschlüsselungsalgorithmus hat sich von TripleDES in AES-256 geändert.

#### <a name="change-description"></a>Änderungsbeschreibung

Wenn in früheren Versionen <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> zum Verschlüsseln von Daten verwendet wird, ohne einen symmetrischen Verschlüsselungsalgorithmus über eine Konstruktorüberladung anzugeben, werden die Daten mit dem TripleDES/3DES/3DES/3DEA/DES3-EDE-Algorithmus verschlüsselt.

Ab .NET Core 3.0 (über Version 4.6.0 des NuGet-Pakets [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/)) wurde der Standardalgorithmus in AES-256 geändert, um die Algorithmen zu modernisieren und die Sicherheit von Standardoptionen zu verbessern. Wenn ein Nachrichtenempfängerzertifikat über einen öffentlichen Diffie-Hellman-Schlüssel (Nicht-EC) verfügt, kann die Verschlüsselung mit einer <xref:System.Security.Cryptography.CryptographicException> aufgrund von Einschränkungen der zugrunde liegenden Plattform fehlschlagen.

Im folgenden Beispielcode werden die Daten mit TripleDES verschlüsselt, wenn die Ausführung unter .NET Core 2.2 oder früher erfolgt. Wenn die Ausführung unter .NET Core 3.0 oder höher erfolgt, wird für die Verschlüsselung AES-256 verwendet.

```csharp
EnvelopedCms cms = new EnvelopedCms(content);
cms.Encrypt(recipient);
return cms.Encode();
```

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie von der Änderung negativ betroffen sind, können Sie die TripleDES-Verschlüsselung wiederherstellen, indem Sie den Bezeichner des Verschlüsselungsalgorithmus in einem <xref:System.Security.Cryptography.Pkcs.EnvelopedCms>-Konstruktor explizit angeben, der einen Parameter vom Typ <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier> enthält, beispielsweise:

```csharp
Oid tripleDesOid = new Oid("1.2.840.113549.3.7", null);
AlgorithmIdentifier tripleDesIdentifier = new AlgorithmIdentifier(tripleDesOid);
EnvelopedCms cms = new EnvelopedCms(content, tripleDesIdentifier);

cms.Encrypt(recipient);
return cms.Encode()l
```

#### <a name="category"></a>Kategorie

Kryptografie

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.ContentInfo)>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor(System.Security.Cryptography.Pkcs.ContentInfo)`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)`

-->
