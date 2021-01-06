---
title: Warnung „SYSLIB0011“
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung „SYSLIB0011“ generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 36292cc5314e2b7677d705780880b7e25ae0dfb6
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596319"
---
# <a name="syslib0011-binaryformatter-serialization-is-obsolete"></a><span data-ttu-id="2fb21-103">SYSLIB0011: BinaryFormatter-Serialisierung ist veraltet</span><span class="sxs-lookup"><span data-stu-id="2fb21-103">SYSLIB0011: BinaryFormatter serialization is obsolete</span></span>

<span data-ttu-id="2fb21-104">Aufgrund der [Sicherheitsrisiken](../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> sind die folgenden APIs ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="2fb21-104">Due to [security vulnerabilities](../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="2fb21-105">Ihre Verwendung im Code ruft zur Kompilierzeit die Warnung `SYSLIB0011` hervor.</span><span class="sxs-lookup"><span data-stu-id="2fb21-105">Using them in code generates warning `SYSLIB0011` at compile time.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="2fb21-106">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="2fb21-106">Workarounds</span></span>

<span data-ttu-id="2fb21-107">Verwenden Sie <xref:System.Text.Json.JsonSerializer> oder <xref:System.Xml.Serialization.XmlSerializer> anstelle von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="2fb21-107">Consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer> instead of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span>

<span data-ttu-id="2fb21-108">Weitere Informationen zu empfohlenen Aktionen finden Sie unter [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter) (Auflösen von Fehlern aufgrund der Veraltung und Deaktivierung von BinaryFormatter).</span><span class="sxs-lookup"><span data-stu-id="2fb21-108">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter).</span></span>

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="2fb21-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fb21-109">See also</span></span>

- [<span data-ttu-id="2fb21-110">Beheben von Fehlern aufgrund der Veraltung und Deaktivierung von BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="2fb21-110">Resolving BinaryFormatter obsoletion and disablement errors</span></span>](https://aka.ms/binaryformatter)
- [<span data-ttu-id="2fb21-111">BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten</span><span class="sxs-lookup"><span data-stu-id="2fb21-111">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](../core-libraries/5.0/binaryformatter-serialization-obsolete.md)
