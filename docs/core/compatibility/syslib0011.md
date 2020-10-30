---
title: Warnung „SYSLIB0011“
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung „SYSLIB0011“ generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2b363e565ce1143c162679c6b74621885378d7ff
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333058"
---
# <a name="syslib0011-binaryformatter-serialization-is-obsolete"></a>SYSLIB0011: BinaryFormatter-Serialisierung ist veraltet

Aufgrund der [Sicherheitsrisiken](../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> sind die folgenden APIs ab .NET 5.0 als veraltet markiert. Ihre Verwendung im Code ruft zur Kompilierzeit die Warnung `SYSLIB0011` hervor.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="workaround"></a>Problemumgehung

Verwenden Sie <xref:System.Text.Json.JsonSerializer> oder <xref:System.Xml.Serialization.XmlSerializer> anstelle von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.

Weitere Informationen zu empfohlenen Aktionen finden Sie unter [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter) (Auflösen von Fehlern aufgrund der Veraltung und Deaktivierung von BinaryFormatter).

## <a name="see-also"></a>Siehe auch

- [Beheben von Fehlern aufgrund der Veraltung und Deaktivierung von BinaryFormatter](https://aka.ms/binaryformatter)
- [BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten](corefx.md#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps)
