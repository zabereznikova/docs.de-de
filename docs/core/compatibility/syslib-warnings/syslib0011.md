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
# <a name="syslib0011-binaryformatter-serialization-is-obsolete"></a><span data-ttu-id="d8883-103">SYSLIB0011: BinaryFormatter-Serialisierung ist veraltet</span><span class="sxs-lookup"><span data-stu-id="d8883-103">SYSLIB0011: BinaryFormatter serialization is obsolete</span></span>

<span data-ttu-id="d8883-104">Aufgrund der [Sicherheitsrisiken](../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> sind die folgenden APIs ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d8883-104">Due to [security vulnerabilities](../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="d8883-105">Ihre Verwendung im Code ruft zur Kompilierzeit die Warnung `SYSLIB0011` hervor.</span><span class="sxs-lookup"><span data-stu-id="d8883-105">Using them in code generates warning `SYSLIB0011` at compile time.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="d8883-106">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="d8883-106">Workarounds</span></span>

<span data-ttu-id="d8883-107">Verwenden Sie <xref:System.Text.Json.JsonSerializer> oder <xref:System.Xml.Serialization.XmlSerializer> anstelle von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="d8883-107">Consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer> instead of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span>

<span data-ttu-id="d8883-108">Weitere Informationen zu empfohlenen Aktionen finden Sie unter [Resolving BinaryFormatter obsoletion and disablement errors](../../../standard/serialization/binaryformatter-security-guide.md) (Auflösen von Fehlern aufgrund der Veraltung und Deaktivierung von BinaryFormatter).</span><span class="sxs-lookup"><span data-stu-id="d8883-108">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](../../../standard/serialization/binaryformatter-security-guide.md).</span></span>

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="d8883-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8883-109">See also</span></span>

- [<span data-ttu-id="d8883-110">Beheben von Fehlern aufgrund der Veraltung und Deaktivierung von BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="d8883-110">Resolving BinaryFormatter obsoletion and disablement errors</span></span>](../../../standard/serialization/binaryformatter-security-guide.md)
- [<span data-ttu-id="d8883-111">BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten</span><span class="sxs-lookup"><span data-stu-id="d8883-111">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](../core-libraries/5.0/binaryformatter-serialization-obsolete.md)
