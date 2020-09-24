---
title: System.String-Methoden
ms.date: 03/30/2017
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
ms.openlocfilehash: 44d32ed1000ca49d9fc29ffcde4506b44fc975b6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155665"
---
# <a name="systemstring-methods"></a><span data-ttu-id="bd286-102">System.String-Methoden</span><span class="sxs-lookup"><span data-stu-id="bd286-102">System.String Methods</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="bd286-103">unterstützt die folgenden <xref:System.String>-Methoden nicht.</span><span class="sxs-lookup"><span data-stu-id="bd286-103">does not support the following <xref:System.String> methods.</span></span>  
  
## <a name="unsupported-systemstring-methods-in-general"></a><span data-ttu-id="bd286-104">Nicht unterstützte System.String-Methoden im Allgemeinen</span><span class="sxs-lookup"><span data-stu-id="bd286-104">Unsupported System.String Methods in General</span></span>  

 <span data-ttu-id="bd286-105">Nicht unterstützte <xref:System.String>-Methoden im Allgemeinen:</span><span class="sxs-lookup"><span data-stu-id="bd286-105">Unsupported <xref:System.String> methods in general:</span></span>  
  
- <span data-ttu-id="bd286-106">Kultur bewusste über Ladungen (Methoden, die ein-Element annehmen `CultureInfo`  /  `StringComparison`  /  `IFormatProvider` ).</span><span class="sxs-lookup"><span data-stu-id="bd286-106">Culture-aware overloads (methods that take a `CultureInfo` / `StringComparison` / `IFormatProvider`).</span></span>  
  
- <span data-ttu-id="bd286-107">Methoden, die ein `char`-Array verwenden oder erzeugen.</span><span class="sxs-lookup"><span data-stu-id="bd286-107">Methods that take or produce a `char` array.</span></span>  
  
## <a name="unsupported-systemstring-static-methods"></a><span data-ttu-id="bd286-108">Nicht unterstützte statische System.String-Methoden</span><span class="sxs-lookup"><span data-stu-id="bd286-108">Unsupported System.String Static Methods</span></span>  
  
|<span data-ttu-id="bd286-109">Nicht unterstützte statische System.String-Methoden</span><span class="sxs-lookup"><span data-stu-id="bd286-109">Unsupported System.String Static Methods</span></span>|  
|----------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|  
  
## <a name="unsupported-systemstring-non-static-methods"></a><span data-ttu-id="bd286-110">Nicht unterstützte nicht statische System.String-Methoden</span><span class="sxs-lookup"><span data-stu-id="bd286-110">Unsupported System.String Non-static Methods</span></span>  
  
|<span data-ttu-id="bd286-111">Nicht unterstützte nicht statische System.String-Methoden</span><span class="sxs-lookup"><span data-stu-id="bd286-111">Unsupported System.String Non-static Methods</span></span>|  
|---------------------------------------------------|  
|<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.Split%2A?displayProperty=nameWithType>|  
|<xref:System.String.ToCharArray?displayProperty=nameWithType>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a><span data-ttu-id="bd286-112">Unterschiede zu .NET</span><span class="sxs-lookup"><span data-stu-id="bd286-112">Differences from .NET</span></span>  
  
- <span data-ttu-id="bd286-113">Abfragen berücksichtigen keine SQL Server-Zusammenstellungen, die möglicherweise auf dem Server aktiv sind. Aus diesem Grund werden standardmäßig kulturbewusste Vergleiche mit Berücksichtigung der Schreibweise erstellt.</span><span class="sxs-lookup"><span data-stu-id="bd286-113">Queries do not account for SQL Server collations that might be in effect on the server, and therefore will provide culture-sensitive, case-insensitive comparisons by default.</span></span> <span data-ttu-id="bd286-114">Dieses Verhalten unterscheidet sich von der standardmäßigen Semantik mit Groß-/Kleinschreibung von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd286-114">This behavior differs from the default, case-sensitive semantics of the .NET Framework.</span></span>  
  
- <span data-ttu-id="bd286-115">Wenn `LastIndexOf` 0 zurückgibt, ist entweder die Zeichenfolge, `NULL` oder die gefundene Position ist 0.</span><span class="sxs-lookup"><span data-stu-id="bd286-115">When `LastIndexOf` returns 0, either the string is `NULL` or the found position is 0.</span></span>  
  
- <span data-ttu-id="bd286-116">Die Verkettung oder andere Operationen mit Zeichenfolgen fester Länge (`CHAR`, `NCHAR`) kann zu unerwarteten Ergebnissen führen, da diese Typen in der Datenbank automatisches Padding verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd286-116">Unexpected results might be returned from concatenation or other operations on fixed-length strings (`CHAR`, `NCHAR`), because these types automatically have padding applied in the database.</span></span>  
  
- <span data-ttu-id="bd286-117">Da viele Methoden, wie `Replace`, `ToLower`, `ToUpper` und die Zeichenindizierung keine gültige Übersetzung für die `TEXT`-Spalte oder die `NTEXT`-Spalte und XML aufweisen, kommt es bei normaler Übersetzung zu `SqlExceptions`.</span><span class="sxs-lookup"><span data-stu-id="bd286-117">Because many methods, such as `Replace`, `ToLower`, `ToUpper`, and the character indexer, have no valid translation for `TEXT` or `NTEXT` columns and XML, `SqlExceptions` occur if translated normally.</span></span> <span data-ttu-id="bd286-118">Dieses Verhalten gilt für diese Typen als akzeptabel.</span><span class="sxs-lookup"><span data-stu-id="bd286-118">This behavior is considered acceptable for these types.</span></span> <span data-ttu-id="bd286-119">Alle Zeichenfolgenoperationen müssen jedoch zur Common Language Runtime (CLR)-Semantik für `VARCHAR`, `NVARCHAR`, `VARCHAR(max)` und `NVARCHAR(max)` passen.</span><span class="sxs-lookup"><span data-stu-id="bd286-119">However, all string operations must match common language runtime (CLR) semantics for `VARCHAR`, `NVARCHAR`, `VARCHAR(max)`, and `NVARCHAR(max)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd286-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bd286-120">See also</span></span>

- [<span data-ttu-id="bd286-121">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="bd286-121">Data Types and Functions</span></span>](data-types-and-functions.md)
