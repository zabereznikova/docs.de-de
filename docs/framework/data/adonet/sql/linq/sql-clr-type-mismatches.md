---
title: SQL-CLR-Typenkonflikte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0a90c33f-7ed7-4501-ad5f-6224c5da8e9b
ms.openlocfilehash: 27708f4bb8e191156f578132602570bc4a6337b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781200"
---
# <a name="sql-clr-type-mismatches"></a><span data-ttu-id="6231b-102">SQL-CLR-Typenkonflikte</span><span class="sxs-lookup"><span data-stu-id="6231b-102">SQL-CLR Type Mismatches</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="6231b-103">automatisiert einen Großteil des Übersetzungsprozesses zwischen dem Objektmodell und SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6231b-103">automates much of the translation between the object model and SQL Server.</span></span> <span data-ttu-id="6231b-104">Trotzdem verhindern einige Situationen die genaue Übersetzung.</span><span class="sxs-lookup"><span data-stu-id="6231b-104">Nevertheless, some situations prevent exact translation.</span></span> <span data-ttu-id="6231b-105">In den folgenden Abschnitten werden diese wichtigen Konflikte zwischen den CLR (Common Language Runtime)-Typen und den SQL Server-Datenbanktypen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="6231b-105">These key mismatches between the common language runtime (CLR) types and the SQL Server database types are summarized in the following sections.</span></span> <span data-ttu-id="6231b-106">Weitere Informationen zu bestimmten Typzuordnungen und zur Funktions Übersetzung finden Sie unter [SQL-CLR-Typzuordnung](sql-clr-type-mapping.md) und [Datentypen und Funktionen](data-types-and-functions.md).</span><span class="sxs-lookup"><span data-stu-id="6231b-106">You can find more details about specific type mappings and function translation at [SQL-CLR Type Mapping](sql-clr-type-mapping.md) and [Data Types and Functions](data-types-and-functions.md).</span></span>

## <a name="data-types"></a><span data-ttu-id="6231b-107">Datentypen</span><span class="sxs-lookup"><span data-stu-id="6231b-107">Data Types</span></span>

<span data-ttu-id="6231b-108">Eine Übersetzung zwischen CLR und SQL Server wird ausgeführt, wenn eine Abfrage an die Datenbank gesendet und die Ergebnisse an das Objektmodell zurückgesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-108">Translation between the CLR and SQL Server occurs when a query is being sent to the database, and when the results are sent back to your object model.</span></span> <span data-ttu-id="6231b-109">Zum Beispiel erfordert folgende Transact-SQL-Abfrage zwei Wertekonvertierungen:</span><span class="sxs-lookup"><span data-stu-id="6231b-109">For example, the following Transact-SQL query requires two value conversions:</span></span>

```sql
Select DateOfBirth From Customer Where CustomerId = @id
```

<span data-ttu-id="6231b-110">Damit die Abfrage von SQL Server ausgeführt werden kann, muss der Wert für den Transact-SQL-Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-110">Before the query can be executed on SQL Server, the value for the Transact-SQL parameter must be specified.</span></span> <span data-ttu-id="6231b-111">In diesem Beispiel muss der `id`-Parameterwert zunächst von einem CLR-<xref:System.Int32?displayProperty=nameWithType>-Typ in einen SQL Server-`INT`-Typ übersetzt werden, damit die Datenbank den Wert interpretieren kann.</span><span class="sxs-lookup"><span data-stu-id="6231b-111">In this example, the `id` parameter value must first be translated from a CLR <xref:System.Int32?displayProperty=nameWithType> type to a SQL Server `INT` type so that the database can understand what the value is.</span></span> <span data-ttu-id="6231b-112">Um anschließend die Ergebnisse abzurufen, muss die `DateOfBirth`-Spalte von SQL Server von einem SQL Server-`DATETIME`-Typ in einen CLR-<xref:System.DateTime?displayProperty=nameWithType>-Typ übersetzt werden, damit er im Objektmodell verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6231b-112">Then to retrieve the results, the SQL Server `DateOfBirth` column must be translated from a SQL Server `DATETIME` type to a CLR <xref:System.DateTime?displayProperty=nameWithType> type for use in the object model.</span></span> <span data-ttu-id="6231b-113">In diesem Beispiel haben die Typen im CLR-Objektmodell und der SQL Server-Datenbank natürliche Mappings.</span><span class="sxs-lookup"><span data-stu-id="6231b-113">In this example, the types in the CLR object model and SQL Server database have natural mappings.</span></span> <span data-ttu-id="6231b-114">Dies ist jedoch nicht immer der Fall.</span><span class="sxs-lookup"><span data-stu-id="6231b-114">But, this is not always the case.</span></span>

### <a name="missing-counterparts"></a><span data-ttu-id="6231b-115">Fehlende Gegenstücke</span><span class="sxs-lookup"><span data-stu-id="6231b-115">Missing Counterparts</span></span>

<span data-ttu-id="6231b-116">Die folgenden Typen weisen keine angemessenen Gegenstücke auf.</span><span class="sxs-lookup"><span data-stu-id="6231b-116">The following types do not have reasonable counterparts.</span></span>

