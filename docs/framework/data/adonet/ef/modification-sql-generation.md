---
title: Generierung von Änderungen in SQL
ms.date: 03/30/2017
ms.assetid: 2188a39d-46ed-4a8b-906a-c9f15e6fefd1
ms.openlocfilehash: 13ed7186981e82d47f00b6a38a4328ed75f527f4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374751"
---
# <a name="modification-sql-generation"></a><span data-ttu-id="5ac4b-102">Generierung von Änderungen in SQL</span><span class="sxs-lookup"><span data-stu-id="5ac4b-102">Modification SQL Generation</span></span>

<span data-ttu-id="5ac4b-103">In diesem Abschnitt wird erläutert, wie ein SQL-Änderungsgenerierungsmodul für den Anbieter (von SQL:1999-kompatiblen Datenbanken) entwickelt wird.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-103">This section discusses how to develop a modification SQL generation module for your (SQL:1999-compliant database) provider.</span></span> <span data-ttu-id="5ac4b-104">Mit diesem Modul wird eine Änderungsbefehlsstruktur in die entsprechenden INSERT-, UPDATE- oder DELETE-Anweisungen von SQL übersetzt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-104">This module is responsible for translating a modification command tree into the appropriate SQL INSERT, UPDATE or DELETE statements.</span></span>

<span data-ttu-id="5ac4b-105">Weitere Informationen zu SQL-Generierung für select-Anweisungen, finden Sie unter [SQL-Generierung](../../../../../docs/framework/data/adonet/ef/sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="5ac4b-105">For information about SQL generation for select statements, see [SQL Generation](../../../../../docs/framework/data/adonet/ef/sql-generation.md).</span></span>

## <a name="overview-of-modification-command-trees"></a><span data-ttu-id="5ac4b-106">Übersicht über Änderungsbefehlsstrukturen</span><span class="sxs-lookup"><span data-stu-id="5ac4b-106">Overview of Modification Command Trees</span></span>

<span data-ttu-id="5ac4b-107">Das SQL-Änderungsgenerierungsmodul generiert datenbankspezifische SQL-Änderungsanweisungen anhand einer bestimmten eingegebenen DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-107">The modification SQL generation module generates database-specific modification SQL statements based on a given input DbModificationCommandTree.</span></span>

<span data-ttu-id="5ac4b-108">Eine DbModificationCommandTree ist eine Objektmodelldarstellung eines DML- Änderungsvorgangs (ein Einfüge-, Update- oder Löschvorgang), der von DbCommandTree erbt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-108">A DbModificationCommandTree is an object model representation of a modification DML operation (an insert, an update, or a delete operation), inheriting from DbCommandTree.</span></span> <span data-ttu-id="5ac4b-109">Es gibt drei Implementierungen von DbModificationCommandTree:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-109">There are three implementations of DbModificationCommandTree:</span></span>

- <span data-ttu-id="5ac4b-110">DbInsertCommandTree</span><span class="sxs-lookup"><span data-stu-id="5ac4b-110">DbInsertCommandTree</span></span>

- <span data-ttu-id="5ac4b-111">DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="5ac4b-111">DbUpdateCommandTree</span></span>

- <span data-ttu-id="5ac4b-112">DbDeleteCommandTree</span><span class="sxs-lookup"><span data-stu-id="5ac4b-112">DbDeleteCommandTree</span></span>

<span data-ttu-id="5ac4b-113">DbModificationCommandTree und ihre Implementierung, die erstellt werden, indem die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] stellen immer einen einzelne Zeile Vorgang dar.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-113">DbModificationCommandTree and its implementations that are produced by the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] always represent a single row operation.</span></span> <span data-ttu-id="5ac4b-114">In diesem Abschnitt werden diese Typen mit ihren Einschränkungen in .NET Framework 3.5 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-114">This section describes these types with their constraints in the .NET Framework version 3.5.</span></span>

