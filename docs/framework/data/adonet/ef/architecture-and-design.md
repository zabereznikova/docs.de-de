---
title: Architektur und Entwurf
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd738d39-00e2-4bab-b387-90aac1a014bd
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 48b80856242730a5412cd9d5d8dd2c7f857304ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="architecture-and-design"></a><span data-ttu-id="8c1db-102">Architektur und Entwurf</span><span class="sxs-lookup"><span data-stu-id="8c1db-102">Architecture and Design</span></span>
<span data-ttu-id="8c1db-103">Das SQL-Generierungsmodul im die [Beispielanbieter](http://go.microsoft.com/fwlink/?LinkId=180616) wird als Besucher für die Ausdrucksbaumstruktur, die die Befehlsstruktur darstellt implementiert.</span><span class="sxs-lookup"><span data-stu-id="8c1db-103">The SQL generation module in the [Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) is implemented as a visitor on the expression tree that represents the command tree.</span></span> <span data-ttu-id="8c1db-104">Die Generierung erfolgt, indem die Ausdrucksbaumstruktur einmal durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="8c1db-104">The generation is done in a single pass over the expression tree.</span></span>  
  
 <span data-ttu-id="8c1db-105">Die Knoten der Struktur werden von unten nach oben verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8c1db-105">The nodes of the tree are processed from the bottom up.</span></span> <span data-ttu-id="8c1db-106">Zuerst wird eine Zwischenstruktur erzeugt: SqlSelectStatement oder SqlBuilder, die beide ISqlFragment implementieren.</span><span class="sxs-lookup"><span data-stu-id="8c1db-106">First, an intermediate structure is produced: SqlSelectStatement or SqlBuilder, both implementing ISqlFragment.</span></span> <span data-ttu-id="8c1db-107">Danach wird die SQL-Zeichenfolgenanweisung aus dieser Struktur erzeugt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-107">Next, the string SQL statement is produced from that structure.</span></span> <span data-ttu-id="8c1db-108">Es gibt zwei Gründe für die Zwischenstruktur:</span><span class="sxs-lookup"><span data-stu-id="8c1db-108">There are two reasons for the intermediate structure:</span></span>  
  
-   <span data-ttu-id="8c1db-109">Logisch wird eine SQL SELECT-Anweisung der Reihenfolge nach gefüllt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-109">Logically, a SQL SELECT statement is populated out of order.</span></span> <span data-ttu-id="8c1db-110">Auf die Knoten, die in der FROM-Klausel verwendet werden, wird vor den Knoten zugegriffen, die in den WHERE-, GROUP BY- und ORDER BY-Klauseln verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-110">The nodes that participate in the FROM clause are visited before the nodes that participate in the WHERE, GROUP BY, and the ORDER BY clause.</span></span>  
  
-   <span data-ttu-id="8c1db-111">Um Aliase umzubenennen, müssen Sie alle verwendeten Aliase identifizieren, sodass Konflikte während der Umbenennung vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-111">To rename aliases, you must identify all used aliases to avoid collisions during renaming.</span></span> <span data-ttu-id="8c1db-112">Wenn Sie die Umbenennungsoptionen in SqlBuilder verzögern möchten, können Sie Symbolobjekte verwenden, um die Spalten darzustellen, die für die Umbenennung infrage kommen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-112">To defer the renaming choices in SqlBuilder, use Symbol objects to represent the columns that are candidates for renaming.</span></span>  
  
 <span data-ttu-id="8c1db-113">![Diagramm](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span><span class="sxs-lookup"><span data-stu-id="8c1db-113">![Diagram](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span></span>  
  
 <span data-ttu-id="8c1db-114">In der ersten Phase während des Zugriffs auf die Ausdrucksbaumstruktur werden Ausdrücke in SqlSelectStatements gruppiert sowie Joins und Joinaliase vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="8c1db-114">In the first phase, while visiting the expression tree, expressions are grouped into SqlSelectStatements, joins are flattened, and join aliases are flattened.</span></span> <span data-ttu-id="8c1db-115">Während dieses Durchgangs stellen Symbolobjekte Spalten oder Eingabealiase dar, die möglicherweise umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-115">During this pass, Symbol objects represent columns or input aliases that may be renamed.</span></span>  
  
 <span data-ttu-id="8c1db-116">In der zweiten Phase, während die tatsächliche Zeichenfolge erzeugt wird, werden Aliase umbenannt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-116">In the second phase, while producing the actual string, aliases are renamed.</span></span>  
  
## <a name="data-structures"></a><span data-ttu-id="8c1db-117">Datenstrukturen</span><span class="sxs-lookup"><span data-stu-id="8c1db-117">Data Structures</span></span>  
 <span data-ttu-id="8c1db-118">In diesem Abschnitt wird erläutert, die verwendeten Typen die [Beispielanbieter](http://go.microsoft.com/fwlink/?LinkId=180616) , dass Sie zum Erstellen einer SQL-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-118">This section discusses the types used in the [Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) that you use to build a SQL statement.</span></span>  
  
### <a name="isqlfragment"></a><span data-ttu-id="8c1db-119">ISqlFragment</span><span class="sxs-lookup"><span data-stu-id="8c1db-119">ISqlFragment</span></span>  
 <span data-ttu-id="8c1db-120">In diesem Abschnitt werden die Klassen behandelt, die die ISqlFragment-Schnittstelle implementieren. Diese dient zwei Zwecken:</span><span class="sxs-lookup"><span data-stu-id="8c1db-120">This section covers the classes that implement the ISqlFragment interface, which serves two purposes:</span></span>  
  
-   <span data-ttu-id="8c1db-121">Als allgemeiner Rückgabetyp für alle Besuchermethoden</span><span class="sxs-lookup"><span data-stu-id="8c1db-121">A common return type for all the visitor methods.</span></span>  
  
-   <span data-ttu-id="8c1db-122">Zur Bereitstellung einer Methode, um die endgültige SQL-Zeichenfolge zu schreiben</span><span class="sxs-lookup"><span data-stu-id="8c1db-122">Gives a method to write the final SQL string.</span></span>  
  
```  
internal interface ISqlFragment {  
   void WriteSql(SqlWriter writer, SqlGenerator sqlGenerator);  
}  
```  
  
#### <a name="sqlbuilder"></a><span data-ttu-id="8c1db-123">SqlBuilder</span><span class="sxs-lookup"><span data-stu-id="8c1db-123">SqlBuilder</span></span>  
 <span data-ttu-id="8c1db-124">SqlBuilder ist ein Sammelwerkzeug für die endgültige SQL-Zeichenfolge, ähnlich StringBuilder.</span><span class="sxs-lookup"><span data-stu-id="8c1db-124">SqlBuilder is a gathering device for the final SQL string, similar to StringBuilder.</span></span> <span data-ttu-id="8c1db-125">Er besteht aus den Zeichenfolgen, die den endgültigen SQL-Code bilden, und ISqlFragments, die in Zeichenfolgen konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="8c1db-125">It consists of the strings that make up the final SQL, along with ISqlFragments that can be converted into strings.</span></span>  
  
```  
internal sealed class SqlBuilder : ISqlFragment {  
   public void Append(object s)  
   public void AppendLine()  
   public bool IsEmpty  
}  
```  
  
#### <a name="sqlselectstatement"></a><span data-ttu-id="8c1db-126">SqlSelectStatement</span><span class="sxs-lookup"><span data-stu-id="8c1db-126">SqlSelectStatement</span></span>  
 <span data-ttu-id="8c1db-127">SqlSelectStatement stellt eine kanonische SQL SELECT-Anweisung der Form "SELECT...</span><span class="sxs-lookup"><span data-stu-id="8c1db-127">SqlSelectStatement represents a canonical SQL SELECT statement of the shape "SELECT …</span></span> <span data-ttu-id="8c1db-128">VON..</span><span class="sxs-lookup"><span data-stu-id="8c1db-128">FROM  ..</span></span> <span data-ttu-id="8c1db-129">WHERE...</span><span class="sxs-lookup"><span data-stu-id="8c1db-129">WHERE …</span></span> <span data-ttu-id="8c1db-130">GRUPPIEREN SIE NACH...</span><span class="sxs-lookup"><span data-stu-id="8c1db-130">GROUP BY …</span></span> <span data-ttu-id="8c1db-131">ORDER BY".</span><span class="sxs-lookup"><span data-stu-id="8c1db-131">ORDER BY".</span></span>  
  
 <span data-ttu-id="8c1db-132">Jede der SQL-Klauseln wird durch einen StringBuilder dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-132">Each of the SQL clauses is represented by a StringBuilder.</span></span> <span data-ttu-id="8c1db-133">Außerdem überwacht es, ob "Distinct" angegeben wurde und es sich um die Anweisung auf oberster Ebene handelt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-133">In addition, it tracks whether Distinct has been specified and whether the statement is topmost.</span></span> <span data-ttu-id="8c1db-134">Wenn es sich nicht um die Anweisung auf oberster Ebene handelt, wird die ORDER BY-Klausel weggelassen, es sei denn, die Anweisung verfügt auch über eine TOP-Klausel.</span><span class="sxs-lookup"><span data-stu-id="8c1db-134">If the statement is not topmost, the ORDER BY clause is omitted unless the statement also has a TOP clause.</span></span>  
  
 <span data-ttu-id="8c1db-135">FromExtents enthält die Liste der Eingaben für die SELECT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8c1db-135">FromExtents contains the list of inputs for the SELECT statement.</span></span> <span data-ttu-id="8c1db-136">Darin ist normalerweise nur ein Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c1db-136">There is usually just one element in this.</span></span> <span data-ttu-id="8c1db-137">SELECT-Anweisungen für Joins können vorübergehend über mehr als ein Element verfügen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-137">SELECT statements for joins may temporarily have more than one element.</span></span>  
  
 <span data-ttu-id="8c1db-138">Wenn die SELECT-Anweisung von einem Joinknoten erstellt wird, verwaltet SqlSelectStatement eine Liste aller Blöcke, die in dem Join in AllJoinExtents vereinfacht wurden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-138">If the SELECT statement is created by a Join node, SqlSelectStatement maintains a list of all the extents that have been flattened in the join in AllJoinExtents.</span></span> <span data-ttu-id="8c1db-139">OuterExtents stellt äußere Verweise des SqlSelectStatement dar und wird zur Umbenennung von Eingabealiasen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c1db-139">OuterExtents represents outer references of the SqlSelectStatement and is used for input alias renaming.</span></span>  
  
```  
internal sealed class SqlSelectStatement : ISqlFragment {  
   internal bool IsDistinct { get, set };  
   internal bool IsTopMost  
  
   internal List<Symbol> AllJoinExtents { get, set };  
   internal List<Symbol> FromExtents { get};  
   internal Dictionary<Symbol, bool> OuterExtents { get};  
  
   internal TopClause Top { get, set };  
  
   internal SqlBuilder Select {get};  
   internal SqlBuilder From  
   internal SqlBuilder Where  
   internal SqlBuilder GroupBy  
   public SqlBuilder OrderBy  
}  
```  
  
#### <a name="topclause"></a><span data-ttu-id="8c1db-140">TopClause</span><span class="sxs-lookup"><span data-stu-id="8c1db-140">TopClause</span></span>  
 <span data-ttu-id="8c1db-141">TopClause stellt den TOP-Ausdruck in einem SqlSelectStatement dar.</span><span class="sxs-lookup"><span data-stu-id="8c1db-141">TopClause represents the TOP expression in a SqlSelectStatement.</span></span> <span data-ttu-id="8c1db-142">Die TopCount-Eigenschaft gibt an, wie viele TOP-Zeilen ausgewählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-142">The TopCount property indicates how many TOP rows should be selected.</span></span>  <span data-ttu-id="8c1db-143">Wenn WithTies den Wert true hat, wurde TopClause aus einem DbLimitExpression erstellt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-143">When WithTies is true, the TopClause was built from a DbLimitExpession.</span></span>  
  
```  
class TopClause : ISqlFragment {  
   internal bool WithTies {get}  
   internal ISqlFragment TopCount {get}  
   internal TopClause(ISqlFragment topCount, bool withTies)  
   internal TopClause(int topCount, bool withTies)  
}  
```  
  
### <a name="symbols"></a><span data-ttu-id="8c1db-144">Symbole</span><span class="sxs-lookup"><span data-stu-id="8c1db-144">Symbols</span></span>  
 <span data-ttu-id="8c1db-145">Die symbolbezogenen Klassen und die Symboltabelle führen die Umbenennung von Eingabealiasen, die Vereinfachung von Joinaliasen und die Umbenennung von Spaltenaliasen aus.</span><span class="sxs-lookup"><span data-stu-id="8c1db-145">The Symbol-related classes and the symbol table perform input alias renaming, join alias flattening, and column alias renaming.</span></span>  
  
 <span data-ttu-id="8c1db-146">Die Symbol-Klasse stellt einen Block, eine geschachtelte SELECT-Anweisung oder eine Spalte dar.</span><span class="sxs-lookup"><span data-stu-id="8c1db-146">The Symbol class represents an extent, a nested SELECT statement, or a column.</span></span> <span data-ttu-id="8c1db-147">Sie wird statt eines tatsächlichen Alias verwendet, um das Umbenennen nach der Verwendung zu ermöglichen, und enthält zusätzlich weitere Informationen für das Artefakt, das sie darstellt (beispielsweise den Typ).</span><span class="sxs-lookup"><span data-stu-id="8c1db-147">It is used instead of an actual alias to allow for renaming after it has been used and it also carries additional information for the artifact it represents (like the type).</span></span>  
  
```  
class Symbol : ISqlFragment {  
   internal Dictionary<string, Symbol> Columns {get}  
   internal bool NeedsRenaming {get, set}  
   internal bool IsUnnest {get, set}   //not used  
  
   public string Name{get}  
   public string NewName {get,set}  
   internal TypeUsage Type {get, set}  
  
   public Symbol(string name, TypeUsage type)  
}  
```  
  
 <span data-ttu-id="8c1db-148">In Name wird der ursprüngliche Alias für den dargestellten Block, die geschachtelte SELECT-Anweisung oder eine Spalte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8c1db-148">Name stores the original alias for the represented extent, nested SELECT statement, or a column.</span></span>  
  
 <span data-ttu-id="8c1db-149">In NewName wird der Alias gespeichert, der in der SQL SELECT-Anweisung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8c1db-149">NewName stores the alias that will be used in the SQL SELECT statement.</span></span> <span data-ttu-id="8c1db-150">Er ist ursprünglich auf Name festgelegt und wird nur bei Bedarf beim Generieren der endgültigen Zeichenfolgenabfrage umbenannt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-150">It is originally set to Name, and only renamed if needed when generating the final string query.</span></span>  
  
 <span data-ttu-id="8c1db-151">Type ist nur für Symbole von Nutzen, die Blöcke und geschachtelte SELECT-Anweisungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-151">Type is only useful for symbols representing extents and nested SELECT statements.</span></span>  
  
#### <a name="symbolpair"></a><span data-ttu-id="8c1db-152">SymbolPair</span><span class="sxs-lookup"><span data-stu-id="8c1db-152">SymbolPair</span></span>  
 <span data-ttu-id="8c1db-153">Die SymbolPair-Klasse dient der Datensatzvereinfachung.</span><span class="sxs-lookup"><span data-stu-id="8c1db-153">The SymbolPair class addresses record flattening.</span></span>  
  
 <span data-ttu-id="8c1db-154">Nehmen Sie den Eigenschaftsausdruck D(v, "j3.j2.j1.a.x") als Beispiel, bei dem v ein VarRef ist, j1, j2, j3 Joins sind, a ein Block ist und x eine Spalte ist.</span><span class="sxs-lookup"><span data-stu-id="8c1db-154">Consider a property expression D(v, "j3.j2.j1.a.x") where v is a VarRef, j1, j2, j3 are joins, a is an extent, and x is a columns.</span></span>  
  
 <span data-ttu-id="8c1db-155">Dieser Ausdruck muss schließlich in {j'}.{x'} übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-155">This has to be translated eventually into {j'}.{x'}.</span></span> <span data-ttu-id="8c1db-156">Das Quellfeld stellt das äußerste SqlStatement dar, das einen Joinausdruck (etwa j2) darstellt. Dies ist immer ein Joinsymbol.</span><span class="sxs-lookup"><span data-stu-id="8c1db-156">The source field represents the outermost SqlStatement, representing a join expression (say j2); this is always a Join symbol.</span></span> <span data-ttu-id="8c1db-157">Das Spaltenfeld bewegt sich von einem Joinsymbol zum nächsten, bis es bei einem Symbol stoppt, das kein Joinsymbol ist.</span><span class="sxs-lookup"><span data-stu-id="8c1db-157">The column field moves from one join symbol to the next until it stops at a non-join symbol.</span></span> <span data-ttu-id="8c1db-158">Dies wird beim Zugriff auf einen DbPropertyExpression zurückgegeben, wird jedoch nie einem SqlBuilder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-158">This is returned when visiting a DbPropertyExpression but is never added to a SqlBuilder.</span></span>  
  
```  
class SymbolPair : ISqlFragment {  
   public Symbol Source;  
   public Symbol Column;  
   public SymbolPair(Symbol source, Symbol column)  
}  
```  
  
#### <a name="joinsymbol"></a><span data-ttu-id="8c1db-159">JoinSymbol</span><span class="sxs-lookup"><span data-stu-id="8c1db-159">JoinSymbol</span></span>  
 <span data-ttu-id="8c1db-160">Ein Joinsymbol ist ein Symbol, das eine geschachtelte SELECT-Anweisung mit einem Join oder einer Joineingabe darstellt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-160">A Join symbol is a Symbol that represents a nested SELECT statement with a join or a join input.</span></span>  
  
```  
internal sealed class JoinSymbol : Symbol {  
   internal List<Symbol> ColumnList {get, set}  
   internal List<Symbol> ExtentList {get}  
   internal List<Symbol> FlattenedExtentList {get, set}  
   internal Dictionary<string, Symbol> NameToExtent {get}  
   internal bool IsNestedJoin {get, set}  
  
   public JoinSymbol(string name, TypeUsage type, List<Symbol> extents)  
}  
```  
  
 <span data-ttu-id="8c1db-161">ColumnList stellt die Liste der Spalten in der SELECT-Klausel dar, wenn dieses Symbol eine SQL SELECT-Anweisung darstellt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-161">ColumnList represents the list of columns in the SELECT clause if this symbol represents a SQL SELECT statement.</span></span> <span data-ttu-id="8c1db-162">ExtentList ist die Liste der Blöcke in der SELECT-Klausel.</span><span class="sxs-lookup"><span data-stu-id="8c1db-162">ExtentList is the list of extents in the SELECT clause.</span></span> <span data-ttu-id="8c1db-163">Wenn der Join über mehrere auf der obersten Ebene vereinfachte Blöcke verfügt, überwacht FlattenedExtentList die Blöcke, um sicherzustellen, dass die Blockaliase ordnungsgemäß umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-163">If the join has multiple extents flattened at the top level, FlattenedExtentList tracks the extents to ensure that extent aliases are renamed correctly.</span></span>  
  
 <span data-ttu-id="8c1db-164">NameToExtent verfügt über alle Blöcke in ExtentList als Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="8c1db-164">NameToExtent has all the extents in ExtentList as a dictionary.</span></span> <span data-ttu-id="8c1db-165">IsNestedJoin wird verwendet, um zu bestimmen, ob ein JoinSymbol ein gewöhnliches Joinsymbol oder eines ist, das über ein entsprechendes SqlSelectStatement verfügt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-165">IsNestedJoin is used to determine whether a JoinSymbol is an ordinary join symbol or one that has a corresponding SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="8c1db-166">Alle Listen werden genau einmal festgelegt und dann für Suchen oder die Enumeration verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c1db-166">All the lists are set exactly once and then used for lookups or enumeration.</span></span>  
  
#### <a name="symboltable"></a><span data-ttu-id="8c1db-167">SymbolTable</span><span class="sxs-lookup"><span data-stu-id="8c1db-167">SymbolTable</span></span>  
 <span data-ttu-id="8c1db-168">SymbolTable wird verwendet, um Variablennamen in Symbole aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-168">SymbolTable is used to resolve variable names to Symbols.</span></span> <span data-ttu-id="8c1db-169">SymbolTable wird als Stapel mit einem neuen Eintrag für jeden Bereich implementiert.</span><span class="sxs-lookup"><span data-stu-id="8c1db-169">SymbolTable is implemented as a stack with a new entry for each scope.</span></span> <span data-ttu-id="8c1db-170">Suchen suchen vom Anfang des Stapels abwärts, bis ein Eintrag gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="8c1db-170">Lookups search from the top of the stack to the bottom until an entry is found.</span></span>  
  
```  
internal sealed class SymbolTable {  
   internal void EnterScope()  
   internal void ExitScope()  
   internal void Add(string name, Symbol value)  
   internal Symbol Lookup(string name)  
}  
```  
  
 <span data-ttu-id="8c1db-171">Es gibt nur eine SymbolTable pro Instanz des SQL-Generierungsmoduls.</span><span class="sxs-lookup"><span data-stu-id="8c1db-171">There is only one SymbolTable per one instance of the Sql Generation module.</span></span> <span data-ttu-id="8c1db-172">Für jeden relationalen Knoten wird in Bereiche gewechselt und werden diese Bereiche wieder verlassen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-172">Scopes are entered and exited for each relational node.</span></span> <span data-ttu-id="8c1db-173">Alle Symbole in früheren Bereichen sind für spätere Bereiche sichtbar, es sei denn, sie werden von anderen Symbolen mit dem gleichen Namen ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="8c1db-173">All symbols in earlier scopes are visible to later scopes unless hidden by other symbols with the same name.</span></span>  
  
### <a name="global-state-for-the-visitor"></a><span data-ttu-id="8c1db-174">Globaler Zustand für den Besucher</span><span class="sxs-lookup"><span data-stu-id="8c1db-174">Global State for the Visitor</span></span>  
 <span data-ttu-id="8c1db-175">Wenn Sie die Umbenennung von Aliasen und Spalten unterstützen möchten, sollten Sie eine Liste aller Spaltennamen (AllColumnNames) und Blockaliase (AllExtentNames) vorhalten, die bei der ersten Verarbeitung der Abfragestruktur verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-175">To assist in renaming of aliases and columns, maintain a list of all the column names (AllColumnNames) and extent aliases (AllExtentNames) that have been used in the first pass over the query tree.</span></span>  <span data-ttu-id="8c1db-176">Die Symboltabelle löst Variablennamen in Symbole auf.</span><span class="sxs-lookup"><span data-stu-id="8c1db-176">The symbol table resolves variable names to Symbols.</span></span> <span data-ttu-id="8c1db-177">IsVarRefSingle wird nur zu Überprüfungszwecken verwendet und ist nicht unbedingt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c1db-177">IsVarRefSingle is only used for verification purposes, it is not strictly necessary.</span></span>  
  
 <span data-ttu-id="8c1db-178">Mithilfe der beiden über CurrentSelectStatement und IsParentAJoin verwendeten Stapel werden "Parameter" von übergeordneten Knoten an untergeordnete Knoten übergeben, da das Besuchermuster es nicht zulässt, Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="8c1db-178">The two stacks used via CurrentSelectStatement and IsParentAJoin are used to pass "parameters" from parent to child nodes, since the visitor pattern does not allow us to pass parameters.</span></span>  
  
```  
internal Dictionary<string, int> AllExtentNames {get}  
internal Dictionary<string, int> AllColumnNames {get}  
SymbolTable symbolTable = new SymbolTable();  
bool isVarRefSingle = false;  
  
Stack<SqlSelectStatement> selectStatementStack;  
private SqlSelectStatement CurrentSelectStatement{get}  
  
Stack<bool> isParentAJoinStack;  
private bool IsParentAJoin{get}  
```  
  
## <a name="common-scenarios"></a><span data-ttu-id="8c1db-179">Häufige Szenarien</span><span class="sxs-lookup"><span data-stu-id="8c1db-179">Common Scenarios</span></span>  
 <span data-ttu-id="8c1db-180">In diesem Abschnitt werden häufig verwendete Anbieterszenarien erläutert.</span><span class="sxs-lookup"><span data-stu-id="8c1db-180">This section discusses common provider scenarios.</span></span>  
  
### <a name="grouping-expression-nodes-into-sql-statements"></a><span data-ttu-id="8c1db-181">Gruppieren von Ausdrucksknoten in SQL-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="8c1db-181">Grouping Expression Nodes into SQL Statements</span></span>  
 <span data-ttu-id="8c1db-182">Ein SqlSelectStatement wird erstellt, wenn beim Zugriff auf die Struktur von unten der erste relationale Knoten (in der Regel ein DbScanExpression-Block) gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="8c1db-182">A SqlSelectStatement is created when the first relational node is encountered (typically a DbScanExpression extent) when visiting the tree from the bottom up.</span></span> <span data-ttu-id="8c1db-183">Wenn Sie eine SQL SELECT-Anweisung mit so wenigen geschachtelten Abfragen wie möglich erzeugen möchten, müssen Sie so viele ihrer übergeordneten Knoten wie möglich in diesem SqlSelectStatement aggregieren.</span><span class="sxs-lookup"><span data-stu-id="8c1db-183">To produce a SQL SELECT statement with as few nested queries as possible, aggregate as many of its parent nodes as possible in that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="8c1db-184">Die Entscheidung, ob dem aktuellen (beim Zugriff auf die Eingabe zurückgegebenen) SqlSelectStatement ein angegebener (relationaler) Knoten hinzugefügt werden kann oder eine neue Anweisung gestartet werden muss, wird von der IsCompatible-Methode berechnet. Außerdem hängt die Entscheidung vom bereits im SqlSelectStatement vorhandenen Inhalt ab, der wiederum davon abhängt, welche Knoten dem angegebenen Knoten untergeordnet waren.</span><span class="sxs-lookup"><span data-stu-id="8c1db-184">The decision of whether a given (relational) node can be added to the current SqlSelectStatement (the one returned when visiting the input) or if a new statement needs to be started is computed by the method IsCompatible and depends on what is already in the SqlSelectStatement, which depends on what nodes were below the given node.</span></span>  
  
 <span data-ttu-id="8c1db-185">Wenn SQL-Anweisungsklauseln nach Klauseln ausgewertet werden, bei denen die Knoten, die zum Zusammenführen vorgesehen sind, nicht leer sind, können die Knoten der aktuellen Anweisung normalerweise nicht hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-185">Typically, if SQL statement clauses are evaluated after clauses where the nodes being considered for merging are not empty, the node cannot be added to the current statement.</span></span> <span data-ttu-id="8c1db-186">Wenn der nächste Knoten z. B. ein Filter ist, kann dieser Knoten nur in das aktuelle SqlSelectStatement integriert werden, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8c1db-186">For example, if the next node is a Filter, that node can be incorporated into the current SqlSelectStatement only if the following is true:</span></span>  
  
-   <span data-ttu-id="8c1db-187">Die SELECT-Liste ist leer.</span><span class="sxs-lookup"><span data-stu-id="8c1db-187">The SELECT list is empty.</span></span> <span data-ttu-id="8c1db-188">Wenn die SELECT-Liste nicht leer ist, wurde die Auswahlliste von einem Knoten erzeugt, der dem Filter vorausgeht, und das Prädikat verweist möglicherweise auf von dieser SELECT-Liste erzeugte Spalten.</span><span class="sxs-lookup"><span data-stu-id="8c1db-188">If the SELECT list is not empty, the select list was produced by a node preceding the filter and the predicate may refer to columns produced by that SELECT list.</span></span>  
  
-   <span data-ttu-id="8c1db-189">Die GROUP BY-Klausel ist leer.</span><span class="sxs-lookup"><span data-stu-id="8c1db-189">The GROUPBY is empty.</span></span> <span data-ttu-id="8c1db-190">Wenn die GROUP BY-Klausel nicht leer ist, würde das Hinzufügen des Filters bedeuten, dass vor dem Gruppieren gefiltert würde. Das ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8c1db-190">If the GROUPBY is not empty, adding the filter would mean filtering before grouping, which is not correct.</span></span>  
  
-   <span data-ttu-id="8c1db-191">Die TOP-Klausel ist leer.</span><span class="sxs-lookup"><span data-stu-id="8c1db-191">The TOP clause is empty.</span></span> <span data-ttu-id="8c1db-192">Wenn die TOP-Klausel nicht leer ist, würde das Hinzufügen des Filters bedeuten, dass vor dem Ausführen der TOP-Klausel gefiltert würde. Das ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8c1db-192">If the TOP clause is not empty, adding the filter would mean filtering before doing TOP, which is not correct.</span></span>  
  
 <span data-ttu-id="8c1db-193">Dies gilt nicht für nicht relationale Knoten wie DbConstantExpression oder arithmetische Ausdrücke, da diese immer als Teil eines vorhandenen SqlSelectStatements eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="8c1db-193">This does not apply to non-relational nodes like DbConstantExpression or arithmetic expressions, because these are always included as part of an existing SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="8c1db-194">Wird festgestellt, dass es sich um den Stamm der Joinstruktur (ein Joinknoten, der nicht über ein übergeordnetes Joinelement verfügt) handelt, wird ebenfalls ein neues SqlSelectStatement gestartet.</span><span class="sxs-lookup"><span data-stu-id="8c1db-194">Also, when encountering the root of join tree (a join node that does not have a join parent), a new SqlSelectStatement is started.</span></span> <span data-ttu-id="8c1db-195">Alle zugehörigen linken untergeordneten Joinelemente werden in diesem SqlSelectStatement aggregiert.</span><span class="sxs-lookup"><span data-stu-id="8c1db-195">All of its left spine join children are aggregated into that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="8c1db-196">Jedes Mal, wenn ein neues SqlSelectStatement gestartet wird und das aktuelle der Eingabe hinzugefügt wird, muss das aktuelle SqlSelectStatement möglicherweise durch das Hinzufügen von Projektionsspalten (eine SELECT-Klausel) abgeschlossen werden, wenn keine vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8c1db-196">Whenever a new SqlSelectStatement is started, and the current one is added to the input, the current SqlSelectStatement may need to be completed by adding projection columns (a SELECT clause) if one does not exist.</span></span> <span data-ttu-id="8c1db-197">Dies erfolgt mit der Methode AddDefaultColumns, die die FromExtents des SqlSelectStatements verwendet und alle Spalten zur Liste der projizierten Spalten hinzufügt, die in der Liste der von FromExtents dargestellten Blöcke im Gültigkeitsbereich liegen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-197">This is done with the method AddDefaultColumns, which looks at the FromExtents of the SqlSelectStatement and adds all the columns that the list of extents represented by FromExtents brings in scope to the list of projected columns.</span></span> <span data-ttu-id="8c1db-198">Auf diese Weise wird verfahren, da zu diesem Zeitpunkt unbekannt ist, auf welche Spalten die anderen Knoten verweisen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-198">This is done, because at that point, it is unknown which columns are referenced by the other nodes.</span></span> <span data-ttu-id="8c1db-199">Dies kann so optimiert werden, dass nur die Spalten projiziert werden, die später verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8c1db-199">This can be optimized to only project the columns that can later be used.</span></span>  
  
### <a name="join-flattening"></a><span data-ttu-id="8c1db-200">Joinvereinfachung</span><span class="sxs-lookup"><span data-stu-id="8c1db-200">Join Flattening</span></span>  
 <span data-ttu-id="8c1db-201">Die IsParentAJoin-Eigenschaft hilft zu bestimmen, ob ein angegebener Join vereinfacht werden kann.</span><span class="sxs-lookup"><span data-stu-id="8c1db-201">The IsParentAJoin property helps determine whether a given join can be flattened.</span></span> <span data-ttu-id="8c1db-202">Insbesondere gibt IsParentAJoin `true` nur für das linke untergeordnete Element eines Joins und für jeden DbScanExpression zurück, der eine sofortige Eingabe für einen Join darstellt. In diesem Fall verwendet dieser untergeordnete Knoten das gleiche SqlSelectStatement erneut, das das übergeordnete Element später verwenden würde.</span><span class="sxs-lookup"><span data-stu-id="8c1db-202">In particular, IsParentAJoin returns `true` only for the left child of a join and for each DbScanExpression that is an immediate input to a join, in which case that child node reuses the same SqlSelectStatement that the parent would later use.</span></span> <span data-ttu-id="8c1db-203">Weitere Informationen finden Sie unter "Joinausdrücke".</span><span class="sxs-lookup"><span data-stu-id="8c1db-203">For more information, see "Join Expressions".</span></span>  
  
### <a name="input-alias-redirecting"></a><span data-ttu-id="8c1db-204">Eingabealiasumleitung</span><span class="sxs-lookup"><span data-stu-id="8c1db-204">Input Alias Redirecting</span></span>  
 <span data-ttu-id="8c1db-205">Die Eingabealiasumleitung erfolgt mithilfe der Symboltabelle.</span><span class="sxs-lookup"><span data-stu-id="8c1db-205">Input alias redirecting is accomplished with the symbol table.</span></span>  
  
 <span data-ttu-id="8c1db-206">Um eingabealiasumleitung zu erläutern, finden Sie im ersten Beispiel [Generieren von SQL aus Befehlsstrukturen – Best Practices](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="8c1db-206">To explain input alias redirecting, refer to the first example in [Generating SQL from Command Trees - Best Practices](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md).</span></span>  <span data-ttu-id="8c1db-207">Dort musste "a" in der Projektion zu "b" umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-207">There "a" needed to be redirected to "b" in the projection.</span></span>  
  
 <span data-ttu-id="8c1db-208">Wenn ein SqlSelectStatement-Objekt erstellt wird, wird der Block, der als Eingabe für den Knoten dient, in die From-Eigenschaft des SqlSelectStatements eingefügt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-208">When a SqlSelectStatement object is created, the extent that is the input to the node is put in the From property of the SqlSelectStatement.</span></span> <span data-ttu-id="8c1db-209">Ein Symbol (<symbol_b>) wird auf Grundlage des Eingabebindungsnamens ("b") erstellt, um diesen Block darzustellen, und "AS  " +  <symbol_b> werden an die From-Klausel angefügt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-209">A Symbol (<symbol_b>) is created based on the input binding name ("b") to represent that extent and "AS  " +  <symbol_b> is appended to the From Clause.</span></span>  <span data-ttu-id="8c1db-210">Das Symbol wird außerdem der FromExtents-Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-210">The symbol is also added to the FromExtents property.</span></span>  
  
 <span data-ttu-id="8c1db-211">Das Symbol wird auch zur Symboltabelle hinzugefügt, um den Eingabebindungsnamen damit zu verknüpfen ("b", <symbol_b>).</span><span class="sxs-lookup"><span data-stu-id="8c1db-211">The symbol is also added to the symbol table to link the input binding name to it ("b", <symbol_b>).</span></span>  
  
 <span data-ttu-id="8c1db-212">Wenn ein nachfolgender Knoten dieses SqlSelectStatement wiederverwendet, fügt es der Symboltabelle einen Eintrag hinzu, um seinen Eingabebindungsnamen mit diesem Symbol zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-212">If a subsequent node reuses that SqlSelectStatement, it adds an entry to the symbol table to link its input binding name to that symbol.</span></span> <span data-ttu-id="8c1db-213">In unserem Beispiel würde der DbProjectExpression mit dem eingabebindungsnamen "a" das SqlSelectStatement wiederverwenden und hinzufügen ("a", \< Symbol_b >) der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8c1db-213">In our example, the DbProjectExpression with the input binding name of "a" would reuse the SqlSelectStatement and add ("a", \< symbol_b>) to the table.</span></span>  
  
 <span data-ttu-id="8c1db-214">Wenn Ausdrücke auf den Eingabebindungsnamen des Knotens verweisen, der das SqlSelectStatement wiederverwendet, wird dieser Verweis mithilfe der Symboltabelle in das richtige umgeleitete Symbol aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="8c1db-214">When expressions reference the input binding name of the node that is reusing the SqlSelectStatement, that reference is resolved using the symbol table to the correct redirected symbol.</span></span> <span data-ttu-id="8c1db-215">Wenn "a" von "a.x" beim Zugriff auf DbVariableReferenceExpression, der "a" darstellt, aufgelöst wird, wird es in das Symbol <symbol_b> aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="8c1db-215">When "a" from "a.x" is resolved while visiting the DbVariableReferenceExpression representing "a" it will resolve to the Symbol <symbol_b>.</span></span>  
  
### <a name="join-alias-flattening"></a><span data-ttu-id="8c1db-216">Joinaliasvereinfachung</span><span class="sxs-lookup"><span data-stu-id="8c1db-216">Join Alias Flattening</span></span>  
 <span data-ttu-id="8c1db-217">Im Abschnitt mit dem Titel "DbPropertyExpression" wird beschrieben, wie beim Zugriff auf einen DbPropertyExpression die Joinaliasvereinfachung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="8c1db-217">Join alias flattening is achieved when visiting a DbPropertyExpression as described in the section titled DbPropertyExpression.</span></span>  
  
### <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="8c1db-218">Spaltennamen- und Blockaliasumbenennung</span><span class="sxs-lookup"><span data-stu-id="8c1db-218">Column Name and Extent Alias Renaming</span></span>  
 <span data-ttu-id="8c1db-219">Das Problem der Spaltennamen- und Blockaliasumbenennung wird durch die Verwendung von Symbolen gelöst, die erst in der zweiten Phase der Generierung durch Aliase ersetzt werden, wie im Abschnitt mit dem Titel "Zweite Phase der SQL-Generierung: Generieren des Zeichenfolgenbefehls" beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="8c1db-219">The issue of column name and extent alias renaming is addressed by using symbols that only get substituted with aliases in the second phase of the generation described in the section titled Second Phase of SQL Generation: Generating the String Command.</span></span>  
  
## <a name="first-phase-of-the-sql-generation-visiting-the-expression-tree"></a><span data-ttu-id="8c1db-220">Erste Phase der SQL-Generierung: Zugriff auf die Ausdrucksstruktur</span><span class="sxs-lookup"><span data-stu-id="8c1db-220">First Phase of the SQL Generation: Visiting the Expression Tree</span></span>  
 <span data-ttu-id="8c1db-221">In diesem Abschnitt wird die erste Phase der SQL-Generierung beschrieben, wenn auf den Ausdruck zugegriffen wird, der die Abfrage darstellt, und eine Zwischenstruktur (entweder ein SqlSelectStatement oder ein SqlBuilder) erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="8c1db-221">This section describes the first phase of SQL generation, when the expression representing the query is visited and an intermediate structure is produced, either a SqlSelectStatement or a SqlBuilder.</span></span>  
  
 <span data-ttu-id="8c1db-222">In diesem Abschnitt werden die Prinzipien des Zugriffs auf unterschiedliche Kategorien von Ausdrucksknoten und Details des Zugriffs auf bestimmte Ausdruckstypen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8c1db-222">This section describes the principles of visiting different expression node categories, and details of visiting specific expression types.</span></span>  
  
### <a name="relational-non-join-nodes"></a><span data-ttu-id="8c1db-223">Relationale Knoten, die nicht zu einem Join gehören</span><span class="sxs-lookup"><span data-stu-id="8c1db-223">Relational (Non-Join) Nodes</span></span>  
 <span data-ttu-id="8c1db-224">Die folgenden Ausdruckstypen unterstützen Knoten, die nicht zu einem Join gehören:</span><span class="sxs-lookup"><span data-stu-id="8c1db-224">The following expression types support non-join nodes:</span></span>  
  
-   <span data-ttu-id="8c1db-225">DbDistinctExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-225">DbDistinctExpression</span></span>  
  
-   <span data-ttu-id="8c1db-226">DbFilterExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-226">DbFilterExpression</span></span>  
  
-   <span data-ttu-id="8c1db-227">DbGroupByExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-227">DbGroupByExpression</span></span>  
  
-   <span data-ttu-id="8c1db-228">DbLimitExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-228">DbLimitExpession</span></span>  
  
-   <span data-ttu-id="8c1db-229">DbProjectExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-229">DbProjectExpression</span></span>  
  
-   <span data-ttu-id="8c1db-230">DbSkipExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-230">DbSkipExpression</span></span>  
  
-   <span data-ttu-id="8c1db-231">DbSortExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-231">DbSortExpression</span></span>  
  
 <span data-ttu-id="8c1db-232">Der Zugriff auf diese Knoten erfolgt nach dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="8c1db-232">Visiting these nodes follows the following pattern:</span></span>  
  
1.  <span data-ttu-id="8c1db-233">Zugreifen auf die relationale Eingabe und Abrufen des resultierenden SqlSelectStatements.</span><span class="sxs-lookup"><span data-stu-id="8c1db-233">Visit the relational input and get the resulting SqlSelectStatement.</span></span> <span data-ttu-id="8c1db-234">Folgende Eingaben sind bei einem relationalen Knoten möglich:</span><span class="sxs-lookup"><span data-stu-id="8c1db-234">The input to a relational node could be one of the following:</span></span>  
  
    -   <span data-ttu-id="8c1db-235">Ein relationaler Knoten, einschließlich eines Blocks (z. B. ein DbScanExpression).</span><span class="sxs-lookup"><span data-stu-id="8c1db-235">A relational node, including an extent (a DbScanExpression, for example).</span></span> <span data-ttu-id="8c1db-236">Der Zugriff auf einen solchen Knoten gibt ein SqlSelectStatement zurück.</span><span class="sxs-lookup"><span data-stu-id="8c1db-236">Visiting such a node returns a SqlSelectStatement.</span></span>  
  
    -   <span data-ttu-id="8c1db-237">Ein Festlegungsausdruck (z. B. UNION ALL).</span><span class="sxs-lookup"><span data-stu-id="8c1db-237">A set operation expression (UNION ALL, for example).</span></span> <span data-ttu-id="8c1db-238">Das Ergebnis muss in Klammern eingeschlossen und in die FROM-Klausel eines neuen SqlSelectStatements eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-238">The result has to be wrapped in brackets and put in the FROM clause of a new SqlSelectStatement.</span></span>  
  
2.  <span data-ttu-id="8c1db-239">Überprüfen Sie, ob der aktuelle Knoten dem SqlSelectStatement hinzugefügt werden kann, das von der Eingabe erzeugt wurde.</span><span class="sxs-lookup"><span data-stu-id="8c1db-239">Check whether the current node can be added to the SqlSelectStatement produced by the input.</span></span> <span data-ttu-id="8c1db-240">Im Abschnitt mit dem Titel "Gruppieren von Ausdrücken in SQL-Anweisungen" wird dies beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8c1db-240">The section titled Grouping Expressions into SQL Statements describes this.</span></span> <span data-ttu-id="8c1db-241">Wenn das nicht der Fall ist, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="8c1db-241">If not,</span></span>  
  
    -   <span data-ttu-id="8c1db-242">Lesen Sie das aktuelle SqlSelectStatement-Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="8c1db-242">Pop the current SqlSelectStatement object.</span></span>  
  
    -   <span data-ttu-id="8c1db-243">Erstellen Sie ein neues SqlSelectStatement-Objekt, und fügen Sie das ausgelesene SqlSelectStatement als FROM-Klausel des neuen SqlSelectStatement-Objekts hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c1db-243">Create a new SqlSelectStatement object and add the popped SqlSelectStatement as the FROM of the new SqlSelectStatement object.</span></span>  
  
    -   <span data-ttu-id="8c1db-244">Legen Sie das neue Objekt oben auf dem Stapel ab.</span><span class="sxs-lookup"><span data-stu-id="8c1db-244">Put the new object on top of the stack.</span></span>  
  
3.  <span data-ttu-id="8c1db-245">Leiten Sie die Eingabeausdruckbindung auf das passende Symbol aus der Eingabe um.</span><span class="sxs-lookup"><span data-stu-id="8c1db-245">Redirect the input expression binding to the correct symbol from the input.</span></span> <span data-ttu-id="8c1db-246">Diese Informationen werden im SqlSelectStatement-Objekt verwaltet.</span><span class="sxs-lookup"><span data-stu-id="8c1db-246">This information is maintained in the SqlSelectStatement object.</span></span>  
  
4.  <span data-ttu-id="8c1db-247">Fügen Sie einen neuen SymbolTable-Bereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c1db-247">Add a new SymbolTable scope.</span></span>  
  
5.  <span data-ttu-id="8c1db-248">Greifen Sie auf den Teil des Ausdrucks zu (z. B. Projektion und Prädikat), der nicht zur Eingabe gehört.</span><span class="sxs-lookup"><span data-stu-id="8c1db-248">Visit the non-input part of the expression (for example, Projection and Predicate).</span></span>  
  
6.  <span data-ttu-id="8c1db-249">Lesen Sie alle Objekte aus, die den globalen Stapeln hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-249">Pop all the objects added to the global stacks.</span></span>  
  
 <span data-ttu-id="8c1db-250">DbSkipExpression hat keine direkte Entsprechung in SQL.</span><span class="sxs-lookup"><span data-stu-id="8c1db-250">DbSkipExpression not have a direct equivalent in SQL.</span></span> <span data-ttu-id="8c1db-251">Logisch wird es übersetzt in:</span><span class="sxs-lookup"><span data-stu-id="8c1db-251">Logically, it is translated into:</span></span>  
  
```  
SELECT Y.x1, Y.x2, ..., Y.xn  
FROM (  
   SELECT X.x1, X.x2, ..., X.xn, row_number() OVER (ORDER BY sk1, sk2, ...) AS [row_number]   
   FROM input as X   
   ) as Y  
WHERE Y.[row_number] > count   
ORDER BY sk1, sk2, ...  
```  
  
### <a name="join-expressions"></a><span data-ttu-id="8c1db-252">Joinausdrücke</span><span class="sxs-lookup"><span data-stu-id="8c1db-252">Join Expressions</span></span>  
 <span data-ttu-id="8c1db-253">Folgende Ausdrücke gelten als Joinausdrücke und werden einheitlich durch die VisitJoinExpression-Methode verarbeitet:</span><span class="sxs-lookup"><span data-stu-id="8c1db-253">The following are considered join expressions and they are processed in a common way, by the VisitJoinExpression method:</span></span>  
  
-   <span data-ttu-id="8c1db-254">DbApplyExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-254">DbApplyExpression</span></span>  
  
-   <span data-ttu-id="8c1db-255">DbJoinExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-255">DbJoinExpression</span></span>  
  
-   <span data-ttu-id="8c1db-256">DbCrossJoinExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-256">DbCrossJoinExpression</span></span>  
  
 <span data-ttu-id="8c1db-257">Der Zugriff erfolgt in folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="8c1db-257">The following are the visit steps:</span></span>  
  
 <span data-ttu-id="8c1db-258">Vor dem Zugriff auf die untergeordneten Elemente wird zunächst IsParentAJoin aufgerufen, um zu überprüfen, ob der Joinknoten ein untergeordnetes Element eines Joins der linken Seite ist.</span><span class="sxs-lookup"><span data-stu-id="8c1db-258">First, before visiting the children, IsParentAJoin is invoked to check whether the join node is a child of a join along a left spine.</span></span> <span data-ttu-id="8c1db-259">Wird false zurückgegeben, wird ein neues SqlSelectStatement gestartet.</span><span class="sxs-lookup"><span data-stu-id="8c1db-259">If it returns false, a new SqlSelectStatement is started.</span></span> <span data-ttu-id="8c1db-260">In dieser Hinsicht unterscheidet sich der Zugriff auf Joins vom Zugriff auf die übrigen Knoten, da das übergeordnete Element (der Joinknoten) das SqlSelectStatement erstellt, das die untergeordneten Elemente ggf. verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-260">In that sense, joins are visited differently from the rest of the nodes, as the parent (the join node) creates the SqlSelectStatement for the children to possibly use.</span></span>  
  
 <span data-ttu-id="8c1db-261">Verarbeiten Sie im zweiten Schritt die Eingaben einzeln.</span><span class="sxs-lookup"><span data-stu-id="8c1db-261">Second, process the inputs one at a time.</span></span> <span data-ttu-id="8c1db-262">Für jede Eingabe gilt:</span><span class="sxs-lookup"><span data-stu-id="8c1db-262">For each input:</span></span>  
  
1.  <span data-ttu-id="8c1db-263">Greifen Sie auf die Eingabe zu.</span><span class="sxs-lookup"><span data-stu-id="8c1db-263">Visit the input.</span></span>  
  
2.  <span data-ttu-id="8c1db-264">Verarbeiten Sie das Ergebnis nach dem Zugriff auf die Eingabe durch den Aufruf von ProcessJoinInputResult. Diese Methode ist für die Verwaltung der Symboltabelle nach dem Zugriff auf ein untergeordnetes Element eines Joinausdrucks und gegebenenfalls den Abschluss des vom untergeordneten Element erzeugten SqlSelectStatements zuständig.</span><span class="sxs-lookup"><span data-stu-id="8c1db-264">Post process the result of visiting the input by invoking ProcessJoinInputResult, which is responsible for maintaining the symbol table after visiting a child of a join expression and possibly finishing the SqlSelectStatement produced by the child.</span></span> <span data-ttu-id="8c1db-265">Das untergeordnete Element kann eines der folgenden Ergebnisse haben:</span><span class="sxs-lookup"><span data-stu-id="8c1db-265">The child's result could be one of the following:</span></span>  
  
    -   <span data-ttu-id="8c1db-266">Ein anderes SqlSelectStatement als das, dem das übergeordnete Element hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8c1db-266">A SqlSelectStatement different from the one to which the parent will be added.</span></span> <span data-ttu-id="8c1db-267">In dem Fall muss es möglicherweise durch das Hinzufügen von Standardspalten vervollständigt werden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-267">In such case, it may need to be completed by adding default columns.</span></span> <span data-ttu-id="8c1db-268">Wenn die Eingabe ein Join war, müssen Sie ein neues Joinsymbol erstellen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-268">If the input was a Join, you need to create a new join symbol.</span></span> <span data-ttu-id="8c1db-269">Erstellen Sie andernfalls ein normales Symbol.</span><span class="sxs-lookup"><span data-stu-id="8c1db-269">Otherwise, create a normal symbol.</span></span>  
  
    -   <span data-ttu-id="8c1db-270">Ein Block (z. B. ein DbScanExpression). In diesem Fall wird es einfach der Liste der Eingaben des SqlSelectStatements des übergeordneten Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-270">An extent (a DbScanExpression, for example), in which case it is simply added to the list of inputs of the parent’s SqlSelectStatement.</span></span>  
  
    -   <span data-ttu-id="8c1db-271">Kein SqlSelectStatement. In diesem Fall wird es in Klammern eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-271">Not a SqlSelectStatement, in which case it is wrapped with brackets.</span></span>  
  
    -   <span data-ttu-id="8c1db-272">Das gleiche SqlSelectStatement, dem das übergeordnete Element hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8c1db-272">The same SqlSelectStatement to which the parent is added.</span></span> <span data-ttu-id="8c1db-273">In diesem Fall müssen die Symbole in der FromExtents-Liste durch ein einzelnes neues JoinSymbol ersetzt werden, das alle Symbole darstellt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-273">In such case, the symbols in the FromExtents list need to be replaced with a single new JoinSymbol representing them all.</span></span>  
  
    -   <span data-ttu-id="8c1db-274">Für die ersten drei Fälle wird AddFromSymbol aufgerufen, um die AS-Klausel hinzuzufügen und die Symboltabelle zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8c1db-274">For the first three cases, AddFromSymbol is called to add the AS clause, and update the symbol table.</span></span>  
  
 <span data-ttu-id="8c1db-275">Im dritten Schritt wird auf die Joinbedingung (sofern vorhanden) zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-275">Third, the join condition (if any) is visited.</span></span>  
  
### <a name="set-operations"></a><span data-ttu-id="8c1db-276">Mengenvorgänge</span><span class="sxs-lookup"><span data-stu-id="8c1db-276">Set Operations</span></span>  
 <span data-ttu-id="8c1db-277">Die Set-Vorgänge DbUnionAllExpression, DbExceptExpression und DbIntersectExpression werden von der Methode VisitSetOpExpression verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8c1db-277">The set operations DbUnionAllExpression, DbExceptExpression, and DbIntersectExpression are processed by the method VisitSetOpExpression.</span></span> <span data-ttu-id="8c1db-278">Sie erstellt einen SqlBuilder der Form</span><span class="sxs-lookup"><span data-stu-id="8c1db-278">It creates a SqlBuilder of the shape</span></span>  
  
```xml  
<leftSqlSelectStatement> <setOp> <rightSqlSelectStatement>  
```  
  
 <span data-ttu-id="8c1db-279">Wobei \<LeftSqlSelectStatement > und \<RightSqlSelectStatement > SqlSelectStatements, die durch den Zugriff auf jede der Eingaben ermittelt werden und \<SetOp > ist der entsprechende Vorgang (z. B. UNION ALL).</span><span class="sxs-lookup"><span data-stu-id="8c1db-279">Where \<leftSqlSelectStatement> and \<rightSqlSelectStatement> are SqlSelectStatements obtained by visiting each of the inputs, and \<setOp> is the corresponding operation (UNION ALL for example).</span></span>  
  
### <a name="dbscanexpression"></a><span data-ttu-id="8c1db-280">DbScanExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-280">DbScanExpression</span></span>  
 <span data-ttu-id="8c1db-281">Wenn in einem Joinkontext (als Eingabe für einen Join, der ein linkes untergeordnetes Element eines anderen Joins ist) darauf zugegriffen wird, gibt DbScanExpression einen SqlBuilder mit dem SQL-Zielcode für das entsprechende Ziel zurück, der entweder aus einer definierenden Abfrage, einer Tabelle oder einer Ansicht besteht.</span><span class="sxs-lookup"><span data-stu-id="8c1db-281">If visited in a join context (as an input to a join that is a left child of another join), DbScanExpression returns a SqlBuilder with the target SQL for the corresponding target, which is either a defining query, table, or a view.</span></span> <span data-ttu-id="8c1db-282">Andernfalls wird ein neues SqlSelectStatement erstellt, bei dem das FROM-Feld so festgelegt wird, dass es dem entsprechenden Ziel entspricht.</span><span class="sxs-lookup"><span data-stu-id="8c1db-282">Otherwise, a new SqlSelectStatement is created with the FROM field set to correspond to the corresponding target.</span></span>  
  
### <a name="dbvariablereferenceexpression"></a><span data-ttu-id="8c1db-283">DbVariableReferenceExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-283">DbVariableReferenceExpression</span></span>  
 <span data-ttu-id="8c1db-284">Der Zugriff auf einen DbVariableReferenceExpression gibt auf Basis einer Suche in der Symboltabelle das Symbol zurück, das diesem Variablenverweisausdruck entspricht.</span><span class="sxs-lookup"><span data-stu-id="8c1db-284">The visit of a DbVariableReferenceExpression returns the Symbol corresponding to that variable reference expression based on a look up in the symbol table.</span></span>  
  
### <a name="dbpropertyexpression"></a><span data-ttu-id="8c1db-285">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-285">DbPropertyExpression</span></span>  
 <span data-ttu-id="8c1db-286">Beim Zugriff auf einen DbPropertyExpression wird eine Joinaliasvereinfachung erkannt und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8c1db-286">Join alias flattening is identified and processed when visiting a DbPropertyExpression.</span></span>  
  
 <span data-ttu-id="8c1db-287">Zuerst wird auf die Instance-Eigenschaft zugegriffen. Das Ergebnis ist ein Symbol, ein JoinSymbol oder ein SymbolPair.</span><span class="sxs-lookup"><span data-stu-id="8c1db-287">The Instance property is first visited and the result is a Symbol, a JoinSymbol, or a SymbolPair.</span></span> <span data-ttu-id="8c1db-288">Diese drei Fälle werden folgendermaßen behandelt:</span><span class="sxs-lookup"><span data-stu-id="8c1db-288">Here is how these three cases are handled:</span></span>  
  
-   <span data-ttu-id="8c1db-289">Wenn ein JoinSymbol zurückgegeben wird, enthält seine NameToExtent-Eigenschaft ein Symbol für die benötigte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8c1db-289">If a JoinSymbol is returned, than its NameToExtent property contains a symbol for the needed property.</span></span> <span data-ttu-id="8c1db-290">Wenn das Joinsymbol einen geschachtelten Join darstellt, wird ein neues Symbolpaar mit dem Joinsymbol zur Nachverfolgung des Symbols, das als Instanzalias verwendet würde, und dem Symbol, das die tatsächliche Eigenschaft für die weitere Auflösung darstellt, zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8c1db-290">If the join symbol represents a nested join, a new Symbol pair is returned with the join symbol to track the symbol that would be used as the instance alias, and the symbol representing the actual property for further resolving.</span></span>  
  
-   <span data-ttu-id="8c1db-291">Wenn ein SymbolPair zurückgegeben wird und der Spaltenteil ein Joinsymbol ist, wird wieder ein Joinsymbol zurückgegeben. Dieses Mal wird die Spalteneigenschaft jedoch aktualisiert, damit sie auf die durch den aktuellen Eigenschaftsausdruck dargestellte Eigenschaft verweist.</span><span class="sxs-lookup"><span data-stu-id="8c1db-291">If a SymbolPair is returned and the Column part is a join symbol, a join symbol is again returned, but now the column property is updated to point to the property represented by the current property expression.</span></span> <span data-ttu-id="8c1db-292">Andernfalls wird ein SqlBuilder mit der SymbolPair-Quelle als Alias und dem Symbol für die aktuelle Eigenschaft als Spalte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8c1db-292">Otherwise a SqlBuilder is returned with the SymbolPair source as the alias, and the symbol for the current property as the column.</span></span>  
  
-   <span data-ttu-id="8c1db-293">Wenn ein Symbol zurückgegeben wird, gibt die Visit-Methode eine SqlBuilder-Methode mit dieser Instanz als Alias und dem Eigenschaftennamen als Spaltenname zurück.</span><span class="sxs-lookup"><span data-stu-id="8c1db-293">If a Symbol is returned, the Visit method returns a SqlBuilder method with that instance as the alias, and the property name as column name.</span></span>  
  
### <a name="dbnewinstanceexpression"></a><span data-ttu-id="8c1db-294">DbNewInstanceExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-294">DbNewInstanceExpression</span></span>  
 <span data-ttu-id="8c1db-295">Wenn DbNewInstanceExpression als Projection-Eigenschaft von DbProjectExpression verwendet wird, erzeugt DbNewInstanceExpression eine durch Trennzeichen getrennte Liste der Argumente, um die projizierten Spalten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-295">When used as the Projection property of DbProjectExpression, DbNewInstanceExpression produces a comma-separated list of the arguments to represent the projected columns.</span></span>  
  
 <span data-ttu-id="8c1db-296">Wenn die Rückgabe von DbNewInstanceExpression vom Typ Auflistung ist und eine neue Auflistung der Ausdrücke definiert, die als Argumente bereitgestellt wurden, werden die folgenden drei Fälle getrennt behandelt:</span><span class="sxs-lookup"><span data-stu-id="8c1db-296">When DbNewInstanceExpression has a collection return type, and defines a new collection of the expressions provided as arguments, the following three cases are handled separately:</span></span>  
  
-   <span data-ttu-id="8c1db-297">Wenn DbElementExpression das einzige Argument von DbNewInstanceExpression ist, wird er wie folgt übersetzt:</span><span class="sxs-lookup"><span data-stu-id="8c1db-297">If DbNewInstanceExpression has DbElementExpression as the only argument, it is translated as follows:</span></span>  
  
    ```  
    NewInstance(Element(X)) =>  SELECT TOP 1 …FROM X  
    ```  
  
 <span data-ttu-id="8c1db-298">Wenn DbNewInstanceExpression über keine Argumente verfügt (eine leere Tabelle darstellt), wird DbNewInstanceExpression übersetzt in:</span><span class="sxs-lookup"><span data-stu-id="8c1db-298">If DbNewInstanceExpression has no arguments (represents an empty table), DbNewInstanceExpression is translated into:</span></span>  
  
```  
SELECT CAST(NULL AS <primitiveType>) as X  
FROM (SELECT 1) AS Y WHERE 1=0  
```  
  
 <span data-ttu-id="8c1db-299">Andernfalls bildet DbNewInstanceExpression eine UNION ALL-Folge der Argumente:</span><span class="sxs-lookup"><span data-stu-id="8c1db-299">Otherwise DbNewInstanceExpression builds a union-all ladder of the arguments:</span></span>  
  
```  
SELECT <visit-result-arg1> as X  
UNION ALL SELECT <visit-result-arg2> as X  
UNION ALL …  
UNION ALL SELECT <visit-result-argN> as X  
```  
  
### <a name="dbfunctionexpression"></a><span data-ttu-id="8c1db-300">DbFunctionExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-300">DbFunctionExpression</span></span>  
 <span data-ttu-id="8c1db-301">Kanonische und integrierte Funktionen werden auf die gleiche Weise verarbeitet: Wenn sie besondere Behandlung benötigen (z. B. TRIM(Zeichenfolge) zu LTRIM(RTRIM(Zeichenfolge)), wird der entsprechende Handler aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-301">Canonical and built-in functions are processed the same way: if they need special handling (TRIM(string) to  LTRIM(RTRIM(string), for example), the appropriate handler is invoked.</span></span> <span data-ttu-id="8c1db-302">Andernfalls werden sie in Funktionsname(arg1, arg2, ..., argn) übersetzt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-302">Otherwise they are translated to FunctionName(arg1, arg2, ..., argn).</span></span>  
  
 <span data-ttu-id="8c1db-303">Um festzustellen, welche Funktionen eine besondere Behandlung benötigen, sowie für die entsprechenden Handler werden Wörterbücher verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c1db-303">Dictionaries are used to keep track of which functions need special handling and their appropriate handlers.</span></span>  
  
 <span data-ttu-id="8c1db-304">Benutzerdefinierte Funktionen werden in Namespacename.Funktionsname(arg1, arg2, ..., argn) übersetzt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-304">User-defined functions are tanslated to NamespaceName.FunctionName(arg1, arg2, ..., argn).</span></span>  
  
### <a name="dbelementexpression"></a><span data-ttu-id="8c1db-305">DbElementExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-305">DbElementExpression</span></span>  
 <span data-ttu-id="8c1db-306">Die Methode, die auf DbElementExpression zugreift, wird nur für den Zugriff auf einen DbElementExpression aufgerufen, wenn er zur Darstellung einer skalaren Unterabfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8c1db-306">The method that visits DbElementExpression is only invoked for visiting a DbElementExpression when used to represent a scalar subquery.</span></span> <span data-ttu-id="8c1db-307">Daher wird DbElementExpression in ein vollständiges SqlSelectStatement übersetzt und mit Klammern versehen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-307">Therefore, DbElementExpression translates into a complete SqlSelectStatement and adds brackets around it.</span></span>  
  
### <a name="dbquantifierexpression"></a><span data-ttu-id="8c1db-308">DbQuantifierExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-308">DbQuantifierExpression</span></span>  
 <span data-ttu-id="8c1db-309">Abhängig vom Ausdruckstyp (Any oder All) wird DbQuantifierExpression folgendermaßen übersetzt:</span><span class="sxs-lookup"><span data-stu-id="8c1db-309">Depending on the expression type (Any or All), DbQuantifierExpression is translated it as:</span></span>  
  
```  
Any(input, x) => Exists(Filter(input,x))  
All(input, x) => Not Exists(Filter(input, not(x))  
```  
  
### <a name="dbnotexpression"></a><span data-ttu-id="8c1db-310">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-310">DbNotExpression</span></span>  
 <span data-ttu-id="8c1db-311">In einigen Fällen ist es möglich, die Übersetzung von DbNotExpression mit seinem Eingabeausdruck zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="8c1db-311">In some cases it is possible to collapse the translation of DbNotExpression with its input expression.</span></span> <span data-ttu-id="8c1db-312">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8c1db-312">For example:</span></span>  
  
```  
Not(IsNull(a)) =>  "a IS NOT NULL"  
Not(All(input, x) => Not (Not Exists(Filter(input, not(x))) => Exists(Filter(input, not(x))  
```  
  
 <span data-ttu-id="8c1db-313">Der Grund für die zweite Reduzierung besteht darin, dass beim Übersetzen von DbQuantifierExpression vom Typ All Ineffizienzen vom Anbieter eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-313">The reason the second collapse is performed is because inefficiencies were introduced by the provider when translating DbQuantifierExpression of type All.</span></span> <span data-ttu-id="8c1db-314">Daher konnte die Vereinfachung vom Entity Framework nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-314">Thus the Entity Framework could not have done the simplification.</span></span>  
  
### <a name="dbisemptyexpression"></a><span data-ttu-id="8c1db-315">DbIsEmptyExpression</span><span class="sxs-lookup"><span data-stu-id="8c1db-315">DbIsEmptyExpression</span></span>  
 <span data-ttu-id="8c1db-316">DbIsEmptyExpression wird folgendermaßen übersetzt:</span><span class="sxs-lookup"><span data-stu-id="8c1db-316">DbIsEmptyExpression is translated as:</span></span>  
  
```  
IsEmpty(inut) = Not Exists(input)  
```  
  
## <a name="second-phase-of-sql-generation-generating-the-string-command"></a><span data-ttu-id="8c1db-317">Zweite Phase der SQL-Generierung: Generieren des Zeichenfolgenbefehls</span><span class="sxs-lookup"><span data-stu-id="8c1db-317">Second Phase of SQL Generation: Generating the String Command</span></span>  
 <span data-ttu-id="8c1db-318">Beim Generieren eines SQL-Zeichenfolgenbefehls erzeugt das SqlSelectStatement tatsächliche Aliase für die Symbole. Damit wird das Problem der Umbenennung von Spaltennamen und Blockaliasen gelöst.</span><span class="sxs-lookup"><span data-stu-id="8c1db-318">When generating a string SQL command, the SqlSelectStatement produces actual aliases for the symbols, which addresses the issue of column name and extent alias renaming.</span></span>  
  
 <span data-ttu-id="8c1db-319">Die Blockaliasumbenennung erfolgt beim Schreiben des SqlSelectStatement-Objekts in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8c1db-319">Extent alias renaming occurs while writing the SqlSelectStatement object into a string.</span></span> <span data-ttu-id="8c1db-320">Erstellen Sie zuerst eine Liste aller von den äußeren Blöcken verwendeten Aliase.</span><span class="sxs-lookup"><span data-stu-id="8c1db-320">First create a list of all the aliases used by the outer extents.</span></span> <span data-ttu-id="8c1db-321">Jedes Symbol in FromExtents (oder AllJoinExtents, wenn es nicht NULL ist) wird umbenannt, wenn der Name mit einem der äußeren Blöcke übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-321">Each symbol in the FromExtents (or AllJoinExtents if it is non-null), gets renamed if it collides with any of the outer extents.</span></span> <span data-ttu-id="8c1db-322">Wenn eine Umbenennung erforderlich ist, entsteht kein Konflikt mit einem der Blöcke, die in AllExtentNames gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="8c1db-322">If renaming is needed, it will not conflict with any of the extents collected in AllExtentNames.</span></span>  
  
 <span data-ttu-id="8c1db-323">Die Umbenennung von Spalten erfolgt beim Schreiben eines Symbol-Objekts in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8c1db-323">Column renaming occurs while writing a Symbol object to a string.</span></span> <span data-ttu-id="8c1db-324">AddDefaultColumns hat in der ersten Phase festgestellt, ob ein bestimmtes Spaltensymbol umbenannt werden muss.</span><span class="sxs-lookup"><span data-stu-id="8c1db-324">AddDefaultColumns in the first phase has determined if a certain column symbol has to be renamed.</span></span> <span data-ttu-id="8c1db-325">In der zweiten Phase wird nur die Umbenennung vorgenommen, um sicherzustellen, dass kein Konflikt zwischen dem erzeugten Namen und einem in AllColumnNames verwendeten Namen auftritt.</span><span class="sxs-lookup"><span data-stu-id="8c1db-325">In the second phase only the rename occurs making sure that the name produced does not conflict with any name used in AllColumnNames</span></span>  
  
 <span data-ttu-id="8c1db-326">Um eindeutige Namen sowohl für Blockaliase als auch für Spalten zu generieren, müssen Sie <existing_name>_n verwenden, wobei n der kleinste Alias ist, der noch nicht verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8c1db-326">To produce unique names both for extent aliases and for columns, use <existing_name>_n where n is the smallest alias that has not been used yet.</span></span> <span data-ttu-id="8c1db-327">Die globale Liste aller Aliase erhöht den Bedarf an wiederholten Umbenennungen.</span><span class="sxs-lookup"><span data-stu-id="8c1db-327">The global list of all aliases increases the need for cascading renames.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c1db-328">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c1db-328">See Also</span></span>  
 [<span data-ttu-id="8c1db-329">SQL-Generierung im Beispielanbieter</span><span class="sxs-lookup"><span data-stu-id="8c1db-329">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)
