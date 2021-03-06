---
title: Warnung „SYSLIB0011“
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung „SYSLIB0011“ generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 85b5e07b1ecd6852d8c8e93cc3e89ced4b021ef9
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189856"
---
# <a name="syslib0011-binaryformatter-serialization-is-obsolete"></a>SYSLIB0011: BinaryFormatter-Serialisierung ist veraltet

Aufgrund der [Sicherheitsrisiken](../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> sind die folgenden APIs ab .NET 5.0 als veraltet markiert. Ihre Verwendung im Code ruft zur Kompilierzeit die Warnung `SYSLIB0011` hervor.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="workarounds"></a>Problemumgehung

Verwenden Sie <xref:System.Text.Json.JsonSerializer> oder <xref:System.Xml.Serialization.XmlSerializer> anstelle von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.

Weitere Informationen zu empfohlenen Aktionen finden Sie unter [Resolving BinaryFormatter obsoletion and disablement errors](../../../standard/serialization/binaryformatter-security-guide.md) (Auflösen von Fehlern aufgrund der Veraltung und Deaktivierung von BinaryFormatter).

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Siehe auch

- [Beheben von Fehlern aufgrund der Veraltung und Deaktivierung von BinaryFormatter](../../../standard/serialization/binaryformatter-security-guide.md)
- [BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten](../core-libraries/5.0/binaryformatter-serialization-obsolete.md)
