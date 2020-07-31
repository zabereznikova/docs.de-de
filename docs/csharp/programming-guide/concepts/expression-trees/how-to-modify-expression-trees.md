---
title: Ändern von Ausdrucksbaumstrukturen (C#)
description: Hier erfahren Sie, wie Sie eine Ausdrucksbaumstruktur ändern, indem Sie eine Kopie einer vorhandenen Ausdrucksbaumstruktur erstellen und die erforderlichen Änderungen vornehmen.
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: 45aea18e253811d4e5c60f23f7f8496d4358f64c
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105610"
---
# <a name="how-to-modify-expression-trees-c"></a><span data-ttu-id="3c683-103">Ändern von Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="3c683-103">How to modify expression trees (C#)</span></span>
<span data-ttu-id="3c683-104">In diesem Thema erfahren Sie, wie Sie eine Ausdrucksbaumstruktur ändern können.</span><span class="sxs-lookup"><span data-stu-id="3c683-104">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="3c683-105">Ausdrucksbaumstrukturen sind unveränderlich, d.h. sie können nicht direkt modifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="3c683-105">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="3c683-106">Um eine Ausdrucksbaumstruktur zu verändern, müssen Sie eine Kopie eines vorhandenen Ausdrucksbaumstruktur erstellen und währenddessen die erforderlichen Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="3c683-106">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="3c683-107">Sie können die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse verwenden, um einen vorhandenen Ausdrucksbaum zu durchlaufen und jeden Knoten zu kopieren, der durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="3c683-107">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="3c683-108">So ändern Sie Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="3c683-108">To modify an expression tree</span></span>  
  
1. <span data-ttu-id="3c683-109">Erstellen Sie ein neues **Konsolenanwendungsprojekt**.</span><span class="sxs-lookup"><span data-stu-id="3c683-109">Create a new **Console Application** project.</span></span>  
  
2. <span data-ttu-id="3c683-110">Fügen Sie der Datei eine `using`-Anweisung für den `System.Linq.Expressions`-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c683-110">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3. <span data-ttu-id="3c683-111">Fügen Sie die `AndAlsoModifier`-Klasse in Ihr Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="3c683-111">Add the `AndAlsoModifier` class to your project.</span></span>  
  
    ```csharp  
    public class AndAlsoModifier : ExpressionVisitor  
    {  
        public Expression Modify(Expression expression)  
        {  
            return Visit(expression);  
        }  
  
        protected override Expression VisitBinary(BinaryExpression b)  
        {  
            if (b.NodeType == ExpressionType.AndAlso)  
            {  
                Expression left = this.Visit(b.Left);  
                Expression right = this.Visit(b.Right);  
  
                // Make this binary expression an OrElse operation instead of an AndAlso operation.  
                return Expression.MakeBinary(ExpressionType.OrElse, left, right, b.IsLiftedToNull, b.Method);  
            }  
  
            return base.VisitBinary(b);  
        }  
    }  
    ```  
  
     <span data-ttu-id="3c683-112">Diese Klasse erbt die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse und ist darauf spezialisiert, Ausdrücke zu verändern, die bedingte `AND`-Vorgänge darstellen.</span><span class="sxs-lookup"><span data-stu-id="3c683-112">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="3c683-113">Es ändert diese Vorgänge von einem bedingten `AND` in ein bedingtes `OR`.</span><span class="sxs-lookup"><span data-stu-id="3c683-113">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="3c683-114">Zu diesem Zweck setzt die Klasse die <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>-Methode der Basisklasse außer Kraft, weil bedingte `AND`-Ausdrücke als binäre Ausdrücke dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3c683-114">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="3c683-115">Für die `VisitBinary`-Methode gilt Folgendes: Wenn der an die Methode übergebene Ausdruck eine bedingte `AND`-Operation darstellt, erstellt der Code einen neuen Ausdruck, der den bedingten Operator `OR` anstelle des bedingten Operators `AND` enthält.</span><span class="sxs-lookup"><span data-stu-id="3c683-115">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="3c683-116">Wenn der an `VisitBinary` übergebene Ausdruck keinen bedingten `AND`-Vorgang darstellt, verzögert die Methode die Implementierung der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="3c683-116">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="3c683-117">Die Basisklassenmethode erstellt Knoten, die den übergebenen Ausdrucksbaumstrukturen gleichen. In diesem Fall sind die Teilstrukturen der Knoten jedoch durch die Ausdrucksbaumstrukturen ersetzt, die vom Besucher rekursiv erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3c683-117">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4. <span data-ttu-id="3c683-118">Fügen Sie der Datei eine `using`-Anweisung für den `System.Linq.Expressions`-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c683-118">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5. <span data-ttu-id="3c683-119">Fügen Sie der `Main`-Methode in der Datei „Program.cs“ Code hinzu, um eine Ausdrucksbaumstruktur zu erstellen, und übergeben Sie diese Struktur an die Methode, die sie ändert.</span><span class="sxs-lookup"><span data-stu-id="3c683-119">Add code to the `Main` method in the Program.cs file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
    ```csharp  
    Expression<Func<string, bool>> expr = name => name.Length > 10 && name.StartsWith("G");  
    Console.WriteLine(expr);  
  
    AndAlsoModifier treeModifier = new AndAlsoModifier();  
    Expression modifiedExpr = treeModifier.Modify((Expression) expr);  
  
    Console.WriteLine(modifiedExpr);  
  
    /*  This code produces the following output:  
  
        name => ((name.Length > 10) && name.StartsWith("G"))  
        name => ((name.Length > 10) || name.StartsWith("G"))  
    */  
    ```  
  
     <span data-ttu-id="3c683-120">Der Code erstellt einen Ausdruck, der einen bedingten `AND`-Vorgang enthält.</span><span class="sxs-lookup"><span data-stu-id="3c683-120">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="3c683-121">Er erstellt anschließend eine Instanz der `AndAlsoModifier`-Klasse und übergibt den Ausdruck an die `Modify`-Methode dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="3c683-121">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="3c683-122">Sowohl der ursprüngliche als auch der geänderte Ausdrucksbaum werden ausgegeben, um die Änderungen zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="3c683-122">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6. <span data-ttu-id="3c683-123">Kompilieren Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="3c683-123">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c683-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c683-124">See also</span></span>

- [<span data-ttu-id="3c683-125">Ausführen von Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="3c683-125">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="3c683-126">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="3c683-126">Expression Trees (C#)</span></span>](./index.md)
