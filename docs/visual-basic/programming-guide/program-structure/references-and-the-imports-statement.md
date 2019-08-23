---
title: Verweise und die Imports-Anweisung (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 99afa42994dd09d0b5faaeaf534fbc4b41816998
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962477"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="8e42d-102">Verweise und die Imports-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e42d-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="8e42d-103">Sie können externe Objekte für Ihr Projekt verfügbar machen, indem Sie im Menü **Projekt** den Befehl **Verweis hinzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="8e42d-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="8e42d-104">Verweise in Visual Basic können auf Assemblys verweisen, die wie Typbibliotheken vorliegen, aber weitere Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8e42d-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="8e42d-105">Die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8e42d-105">The Imports Statement</span></span>  
 <span data-ttu-id="8e42d-106">Assemblys enthalten einen oder mehrere Namespaces.</span><span class="sxs-lookup"><span data-stu-id="8e42d-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="8e42d-107">Wenn Sie einen Verweis auf eine Assembly hinzufügen, können Sie einem Modul `Imports` , das die Sichtbarkeit der Namespaces dieser Assembly innerhalb des Moduls steuert, auch eine-Anweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8e42d-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="8e42d-108">Die `Imports` -Anweisung stellt einen Bereichs Kontext bereit, in dem Sie nur den Teil des-Namespace verwenden können, der für die Bereitstellung eines eindeutigen Verweises erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8e42d-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="8e42d-109">Die `Imports` -Anweisung weist die folgende Syntax auf:</span><span class="sxs-lookup"><span data-stu-id="8e42d-109">The `Imports` statement has the following syntax:</span></span>  
  
 `Imports [Aliasname =] Namespace`  
  
 <span data-ttu-id="8e42d-110">`Aliasname`bezieht sich auf einen Kurznamen, den Sie im Code verwenden können, um auf einen importierten Namespace zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="8e42d-110">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="8e42d-111">`Namespace`ist ein Namespace, der entweder über einen Projekt Verweis, über eine Definition innerhalb des Projekts oder eine vorherige `Imports` Anweisung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8e42d-111">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="8e42d-112">Ein Modul kann eine beliebige Anzahl von `Imports` -Anweisungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8e42d-112">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="8e42d-113">Sie müssen nach allen `Option` -Anweisungen (sofern vorhanden), aber vor einem anderen Code angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8e42d-113">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e42d-114">Verwechseln Sie Projekt Verweise nicht mit der `Imports` -Anweisung oder `Declare` der-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8e42d-114">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="8e42d-115">Projekt Verweise machen externe Objekte (z. b. Objekte in Assemblys) für Visual Basic Projekte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8e42d-115">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="8e42d-116">Die `Imports` -Anweisung wird verwendet, um den Zugriff auf Projekt Verweise zu vereinfachen, bietet aber keinen Zugriff auf diese Objekte.</span><span class="sxs-lookup"><span data-stu-id="8e42d-116">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="8e42d-117">Die `Declare` -Anweisung wird verwendet, um einen Verweis auf eine externe Prozedur in einer Dynamic Link Library (dll) zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8e42d-117">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="8e42d-118">Verwenden von Aliasen mit der Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8e42d-118">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="8e42d-119">Die `Imports` -Anweisung vereinfacht den Zugriff auf Methoden von Klassen, da die Notwendigkeit entfällt, die voll qualifizierten Namen von verweisen explizit einzugeben.</span><span class="sxs-lookup"><span data-stu-id="8e42d-119">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="8e42d-120">Mit Aliasen können Sie nur einem Teil eines Namespace einen freundlicheren Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8e42d-120">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="8e42d-121">Beispielsweise ist die Sequenz zum Wagen Rücklauf/Zeilenvorschub, die bewirkt, dass ein einzelnes Textzeile in mehreren Zeilen angezeigt <xref:Microsoft.VisualBasic.ControlChars> wird, Teil <xref:Microsoft.VisualBasic?displayProperty=nameWithType> des Moduls im-Namespace.</span><span class="sxs-lookup"><span data-stu-id="8e42d-121">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="8e42d-122">Wenn Sie diese Konstante in einem Programm ohne Alias verwenden möchten, müssen Sie den folgenden Code eingeben:</span><span class="sxs-lookup"><span data-stu-id="8e42d-122">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 <span data-ttu-id="8e42d-123">`Imports`-Anweisungen müssen immer die ersten Zeilen sein, die `Option` direkt auf alle-Anweisungen in einem Modul folgen.</span><span class="sxs-lookup"><span data-stu-id="8e42d-123">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="8e42d-124">Das folgende Code Fragment zeigt, wie Sie einen Alias importieren und dem <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> Modul zuweisen:</span><span class="sxs-lookup"><span data-stu-id="8e42d-124">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 <span data-ttu-id="8e42d-125">Zukünftige Verweise auf diesen Namespace können erheblich kürzer sein:</span><span class="sxs-lookup"><span data-stu-id="8e42d-125">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 <span data-ttu-id="8e42d-126">Wenn eine `Imports` -Anweisung keinen Aliasnamen enthält, können innerhalb des importierten Namespace definierte Elemente ohne Qualifizierung im Modul verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e42d-126">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="8e42d-127">Wenn der Aliasname angegeben ist, muss er als Qualifizierer für Namen verwendet werden, die in diesem Namespace enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8e42d-127">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e42d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e42d-128">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="8e42d-129">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e42d-129">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="8e42d-130">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="8e42d-130">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="8e42d-131">Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="8e42d-131">How to: Create and Use Assemblies Using the Command Line</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
- [<span data-ttu-id="8e42d-132">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="8e42d-132">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