- <span data-ttu-id="6231b-117">Konflikte im CLR-<xref:System>-Namespace:</span><span class="sxs-lookup"><span data-stu-id="6231b-117">Mismatches in the CLR <xref:System> namespace:</span></span>

  - <span data-ttu-id="6231b-118">**Ganze Zahlen ohne**Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="6231b-118">**Unsigned integers**.</span></span> <span data-ttu-id="6231b-119">Diese Typen werden in der Regel größeren Äquivalenten mit Vorzeichen zugeordnet, um ein Überlaufen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6231b-119">These types are typically mapped to their signed counterparts of larger size to avoid overflow.</span></span> <span data-ttu-id="6231b-120">Literale können auf der Basis des Werts in eine mit Vorzeichen versehene Zahl der gleichen oder einer kleineren Größe umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-120">Literals can be converted to a signed numeric of the same or smaller size, based on value.</span></span>

  - <span data-ttu-id="6231b-121">**Boolescher**Wert.</span><span class="sxs-lookup"><span data-stu-id="6231b-121">**Boolean**.</span></span> <span data-ttu-id="6231b-122">Diese Typen können einem Bit oder einem größeren numerischen Wert/einer Zeichenfolge zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-122">These types can be mapped to a bit or larger numeric or string.</span></span> <span data-ttu-id="6231b-123">Ein Literal kann einem Ausdruck zugeordnet werden, der den gleichen Wert ergibt (Beispiel: `1=1` in SQL für `True` in CLS).</span><span class="sxs-lookup"><span data-stu-id="6231b-123">A literal can be mapped to an expression that evaluates to the same value (for example, `1=1` in SQL for `True` in CLS).</span></span>

  - <span data-ttu-id="6231b-124">**TimeSpan**.</span><span class="sxs-lookup"><span data-stu-id="6231b-124">**TimeSpan**.</span></span> <span data-ttu-id="6231b-125">Dieser Typ steht für den Unterschied zwischen zwei `DateTime`-Werten und entspricht nicht dem `timestamp` von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6231b-125">This type represents the difference between two `DateTime` values and does not correspond to the `timestamp` of SQL Server.</span></span> <span data-ttu-id="6231b-126">Die CLR-<xref:System.TimeSpan?displayProperty=nameWithType> wird möglicherweise auch dem `TIME`-Typ in SQL Server zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6231b-126">The CLR <xref:System.TimeSpan?displayProperty=nameWithType> may also map to the SQL Server `TIME` type in some cases.</span></span> <span data-ttu-id="6231b-127">Der `TIME`-Typ in SQL Server kann nur positive Werte unter 24 Stunden darstellen.</span><span class="sxs-lookup"><span data-stu-id="6231b-127">The SQL Server `TIME` type was only intended to represent positive values less than 24 hours.</span></span> <span data-ttu-id="6231b-128">Die CLR-<xref:System.TimeSpan> hat einen viel größeren Bereich.</span><span class="sxs-lookup"><span data-stu-id="6231b-128">The CLR <xref:System.TimeSpan> has a much larger range.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6231b-129">SQL Server spezifische .NET Framework Typen in <xref:System.Data.SqlTypes> werden in diesem Vergleich nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="6231b-129">SQL Server-specific .NET Framework types in <xref:System.Data.SqlTypes> are not included in this comparison.</span></span>

- <span data-ttu-id="6231b-130">Konflikte in SQL Server:</span><span class="sxs-lookup"><span data-stu-id="6231b-130">Mismatches in SQL Server:</span></span>

  - <span data-ttu-id="6231b-131">**Zeichen Typen mit fester Länge**.</span><span class="sxs-lookup"><span data-stu-id="6231b-131">**Fixed length character types**.</span></span> <span data-ttu-id="6231b-132">Transact-SQL unterscheidet zwischen Unicode-und nicht-Unicode-Kategorien und verfügt über drei unterschiedliche Typen in `nchar`jeder Kategorie: `nvarchar`Fixed length / `char`, Variable Length /und `varchar` größere Größe `ntext`. / `text`</span><span class="sxs-lookup"><span data-stu-id="6231b-132">Transact-SQL distinguishes between Unicode and non-Unicode categories and has three distinct types in each category: fixed length `nchar`/`char`, variable length `nvarchar`/`varchar`, and larger-sized `ntext`/`text`.</span></span> <span data-ttu-id="6231b-133">Typen mit Zeichen fester Länge könnten zum Abrufen von Zeichen dem CLR-<xref:System.Char?displayProperty=nameWithType>-Typ zugeordnet werden. Hinsichtlich Konvertierung und Verhalten entsprechen sie jedoch nicht dem gleichen Typ.</span><span class="sxs-lookup"><span data-stu-id="6231b-133">The fixed length character types could be mapped to the CLR <xref:System.Char?displayProperty=nameWithType> type for retrieving characters, but they do not really correspond to the same type in conversions and behavior.</span></span>

  - <span data-ttu-id="6231b-134">**Bit**.</span><span class="sxs-lookup"><span data-stu-id="6231b-134">**Bit**.</span></span> <span data-ttu-id="6231b-135">Obwohl die `bit`-Domäne die gleiche Anzahl von Werten aufweist wie `Nullable<Boolean>`, handelt es sich um verschiedene Typen.</span><span class="sxs-lookup"><span data-stu-id="6231b-135">Although the `bit` domain has the same number of values as `Nullable<Boolean>`, the two are different types.</span></span> <span data-ttu-id="6231b-136">`Bit`nimmt Werte `1` und `0` anstelle von `true`undkannnicht alsäquivalentzubooleschenAusdrückenverwendetwerden./ `false`</span><span class="sxs-lookup"><span data-stu-id="6231b-136">`Bit` takes values `1` and `0` instead of `true`/`false`, and cannot be used as an equivalent to Boolean expressions.</span></span>

  - <span data-ttu-id="6231b-137">**Zeitstempel**.</span><span class="sxs-lookup"><span data-stu-id="6231b-137">**Timestamp**.</span></span> <span data-ttu-id="6231b-138">Im Gegensatz zum CLR-<xref:System.TimeSpan?displayProperty=nameWithType>-Typ stellt der SQL Server-`TIMESTAMP`-Typ eine von der Datenbank erzeugte Zahl mit 8 Bytes dar, die für jedes Update eindeutig ist und nicht auf dem Unterschied zwischen <xref:System.DateTime>-Werten basiert.</span><span class="sxs-lookup"><span data-stu-id="6231b-138">Unlike the CLR <xref:System.TimeSpan?displayProperty=nameWithType> type, the SQL Server `TIMESTAMP` type represents an 8-byte number generated by the database that is unique for each update and is not based on the difference between <xref:System.DateTime> values.</span></span>

  - <span data-ttu-id="6231b-139">**Money** und **smallmoney**.</span><span class="sxs-lookup"><span data-stu-id="6231b-139">**Money** and **SmallMoney**.</span></span> <span data-ttu-id="6231b-140">Diese Typen können <xref:System.Decimal> zugewiesen werden, sie sind jedoch grundsätzlich verschieden und werden von serverbasierten Funktionen und Konvertierungen dementsprechend behandelt.</span><span class="sxs-lookup"><span data-stu-id="6231b-140">These types can be mapped to <xref:System.Decimal> but are basically different types and are treated as such by server-based functions and conversions.</span></span>

