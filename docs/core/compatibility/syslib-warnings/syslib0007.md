---
title: Warnung SYSLIB0007
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0007 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: c011340665a0c53172bf5b23e032d78301b3cd72
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596320"
---
# <a name="syslib0007-default-implementations-of-cryptography-algorithms-not-supported"></a>SYSLIB0007: Standardimplementierungen von Kryptografiealgorithmen werden nicht unterstützt

Das im .NET Framework vorhandene kryptografische Konfigurationssystem bietet keine kryptografische Agilität und ist in .NET Core sowie .NET 5.0 und höher nicht mehr vorhanden. Die Anforderungen von .NET an die Abwärtskompatibilität hindern das Framework außerdem daran, bestimmte kryptografische APIs zu aktualisieren, um bei den Fortschritten der Kryptografie auf dem aktuellen Stand zu bleiben. Aufgrund dessen sind die folgenden APIs ab .NET 5.0 als veraltet markiert. Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0007` hervor.

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

## <a name="workarounds"></a>Problemumgehung

- Es wird empfohlen, Aufrufe der jetzt veralteten APIs für bestimmte Algorithmen, z. B. <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>, durch Aufrufe von Factorymethoden zu ersetzen. So haben Sie die vollständige Kontrolle darüber, welche Algorithmen instanziiert werden.

- Wenn Sie die Kompatibilität mit vorhandenen von .NET Framework-Apps generierten Payloads aufrechterhalten müssen, die die nun veralteten APIs verwenden, verwenden Sie die in der folgenden Tabelle vorgeschlagenen Ersetzungen. Die Tabelle liefert Ihnen eine Zuordnung von Standardalgorithmen des .NET Frameworks zu ihren Entsprechungen in .NET 5 und höher.

  | .NET Framework | Mit .NET Core/.NET 5.0 und höher kompatible Ersetzung | Bemerkungen |
  | - | - | - |
  | <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.RSA.Create?displayProperty=nameWithType> | |
  | <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.SHA1.Create?displayProperty=nameWithType> | Der SHA-1-Algorithmus gilt als nicht mehr nutzbar. Sie sollten wenn möglich einen stärkeren Algorithmus verwenden. Wenden Sie sich an Ihren Sicherheitsberater, um weitere Schritte abzusprechen. |
  | <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | Der HMACSHA1-Algorithmus sollte für die meisten modernen Anwendungen nicht verwendet werden. Sie sollten wenn möglich einen stärkeren Algorithmus verwenden. Wenden Sie sich an Ihren Sicherheitsberater, um weitere Schritte abzusprechen. |
  | <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | Der HMACSHA1-Algorithmus sollte für die meisten modernen Anwendungen nicht verwendet werden. Sie sollten wenn möglich einen stärkeren Algorithmus verwenden. Wenden Sie sich an Ihren Sicherheitsberater, um weitere Schritte abzusprechen. |
  | <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> |

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Siehe auch

- [Das Instanziieren von Standardimplementierungen kryptografischer Abstraktionen wird nicht unterstützt](../cryptography/5.0/instantiating-default-implementations-of-cryptographic-abstractions-not-supported.md)
