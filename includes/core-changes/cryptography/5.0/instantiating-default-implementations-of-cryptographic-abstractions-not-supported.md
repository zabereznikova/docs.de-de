---
ms.openlocfilehash: 8198eca5b9c63d9717260b71ac6687dbf7245f35
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159552"
---
### <a name="instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported"></a>Das Instanziieren von Standardimplementierungen kryptografischer Abstraktionen wird nicht unterstützt

Die `Create()`-Überladungen ohne Parameter in kryptografischen Abstraktionen gelten ab .NET 5.0 als Warnung als veraltet.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework 2.0–4.8 können abstrakte kryptografische Primitivfactorys wie <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> so konfiguriert werden, dass sie verschiedene Algorithmen zurückgegeben. In einer Standardinstallation von .NET Framework 4.8 gibt die statische Methode <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> ohne Parameter beispielsweise eine Instanz des SHA1-Algorithmus zurück. Sehen Sie sich dazu den folgenden Codeausschnitt an.

**Nur für .NET Framework**

```csharp
// Return an instance of the default hash algorithm (SHA1).
HashAlgorithm alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA1CryptoServiceProvider'.
Console.WriteLine(alg.GetType());

// Change the default algorithm to be SHA256, not SHA1.
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), typeof(HashAlgorithm).FullName);
alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA256CryptoServiceProvider'.
Console.WriteLine(alg.GetType());
```

Sie können auch eine [computerweite Konfiguration](../../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md) verwenden, um den Standardalgorithmus zu ändern, ohne `CryptoConfig` programmgesteuert aufrufen zu müssen.

In .NET Core 2.0–3.1 führen abstrakte kryptografische Primitivfactorys wie <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> immer zu einer <xref:System.PlatformNotSupportedException>-Ausnahme.

```csharp
// Throws PlatformNotSupportedException on .NET Core.
HashAlgorithm alg = HashAlgorithm.Create();
```

In .NET 5.0 und höheren Versionen sind abstrakte kryptografische Primitivfactorys wie <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> als veraltet gekennzeichnet und führen zu einer Kompilierzeitwarnung mit der ID `SYSLIB0007`. Zur Laufzeit wird für diese Methoden weiterhin eine <xref:System.PlatformNotSupportedException>-Ausnahme zurückgegeben.

```csharp
// Throws PlatformNotSupportedException.
// Also produces compile-time warning SYSLIB0007 on .NET 5+.
HashAlgorithm alg = HashAlgorithm.Create();
```

Dies ist eine Änderung, die nur die Kompilierzeit betrifft. Hinsichtlich der Laufzeit gibt es keine Änderung im Vergleich zu früheren Versionen von .NET Core.

> [!NOTE]
>
> - Nur die Überladungen der `Create()`-Methoden ohne Parameter sind veraltet. Parametrisierte Überladungen sind nicht veraltet und funktionieren weiterhin wie zu erwarten.
>
>   ```csharp
>   // Call Create(string), providing an explicit algorithm family name.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   HashAlgorithm hashAlg = HashAlgorithm.Create("SHA256");
>   ```
>
> - Überladungen ohne Parameter aus *bestimmten* Algorithmusfamilien (keine Abstraktionen) sind nicht veraltet und funktionieren weiterhin wie zu erwarten.
>
>   ```csharp
>   // Call a specific algorithm family's parameterless Create() ctor.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   Aes aesAlg = Aes.Create();
>   ```

#### <a name="reason-for-change"></a>Grund für die Änderung

Das im .NET Framework vorhandene kryptografische Konfigurationssystem ist in .NET Core und .NET 5.0 und höher nicht mehr vorhanden, da das Legacysystem nicht die erforderliche kryptografische Agilität bieten kann. Die Anforderungen von .NET an die Abwärtskompatibilität hindern das Framework außerdem daran, bestimmte kryptografische APIs zu aktualisieren, um bei den Fortschritten der Kryptografie auf dem aktuellen Stand zu bleiben. Die <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>-Methode wurde beispielsweise in .NET Framework 1.0 eingeführt, als der SHA-1-Hashalgorithmus aktuell war. Seitdem sind zwanzig Jahre vergangen, und SHA-1 gilt heute als nicht mehr funktionsfähig. <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> kann aber nicht so geändert werden, dass ein anderer Algorithmus zurückgegeben wird. Diese Änderung würde einen nicht akzeptablen Breaking Change für das Verwenden von Anwendungen mit sich führen.

