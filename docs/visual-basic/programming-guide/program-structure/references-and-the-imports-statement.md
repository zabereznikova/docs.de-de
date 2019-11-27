---
title: Verweise und die Imports-Anweisung
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 31b4fe001f2b8a62ac30488053c57cd186020421
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347279"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="2b530-102">Verweise und die Imports-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b530-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="2b530-103">Sie können externe Objekte für Ihr Projekt verfügbar machen, indem Sie im Menü **Projekt** den Befehl **Verweis hinzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2b530-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="2b530-104">Verweise in Visual Basic können auf Assemblys verweisen, die wie Typbibliotheken vorliegen, aber weitere Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="2b530-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="2b530-105">Die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2b530-105">The Imports Statement</span></span>  
 <span data-ttu-id="2b530-106">Assemblys enthalten einen oder mehrere Namespaces.</span><span class="sxs-lookup"><span data-stu-id="2b530-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="2b530-107">Wenn Sie einen Verweis auf eine Assembly hinzufügen, können Sie einem Modul, das die Sichtbarkeit der Namespaces dieser Assembly innerhalb des Moduls steuert, auch eine `Imports`-Anweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2b530-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="2b530-108">Die `Imports`-Anweisung stellt einen Bereichs Kontext bereit, in dem Sie nur den Teil des-Namespace verwenden können, der zum Bereitstellen eines eindeutigen Verweises erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2b530-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="2b530-109">Die `Imports`-Anweisung weist die folgende Syntax auf:</span><span class="sxs-lookup"><span data-stu-id="2b530-109">The `Imports` statement has the following syntax:</span></span>  
  
 `Imports [Aliasname =] Namespace`  
  
 <span data-ttu-id="2b530-110">`Aliasname` verweist auf einen Kurznamen, den Sie im Code verwenden können, um auf einen importierten Namespace zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="2b530-110">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="2b530-111">`Namespace` ist ein Namespace, der entweder über einen Projekt Verweis, über eine Definition innerhalb des Projekts oder eine vorherige `Imports` Anweisung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2b530-111">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="2b530-112">Ein Modul kann eine beliebige Anzahl von `Imports`-Anweisungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="2b530-112">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="2b530-113">Sie müssen nach allen `Option`-Anweisungen (sofern vorhanden), aber vor einem anderen Code angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2b530-113">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b530-114">Verwechseln Sie Projekt Verweise nicht mit der `Imports`-Anweisung oder der `Declare`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2b530-114">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="2b530-115">Projekt Verweise machen externe Objekte (z. b. Objekte in Assemblys) für Visual Basic Projekte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2b530-115">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="2b530-116">Die `Imports`-Anweisung wird verwendet, um den Zugriff auf Projekt Verweise zu vereinfachen, bietet aber keinen Zugriff auf diese Objekte.</span><span class="sxs-lookup"><span data-stu-id="2b530-116">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="2b530-117">Die `Declare`-Anweisung wird verwendet, um einen Verweis auf eine externe Prozedur in einer Dynamic Link Library (dll) zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="2b530-117">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="2b530-118">Verwenden von Aliasen mit der Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2b530-118">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="2b530-119">Die `Imports`-Anweisung vereinfacht den Zugriff auf Methoden von Klassen, da die Notwendigkeit entfällt, die voll qualifizierten Namen von verweisen explizit einzugeben.</span><span class="sxs-lookup"><span data-stu-id="2b530-119">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="2b530-120">Mit Aliasen können Sie nur einem Teil eines Namespace einen freundlicheren Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2b530-120">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="2b530-121">Beispielsweise ist die Reihenfolge der Wagen Rücklauf/Zeilenvorschub, die bewirkt, dass ein einzelnes Textzeile in mehreren Zeilen angezeigt wird, Teil des <xref:Microsoft.VisualBasic.ControlChars> Moduls im <xref:Microsoft.VisualBasic?displayProperty=nameWithType>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="2b530-121">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="2b530-122">Wenn Sie diese Konstante in einem Programm ohne Alias verwenden möchten, müssen Sie den folgenden Code eingeben:</span><span class="sxs-lookup"><span data-stu-id="2b530-122">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 <span data-ttu-id="2b530-123">`Imports`-Anweisungen müssen immer die ersten Zeilen sein, die direkt nach allen `Option` Anweisungen in einem Modul stehen.</span><span class="sxs-lookup"><span data-stu-id="2b530-123">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="2b530-124">Das folgende Code Fragment zeigt, wie Sie einen Alias importieren und dem <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType>-Modul zuweisen:</span><span class="sxs-lookup"><span data-stu-id="2b530-124">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 <span data-ttu-id="2b530-125">Zukünftige Verweise auf diesen Namespace können erheblich kürzer sein:</span><span class="sxs-lookup"><span data-stu-id="2b530-125">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 <span data-ttu-id="2b530-126">Wenn eine `Imports` Anweisung keinen Aliasnamen enthält, können innerhalb des importierten Namespace definierte Elemente im Modul ohne Qualifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b530-126">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="2b530-127">Wenn der Aliasname angegeben ist, muss er als Qualifizierer für Namen verwendet werden, die in diesem Namespace enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2b530-127">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b530-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b530-128">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="2b530-129">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b530-129">Namespaces in Visual Basic</span></span>](namespaces.md)
- [<span data-ttu-id="2b530-130">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="2b530-130">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="2b530-131">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="2b530-131">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