### <a name="multiple-mappings"></a><span data-ttu-id="6231b-141">Mehrere Mappings</span><span class="sxs-lookup"><span data-stu-id="6231b-141">Multiple Mappings</span></span>

<span data-ttu-id="6231b-142">Einem oder mehreren CLR-Datentypen können viele SQL Server-Datentypen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-142">There are many SQL Server data types that you can map to one or more CLR data types.</span></span> <span data-ttu-id="6231b-143">Genauso können einem oder mehreren SQL Server-Typen mehrere CLR-Typen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-143">There are also many CLR types that you can map to one or more SQL Server types.</span></span> <span data-ttu-id="6231b-144">Zwar wird ein Mapping möglicherweise von LINQ to SQL unterstützt, dies bedeutet jedoch nicht, dass die beiden zwischen CLR und SQL Server zugeordneten Typen in Genauigkeit, Bereich und Semantik übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6231b-144">Although a mapping may be supported by LINQ to SQL, it does not mean that the two types mapped between the CLR and SQL Server are a perfect match in precision, range, and semantics.</span></span> <span data-ttu-id="6231b-145">Einige Mappings schließen möglicherweise Abweichungen in einer oder allen Dimensionen ein.</span><span class="sxs-lookup"><span data-stu-id="6231b-145">Some mappings may include differences in any or all of these dimensions.</span></span> <span data-ttu-id="6231b-146">Ausführliche Informationen zu diesen potenziellen Unterschieden bei den verschiedenen Mappingmöglichkeiten finden Sie unter [SQL-CLR-Typzuordnung](sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="6231b-146">You can find details about these potential differences for the various mapping possibilities at [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>

### <a name="user-defined-types"></a><span data-ttu-id="6231b-147">Benutzerdefinierte Typen</span><span class="sxs-lookup"><span data-stu-id="6231b-147">User-defined Types</span></span>

<span data-ttu-id="6231b-148">Benutzerdefinierte CLR-Typen werden für die Überbrückung der Typsystemlücke entworfen.</span><span class="sxs-lookup"><span data-stu-id="6231b-148">User-defined CLR types are designed to help bridge the type system gap.</span></span> <span data-ttu-id="6231b-149">Sie fördern jedoch interessante Aspekte der Typversionierung zu Tage.</span><span class="sxs-lookup"><span data-stu-id="6231b-149">Nevertheless they surface interesting issues about type versioning.</span></span> <span data-ttu-id="6231b-150">Eine Versionsänderung auf dem Client kann ggf. nicht durch Änderung des Typs auf dem Datenbankserver zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-150">A change in the version on the client might not be matched by a change in the type stored on the database server.</span></span> <span data-ttu-id="6231b-151">Eine solche Änderung führt zu einem weiteren Typenkonflikt, bei dem die Typsemantik möglicherweise abweicht und die Versionslücke sichtbar wird.</span><span class="sxs-lookup"><span data-stu-id="6231b-151">Any such change causes another type mismatch where the type semantics might not match and the version gap is likely to become visible.</span></span> <span data-ttu-id="6231b-152">Weitere Komplikationen treten auf, wenn Vererbungshierarchien in aufeinander folgenden Versionen umgestaltet werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-152">Further complications occur as inheritance hierarchies are refactored in successive versions.</span></span>

## <a name="expression-semantics"></a><span data-ttu-id="6231b-153">Ausdruckssemantik</span><span class="sxs-lookup"><span data-stu-id="6231b-153">Expression Semantics</span></span>

<span data-ttu-id="6231b-154">Zusätzlich zum paarweisen Konflikt zwischen CLR- und Datenbanktypen wird die Komplexität des Konflikts durch Ausdrücke erhöht.</span><span class="sxs-lookup"><span data-stu-id="6231b-154">In addition to the pairwise mismatch between CLR and database types, expressions add complexity to the mismatch.</span></span> <span data-ttu-id="6231b-155">Konflikte in der Operatorsemantik, der Funktionssemantik, der impliziten Typkonvertierung und in den Rangfolgenregeln müssen berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-155">Mismatches in operator semantics, function semantics, implicit type conversion, and precedence rules must be considered.</span></span>

<span data-ttu-id="6231b-156">Die folgenden Unterabschnitte veranschaulichen den Konflikt zwischen anscheinend ähnlichen Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="6231b-156">The following subsections illustrate the mismatch between apparently similar expressions.</span></span> <span data-ttu-id="6231b-157">Möglicherweise können SQL-Ausdrücke erzeugt werden, die zu einem angegebenen CLR-Ausdruck semantisch äquivalent sind.</span><span class="sxs-lookup"><span data-stu-id="6231b-157">It might be possible to generate SQL expressions that are semantically equivalent to a given CLR expression.</span></span> <span data-ttu-id="6231b-158">Es ist jedoch nicht klar, ob die semantischen Unterschiede zwischen anscheinend ähnlichen Ausdrücken für einen CLR-Benutzer erkennbar sind und ob die für die semantische Gleichheit erforderlichen Änderungen beabsichtigt sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="6231b-158">However, it is not clear whether the semantic differences between apparently similar expressions are evident to a CLR user, and therefore whether the changes that are required for semantic equivalence are intended or not.</span></span> <span data-ttu-id="6231b-159">Dies ist insbesondere dann ein Problem, wenn ein Ausdruck für einen Satz von Werten ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="6231b-159">This is an especially critical issue when an expression is evaluated for a set of values.</span></span> <span data-ttu-id="6231b-160">Die Sichtbarkeit der Unterschiede kann je nach den Daten variieren und lässt sich beim Codieren und Debuggen nur schwer identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6231b-160">The visibility of the difference might depend on data- and be hard to identify during coding and debugging.</span></span>

