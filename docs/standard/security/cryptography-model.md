---
title: .Net-Kryptografiemodell
description: Überprüfen Sie die Implementierungen der üblichen Kryptografiealgorithmen in .net. Erfahren Sie mehr über das erweiterbare Kryptografiemodell der Objekt Vererbung, des streamentwurfs & Konfiguration.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], model
- encryption [.NET], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: 0b3e07238bf0932572c222f7b947cfa7ae0221a9
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556994"
---
# <a name="net-cryptography-model"></a>.Net-Kryptografiemodell

.Net bietet Implementierungen von vielen standardmäßigen Kryptografiealgorithmen, und das .net-Kryptografiemodell ist erweiterbar.

## <a name="object-inheritance"></a>Objektvererbung

Das Kryptografiesystem von .NET implementiert ein erweiterbares Muster der abgeleiteten Klassen Vererbung. Die Hierarchie lautet wie folgt:

- Algorithmustypen Klasse, <xref:System.Security.Cryptography.SymmetricAlgorithm> z <xref:System.Security.Cryptography.AsymmetricAlgorithm> . b <xref:System.Security.Cryptography.HashAlgorithm> ., oder. Diese Ebene ist abstrakt.

- Algorithmusklasse, die von einer Algorithmustypklasse erbt; z. B. <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA> oder <xref:System.Security.Cryptography.ECDiffieHellman>. Diese Ebene ist abstrakt.

- Implementierung einer Algorithmusklasse, die von einer Algorithmusklasse erbt; z. B. <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> oder <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Diese Ebene ist vollständig implementiert.

Mit diesem Muster abgeleiteter Klassen können Sie einen neuen Algorithmus oder eine neue Implementierung eines vorhandenen Algorithmus hinzufügen. Möchten Sie z. B. einen neuen Algorithmus für einen öffentlichem Schlüssel erstellen, würden Sie von der <xref:System.Security.Cryptography.AsymmetricAlgorithm>-Klasse erben. Um eine neue Implementierung eines bestimmten Algorithmus zu erstellen, würden Sie eine nicht abstrakte abgeleitete Klasse dieses Algorithmus erstellen.

## <a name="how-algorithms-are-implemented-in-net"></a>Implementierung von Algorithmen in .net

Als ein Beispiel für die verschiedenen Implementierungen eines Algorithmus können Sie sich symmetrische Algorithmen ansehen. Die Basis für alle symmetrischen Algorithmen ist <xref:System.Security.Cryptography.SymmetricAlgorithm> , die von, und anderen geerbt wird, die <xref:System.Security.Cryptography.Aes> <xref:System.Security.Cryptography.TripleDES> nicht mehr empfohlen werden.

<xref:System.Security.Cryptography.Aes>wird von <xref:System.Security.Cryptography.AesCryptoServiceProvider> , <xref:System.Security.Cryptography.AesCng> und geerbt <xref:System.Security.Cryptography.AesManaged> .

In .NET Framework unter Windows:

* `*CryptoServiceProvider`Algorithmusklassen, wie z <xref:System.Security.Cryptography.AesCryptoServiceProvider> . b., sind Wrapper für die Windows Cryptography API (CAPI)-Implementierung eines Algorithmus.
* `*Cng`Algorithmusklassen, z <xref:System.Security.Cryptography.ECDiffieHellmanCng> . b., sind Wrapper um die CNG-Implementierung (Cryptography Next Generation) von Windows.
* `*Managed`Klassen, wie z <xref:System.Security.Cryptography.AesManaged> . b., werden vollständig in verwaltetem Code geschrieben. `*Managed`Implementierungen sind nicht durch die Federal Information Processing Standards (fps) zertifiziert und möglicherweise langsamer als die `*CryptoServiceProvider` `*Cng` Wrapper Klassen und.

In .net Core und .net 5 und höheren Versionen sind alle Implementierungsklassen ( `*CryptoServiceProvider` , `*Managed` und `*Cng` ) Wrapper für die Betriebssystem Algorithmen (OS). Wenn die Betriebssystem Algorithmen mit der Verwendung von "fps" zertifiziert sind, werden von .net mit der Verwendung von "PPS" Weitere Informationen finden Sie unter [plattformübergreifende Kryptographie](cross-platform-cryptography.md).

In den meisten Fällen ist es nicht erforderlich, direkt auf eine algorithmusimplementierungs Klasse zu verweisen, z `AesCryptoServiceProvider` . b.. Die Methoden und Eigenschaften, die Sie in der Regel benötigen, sind in der Basis Algorithmusklasse, z `Aes` . b. Erstellen Sie eine Instanz einer Standard Implementierungs Klasse, indem Sie eine Factorymethode für die basisalgorithmusklasse verwenden, und verweisen Sie auf die basisalgorithmusklasse. Sehen Sie sich beispielsweise die hervorgehobene Codezeile im folgenden Beispiel an:

:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs" highlight="16":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb" highlight="12":::

## <a name="cryptographic-configuration"></a>Kryptografische Konfiguration

Mithilfe der Kryptografiekonfiguration können Sie eine bestimmte Implementierung eines Algorithmus in einen Algorithmusnamen auflösen und so die Erweiterbarkeit der .net-Kryptografieklassen ermöglichen. Sie können Ihre eigene Hardware- oder Softwareimplementierung eines Algorithmus hinzufügen und die Implementierung dem von Ihnen gewählten Algorithmusnamen zuordnen. Ist in der Konfigurationsdatei kein Algorithmus angegeben, werden die Standardeinstellungen verwendet.

## <a name="choosing-an-algorithm"></a>Auswählen eines Algorithmus

Sie können einen Algorithmus für unterschiedliche Zwecke wählen: z. B. für Datenintegrität, für Datenschutz oder zum Generieren eines Schlüssels. Symmetrische und Hashalgorithmen sind dazu vorgesehen, Daten entweder aus Integritätsgründen (Schutz vor Änderungen) oder aus Datenschutzgründen (Schutz vor Anzeigen) zu schützen. Hashalgorithmen werden hauptsächlich für die Datenintegrität verwendet.

Es folgt eine Liste empfohlener Algorithmen nach Anwendung:

- Datenschutz:
  - <xref:System.Security.Cryptography.Aes>
- Datenintegrität:
  - <xref:System.Security.Cryptography.HMACSHA256>
  - <xref:System.Security.Cryptography.HMACSHA512>
- Digitale Signatur:
  - <xref:System.Security.Cryptography.ECDsa>
  - <xref:System.Security.Cryptography.RSA>
- Schlüsselaustausch:
  - <xref:System.Security.Cryptography.ECDiffieHellman>
  - <xref:System.Security.Cryptography.RSA>
- Zufallszahlengenerierung:
  - <xref:System.Security.Cryptography.RandomNumberGenerator.Create%2A?displayProperty=nameWithType>
- Generieren eines Schlüssels aus einem Kennwort:
  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a>Weitere Informationen

- [Kryptografische Dienste](cryptographic-services.md)
- [Plattformübergreifende Kryptografie](cross-platform-cryptography.md)
- [ASP.net Core Datenschutz](/aspnet/core/security/data-protection/introduction)
