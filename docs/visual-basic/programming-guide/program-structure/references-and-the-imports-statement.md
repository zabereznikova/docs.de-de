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
ms.openlocfilehash: bd08940ac04d0218f3d3936514a72c12449b34ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505561"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="6ac90-102">Verweise und die Imports-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ac90-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="6ac90-103">Können Sie externe Objekte verfügbar machen zu Ihrem Projekt durch Auswählen der **Verweis hinzufügen** Befehl die **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="6ac90-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="6ac90-104">Verweise in Visual Basic können auf Assemblys verweisen, die ähneln Typbibliotheken jedoch mehr Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="6ac90-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="6ac90-105">Die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6ac90-105">The Imports Statement</span></span>  
 <span data-ttu-id="6ac90-106">Assemblys enthalten einen oder mehrere Namespaces.</span><span class="sxs-lookup"><span data-stu-id="6ac90-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="6ac90-107">Wenn Sie einen Verweis auf eine Assembly hinzufügen, können Sie auch Hinzufügen einer `Imports` Anweisung, um ein Modul, das die Sichtbarkeit dieses Namespaces innerhalb des Moduls gesteuert.</span><span class="sxs-lookup"><span data-stu-id="6ac90-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="6ac90-108">Die `Imports` Anweisung stellt einen Kontextbereich mit der Sie nur den Teil des Namespace erforderlich, geben Sie einen eindeutigen Verweis verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="6ac90-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="6ac90-109">Die `Imports` Anweisung weist die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="6ac90-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="6ac90-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="6ac90-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="6ac90-111">`Aliasname` bezieht sich auf einen kurzen Namen, die, den Sie im Code verwenden können, um zu einem importierten Namespace zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="6ac90-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="6ac90-112">`Namespace` ist ein Namespace, die zur Verfügung, entweder durch einen Projektverweis, über eine Definition innerhalb des Projekts oder durch eine vorherige `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6ac90-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="6ac90-113">Ein Modul kann eine beliebige Anzahl von enthalten `Imports` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6ac90-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="6ac90-114">Müssen sie nach jedem stehen `Option` -Anweisungen, falls vorhanden, jedoch vor jedem anderen Code.</span><span class="sxs-lookup"><span data-stu-id="6ac90-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ac90-115">Verwechseln Sie nicht die Projektverweise mit den `Imports` Anweisung oder der `Declare` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6ac90-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="6ac90-116">Projekt-verweisen, an dem externe Objekte, z. B. Objekte, die in Assemblys, Visual Basic-Projekte zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="6ac90-116">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="6ac90-117">Die `Imports` Anweisung wird verwendet, um den Zugriff auf die Projektverweise vereinfachen, aber ermöglicht keinen Zugriff auf diese Objekte.</span><span class="sxs-lookup"><span data-stu-id="6ac90-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="6ac90-118">Die `Declare` -Anweisung verwendet, um einen Verweis auf eine externe Prozedur in einer Dynamic Link Library (DLL) zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="6ac90-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="6ac90-119">Using-Aliase mit der Importanweisung</span><span class="sxs-lookup"><span data-stu-id="6ac90-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="6ac90-120">Die `Imports` Anweisung erleichtert es, Methoden der Klassen für den Datenzugriff durch den Wegfall um explizit die vollqualifizierten Namen von verweisen.</span><span class="sxs-lookup"><span data-stu-id="6ac90-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="6ac90-121">Aliase können Sie nur einen Teil eines Namespace einen aussagekräftigeren Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6ac90-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="6ac90-122">Beispielsweise ist der Wagenrücklauf/Zeilenvorschub Sequenz, die bewirkt, dass ein einzelnes Stück Text auf mehrere Zeilen angezeigt werden Teil der <xref:Microsoft.VisualBasic.ControlChars> -Modul in die <xref:Microsoft.VisualBasic?displayProperty=nameWithType> Namespace.</span><span class="sxs-lookup"><span data-stu-id="6ac90-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="6ac90-123">Um diese Konstante in einem Programm ohne Alias verwenden, müssen Sie den folgenden Code eingeben:</span><span class="sxs-lookup"><span data-stu-id="6ac90-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 <span data-ttu-id="6ac90-124">`Imports` Anweisungen muss immer die ersten Zeilen, die unmittelbar nach einem `Option` Anweisungen in einem Modul.</span><span class="sxs-lookup"><span data-stu-id="6ac90-124">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="6ac90-125">Das folgende Codefragment zeigt, wie zum Importieren und weisen Sie einen Alias für die <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> Modul:</span><span class="sxs-lookup"><span data-stu-id="6ac90-125">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 <span data-ttu-id="6ac90-126">Zukünftige Verweise für diesen Namespace können wesentlich kürzer sein:</span><span class="sxs-lookup"><span data-stu-id="6ac90-126">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 <span data-ttu-id="6ac90-127">Wenn ein `Imports` -Anweisung keinen Aliasnamen, die in den importierten Namespace definierten Elemente in das Modul ohne Qualifikation verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6ac90-127">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="6ac90-128">Wenn der Aliasname angegeben wird, muss sie für Namen, die in diesem Namespace enthaltenen als Qualifizierer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ac90-128">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac90-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ac90-129">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="6ac90-130">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6ac90-130">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="6ac90-131">Assemblys und der globale Assemblycache</span><span class="sxs-lookup"><span data-stu-id="6ac90-131">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [<span data-ttu-id="6ac90-132">Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="6ac90-132">How to: Create and Use Assemblies Using the Command Line</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
- [<span data-ttu-id="6ac90-133">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="6ac90-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