### <a name="null-semantics"></a><span data-ttu-id="6231b-161">NULL-Semantik</span><span class="sxs-lookup"><span data-stu-id="6231b-161">Null Semantics</span></span>

<span data-ttu-id="6231b-162">SQL-Ausdrücke stellen eine Logik mit drei Werten für boolesche Ausdrücke bereit.</span><span class="sxs-lookup"><span data-stu-id="6231b-162">SQL expressions provide three-valued logic for Boolean expressions.</span></span> <span data-ttu-id="6231b-163">Das Ergebnis kann den Wert true, false oder NULL haben.</span><span class="sxs-lookup"><span data-stu-id="6231b-163">The result can be true, false, or null.</span></span> <span data-ttu-id="6231b-164">Im Gegensatz dazu gibt CLR ein boolesches Ergebnis mit zwei Werten für Vergleiche an, die NULL-Werte einschließen.</span><span class="sxs-lookup"><span data-stu-id="6231b-164">By contrast, CLR specifies two-valued Boolean result for comparisons involving null values.</span></span> <span data-ttu-id="6231b-165">Betrachten Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="6231b-165">Consider the following code:</span></span>

[!code-csharp[DLinqMismatch#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#2)]
[!code-vb[DLinqMismatch#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#2)]

```sql
-- Assume col1 and col2 are integer columns with null values.
-- Assume that ANSI null behavior has not been explicitly
--  turned off.
Select …
From …
Where col1 = col2
-- Evaluates to null, not true and the corresponding row is not
--   selected.
-- To obtain matching behavior (i -> col1, j -> col2) change
--   the query to the following:
Select …
From …
Where
    col1 = col2
or (col1 is null and col2 is null)
-- (Visual Basic 'Nothing'.)
```

<span data-ttu-id="6231b-166">Ein ähnliches Problem tritt bei Annahme von Ergebnissen mit zwei Werten auf.</span><span class="sxs-lookup"><span data-stu-id="6231b-166">A similar problem occurs with the assumption about two-valued results.</span></span>

[!code-csharp[DLinqMismatch#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#3)]
[!code-vb[DLinqMismatch#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#3)]

```sql
-- Assume col1 and col2 are nullable columns.
-- Assume that ANSI null behavior has not been explicitly
--   turned off.
Select …
From …
Where
    col1 = col2
or col1 != col2
-- Visual Basic: col1 <> col2.

-- Excludes the case where the boolean expression evaluates
--   to null. Therefore the where clause does not always
--   evaluate to true.
```

<span data-ttu-id="6231b-167">Im vorherigen Fall erhalten Sie bei der SQL-Erzeugung ein gleichwertiges Verhalten, die Übersetzung kann jedoch Ihre Absicht möglicherweise nicht korrekt widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="6231b-167">In the previous case, you can get equivalent behavior in generating SQL, but the translation might not accurately reflect your intention.</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="6231b-168">die Vergleichs Semantik für `nothing` SQL wird von nicht C# `null` erzwungen oder Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6231b-168">does not impose C# `null` or Visual Basic `nothing` comparison semantics on SQL.</span></span> <span data-ttu-id="6231b-169">Vergleichsoperatoren werden syntaktisch zu ihren SQL-Entsprechungen übersetzt.</span><span class="sxs-lookup"><span data-stu-id="6231b-169">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="6231b-170">Die Semantik reflektiert SQL-Semantik, wie von den Server- oder Verbindungseinstellungen definiert.</span><span class="sxs-lookup"><span data-stu-id="6231b-170">The semantics reflect SQL semantics as defined by server or connection settings.</span></span> <span data-ttu-id="6231b-171">Die beiden NULL-Werte gelten bei den standardmäßigen SQL Server-Einstellungen als ungleich (obwohl Sie die Semantik über die Einstellungen ändern können).</span><span class="sxs-lookup"><span data-stu-id="6231b-171">Two null values are considered unequal under default SQL Server settings (although you can change the settings to change the semantics).</span></span> <span data-ttu-id="6231b-172">Dennoch berücksichtigt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] keine Servereinstellungen in der Abfrageübersetzung.</span><span class="sxs-lookup"><span data-stu-id="6231b-172">Regardless, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not consider server settings in query translation.</span></span>

<span data-ttu-id="6231b-173">Ein Vergleich mit dem `null`-Literal (`nothing`-Literal) wird zur entsprechenden SQL-Version (`is null` oder `is not null`) übersetzt.</span><span class="sxs-lookup"><span data-stu-id="6231b-173">A comparison with the literal `null` (`nothing`) is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>

<span data-ttu-id="6231b-174">Der Wert von `null` (`nothing`) in der Zusammenstellung wird von SQL Server definiert. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ändert die Zusammenstellung nicht.</span><span class="sxs-lookup"><span data-stu-id="6231b-174">The value of `null` (`nothing`) in collation is defined by SQL Server; [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not change the collation.</span></span>

### <a name="type-conversion-and-promotion"></a><span data-ttu-id="6231b-175">Typkonvertierung und Heraufstufung</span><span class="sxs-lookup"><span data-stu-id="6231b-175">Type Conversion and Promotion</span></span>

<span data-ttu-id="6231b-176">SQL unterstützt einen umfangreichen Satz impliziter Konvertierungen in Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="6231b-176">SQL supports a rich set of implicit conversions in expressions.</span></span> <span data-ttu-id="6231b-177">Ähnliche Ausdrücke in C# würden eine explizite Umwandlung erfordern.</span><span class="sxs-lookup"><span data-stu-id="6231b-177">Similar expressions in C# would require an explicit cast.</span></span> <span data-ttu-id="6231b-178">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6231b-178">For example:</span></span>

- <span data-ttu-id="6231b-179">Der `Nvarchar`-Typ und der `DateTime`-Typ können in SQL ohne explizite Umwandlungen verglichen werden. C# erfordert explizite Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="6231b-179">`Nvarchar` and `DateTime` types can be compared in SQL without any explicit casts; C# requires explicit conversion.</span></span>

- <span data-ttu-id="6231b-180">`Decimal` wird in SQL implizit in `DateTime` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="6231b-180">`Decimal` is implicitly converted to `DateTime` in SQL.</span></span> <span data-ttu-id="6231b-181">C# ermöglicht keine implizite Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="6231b-181">C# does not allow for an implicit conversion.</span></span>

<span data-ttu-id="6231b-182">In gleicher Weise unterscheidet sich die Typreihenfolge in Transact-SQL von derjenigen in C#, da der zu Grunde liegende Typsatz abweicht.</span><span class="sxs-lookup"><span data-stu-id="6231b-182">Likewise, type precedence in Transact-SQL differs from type precedence in C# because the underlying set of types is different.</span></span> <span data-ttu-id="6231b-183">In der Tat gibt es keine klare Teilmenge-Obermenge-Beziehung zwischen den Rangfolgenlisten.</span><span class="sxs-lookup"><span data-stu-id="6231b-183">In fact, there is no clear subset/superset relationship between the precedence lists.</span></span> <span data-ttu-id="6231b-184">Beispielsweise führt der Vergleich von `nvarchar` mit `varchar` zur impliziten Konvertierung des `varchar`-Ausdrucks in `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="6231b-184">For example, comparing an `nvarchar` with a `varchar` causes the implicit conversion of the `varchar` expression to `nvarchar`.</span></span> <span data-ttu-id="6231b-185">CLR bietet keine äquivalente Heraufstufung.</span><span class="sxs-lookup"><span data-stu-id="6231b-185">The CLR provides no equivalent promotion.</span></span>

<span data-ttu-id="6231b-186">In einfachen Fällen führen diese Unterschiede zu CLR-Ausdrücken mit Umwandlungen, die für den entsprechenden SQL-Ausdruck redundant sind.</span><span class="sxs-lookup"><span data-stu-id="6231b-186">In simple cases, these differences cause CLR expressions with casts to be redundant for a corresponding SQL expression.</span></span> <span data-ttu-id="6231b-187">Noch wichtiger ist, dass die direkten Ergebnisse eines SQL-Ausdrucks implizit auf einen Typ heraufgestuft werden können, der kein genaues Gegenstück in C# aufweist (und umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="6231b-187">More importantly, the intermediate results of a SQL expression might be implicitly promoted to a type that has no accurate counterpart in C#, and vice versa.</span></span> <span data-ttu-id="6231b-188">Insgesamt führen Tests, Debuggen und Validierung solcher Ausdrücke zu einer erheblichen Belastung für die Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6231b-188">Overall, the testing, debugging, and validation of such expressions adds significant burden on the user.</span></span>

### <a name="collation"></a><span data-ttu-id="6231b-189">Sortierreihenfolge</span><span class="sxs-lookup"><span data-stu-id="6231b-189">Collation</span></span>

<span data-ttu-id="6231b-190">Transact-SQL unterstützt explizite Sortierungen als Anmerkungen zu Zeichenfolgentypen.</span><span class="sxs-lookup"><span data-stu-id="6231b-190">Transact-SQL supports explicit collations as annotations to character string types.</span></span> <span data-ttu-id="6231b-191">Diese Sortierreihenfolgen bestimmen die Gültigkeit von bestimmten Vergleichen.</span><span class="sxs-lookup"><span data-stu-id="6231b-191">These collations determine the validity of certain comparisons.</span></span> <span data-ttu-id="6231b-192">Zwei Spalten mit anderen expliziten Sortierreihenfolgen zu vergleichen ist z. B. unzulässig.</span><span class="sxs-lookup"><span data-stu-id="6231b-192">For example, comparing two columns with different explicit collations is an error.</span></span> <span data-ttu-id="6231b-193">Die Verwendung eines erheblich einfacheren CTS-Zeichenfolgentyps verursacht keine solchen Fehler.</span><span class="sxs-lookup"><span data-stu-id="6231b-193">The use of much simplified CTS string type does not cause such errors.</span></span> <span data-ttu-id="6231b-194">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6231b-194">Consider the following example:</span></span>

```sql
create table T2 (
    Col1 nvarchar(10),
    Col2      nvarchar(10) collate Latin_general_ci_as
)
```

[!code-csharp[DLinqMismatch#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#4)]
[!code-vb[DLinqMismatch#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#4)]

```sql
Select …
From …
Where Col1 = Col2
-- Error, collation conflict.
```

<span data-ttu-id="6231b-195">Tatsächlich erstellt die Sortierungs Unterklausel einen *eingeschränkten Typ* , der nicht ersetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6231b-195">In effect, the collation subclause creates a *restricted type* that is not substitutable.</span></span>

<span data-ttu-id="6231b-196">Auf ähnliche Weise kann die Sortierreihenfolge über Typsysteme hinweg deutlich abweichen.</span><span class="sxs-lookup"><span data-stu-id="6231b-196">Similarly, the sort order can be significantly different across the type systems.</span></span> <span data-ttu-id="6231b-197">Dieser Unterschied wirkt sich auf die Ergebnissortierung aus.</span><span class="sxs-lookup"><span data-stu-id="6231b-197">This difference affects the sorting of results.</span></span> <span data-ttu-id="6231b-198"><xref:System.Guid> wird über alle 16 Bytes hinweg in lexikografischer Reihenfolge (`IComparable()`), sortiert. T-SQL hingegen vergleicht GUIDs in folgender Reihenfolge: node(10-15), clock-seq(8-9), time-high(6-7), time-mid(4-5), time-low(0-3).</span><span class="sxs-lookup"><span data-stu-id="6231b-198"><xref:System.Guid> is sorted on all 16 bytes by lexicographic order (`IComparable()`), whereas T-SQL compares GUIDs in the following order: node(10-15), clock-seq(8-9), time-high(6-7), time-mid(4-5), time-low(0-3).</span></span> <span data-ttu-id="6231b-199">Diese Sortierung wurde in SQL 7.0 erstellt, als von NT erstellte GUIDs eine entsprechende Oktettreihenfolge hatten.</span><span class="sxs-lookup"><span data-stu-id="6231b-199">This ordering was done in SQL 7.0 when NT-generated GUIDs had such an octet order.</span></span> <span data-ttu-id="6231b-200">Dieser Ansatz stellte sicher, dass auf dem gleichen Node-Cluster erzeugte GUIDs nach Timestamp in sequenzieller Reihenfolge zusammengestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6231b-200">The approach ensured that GUIDs generated at the same node cluster came together in sequential order according to timestamp.</span></span> <span data-ttu-id="6231b-201">Der Ansatz war auch für die Erstellung von Indizes nützlich (inserts werden nicht zu zufälligen E/As, sondern zu appends).</span><span class="sxs-lookup"><span data-stu-id="6231b-201">The approach was also useful for building indexes (inserts become appends instead of random IOs).</span></span> <span data-ttu-id="6231b-202">Die Reihenfolge wurde aufgrund von Datenschutzaspekten später in Windows durcheinander gebracht, SQL muss jedoch kompatibel bleiben.</span><span class="sxs-lookup"><span data-stu-id="6231b-202">The order was scrambled later in Windows because of privacy concerns, but SQL must maintain compatibility.</span></span> <span data-ttu-id="6231b-203">Eine Problem Umgehung besteht darin <xref:System.Data.SqlTypes.SqlGuid> , anstelle <xref:System.Guid>von zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6231b-203">A workaround is to use <xref:System.Data.SqlTypes.SqlGuid> instead of <xref:System.Guid>.</span></span>

### <a name="operator-and-function-differences"></a><span data-ttu-id="6231b-204">Unterschiede zwischen Operatoren und Funktionen</span><span class="sxs-lookup"><span data-stu-id="6231b-204">Operator and Function Differences</span></span>

<span data-ttu-id="6231b-205">Im Wesentlichen vergleichbare Operatoren und Funktionen verfügen über eine leicht andere Semantik.</span><span class="sxs-lookup"><span data-stu-id="6231b-205">Operators and functions that are essentially comparable have subtly different semantics.</span></span> <span data-ttu-id="6231b-206">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6231b-206">For example:</span></span>

- <span data-ttu-id="6231b-207">C# gibt auf der Grundlage der lexikalischen Reihenfolge von Operanden für logische Operatoren `&&` und `||` als Kurzschlusssemantik an.</span><span class="sxs-lookup"><span data-stu-id="6231b-207">C# specifies short circuit semantics based on lexical order of operands for logical operators `&&` and `||`.</span></span> <span data-ttu-id="6231b-208">SQL wurde andererseits für satzbasierte Abfragen definiert und bietet daher mehr Optimierungsfreiheit hinsichtlich der Ausführungsreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="6231b-208">SQL on the other hand is targeted for set-based queries and therefore provides more freedom for the optimizer to decide the order of execution.</span></span> <span data-ttu-id="6231b-209">Einige der Auswirkungen schließen Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6231b-209">Some of the implications include the following:</span></span>

  - <span data-ttu-id="6231b-210">Die semantisch äquivalente Übersetzung`CASE` erfordert "...</span><span class="sxs-lookup"><span data-stu-id="6231b-210">Semantically equivalent translation would require "`CASE` …</span></span> <span data-ttu-id="6231b-211">`WHEN` …</span><span class="sxs-lookup"><span data-stu-id="6231b-211">`WHEN` …</span></span> <span data-ttu-id="6231b-212">`THEN`"Konstrukt in SQL, um die Neuanordnung der Operanden Ausführung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6231b-212">`THEN`" construct in SQL to avoid reordering of operand execution.</span></span>

  - <span data-ttu-id="6231b-213">Eine lose Übersetzung `AND` in Operatoren kann unerwartete Fehler verursachen C# , / `OR` wenn der Ausdruck darauf basiert, dass der zweite Operand auf dem Ergebnis der Auswertung des ersten Operanden basiert.</span><span class="sxs-lookup"><span data-stu-id="6231b-213">A loose translation to `AND`/`OR` operators could cause unexpected errors if the C# expression relies on evaluation the second operand being based on the result of the evaluation of the first operand.</span></span>

- <span data-ttu-id="6231b-214">`Round()`die Funktion hat eine andere Semantik in .NET Framework und T-SQL.</span><span class="sxs-lookup"><span data-stu-id="6231b-214">`Round()` function has different semantics in .NET Framework and in T-SQL.</span></span>

- <span data-ttu-id="6231b-215">Der Startindex für Zeichenfolgen in CLR ist 0, in SQL jedoch 1.</span><span class="sxs-lookup"><span data-stu-id="6231b-215">Starting index for strings is 0 in the CLR but 1 in SQL.</span></span> <span data-ttu-id="6231b-216">Aus diesem Grund muss jede Funktion mit einem Index übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-216">Therefore, any function that has index needs index translation.</span></span>

- <span data-ttu-id="6231b-217">CLR unterstützt den Modulusoperator ("%") für Gleitkommazahlen, SQL jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="6231b-217">The CLR supports modulus (‘%’) operator for floating point numbers but SQL does not.</span></span>

- <span data-ttu-id="6231b-218">Der `Like`-Operator ruft automatische Überladungen auf der Grundlage von impliziten Konvertierungen ab.</span><span class="sxs-lookup"><span data-stu-id="6231b-218">The `Like` operator effectively acquires automatic overloads based on implicit conversions.</span></span> <span data-ttu-id="6231b-219">Obwohl der `Like`-Operator für Zeichenfolgen mit Zeichen definiert ist, ermöglicht die implizite Konvertierung von numerischen Typen oder `DateTime`-Typen die Verwendung dieser abweichenden Typen auch mit `Like`.</span><span class="sxs-lookup"><span data-stu-id="6231b-219">Although the `Like` operator is defined to operate on character string types, implicit conversion from numeric types or `DateTime` types allows for those non-string types to be used with `Like` just as well.</span></span> <span data-ttu-id="6231b-220">In CTS sind vergleichbare implizite Konvertierungen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6231b-220">In CTS, comparable implicit conversions do not exist.</span></span> <span data-ttu-id="6231b-221">Deshalb werden zusätzliche Überladungen benötigt.</span><span class="sxs-lookup"><span data-stu-id="6231b-221">Therefore, additional overloads are needed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6231b-222">Dieses Verhalten des `Like`-Operators gilt nur für C#, das `Like`-Schlüsselwort in Visual Basic ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="6231b-222">This `Like` operator behavior applies to C# only; the Visual Basic `Like` keyword is unchanged.</span></span>

- <span data-ttu-id="6231b-223">Der Überlauf ist immer in SQL aktiviert, muss jedoch explizit in C# (nicht in Visual Basic) angegeben werden, um Wraparound zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6231b-223">Overflow is always checked in SQL but it has to be explicitly specified in C# (not in Visual Basic) to avoid wraparound.</span></span> <span data-ttu-id="6231b-224">Gegeben sind die Ganzzahlspalten C1, C2 und C3, wenn C1+C2 in C3 gespeichert wird (Update von T-Satz C3 = C1 + C2).</span><span class="sxs-lookup"><span data-stu-id="6231b-224">Given integer columns C1, C2 and C3, if C1+C2 is stored in C3 (Update T Set C3 = C1 + C2).</span></span>

    ```sql
    create table T3 (
        Col1      integer,
        Col2      integer
    )
    insert into T3 (col1, col2) values (2147483647, 5)
    -- Valid values: max integer value and 5.
    select * from T3 where col1 + col2 < 0
    -- Produces arithmetic overflow error.
    ```

[!code-csharp[DLinqMismatch#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#5)]
[!code-vb[DLinqMismatch#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#5)]

- <span data-ttu-id="6231b-225">SQL führt eine symmetrische arithmetische Rundung durch, während .NET Framework die Verwendung von Bankers verwendet.</span><span class="sxs-lookup"><span data-stu-id="6231b-225">SQL performs symmetric arithmetic rounding while .NET Framework uses banker’s rounding.</span></span> <span data-ttu-id="6231b-226">Weitere Informationen finden Sie im Knowledge Base-Artikel 196652.</span><span class="sxs-lookup"><span data-stu-id="6231b-226">See Knowledgebase article 196652 for additional details.</span></span>

- <span data-ttu-id="6231b-227">Standardmäßig wird in SQL die Groß- und Kleinschreibung bei Zeichenfolgenvergleichen für allgemeine Gebietsschemas nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="6231b-227">By default, for common locales, character-string comparisons are case-insensitive in SQL.</span></span> <span data-ttu-id="6231b-228">In Visual Basic und C# wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="6231b-228">In Visual Basic and in C#, they are case-sensitive.</span></span> <span data-ttu-id="6231b-229">Beispielsweise ( `s == "Food"` `s = "Food"` in Visual Basic) und `s == "Food"` können unterschiedliche Ergebnisse liefern, `s` Wenn `food`ist.</span><span class="sxs-lookup"><span data-stu-id="6231b-229">For example, `s == "Food"` (`s = "Food"` in Visual Basic) and `s == "Food"` can yield different results if `s` is `food`.</span></span>

    ```sql
    -- Assume default US-English locale (case insensitive).
    create table T4 (
        Col1      nvarchar (256)
    )
    insert into T4 values (‘Food’)
    insert into T4 values (‘FOOD’)
    select * from T4 where Col1 = ‘food’
    -- Both the rows are returned because of case-insensitive matching.
    ```

[!code-csharp[DLinqMismatch#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#6)]
[!code-vb[DLinqMismatch#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#6)]

- <span data-ttu-id="6231b-230">Operatoren/Funktionen, die in SQL auf Typargumente mit Zeichen fester Länge angewendet werden, weisen eine deutlich andere Semantik auf als die gleichen Operatoren/Funktionen, die auf eine CLR-<xref:System.String?displayProperty=nameWithType> angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-230">Operators/ functions applied to fixed length character type arguments in SQL have significantly different semantics than the same operators/functions applied to the CLR <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6231b-231">Dies kann auch als Erweiterung der Problematik fehlender Gegenstücke angesehen werden, die in den Abschnitten zu Typen behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="6231b-231">This could also be viewed as an extension of the missing counterpart problem discussed in the section about types.</span></span>

    ```sql
    create table T4 (
        Col1      nchar(4)
    )
    Insert into T5(Col1) values ('21');
    Insert into T5(Col1) values ('1021');
    Select * from T5 where Col1 like '%1'
    -- Only the second row with Col1 = '1021' is returned.
    -- Not the first row!
    ```

     [!code-csharp[DLinqMismatch#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#7)]
     [!code-vb[DLinqMismatch#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#7)]

     <span data-ttu-id="6231b-232">Ein ähnliches Problem tritt bei der Zeichenfolgenverkettung auf.</span><span class="sxs-lookup"><span data-stu-id="6231b-232">A similar problem occurs with string concatenation.</span></span>

    ```sql
    create table T6 (
        Col1      nchar(4)
        Col2       nchar(4)
    )
    Insert into T6 values ('a', 'b');
    Select Col1+Col2 from T6
    -- Returns concatenation of padded strings "a   b   " and not "ab".
    ```

<span data-ttu-id="6231b-233">Zusammenfassend kann eine Konvolutübersetzung für CLR-Ausdrücke erforderlich sein. Es können auch weitere Operatoren/Funktionen benötigt werden, um SQL-Funktionen zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="6231b-233">In summary, a convoluted translation might be required for CLR expressions and additional operators/functions may be necessary to expose SQL functionality.</span></span>

### <a name="type-casting"></a><span data-ttu-id="6231b-234">Typumwandlung</span><span class="sxs-lookup"><span data-stu-id="6231b-234">Type Casting</span></span>

<span data-ttu-id="6231b-235">In C# und SQL können Benutzer die Standardsemantik von Ausdrücken überschreiben, indem sie explizite Typen (`Cast` und `Convert`) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6231b-235">In C# and in SQL, users can override the default semantics of expressions by using explicit type casts (`Cast` and `Convert`).</span></span> <span data-ttu-id="6231b-236">Die Nutzung dieser Möglichkeit über die Grenzen des Typsystems hinweg führt jedoch zu einem Dilemma.</span><span class="sxs-lookup"><span data-stu-id="6231b-236">However, exposing this capability across the type system boundary poses a dilemma.</span></span> <span data-ttu-id="6231b-237">Eine SQL-Umwandlung, die die gewünschte Semantik bereitstellt, kann nicht einfach in eine entsprechende C#-Umwandlung übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-237">A SQL cast that provides the desired semantics cannot be easily translated to a corresponding C# cast.</span></span> <span data-ttu-id="6231b-238">Andererseits kann eine C#-Umwandlung nicht direkt in eine äquivalente SQL-Umwandlung übersetzt werden, da es zu Typenkonflikten, fehlenden Gegenstücken und unterschiedlichen Typhierarchien kommt.</span><span class="sxs-lookup"><span data-stu-id="6231b-238">On the other hand, a C# cast cannot be directly translated into an equivalent SQL cast because of type mismatches, missing counterparts, and different type precedence hierarchies.</span></span> <span data-ttu-id="6231b-239">Es gibt einen Kompromiss zwischen der Darstellung des Typsystemkonflikts und dem Verlust eines großen Teils der Ausdrucksfunktionalität.</span><span class="sxs-lookup"><span data-stu-id="6231b-239">There is a trade-off between exposing the type system mismatch and losing significant power of expression.</span></span>

<span data-ttu-id="6231b-240">In anderen Fällen ist die Typumwandlung möglicherweise nicht in beiden Domänen für die Validierung eines Ausdrucks erforderlich. Sie kann jedoch u. U. notwendig sein, um sicherzustellen, dass ein vom Standard abweichendes Mapping korrekt auf den Ausdruck angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6231b-240">In other cases, type casting might not be needed in either domain for validation of an expression but might be required to make sure that a non-default mapping is correctly applied to the expression.</span></span>

```sql
-- Example from "Non-default Mapping" section extended
create table T5 (
    Col1      nvarchar(10),
    Col2      nvarchar(10)
)
Insert into T5(col1, col2) values (‘3’, ‘2’);
```

[!code-csharp[DLinqMismatch#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#8)]
[!code-vb[DLinqMismatch#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#8)]

```sql
Select *
From T5
Where Col1 + Col2 > 4
-- "Col1 + Col2" expr evaluates to '32'
```

## <a name="performance-issues"></a><span data-ttu-id="6231b-241">Leistungsaspekte</span><span class="sxs-lookup"><span data-stu-id="6231b-241">Performance Issues</span></span>

<span data-ttu-id="6231b-242">Die Berücksichtigung einiger SQL Server-CLR-Typunterschiede kann zu einer Leistungsminderung bei der Überquerung zwischen den CLR-und SQL Server-Typsystemen führen.</span><span class="sxs-lookup"><span data-stu-id="6231b-242">Accounting for some SQL Server-CLR type differences may result in a decrease in performance when crossing between the CLR and SQL Server type systems.</span></span> <span data-ttu-id="6231b-243">Im Folgenden finden Sie Beispielszenarien, die sich auf die Leistung auswirken:</span><span class="sxs-lookup"><span data-stu-id="6231b-243">Examples of scenarios impacting performance include the following:</span></span>

- <span data-ttu-id="6231b-244">Erzwungene Reihenfolge der Evaluierung für logische AND/OR-Operatoren</span><span class="sxs-lookup"><span data-stu-id="6231b-244">Forced order of evaluation for logical and/or operators</span></span>

- <span data-ttu-id="6231b-245">Das Generieren von SQL, um durchzusetzen, dass die Reihenfolge der Prädikatevaluierung die Fähigkeit des SQL-Optimierungsprogramms einschränkt.</span><span class="sxs-lookup"><span data-stu-id="6231b-245">Generating SQL to enforce order of predicate evaluation restricts the SQL optimizer’s ability.</span></span>

- <span data-ttu-id="6231b-246">Typkonvertierungen durch einen CLR-Compiler oder durch eine objektrelationale Abfrageimplementierung können zu Problemen bei der Indexverwendung führen.</span><span class="sxs-lookup"><span data-stu-id="6231b-246">Type conversions, whether introduced by a CLR compiler or by an Object-Relational query implementation, may curtail index usage.</span></span>

     <span data-ttu-id="6231b-247">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="6231b-247">For example,</span></span>

    ```sql
    -- Table DDL
    create table T5 (
        Col1      varchar(100)
    )
    ```

     [!code-csharp[DLinqMismatch#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#9)]
     [!code-vb[DLinqMismatch#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#9)]

     <span data-ttu-id="6231b-248">Berücksichtigen Sie die Übersetzung des Ausdrucks `(s = SOME_STRING_CONSTANT)`.</span><span class="sxs-lookup"><span data-stu-id="6231b-248">Consider the translation of expression `(s = SOME_STRING_CONSTANT)`.</span></span>

    ```sql
    -- Corresponding part of SQL where clause
    Where …
    Col1 = SOME_STRING_CONSTANT
    -- This expression is of the form <varchar> = <nvarchar>.
    -- Hence SQL introduces a conversion from varchar to nvarchar,
    --   resulting in
    Where …
    Convert(nvarchar(100), Col1) = SOME_STRING_CONSTANT
    -- Cannot use the index for column Col1 for some implementations.
    ```

<span data-ttu-id="6231b-249">Zusätzlich zu Semantikunterschieden müssen bei Schnittstellen der Typsysteme von SQL Server und CLR Auswirkungen auf die Leistung berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="6231b-249">In addition to semantic differences, it is important to consider impacts to performance when crossing between the SQL Server and CLR type systems.</span></span> <span data-ttu-id="6231b-250">Bei großen Datensätzen können solche Leistungsprobleme aufzeigen, ob eine Anwendung zur Bereitstellung geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="6231b-250">For large data sets, such performance issues can determine whether an application is deployable.</span></span>

## <a name="see-also"></a><span data-ttu-id="6231b-251">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6231b-251">See also</span></span>

- [<span data-ttu-id="6231b-252">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="6231b-252">Background Information</span></span>](background-information.md)