<span data-ttu-id="5ac4b-115">![Diagram](../../../../../docs/framework/data/adonet/ef/media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span><span class="sxs-lookup"><span data-stu-id="5ac4b-115">![Diagram](../../../../../docs/framework/data/adonet/ef/media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span></span>

<span data-ttu-id="5ac4b-116">DbModificationCommandTree verfügt über eine Zieleigenschaft, die den Zielsatz für den Änderungsvorgang darstellt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-116">DbModificationCommandTree has a Target property that represents the target set for the modification operation.</span></span> <span data-ttu-id="5ac4b-117">Die Ausdruckseigenschaft des Ziels, mit der der Eingabesatz definiert wird, ist immer DbScanExpression.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-117">The Target’s Expression property, which defines the input set is always DbScanExpression.</span></span>  <span data-ttu-id="5ac4b-118">Ein DbScanExpression kann entweder darstellen, eine Tabelle oder Sicht, oder ein Satz von Daten mit einer Abfrage definierten ist die Metadateneigenschaft "Defining Query" des Ziels nicht Null.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-118">A DbScanExpression can either represent a table or a view, or a set of data defined with a query if the metadata property "Defining Query" of its Target is non-null.</span></span>

<span data-ttu-id="5ac4b-119">Ein DbScanExpression, der eine Abfrage darstellt, kann nur dann einen Anbieter als Änderungsziel erreichen, wenn der Satz im Modell mit einer definierenden Abfrage definiert wurde, jedoch keine Funktion für den entsprechenden Änderungsvorgang bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-119">A DbScanExpression that represents a query could only reach a provider as a target of modification if the set was defined by using a defining query in the model but no function was provided for the corresponding modification operation.</span></span> <span data-ttu-id="5ac4b-120">Anbieter (z. B. SqlClient) können ein solches Szenario möglicherweise nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-120">Providers may not be able to support such a scenario (SqlClient, for example, does not).</span></span>

<span data-ttu-id="5ac4b-121">DbInsertCommandTree stellt einen einzeiligen Einfügevorgang dar, der als Befehlsstruktur ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-121">DbInsertCommandTree represents a single row insert operation expressed as a command tree.</span></span>

```csharp
public sealed class DbInsertCommandTree : DbModificationCommandTree {
   public IList<DbModificationClause> SetClauses { get }
   public DbExpression Returning { get }
}
```

<span data-ttu-id="5ac4b-122">DbUpdateCommandTree stellt einen einzeiligen Aktualisierungsvorgang dar, der als Befehlsstruktur ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-122">DbUpdateCommandTree represents a single-row update operation expressed as a command tree.</span></span>

<span data-ttu-id="5ac4b-123">DbDeleteCommandTree stellt eine einzeiligen Löschvorgang dar, der als Befehlsstruktur ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-123">DbDeleteCommandTree represents a single row delete operation expressed as a command tree.</span></span>

### <a name="restrictions-on-modification-command-tree-properties"></a><span data-ttu-id="5ac4b-124">Einschränkungen für Struktureigenschaften von Änderungsbefehlen</span><span class="sxs-lookup"><span data-stu-id="5ac4b-124">Restrictions on Modification Command Tree Properties</span></span>

<span data-ttu-id="5ac4b-125">Die folgenden Informationen und Einschränkungen gelten für die Struktureigenschaften von Änderungsbefehlen.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-125">The following information and restrictions apply to the modification command tree properties.</span></span>

#### <a name="returning-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="5ac4b-126">Returning in DbInsertCommandTree und DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="5ac4b-126">Returning in DbInsertCommandTree and DbUpdateCommandTree</span></span>

<span data-ttu-id="5ac4b-127">Wenn Returning nicht NULL ist, gibt er an, dass der Befehl einen Reader zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-127">When non-null, Returning indicates that the command returns a reader.</span></span> <span data-ttu-id="5ac4b-128">Andernfalls sollte der Befehl einen Skalarwert zurückgeben, der die Anzahl der betroffenen (eingefügten oder aktualisierten) Zeilen angibt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-128">Otherwise, the command should return a scalar value indicating the number of rows affected (inserted or updated).</span></span>

<span data-ttu-id="5ac4b-129">Der Returning-Wert legt eine Projektion der Ergebnisse fest, die auf Grundlage der eingefügten oder aktualisierten Zeile zurückzugeben sind.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-129">The Returning value specifies a projection of results to be returned based on the inserted or the updated row.</span></span> <span data-ttu-id="5ac4b-130">Es kann sich lediglich um den Typ DbNewInstanceExpression handeln, der eine Zeile darstellt, deren Argumente jeweils ein DbPropertyExpression für einen DbVariableReferenceExpression sind, der einen Verweis auf das Ziel der entsprechenden DbModificationCommandTree darstellt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-130">It can only be of type DbNewInstanceExpression representing a row, with each of its arguments being a DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span> <span data-ttu-id="5ac4b-131">Bei den von den DbPropertyExpressions dargestellten Eigenschaften, die in der Returning-Eigenschaft verwendet werden, handelt es sich stets um im Speicher generierte oder berechnete Werte.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-131">The properties represented by the DbPropertyExpressions used in the property Returning are always store generated or computed values.</span></span> <span data-ttu-id="5ac4b-132">In DbInsertCommandTree ist Returning nicht NULL, wenn mindestens eine Eigenschaft der Tabelle, in die die Zeile eingefügt wird, als im Speicher generiert oder berechnet festgelegt ist (in SSDL als StoreGeneratedPattern.Identity oder StoreGeneratedPattern.Computed markiert).</span><span class="sxs-lookup"><span data-stu-id="5ac4b-132">In DbInsertCommandTree, Returning is not null when at least one property of the table in which the row is being inserted is specified as store generated or computed (marked as StoreGeneratedPattern.Identity or StoreGeneratedPattern.Computed in the ssdl).</span></span> <span data-ttu-id="5ac4b-133">In DbUpdateCommandTrees ist Returning nicht NULL, wenn mindestens eine Eigenschaft der Tabelle, in der die Zeile aktualisiert wird, als im Speicher berechnet festgelegt ist (in SSDL als StoreGeneratedPattern.Computed markiert).</span><span class="sxs-lookup"><span data-stu-id="5ac4b-133">In DbUpdateCommandTrees, Returning is not null when at least one property of the table in which the row is being updated is specified as store computed (marked as StoreGeneratedPattern.Computed in the ssdl).</span></span>

#### <a name="setclauses-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="5ac4b-134">SetClauses in DbInsertCommandTree und DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="5ac4b-134">SetClauses in DbInsertCommandTree and DbUpdateCommandTree</span></span>

<span data-ttu-id="5ac4b-135">SetClauses legt die Liste der SET-Klauseln zum Einfügen oder Aktualisieren fest, mit denen der Einfüge- oder Aktualisierungsvorgang definiert wird.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-135">SetClauses specifies the list of insert or update set clauses that define the insert or update operation.</span></span>

```
The elements of the list are specified as type DbModificationClause, which specifies a single clause in an insert or update modification operation. DbSetClause inherits from DbModificationClause and specifies the clause in a modification operation that sets the value of a property. Beginning in version 3.5 of the .NET Framework, all elements in SetClauses are of type SetClause.
```

<span data-ttu-id="5ac4b-136">Property legt die zu aktualisierende Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-136">Property specifies the property that should be updated.</span></span> <span data-ttu-id="5ac4b-137">Es handelt sich stets um einen DbPropertyExpression für einen DbVariableReferenceExpression, der einen Verweis auf das Ziel der entsprechenden DbModificationCommandTree darstellt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-137">It is always a DbPropertyExpression over a DbVariableReferenceExpression, which represents a reference to the Target of the corresponding DbModificationCommandTree.</span></span>

<span data-ttu-id="5ac4b-138">Value legt den neuen Wert für die Aktualisierung der Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-138">Value specifies the new value with which to update the property.</span></span> <span data-ttu-id="5ac4b-139">Er ist entweder vom Typ DbConstantExpression oder DbNullExpression.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-139">It is either of type DbConstantExpression or DbNullExpression.</span></span>

#### <a name="predicate-in-dbupdatecommandtree-and-dbdeletecommandtree"></a><span data-ttu-id="5ac4b-140">Predicate in DbUpdateCommandTree und DbDeleteCommandTree</span><span class="sxs-lookup"><span data-stu-id="5ac4b-140">Predicate in DbUpdateCommandTree and DbDeleteCommandTree</span></span>

<span data-ttu-id="5ac4b-141">Predicate legt das Prädikat fest, mit dem die zu aktualisierenden oder zu löschenden Member der Zielauflistung festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-141">Predicate specifies the predicate used to determine which members of the target collection should be updated or deleted.</span></span> <span data-ttu-id="5ac4b-142">Es handelt sich um eine aus der folgenden Teilmenge von DbExpressions erstellte Ausdrucksbaumstruktur:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-142">It is an expression tree built of the following subset of DbExpressions:</span></span>

- <span data-ttu-id="5ac4b-143">DbComparisonExpression der Art Equals, mit das rechte untergeordnete Element ein DbPropertyExpression wie unten eingeschränkt und das linke untergeordnete Element ein DbConstantExpression.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-143">DbComparisonExpression of kind Equals, with the right child being a DbPropertyExpression as restricted below and the left child a DbConstantExpression.</span></span>

- <span data-ttu-id="5ac4b-144">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="5ac4b-144">DbConstantExpression</span></span>

- <span data-ttu-id="5ac4b-145">DbIsNullExpression für einen DbPropertyExpression als eingeschränkte unten</span><span class="sxs-lookup"><span data-stu-id="5ac4b-145">DbIsNullExpression over a DbPropertyExpression as restricted below</span></span>

- <span data-ttu-id="5ac4b-146">Ein DbPropertyExpression für einen DbVariableReferenceExpression, der einen Verweis auf das Ziel der entsprechenden DbModificationCommandTree darstellt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-146">DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span>

- <span data-ttu-id="5ac4b-147">DbAndExpression</span><span class="sxs-lookup"><span data-stu-id="5ac4b-147">DbAndExpression</span></span>

- <span data-ttu-id="5ac4b-148">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="5ac4b-148">DbNotExpression</span></span>

- <span data-ttu-id="5ac4b-149">DbOrExpression</span><span class="sxs-lookup"><span data-stu-id="5ac4b-149">DbOrExpression</span></span>

## <a name="modification-sql-generation-in-the-sample-provider"></a><span data-ttu-id="5ac4b-150">Generierung von Änderungen in SQL im Beispielanbieter</span><span class="sxs-lookup"><span data-stu-id="5ac4b-150">Modification SQL Generation in the Sample Provider</span></span>

<span data-ttu-id="5ac4b-151">Die [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) veranschaulicht die Komponenten von ADO.NET-Datenanbietern,, die Unterstützung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ac4b-151">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="5ac4b-152">Beim Ziel handelt es sich um eine SQL Server 2005-Datenbank. Die Implementierung erfolgt als übergeordneter Wrapper des ADO.NET 2.0-Datenanbieters System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-152">It targets a SQL Server 2005 database and is implemented as a wrapper on top of System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>

<span data-ttu-id="5ac4b-153">Das SQL-Änderungsgenerierungsmodul des Beispielanbieters (das sich in der Datei SQL Generation\DmlSqlGenerator.cs befindet) erstellt mit einer eingegebenen DbModificationCommandTree eine einzelne SQL-Änderungsanweisung, möglicherweise gefolgt von einer Auswahlanweisung, um einen Reader zurückzugeben, sofern dies durch die DbModificationCommandTree festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-153">The modification SQL generation module of the sample provider (located in the file SQL Generation\DmlSqlGenerator.cs) takes an input DbModificationCommandTree and produces a single modification SQL statement possibly followed by a select statement to return a reader if specified by the DbModificationCommandTree.</span></span> <span data-ttu-id="5ac4b-154">Beachten Sie, dass die Form der generierten Befehle von der SQL Server-Zieldatenbank abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-154">Note that the shape of the commands generated is affected by the target SQL Server database.</span></span>

### <a name="helper-classes-expressiontranslator"></a><span data-ttu-id="5ac4b-155">Hilfsklassen: ExpressionTranslator</span><span class="sxs-lookup"><span data-stu-id="5ac4b-155">Helper Classes: ExpressionTranslator</span></span>

<span data-ttu-id="5ac4b-156">ExpressionTranslator dient für alle Struktureigenschaften von Änderungsbefehlen des Typs DbExpression als allgemeines einfaches Konvertierungsprogramm.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-156">ExpressionTranslator serves as a common lightweight translator for all modification command tree properties of type DbExpression.</span></span> <span data-ttu-id="5ac4b-157">Es unterstützt lediglich die Übersetzung der Ausdruckstypen, für die die Eigenschaften der Änderungsbefehlsstruktur eingeschränkt sind und wird anhand dieser Einschränkungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-157">It supports translation of only the expression types to which the properties of the modification command tree are constrained and is built with the particular constraints in mind.</span></span>

<span data-ttu-id="5ac4b-158">Im Folgenden wird der Zugriff auf bestimmte Ausdruckstypen erläutert (Knoten mit trivialen Übersetzungen werden ausgelassen).</span><span class="sxs-lookup"><span data-stu-id="5ac4b-158">The following information discusses visiting specific expression types (nodes with trivial translations are omitted).</span></span>

### <a name="dbcomparisonexpression"></a><span data-ttu-id="5ac4b-159">DbComparisonExpression</span><span class="sxs-lookup"><span data-stu-id="5ac4b-159">DbComparisonExpression</span></span>

<span data-ttu-id="5ac4b-160">Wenn der ExpressionTranslator mit den preserveMemberValues true erstellt wird und wenn die rechte Konstante ein DbConstantExpression (anstelle von DbNullExpression) ist, wird der linke Operand (eDbPropertyExpressions) diesem DbConstantExpression zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-160">When the ExpressionTranslator is constructed with preserveMemberValues = true, and when the constant to the right is a DbConstantExpression (instead of DbNullExpression), it associates the left operand (a DbPropertyExpressions) with that DbConstantExpression.</span></span> <span data-ttu-id="5ac4b-161">Dies wird verwendet, wenn eine Select-Rückgabeanweisung generiert werden muss, um die betroffene Zeile zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-161">That is used if a return Select statement needs to be generated to identify the affected row.</span></span>

### <a name="dbconstantexpression"></a><span data-ttu-id="5ac4b-162">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="5ac4b-162">DbConstantExpression</span></span>

<span data-ttu-id="5ac4b-163">Für jede Konstante, auf die zugegriffen wird, wird ein Parameter erstellt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-163">For each visited constant a parameter is created.</span></span>

### <a name="dbpropertyexpression"></a><span data-ttu-id="5ac4b-164">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="5ac4b-164">DbPropertyExpression</span></span>

<span data-ttu-id="5ac4b-165">Vorausgesetzt, die Instanz von DbPropertyExpression stellt immer die Eingabetabelle dar, und bei der Generierung wurde kein Alias erstellt (dies geschieht nur in Updateszenarien unter Verwendung einer Tabellenvariable), muss kein Alias für die Eingabe angegeben werden. Die Übersetzung wird in der Standardeinstellung auf den Eigenschaftennamen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-165">Given that the Instance of the DbPropertyExpression always represents the input table, unless the generation has created an alias (which only happens in update scenarios when a table variable is used), no alias needs to be specified for the input; the translation defaults to the property name.</span></span>

## <a name="generating-an-insert-sql-command"></a><span data-ttu-id="5ac4b-166">Generieren eines SQL-Insert-Befehls</span><span class="sxs-lookup"><span data-stu-id="5ac4b-166">Generating an Insert SQL Command</span></span>

<span data-ttu-id="5ac4b-167">Der generierte Einfügebefehl folgt für eine bestimmte DbInsertCommandTree im Beispielanbieter einer der beiden folgenden Einfügevorlagen.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-167">For a given DbInsertCommandTree in the sample provider, the generated insert command follows one of the two insert templates below.</span></span>

<span data-ttu-id="5ac4b-168">Die erste Vorlage verfügt über einen Befehl, mit dem der Einfügevorgang mithilfe der Werte in der Liste mit SetClauses durchgeführt werden kann, sowie über eine SELECT-Anweisung, um die in der Returning-Eigenschaft für die eingefügte Zeile angegebenen Eigenschaften zurückzugeben, sofern die Returning-Eigenschaft nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-168">The first template has a command to perform the insert given the values in the list of SetClauses, and a SELECT statement to return the properties specified in the Returning property for the inserted row if the Returning property was not null.</span></span> <span data-ttu-id="5ac4b-169">Das prädikatelement "\@ @ROWCOUNT > 0" ist true, wenn eine Zeile eingefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-169">The predicate element "\@@ROWCOUNT > 0" is true if a row was inserted.</span></span> <span data-ttu-id="5ac4b-170">Das prädikatelement "KeyMemberI = KeyValueI &#124; SCOPE_IDENTITY()-Funktion" nimmt die Form "KeyMemberI = SCOPE_IDENTITY()" "nur, wenn KeyMemberI einen vom Speicher generierte Schlüssel ist, da SCOPE_IDENTITY()-Funktion gibt, den letzten Identitätswert, der in einer Identität (eingefügt zurück die Spalte im Speicher generierte).</span><span class="sxs-lookup"><span data-stu-id="5ac4b-170">The predicate element "keyMemberI =  keyValueI &#124; scope_identity()" takes the shape  "keyMemberI =  scope_identity()" only if keyMemberI is a store-generated key, because scope_identity() returns the last identity value inserted into an identity (store-generated) column.</span></span>

```sql
-- first insert Template
INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]
VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

<span data-ttu-id="5ac4b-171">Die zweite Vorlage ist erforderlich, wenn die Einfügung das Einfügen einer Zeile festlegt, bei der der Primärschlüssel im Speicher generiert wurde, bei dem es sich jedoch nicht um einen ganzzahligen Typ handelt, sodass er nicht mit scope_identity() verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-171">The second template is needed if the insert specifies inserting a row where the primary key is store-generated but is not an integer type and therefore can't be used with scope_identity()).</span></span> <span data-ttu-id="5ac4b-172">Diese Vorlage wird auch verwendet, wenn ein im Speicher generierter Verbundschlüssel vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-172">It is also used if there is a compound store-generated key.</span></span>

```sql
-- second insert template
DECLARE @generated_keys TABLE [(keyMember0, … keyMemberN)

INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]
 OUTPUT inserted.KeyMember0, …, inserted.KeyMemberN INTO @generated_keys
 VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES

[SELECT <returning_over_t>
 FROM @generated_keys  AS g
JOIN <target> AS t ON g.KeyMember0 = t.KeyMember0 AND … g.KeyMemberN = t.KeyMemberN
 WHERE @@ROWCOUNT > 0
```

<span data-ttu-id="5ac4b-173">Im Folgenden finden Sie ein Beispiel, in dem das im Beispielanbieter enthaltene Modell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-173">The following is an example that uses the model that is included with the sample provider.</span></span> <span data-ttu-id="5ac4b-174">Es wird ein Einfügebefehl aus einer DbInsertCommandTree erstellt.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-174">It generates an insert command from a DbInsertCommandTree.</span></span>

<span data-ttu-id="5ac4b-175">Mit folgendem Code wird eine Kategorie eingefügt:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-175">The following code inserts a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = new Category();
   c.CategoryName = "Test Category";
   c.Description = "A new category for testing";
   northwindContext.AddObject("Categories", c);
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="5ac4b-176">Mit diesem Code wird die folgende Befehlsstruktur erzeugt, die an den Anbieter übergeben wird:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-176">This code produces the following command tree, which is passed to the provider:</span></span>

```
DbInsertCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_SetClauses
| |_DbSetClause
| | |_Property
| | | |_Var(target).CategoryName
| | |_Value
| |   |_'Test Category'
| |_DbSetClause
| | |_Property
| | | |_Var(target).Description
| | |_Value
| |   |_'A new category for testing'
| |_DbSetClause
|   |_Property
|   | |_Var(target).Picture
|   |_Value
|     |_null
|_Returning
  |_NewInstance : Record['CategoryID'=Edm.Int32]
    |_Column : 'CategoryID'
      |_Var(target).CategoryID
```

<span data-ttu-id="5ac4b-177">Beim vom Beispielanbieter erzeugten Speicherbefehl handelt es sich um die folgende SQL-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-177">The store command that the sample provider produces is the following SQL statement:</span></span>

```sql
insert [dbo].[Categories]([CategoryName], [Description], [Picture])
values (@p0, @p1, null)
select [CategoryID]
from [dbo].[Categories]
where @@ROWCOUNT > 0 and [CategoryID] = scope_identity()
```

## <a name="generating-an-update-sql-command"></a><span data-ttu-id="5ac4b-178">Generieren eines SQL-Update-Befehls</span><span class="sxs-lookup"><span data-stu-id="5ac4b-178">Generating an Update SQL Command</span></span>

<span data-ttu-id="5ac4b-179">Der generierte Updatebefehl beruht für eine bestimmte DbUpdateCommandTree auf der folgenden Vorlage:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-179">For a given DbUpdateCommandTree, the generated update command is based on the following template:</span></span>

```sql
-- UPDATE Template
UPDATE <target>
SET setClauseProperty0 = setClauseValue0, .. setClausePropertyN = setClauseValueN  | @i = 0
WHERE <predicate>

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

<span data-ttu-id="5ac4b-180">Die Set-Klausel wurde die falsche Set-Klausel ("@i = 0") nur, wenn keine Set-Klauseln angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-180">The set clause has the fake set clause ("@i = 0") only if no set clauses are specified.</span></span> <span data-ttu-id="5ac4b-181">Auf diese Weise wird sichergestellt, dass alle im Speicher berechneten Spalten erneut berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-181">This is to ensure that any store-computed columns are recomputed.</span></span>

<span data-ttu-id="5ac4b-182">Nur wenn die Returning-Eigenschaft nicht NULL ist, wird eine Auswahlanweisung generiert, um die in der Returning-Eigenschaft angegebenen Eigenschaften zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-182">Only if the Returning property is not null, a select statement is generated to return the properties specified in the Returning property.</span></span>

<span data-ttu-id="5ac4b-183">Im folgenden Beispiel wird mithilfe des im Beispielanbieter enthaltenen Modells ein Updatebefehl generiert.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-183">The following example uses the model that is included with the sample provider to generate an update command.</span></span>

<span data-ttu-id="5ac4b-184">Mit folgendem Benutzercode wird eine Kategorie aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-184">The following user code updates a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "Test Category").First();
   c.CategoryName = "New test name";
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="5ac4b-185">Mit diesem Benutzercode wird die folgende Befehlsstruktur erstellt, die an den Anbieter übergeben wird:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-185">This user code produces the following command tree, which is passed to the provider:</span></span>

```
DbUpdateCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_SetClauses
| |_DbSetClause
|   |_Property
|   | |_Var(target).CategoryName
|   |_Value
|     |_'New test name'
|_Predicate
| |_
|   |_Var(target).CategoryID
|   |_=
|   |_10
|_Returning
```

<span data-ttu-id="5ac4b-186">Der Beispielanbieter erzeugt den folgenden Speicherbefehl:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-186">The sample provider produces the following store command:</span></span>

```sql
update [dbo].[Categories]
set [CategoryName] = @p0
where ([CategoryID] = @p1)
```

### <a name="generating-a-delete-sql-command"></a><span data-ttu-id="5ac4b-187">Generieren eines SQL-Delete-Befehls</span><span class="sxs-lookup"><span data-stu-id="5ac4b-187">Generating a Delete SQL Command</span></span>

<span data-ttu-id="5ac4b-188">Für eine bestimmte DbDeleteCommandTree beruht der generierte DELETE-Befehl auf der folgenden Vorlage:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-188">For a given DbDeleteCommandTree, the generated DELETE command is based on the following template:</span></span>

```sql
-- DELETE Template
DELETE <target>
WHERE <predicate>
```

<span data-ttu-id="5ac4b-189">Im folgenden Beispiel wird mithilfe des im Beispielanbieter enthaltenen Modells ein Löschbefehl generiert.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-189">The following example uses the model that is included with the sample provider to generate a delete command.</span></span>

<span data-ttu-id="5ac4b-190">Mit folgendem Benutzercode wird eine Kategorie gelöscht:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-190">The following user code deletes a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "New test name").First();
   northwindContext.DeleteObject(c);
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="5ac4b-191">Mit diesem Benutzercode wird die folgende Befehlsstruktur erstellt, die an den Anbieter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5ac4b-191">This user code produces the following command tree, which is passed to the provider.</span></span>

```
DbDeleteCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_Predicate
  |_
    |_Var(target).CategoryID
    |_=
    |_10
```

<span data-ttu-id="5ac4b-192">Der Beispielanbieter erzeugt den folgenden Speicherbefehl:</span><span class="sxs-lookup"><span data-stu-id="5ac4b-192">The following store command is produced by the sample provider:</span></span>

```sql
delete [dbo].[Categories]
where ([CategoryID] = @p0)
```

## <a name="see-also"></a><span data-ttu-id="5ac4b-193">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ac4b-193">See also</span></span>

- [<span data-ttu-id="5ac4b-194">Schreiben eines Entity Framework-Datenanbieters</span><span class="sxs-lookup"><span data-stu-id="5ac4b-194">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
