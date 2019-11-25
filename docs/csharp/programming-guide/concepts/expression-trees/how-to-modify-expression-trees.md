---
title: Ändern von Ausdrucksbaumstrukturen (C#)
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: e921c594497d02f5eb16cc60294e947e83636d7a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969900"
---
# <a name="how-to-modify-expression-trees-c"></a><span data-ttu-id="a64c8-102">Ändern von Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="a64c8-102">How to modify expression trees (C#)</span></span>
<span data-ttu-id="a64c8-103">In diesem Thema erfahren Sie, wie Sie eine Ausdrucksbaumstruktur ändern können.</span><span class="sxs-lookup"><span data-stu-id="a64c8-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="a64c8-104">Ausdrucksbaumstrukturen sind unveränderlich, d.h. sie können nicht direkt modifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a64c8-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="a64c8-105">Um eine Ausdrucksbaumstruktur zu verändern, müssen Sie eine Kopie eines vorhandenen Ausdrucksbaumstruktur erstellen und währenddessen die erforderlichen Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="a64c8-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="a64c8-106">Sie können die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse verwenden, um einen vorhandenen Ausdrucksbaum zu durchlaufen und jeden Knoten zu kopieren, der durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="a64c8-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="a64c8-107">So ändern Sie Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="a64c8-107">To modify an expression tree</span></span>  
  
1. <span data-ttu-id="a64c8-108">Erstellen Sie ein neues **Konsolenanwendungsprojekt**.</span><span class="sxs-lookup"><span data-stu-id="a64c8-108">Create a new **Console Application** project.</span></span>  
  
2. <span data-ttu-id="a64c8-109">Fügen Sie der Datei eine `using`-Anweisung für den `System.Linq.Expressions`-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="a64c8-109">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3. <span data-ttu-id="a64c8-110">Fügen Sie die `AndAlsoModifier`-Klasse in Ihr Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="a64c8-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
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
  
     <span data-ttu-id="a64c8-111">Diese Klasse erbt die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse und ist darauf spezialisiert, Ausdrücke zu verändern, die bedingte `AND`-Vorgänge darstellen.</span><span class="sxs-lookup"><span data-stu-id="a64c8-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="a64c8-112">Es ändert diese Vorgänge von einem bedingten `AND` in ein bedingtes `OR`.</span><span class="sxs-lookup"><span data-stu-id="a64c8-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="a64c8-113">Zu diesem Zweck setzt die Klasse die <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>-Methode der Basisklasse außer Kraft, weil bedingte `AND`-Ausdrücke als binäre Ausdrücke dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a64c8-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="a64c8-114">Für die `VisitBinary`-Methode gilt Folgendes: Wenn der an die Methode übergebene Ausdruck eine bedingte `AND`-Operation darstellt, erstellt der Code einen neuen Ausdruck, der den bedingten Operator `OR` anstelle des bedingten Operators `AND` enthält.</span><span class="sxs-lookup"><span data-stu-id="a64c8-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="a64c8-115">Wenn der an `VisitBinary` übergebene Ausdruck keinen bedingten `AND`-Vorgang darstellt, verzögert die Methode die Implementierung der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="a64c8-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="a64c8-116">Die Basisklassenmethode erstellt Knoten, die den übergebenen Ausdrucksbaumstrukturen gleichen. In diesem Fall sind die Teilstrukturen der Knoten jedoch durch die Ausdrucksbaumstrukturen ersetzt, die vom Besucher rekursiv erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a64c8-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4. <span data-ttu-id="a64c8-117">Fügen Sie der Datei eine `using`-Anweisung für den `System.Linq.Expressions`-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="a64c8-117">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5. <span data-ttu-id="a64c8-118">Fügen Sie der `Main`-Methode in der Datei „Program.cs“ Code hinzu, um eine Ausdrucksbaumstruktur zu erstellen, und übergeben Sie diese Struktur an die Methode, die sie ändert.</span><span class="sxs-lookup"><span data-stu-id="a64c8-118">Add code to the `Main` method in the Program.cs file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
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
  
     <span data-ttu-id="a64c8-119">Der Code erstellt einen Ausdruck, der einen bedingten `AND`-Vorgang enthält.</span><span class="sxs-lookup"><span data-stu-id="a64c8-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="a64c8-120">Er erstellt anschließend eine Instanz der `AndAlsoModifier`-Klasse und übergibt den Ausdruck an die `Modify`-Methode dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="a64c8-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="a64c8-121">Sowohl der ursprüngliche als auch der geänderte Ausdrucksbaum werden ausgegeben, um die Änderungen zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="a64c8-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6. <span data-ttu-id="a64c8-122">Kompilieren Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="a64c8-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a64c8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a64c8-123">See also</span></span>

- [<span data-ttu-id="a64c8-124">Ausführen von Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="a64c8-124">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="a64c8-125">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="a64c8-125">Expression Trees (C#)</span></span>](./index.md)