Laut Best Practices müssen Bibliotheken, die Kryptografieprimitive wie AES, SHA-* und RSA verwenden, die volle Kontrolle darüber haben, wie diese Primitive verwendet werden. Anwendungen, für die zukünftige Überprüfungen erforderlich sind, sollten höhere Bibliotheken verwenden, die diese Primitive einschließen, und Funktionen für Schlüsselverwaltung und kryptografische Agilität hinzufügen. Diese Bibliotheken werden oft von der Hostingumgebung bereitgestellt. Ein Beispiel ist die [Datenschutzbibliothek von ASP.NET](/aspnet/core/security/data-protection/), die diese Bedenken für die aufrufende Anwendung auflösen kann.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RC1

#### <a name="recommended-action"></a>Empfohlene Maßnahme

- Es wird empfohlen, Aufrufe der jetzt veralteten APIs für bestimmte Algorithmen, z. B. <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>, durch Aufrufe von Factorymethoden zu ersetzen. So haben Sie die vollständige Kontrolle darüber, welche Algorithmen instanziiert werden.

- Wenn Sie die Kompatibilität mit vorhandenen von .NET Framework-Apps generierten Payloads aufrechterhalten müssen, die die nun veralteten APIs verwenden, verwenden Sie die in der folgenden Tabelle vorgeschlagenen Ersetzungen. Die Tabelle liefert Ihnen eine Zuordnung von Standardalgorithmen des .NET Frameworks zu ihren Entsprechungen in .NET 5 und höher.

  | .NET Framework | Mit .NET Core/.NET 5.0 und höher kompatible Ersetzung | Bemerkungen |
  | - | - | - |
  | <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.RSA.Create?displayProperty=nameWithType> | |
  | <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.SHA1.Create?displayProperty=nameWithType> | Der SHA-1-Algorithmus gilt als nicht mehr nutzbar. Sie sollten wenn möglich einen stärkeren Algorithmus verwenden. Wenden Sie sich an Ihren Sicherheitsberater, um weitere Schritte abzusprechen. |
  | <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | Der HMACSHA1-Algorithmus sollte für die meisten modernen Anwendungen nicht verwendet werden. Sie sollten wenn möglich einen stärkeren Algorithmus verwenden. Wenden Sie sich an Ihren Sicherheitsberater, um weitere Schritte abzusprechen. |
  | <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | Der HMACSHA1-Algorithmus sollte für die meisten modernen Anwendungen nicht verwendet werden. Sie sollten wenn möglich einen stärkeren Algorithmus verwenden. Wenden Sie sich an Ihren Sicherheitsberater, um weitere Schritte abzusprechen. |
  | <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> |

- Wenn Sie die veralteten `Create()`-Überladungen ohne Parameter weiterhin aufrufen müssen, können Sie die `SYSLIB0007`-Warnung im Code unterdrücken.

  ```csharp
  #pragma warning disable SYSLIB0007 // Disable the warning.
  HashAlgorithm alg = HashAlgorithm.Create(); // Still throws PNSE.
  #pragma warning restore SYSLIB0007 // Re-enable the warning.
  ```

  Sie können die Warnung auch in der Projektdatei unterdrücken. Wenn Sie dies tun, wird die Warnung für alle Quelldateien im Projekt deaktiviert.

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0007 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0007</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > Ein Unterdrücken von `SYSLIB0007` deaktiviert nur die Veraltungswarnungen für die hier aufgeführten Kryptografie-APIs. Andere Warnungen werden nicht deaktiviert. Zusätzlich lösen diese veralteten APIs zur Laufzeit weiterhin eine <xref:System.PlatformNotSupportedException>-Ausnahme aus, selbst wenn Sie die Warnung unterdrücken.

#### <a name="category"></a>Kategorie

- Kryptografie

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.AsymmetricAlgorithm.Create`
- `M:System.Security.Cryptography.HashAlgorithm.Create`
- `M:System.Security.Cryptography.HMAC.Create`
- `M:System.Security.Cryptography.KeyedHashAlgorithm.Create`
- `M:System.Security.Cryptography.SymmetricAlgorithm.Create`

-->
