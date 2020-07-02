---
ms.openlocfilehash: 0b62eff8d70873293aafa539f40bf032672df57a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616253"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a>Verwaltete Kryptografieklassen lösen im FIPS-Modus keine CryptographyException aus

#### <a name="details"></a>Details

In .NET Framework 4.7.2 und früheren Versionen lösen verwaltete Kryptografieanbieterklassen wie <xref:System.Security.Cryptography.SHA256Managed> eine Ausnahme des Typs <xref:System.Security.Cryptography.CryptographicException> aus, wenn die kryptografischen Systembibliotheken im FIPS-Modus konfiguriert sind. Diese Ausnahmen werden ausgelöst, da die verwalteten Versionen nicht gemäß FIPS 140-2 (Federal Information Processing Standards) zertifiziert sind. Zudem werden Kryptografiealgorithmen blockiert, die im Sinne der FIPS-Regeln als nicht genehmigt galten.  Da nur wenige Entwickler ihre Entwicklungscomputer im FIPS-Modus betreiben, werden diese Ausnahmen regelmäßig nur bei Produktionssystemen ausgelöst. Anwendungen, die .NET Framework 4.8 und höhere Versionen verwenden, wechseln automatisch zur neueren, gelockerten Richtlinie, sodass <xref:System.Security.Cryptography.CryptographicException> in diesen Fällen nicht mehr standardmäßig ausgelöst wird. Stattdessen leiten die verwalteten Kryptografieklassen kryptografische Vorgänge an eine kryptografische Systembibliothek weiter. Durch diese Richtlinienänderung wird ein möglicherweise verwirrender Unterschied zwischen Entwicklungs- und Produktionsumgebungen beseitigt, und native Komponenten und verwaltete Komponenten werden gemäß derselben Kryptografierichtlinie ausgeführt.

#### <a name="suggestion"></a>Vorschlag

Wenn dieses Verhalten nicht erwünscht ist, können Sie sich dagegen entscheiden und das vorherige Verhalten wiederherstellen, sodass <xref:System.Security.Cryptography.CryptographicException> im FIPS-Modus ausgelöst wird, indem Sie die folgende [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Konfigurationseinstellung im Abschnitt [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Konfigurationsdatei Ihrer Anwendung hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=true" />
</runtime>
```

Wenn Ihre Anwendung .NET Framework 4.7.2 oder frühere Versionen verwendet, können Sie diese Änderung aktivieren, indem Sie die folgende [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Konfigurationseinstellung im Abschnitt [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Konfigurationsdatei Ihrer Anwendung hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=false" />
</runtime>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.8         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType>
