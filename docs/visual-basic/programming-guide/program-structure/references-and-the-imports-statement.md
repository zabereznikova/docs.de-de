---
title: Verweise und die Imports-Anweisung (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 051351c2fa0648de54bbfd36b1630ec1cd49d6f0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="a9243-102">Verweise und die Imports-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9243-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="a9243-103">Sie können externe Objekte verfügbar machen zu Ihrem Projekt durch Auswahl der **Verweis hinzufügen** Befehl der **Projekt** im Menü.</span><span class="sxs-lookup"><span data-stu-id="a9243-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="a9243-104">Verweise in Visual Basic können auf Assemblys verweisen, die entsprechen Typbibliotheken jedoch mehr Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a9243-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="a9243-105">Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a9243-105">The Imports Statement</span></span>  
 <span data-ttu-id="a9243-106">Assemblys umfassen einen oder mehrere Namespaces.</span><span class="sxs-lookup"><span data-stu-id="a9243-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="a9243-107">Wenn Sie einen Verweis auf eine Assembly hinzufügen, können Sie auch Hinzufügen einer `Imports` Anweisung, um ein Modul, das die Sichtbarkeit von dieser Assembly Namespaces innerhalb des Moduls gesteuert.</span><span class="sxs-lookup"><span data-stu-id="a9243-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="a9243-108">Die `Imports` Anweisung stellt einen Kontextbereich, die nur den Teil des Namespaces erforderlich, geben Sie einen eindeutigen Verweis verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="a9243-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="a9243-109">Die `Imports` Anweisung hat folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="a9243-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="a9243-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="a9243-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="a9243-111">`Aliasname` bezieht sich auf einen kurzen Namen, den Sie innerhalb des Codes verwenden können, um auf einen importierten Namespace zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="a9243-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="a9243-112">`Namespace` ist ein Namespace ist verfügbar, entweder durch einen Projektverweis, durch eine Definition innerhalb des Projekts oder durch einen vorherigen `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a9243-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="a9243-113">Ein Modul kann eine beliebige Anzahl von enthalten `Imports` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="a9243-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="a9243-114">Müssen sie nach allen stehen `Option` Anweisungen, falls vorhanden, jedoch vor jedem anderen Code.</span><span class="sxs-lookup"><span data-stu-id="a9243-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9243-115">Verwechseln Sie nicht die Projektverweise mit der `Imports` Anweisung oder der `Declare` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a9243-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="a9243-116">Projektverweise stellen externe Objekte, z. B. Objekte in Assemblys, Visual Basic-Projekte zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a9243-116">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="a9243-117">Die `Imports` -Anweisung wird verwendet, um den Zugriff auf Projektverweise vereinfachen, jedoch keinen Zugriff auf diese Objekte.</span><span class="sxs-lookup"><span data-stu-id="a9243-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="a9243-118">Die `Declare` Anweisung wird verwendet, um einen Verweis auf eine externe Prozedur in einer Dynamic Link Library (DLL) zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a9243-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="a9243-119">Verwenden von Aliasen mit der Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a9243-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="a9243-120">Die `Imports` Anweisung erleichtert es Zugriff auf Methoden von Klassen durch den Wegfall um explizit die vollqualifizierten Namen von verweisen.</span><span class="sxs-lookup"><span data-stu-id="a9243-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="a9243-121">Aliase können Sie nur einen Teil eines Namespace einen benutzerfreundlicheren Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a9243-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="a9243-122">Beispielsweise ist der Wagenrücklauf/Zeilenvorschub Sequenz, die bewirkt, dass ein einzelnes Stück Text, der in mehreren Zeilen angezeigt werden Teil der <xref:Microsoft.VisualBasic.ControlChars> Modul in die <xref:Microsoft.VisualBasic?displayProperty=nameWithType> Namespace.</span><span class="sxs-lookup"><span data-stu-id="a9243-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="a9243-123">Um diese Konstante in einem Programm ohne Alias zu verwenden, müssten Sie den folgenden Code eingeben:</span><span class="sxs-lookup"><span data-stu-id="a9243-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 <span data-ttu-id="a9243-124">`Imports` Anweisungen muss immer die ersten Zeilen, die unmittelbar nach einem `Option` Anweisungen in einem Modul.</span><span class="sxs-lookup"><span data-stu-id="a9243-124">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="a9243-125">Das folgende Codefragment zeigt, wie zum Importieren und einen Alias Zuweisen der <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> Modul:</span><span class="sxs-lookup"><span data-stu-id="a9243-125">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 <span data-ttu-id="a9243-126">Zukünftige Verweise auf diesen Namespace können deutlich kürzer sein:</span><span class="sxs-lookup"><span data-stu-id="a9243-126">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 <span data-ttu-id="a9243-127">Wenn ein `Imports` -Anweisung keines Aliasnamens, in den importierten Namespace definierte Elementen können im Modul ohne Qualifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9243-127">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="a9243-128">Wenn der Aliasname angegeben wird, muss sie für Namen, die in diesem Namespace enthaltenen als Qualifizierer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9243-128">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9243-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9243-129">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ControlChars>  
 <xref:Microsoft.VisualBasic>  
   
 [<span data-ttu-id="a9243-130">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9243-130">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="a9243-131">Assemblys und der globale Assemblycache</span><span class="sxs-lookup"><span data-stu-id="a9243-131">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="a9243-132">Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="a9243-132">How to: Create and Use Assemblies Using the Command Line</span></span>](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [<span data-ttu-id="a9243-133">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="a9243-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
