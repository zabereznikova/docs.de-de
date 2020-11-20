---
title: Behandeln von NULL-Werten
description: Erfahren Sie, wie die .NET Framework Datenanbieter für SQL Server den Wert NULL verarbeitet, und lesen Sie Informationen zu NULL und SqlBoolean, drei wertiger Logik und zum Zuweisen von NULL-Werten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f18b288f-b265-4bbe-957f-c6833c0645ef
ms.openlocfilehash: 2dda65f605ea9de616f01d6e52eb4e0e5def4db7
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982517"
---
# <a name="handling-null-values"></a><span data-ttu-id="2f0d6-103">Behandeln von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="2f0d6-103">Handling Null Values</span></span>

<span data-ttu-id="2f0d6-104">Ein NULL-Wert wird in einer relationalen Datenbank verwendet, wenn der Wert in einer Spalte unbekannt ist oder fehlt.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-104">A null value in a relational database is used when the value in a column is unknown or missing.</span></span> <span data-ttu-id="2f0d6-105">Ein NULL-Wert ist weder eine leere Zeichenfolge (für Zeichen- oder datetime-Datentypen) noch der Wert 0 (für numerische Datentypen).</span><span class="sxs-lookup"><span data-stu-id="2f0d6-105">A null is neither an empty string (for character or datetime data types) nor a zero value (for numeric data types).</span></span> <span data-ttu-id="2f0d6-106">Die ANSI-Spezifikation SQL-92 besagt, dass ein NULL-Wert für alle Datentypen gleich sein muss, damit alle NULL-Werte einheitlich behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-106">The ANSI SQL-92 specification states that a null must be the same for all data types, so that all nulls are handled consistently.</span></span> <span data-ttu-id="2f0d6-107">Der Namespace <xref:System.Data.SqlTypes> bietet Semantik für NULL-Werte, indem die Schnittstelle <xref:System.Data.SqlTypes.INullable> implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-107">The <xref:System.Data.SqlTypes> namespace provides null semantics by implementing the <xref:System.Data.SqlTypes.INullable> interface.</span></span> <span data-ttu-id="2f0d6-108">Jeder der Datentypen in <xref:System.Data.SqlTypes> hat seine eigene `IsNull`-Eigenschaft und einen `Null`-Wert, der einer Instanz dieses Datentyps zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-108">Each of the data types in <xref:System.Data.SqlTypes> has its own `IsNull` property and a `Null` value that can be assigned to an instance of that data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f0d6-109">In der .NET Framework Version 2,0 wurde die Unterstützung für Werttypen, die NULL-Werte zulassen, eingeführt, die es Programmierern ermöglichen, einen Werttyp so zu erweitern, dass alle Werte</span><span class="sxs-lookup"><span data-stu-id="2f0d6-109">The .NET Framework version 2.0 introduced support for nullable value types, which allow programmers to extend a value type to represent all values of the underlying type.</span></span> <span data-ttu-id="2f0d6-110">Diese CLR-Typen, die NULL-Werte zulassen, stellen eine Instanz der- <xref:System.Nullable> Struktur dar.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-110">These CLR nullable value types represent an instance of the <xref:System.Nullable> structure.</span></span> <span data-ttu-id="2f0d6-111">Diese Fähigkeit ist besonders nützlich, wenn Werttypen geschachtelt oder ungeschachtelt sind, was eine verbesserte Kompatibilität mit Objekttypen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-111">This capability is especially useful when value types are boxed and unboxed, providing enhanced compatibility with object types.</span></span> <span data-ttu-id="2f0d6-112">CLR-Typen, die NULL-Werte zulassen, sind nicht für die Speicherung von Daten Bank Nullen gedacht, weil sich ein ANSI-SQL-NULL-Wert nicht wie ein `null` Verweis (oder `Nothing` in Visual Basic) verhält.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-112">CLR nullable value types are not intended for storage of database nulls because an ANSI SQL null does not behave the same way as a `null` reference (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="2f0d6-113">Verwenden Sie zum Arbeiten mit ANSI-SQL-NULL-Werten in Datenbanken NULL-Werte des Typs <xref:System.Data.SqlTypes> anstelle von <xref:System.Nullable>.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-113">For working with database ANSI SQL null values, use <xref:System.Data.SqlTypes> nulls rather than <xref:System.Nullable>.</span></span> <span data-ttu-id="2f0d6-114">Weitere Informationen zum Arbeiten mit CLR-Werten, die NULL-Werte zulassen, in Visual Basic finden Sie Untertypen, [die NULL-](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)Werte zulassen, und für c# siehe [Werte zulässt-Werttypen](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="2f0d6-114">For more information on working with CLR value nullable types in Visual Basic see [Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md), and for C# see [Nullable value types](../../../../csharp/language-reference/builtin-types/nullable-value-types.md).</span></span>  
  
## <a name="nulls-and-three-valued-logic"></a><span data-ttu-id="2f0d6-115">NULL-Werte und dreiwertige Logik</span><span class="sxs-lookup"><span data-stu-id="2f0d6-115">Nulls and Three-Valued Logic</span></span>  

 <span data-ttu-id="2f0d6-116">Durch das Zulassen von NULL-Werten in Spaltendefinitionen wird in Ihre Anwendung dreiwertige Logik eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-116">Allowing null values in column definitions introduces three-valued logic into your application.</span></span> <span data-ttu-id="2f0d6-117">Ein Vergleich kann anhand einer von drei Bedingungen ausgewertet werden:</span><span class="sxs-lookup"><span data-stu-id="2f0d6-117">A comparison can evaluate to one of three conditions:</span></span>  
  
- <span data-ttu-id="2f0d6-118">True</span><span class="sxs-lookup"><span data-stu-id="2f0d6-118">True</span></span>  
  
- <span data-ttu-id="2f0d6-119">False</span><span class="sxs-lookup"><span data-stu-id="2f0d6-119">False</span></span>  
  
- <span data-ttu-id="2f0d6-120">Unknown</span><span class="sxs-lookup"><span data-stu-id="2f0d6-120">Unknown</span></span>  
  
 <span data-ttu-id="2f0d6-121">Da NULL als unbekannt betrachtet wird, werden zwei miteinander verglichene NULL-Werte nicht als gleich angesehen.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-121">Because null is considered to be unknown, two null values compared to each other are not considered to be equal.</span></span> <span data-ttu-id="2f0d6-122">Wenn in Ausdrücken mit arithmetischen Operatoren einer der Operanden NULL ist, ist das Ergebnis ebenfalls NULL.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-122">In expressions using arithmetic operators, if any of the operands is null, the result is null as well.</span></span>  
  
## <a name="nulls-and-sqlboolean"></a><span data-ttu-id="2f0d6-123">NULL-Werte und SqlBoolean</span><span class="sxs-lookup"><span data-stu-id="2f0d6-123">Nulls and SqlBoolean</span></span>  

 <span data-ttu-id="2f0d6-124">Beim Vergleich zwischen beliebigen <xref:System.Data.SqlTypes> wird <xref:System.Data.SqlTypes.SqlBoolean> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-124">Comparison between any <xref:System.Data.SqlTypes> will return a <xref:System.Data.SqlTypes.SqlBoolean>.</span></span> <span data-ttu-id="2f0d6-125">Die `IsNull`-Funktion für jeden `SqlType` gibt <xref:System.Data.SqlTypes.SqlBoolean> zurück und kann verwendet werden, um auf NULL-Werte zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-125">The `IsNull` function for each `SqlType` returns a <xref:System.Data.SqlTypes.SqlBoolean> and can be used to check for null values.</span></span> <span data-ttu-id="2f0d6-126">Die folgenden Wahrheitstabellen zeigen, wie die Operatoren AND, OR und NOT bei Vorhandensein eines NULL-Werts funktionieren.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-126">The following truth tables show how the AND, OR, and NOT operators function in the presence of a null value.</span></span> <span data-ttu-id="2f0d6-127">(T = TRUE, F = FALSE und U = Unbekannt oder NULL.)</span><span class="sxs-lookup"><span data-stu-id="2f0d6-127">(T=true, F=false, and U=unknown, or null.)</span></span>  
  
 <span data-ttu-id="2f0d6-128">![Wahrheitstabelle](./media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")</span><span class="sxs-lookup"><span data-stu-id="2f0d6-128">![Truth Table](./media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")</span></span>  
  
### <a name="understanding-the-ansi_nulls-option"></a><span data-ttu-id="2f0d6-129">Informationen zur ANSI_NULLS-Option</span><span class="sxs-lookup"><span data-stu-id="2f0d6-129">Understanding the ANSI_NULLS Option</span></span>  

 <span data-ttu-id="2f0d6-130"><xref:System.Data.SqlTypes> bietet die gleiche Semantik wie bei aktivierter Option ANSI_NULLS in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-130"><xref:System.Data.SqlTypes> provides the same semantics as when the ANSI_NULLS option is set on in SQL Server.</span></span> <span data-ttu-id="2f0d6-131">Alle arithmetischen Operatoren (+,-, \* ,/,%), bitweise Operatoren (~, &, \| ) und die meisten Funktionen geben NULL zurück, wenn einer der Operanden oder Argumente NULL ist, mit Ausnahme der-Eigenschaft `IsNull` .</span><span class="sxs-lookup"><span data-stu-id="2f0d6-131">All arithmetic operators (+, -, \*, /, %), bitwise operators (~, &, \|), and most functions return null if any of the operands or arguments is null, except for the property `IsNull`.</span></span>  
  
 <span data-ttu-id="2f0d6-132">Der ANSI SQL-92-Standard unterstützt *columnName* = NULL in einer WHERE-Klausel nicht.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-132">The ANSI SQL-92 standard does not support *columnName* = NULL in a WHERE clause.</span></span> <span data-ttu-id="2f0d6-133">In SQL Server steuert die Option ANSI_NULLS sowohl die standardmäßige NULL-Zulässigkeit in der Datenbank als auch die Auswertung von Vergleichen mit NULL-Werten.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-133">In SQL Server, the ANSI_NULLS option controls both default nullability in the database and evaluation of comparisons against null values.</span></span> <span data-ttu-id="2f0d6-134">Wenn ANSI_NULLS auf ON festgelegt ist (Standardeinstellung), muss in Ausdrücken bei Prüfen auf NULL-Werte der Operator IS NULL verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-134">If ANSI_NULLS is turned on (the default), the IS NULL operator must be used in expressions when testing for null values.</span></span> <span data-ttu-id="2f0d6-135">Der folgende Vergleich gibt z. B. immer UNKNOWN zurück, wenn ANSI_NULLS auf ON festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="2f0d6-135">For example, the following comparison always yields unknown when ANSI_NULLS is on:</span></span>  
  
```sql
colname > NULL  
```  
  
 <span data-ttu-id="2f0d6-136">Der Vergleich mit einer Variablen, die einen NULL-Wert enthält, ergibt ebenfalls „Unbekannt“:</span><span class="sxs-lookup"><span data-stu-id="2f0d6-136">Comparison to a variable containing a null value also yields unknown:</span></span>  
  
```sql
colname > @MyVariable  
```  
  
 <span data-ttu-id="2f0d6-137">Verwenden Sie die Prädikate IS NULL oder IS NOT NULL, um zu überprüfen, ob ein NULL-Wert vorliegt.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-137">Use the IS NULL or IS NOT NULL predicate to test for a null value.</span></span> <span data-ttu-id="2f0d6-138">Dadurch nimmt die Komplexität der WHERE-Klausel möglicherweise zu.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-138">This can add complexity to the WHERE clause.</span></span> <span data-ttu-id="2f0d6-139">Beispielsweise lässt die Spalte TerritoryID in der AdventureWorks-Tabelle „Customer“ NULL-Werte zu.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-139">For example, the TerritoryID column in the AdventureWorks Customer table allows null values.</span></span> <span data-ttu-id="2f0d6-140">Soll eine SELECT-Anweisung u. a. das Vorhandensein von NULL-Werten überprüfen, muss ein IS NULL-Prädikat eingefügt werden:</span><span class="sxs-lookup"><span data-stu-id="2f0d6-140">If a SELECT statement is to test for null values in addition to others, it must include an IS NULL predicate:</span></span>  
  
```sql
SELECT CustomerID, AccountNumber, TerritoryID  
FROM AdventureWorks.Sales.Customer  
WHERE TerritoryID IN (1, 2, 3)  
   OR TerritoryID IS NULL  
```  
  
 <span data-ttu-id="2f0d6-141">Wenn Sie ANSI_NULLS in SQL Server auf OFF festlegen, können Sie Ausdrücke erstellen, die den Gleichheitsoperator zum Vergleich mit NULL verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-141">If you set ANSI_NULLS off in SQL Server, you can create expressions that use the equality operator to compare to null.</span></span> <span data-ttu-id="2f0d6-142">Sie können jedoch nicht verhindern, dass verschiedene Verbindungen NULL-Optionen für diese Verbindung festlegen.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-142">However, you can't prevent different connections from setting null options for that connection.</span></span> <span data-ttu-id="2f0d6-143">Die Verwendung von IS NULL zum Testen auf NULL-Werte funktioniert immer, und zwar unabhängig von den ANSI_NULLS-Einstellungen für eine Verbindung.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-143">Using IS NULL to test for null values always works, regardless of the ANSI_NULLS settings for a connection.</span></span>  
  
 <span data-ttu-id="2f0d6-144">Das Deaktivieren von ANSI_NULLS wird in einem `DataSet` nicht unterstützt, das immer dem ANSI-Standard SQL-92 für die Behandlung von NULL-Werten in <xref:System.Data.SqlTypes> folgt.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-144">Setting ANSI_NULLS off is not supported in a `DataSet`, which always follows the ANSI SQL-92 standard for handling null values in <xref:System.Data.SqlTypes>.</span></span>  
  
## <a name="assigning-null-values"></a><span data-ttu-id="2f0d6-145">Zuweisen von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="2f0d6-145">Assigning Null Values</span></span>  

 <span data-ttu-id="2f0d6-146">NULL-Werte sind etwas Besonderes, und ihre Speicher- und Zuordnungssemantik unterscheidet sich in verschiedenen Typen- und Speichersystemen.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-146">Null values are special, and their storage and assignment semantics differ across different type systems and storage systems.</span></span> <span data-ttu-id="2f0d6-147">Ein `Dataset` ist für die Verwendung mit verschiedenen Typ- und Speichersystemen konzipiert.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-147">A `Dataset` is designed to be used with different type and storage systems.</span></span>  
  
 <span data-ttu-id="2f0d6-148">In diesem Abschnitt wird die NULL-Semantik für das Zuweisen von NULL-Werten zu einer <xref:System.Data.DataColumn> in einer <xref:System.Data.DataRow> in den verschiedenen Typensystemen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-148">This section describes the null semantics for assigning null values to a <xref:System.Data.DataColumn> in a <xref:System.Data.DataRow> across the different type systems.</span></span>  
  
 `DBNull.Value`  
 <span data-ttu-id="2f0d6-149">Diese Zuweisung ist gültig für eine `DataColumn` eines beliebigen Typs.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-149">This assignment is valid for a `DataColumn` of any type.</span></span> <span data-ttu-id="2f0d6-150">Wenn der Typ `INullable` implementiert, wird `DBNull.Value` in den entsprechenden stark typisierten NULL-Wert gezwungen.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-150">If the type implements `INullable`, `DBNull.Value` is coerced into the appropriate strongly typed Null value.</span></span>  
  
 `SqlType.Null`  
 <span data-ttu-id="2f0d6-151">Alle <xref:System.Data.SqlTypes>-Datentypen implementieren `INullable`.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-151">All <xref:System.Data.SqlTypes> data types implement `INullable`.</span></span> <span data-ttu-id="2f0d6-152">Wenn der stark typisierte NULL-Wert mithilfe impliziter Umwandlungsoperatoren in den Datentyp der Spalte konvertiert werden kann, sollte die Zuweisung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-152">If the strongly typed null value can be converted into the column's data type using implicit cast operators, the assignment should go through.</span></span> <span data-ttu-id="2f0d6-153">Andernfalls wird eine Ausnahme aufgrund ungültiger Umwandlung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-153">Otherwise an invalid cast exception is thrown.</span></span>  
  
 `null`  
 <span data-ttu-id="2f0d6-154">Wenn 'null' ein zulässiger Wert für den angegebenen Datentyp `DataColumn` ist, wird er in den entsprechenden `DbNull.Value` oder `Null` gezwungen, der dem `INullable`-Typ (`SqlType.Null`) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-154">If 'null' is a legal value for the given `DataColumn` data type, it is coerced into the appropriate `DbNull.Value` or `Null` associated with the `INullable` type (`SqlType.Null`)</span></span>  
  
 `derivedUdt.Null`  
 <span data-ttu-id="2f0d6-155">Bei UDT-Spalten werden NULL-Werte immer basierend auf dem Typ gespeichert, der `DataColumn` zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-155">For UDT columns, nulls are always stored based on the type associated with the `DataColumn`.</span></span> <span data-ttu-id="2f0d6-156">Betrachten Sie den Fall einer UDT, die einer `DataColumn` zugeordnet ist, die nicht `INullable` implementiert, während ihre Unterklasse dies tut.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-156">Consider the case of a UDT associated with a `DataColumn` that does not implement `INullable` while its sub-class does.</span></span> <span data-ttu-id="2f0d6-157">Wenn in diesem Fall ein stark typisierter NULL-Wert der abgeleiteten Klasse zugewiesen ist, wird er als nicht typisierter `DbNull.Value` gespeichert, da die NULL-Speicherung immer im Einklang mit dem Datentyp von DataColumn ist.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-157">In this case, if a strongly typed null value associated with the derived class is assigned, it is stored as an untyped `DbNull.Value`, because null storage is always consistent with the DataColumn's data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f0d6-158">Die Struktur von `Nullable<T>` oder <xref:System.Nullable> wird in `DataSet` derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-158">The `Nullable<T>` or <xref:System.Nullable> structure is not currently supported in the `DataSet`.</span></span>  
  
### <a name="multiple-column-row-assignment"></a><span data-ttu-id="2f0d6-159">Zuweisung mehrerer Spalten (Zeilen)</span><span class="sxs-lookup"><span data-stu-id="2f0d6-159">Multiple Column (Row) Assignment</span></span>  

 <span data-ttu-id="2f0d6-160">`DataTable.Add`, `DataTable.LoadDataRow` oder andere APIs, die ein <xref:System.Data.DataRow.ItemArray%2A> akzeptieren, das einer Zeile zugeordnet wird, ordnen 'null' dem Standardwert von DataColumn zu.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-160">`DataTable.Add`, `DataTable.LoadDataRow`, or other APIs that accept an <xref:System.Data.DataRow.ItemArray%2A> that gets mapped to a row, map 'null' to the DataColumn's default value.</span></span> <span data-ttu-id="2f0d6-161">Wenn ein Objekt im Array `DbNull.Value` oder sein stark typisiertes Pendant enthält, gelten die gleichen Regeln wie oben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-161">If an object in the array contains `DbNull.Value` or its strongly typed counterpart, the same rules as described above are applied.</span></span>  
  
 <span data-ttu-id="2f0d6-162">Außerdem gelten die folgenden Regeln für eine Instanz von NULL-Zuweisungen für `DataRow.["columnName"]`:</span><span class="sxs-lookup"><span data-stu-id="2f0d6-162">In addition, the following rules apply for an instance of `DataRow.["columnName"]` null assignments:</span></span>  
  
1. <span data-ttu-id="2f0d6-163">Der *Standard* Wert ist `DbNull.Value` für alle außer den stark typisierten NULL-Spalten, bei denen es sich um den entsprechenden stark typisierten NULL-Wert handelt.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-163">The *default* value is `DbNull.Value` for all except the strongly typed null columns where it is the appropriate strongly typed null value.</span></span>  
  
2. <span data-ttu-id="2f0d6-164">NULL-Werte werden niemals bei der Serialisierung in XML-Dateien geschrieben (wie in „xsi: nil“).</span><span class="sxs-lookup"><span data-stu-id="2f0d6-164">Null values are never written out during serialization to XML files (as in "xsi:nil").</span></span>  
  
3. <span data-ttu-id="2f0d6-165">Alle Nicht-NULL-Werte, einschließlich der Standardwerte, werden bei der Serialisierung in XML immer geschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-165">All non-null values, including defaults, are always written out while serializing to XML.</span></span> <span data-ttu-id="2f0d6-166">Dies steht im Gegensatz zur XSD/XML-Semantik, bei der ein NULL-Wert (xsi:nil) explizit und der Standardwert implizit ist (wenn er in XML nicht vorhanden ist, kann ein validierender Parser ihn aus einem zugehörigen XSD-Schema abrufen).</span><span class="sxs-lookup"><span data-stu-id="2f0d6-166">This is unlike XSD/XML semantics where a null value (xsi:nil) is explicit and the default value is implicit (if not present in XML, a validating parser can get it from an associated XSD schema).</span></span> <span data-ttu-id="2f0d6-167">Das Gegenteil gilt für `DataTable`: Ein NULL-Wert ist implizit und der Standardwert ist explizit.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-167">The opposite is true for a `DataTable`: a null value is implicit and the default value is explicit.</span></span>  
  
4. <span data-ttu-id="2f0d6-168">Allen fehlenden Spaltenwerten für aus der XML-Eingabe gelesene Zeilen wird NULL zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-168">All missing column values for rows read from XML input are assigned NULL.</span></span> <span data-ttu-id="2f0d6-169">Zeilen, die mit <xref:System.Data.DataTable.NewRow%2A> oder ähnlichen Methoden erstellt werden, wird der Standardwert von DataColumn zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-169">Rows created using <xref:System.Data.DataTable.NewRow%2A> or similar methods are assigned the DataColumn's default value.</span></span>  
  
5. <span data-ttu-id="2f0d6-170">Die <xref:System.Data.DataRow.IsNull%2A>-Methode gibt `true` sowohl für `DbNull.Value` als auch für `INullable.Null` zurück.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-170">The <xref:System.Data.DataRow.IsNull%2A> method returns `true` for both `DbNull.Value` and `INullable.Null`.</span></span>  
  
## <a name="assigning-null-values"></a><span data-ttu-id="2f0d6-171">Zuweisen von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="2f0d6-171">Assigning Null Values</span></span>  

 <span data-ttu-id="2f0d6-172">Der Standardwert für jede <xref:System.Data.SqlTypes>-Instanz ist NULL.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-172">The default value for any <xref:System.Data.SqlTypes> instance is null.</span></span>  
  
 <span data-ttu-id="2f0d6-173">NULL-Werte in <xref:System.Data.SqlTypes> sind typspezifisch und können nicht durch einen einzelnen Wert, wie z. B. `DbNull`, dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-173">Nulls in <xref:System.Data.SqlTypes> are type-specific and cannot be represented by a single value, such as `DbNull`.</span></span> <span data-ttu-id="2f0d6-174">Verwenden Sie die `IsNull`-Eigenschaft, um auf NULL-Werte zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-174">Use the `IsNull` property to check for nulls.</span></span>  
  
 <span data-ttu-id="2f0d6-175">NULL-Werte können einem <xref:System.Data.DataColumn> zugewiesen werden, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-175">Null values can be assigned to a <xref:System.Data.DataColumn> as shown in the following code example.</span></span> <span data-ttu-id="2f0d6-176">Sie können `SqlTypes`-Variablen direkt NULL-Werte zuweisen, ohne eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-176">You can directly assign null values to `SqlTypes` variables without triggering an exception.</span></span>  
  
### <a name="example"></a><span data-ttu-id="2f0d6-177">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f0d6-177">Example</span></span>  

 <span data-ttu-id="2f0d6-178">Das folgende Codebeispiel erstellt eine <xref:System.Data.DataTable> mit zwei Spalten, die als <xref:System.Data.SqlTypes.SqlInt32> und <xref:System.Data.SqlTypes.SqlString> definiert sind.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-178">The following code example creates a <xref:System.Data.DataTable> with two columns defined as <xref:System.Data.SqlTypes.SqlInt32> and <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="2f0d6-179">Der Code fügt eine Zeile mit bekannten Werten und eine Zeile mit NULL-Werten hinzu und iteriert dann durch die <xref:System.Data.DataTable>. Dabei werden die Werte den Variablen zugewiesen, und die Ausgabe wird im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-179">The code adds one row of known values, one row of null values and then iterates through the <xref:System.Data.DataTable>, assigning the values to variables and displaying the output in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/VB/source.vb#1)]  
  
 <span data-ttu-id="2f0d6-180">In diesem Beispiel werden die folgenden Ergebnisse gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2f0d6-180">This example displays the following results:</span></span>  
  
```output
isColumnNull=False, ID=123, Description=Side Mirror  
isColumnNull=True, ID=Null, Description=Null  
```  
  
## <a name="comparing-null-values-with-sqltypes-and-clr-types"></a><span data-ttu-id="2f0d6-181">Vergleichen von NULL-Werten mit "SqlTypes" und CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="2f0d6-181">Comparing Null Values with SqlTypes and CLR Types</span></span>  

 <span data-ttu-id="2f0d6-182">Beim Vergleich von NULL-Werten ist es wichtig, den Unterschied zwischen der Art und Weise zu verstehen, wie die `Equals`-Methode NULL-Werte in <xref:System.Data.SqlTypes> auswertet, im Vergleich dazu, wie sie mit CLR-Typen arbeitet.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-182">When comparing null values, it is important to understand the difference between the way the `Equals` method evaluates null values in <xref:System.Data.SqlTypes> as compared with the way it works with CLR types.</span></span> <span data-ttu-id="2f0d6-183">Alle <xref:System.Data.SqlTypes>`Equals`-Methoden verwenden Datenbanksemantik zur Auswertung von NULL-Werten. Wenn einer oder beide Werte NULL sind, ergibt der Vergleich NULL.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-183">All of the <xref:System.Data.SqlTypes>`Equals` methods use database semantics for evaluating null values: if either or both of the values is null, the comparison yields null.</span></span> <span data-ttu-id="2f0d6-184">Andererseits ergibt das Anwenden der CLR-Methode `Equals` auf zwei <xref:System.Data.SqlTypes> TRUE, wenn beide NULL sind.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-184">On the other hand, using the CLR `Equals` method on two <xref:System.Data.SqlTypes> will yield true if both are null.</span></span> <span data-ttu-id="2f0d6-185">Dies spiegelt den Unterschied zwischen der Verwendung einer Instanzmethode wie der CLR-Methode `String.Equals` und der Verwendung der statischen/gemeinsamen Methode `SqlString.Equals` wider.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-185">This reflects the difference between using an instance method such as the CLR `String.Equals` method, and using the static/shared method, `SqlString.Equals`.</span></span>  
  
 <span data-ttu-id="2f0d6-186">Das folgende Beispiel veranschaulicht den Unterschied in den Ergebnissen zwischen der `SqlString.Equals`-Methode und der `String.Equals`-Methode, wenn jeweils ein Paar NULL-Werte und dann ein Paar leere Zeichenfolgen übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="2f0d6-186">The following example demonstrates the difference in results between the `SqlString.Equals` method and the `String.Equals` method when each is passed a pair of null values and then a pair of empty strings.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/VB/source.vb#1)]  
  
 <span data-ttu-id="2f0d6-187">Der Code erzeugt folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="2f0d6-187">The code produces the following output:</span></span>  
  
```output
SqlString.Equals shared/static method:  
  Two nulls=Null  
  
String.Equals instance method:  
  Two nulls=True  
  
SqlString.Equals shared/static method:  
  Two empty strings=True  
  
String.Equals instance method:  
  Two empty strings=True
```  
  
## <a name="see-also"></a><span data-ttu-id="2f0d6-188">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f0d6-188">See also</span></span>

- [<span data-ttu-id="2f0d6-189">SQL Server-Datentypen und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2f0d6-189">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="2f0d6-190">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2f0d6-190">ADO.NET Overview</span></span>](../ado-net-overview.md)
