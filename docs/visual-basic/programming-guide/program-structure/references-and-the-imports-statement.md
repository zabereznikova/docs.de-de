---
title: Verweise und die Imports-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references, assembly
- namespaces, assemblies
- referencing assemblies
- Imports statement, referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4c6ce65005f84317c96a1124d609c46734d3cc66
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="5666c-102">Verweise und die Imports-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5666c-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="5666c-103">Sie können externe Objekte zur Verfügung stellen zu Ihrem Projekt durch Auswahl der **Verweis hinzufügen** Befehl die **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="5666c-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="5666c-104">Verweise in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] können auf Assemblys zeigen, die vergleichbar Typbibliotheken jedoch mehr Informationen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5666c-104">References in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="5666c-105">Die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5666c-105">The Imports Statement</span></span>  
 <span data-ttu-id="5666c-106">Assemblys umfassen einen oder mehrere Namespaces.</span><span class="sxs-lookup"><span data-stu-id="5666c-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="5666c-107">Wenn Sie einen Verweis auf eine Assembly hinzufügen, können Sie auch hinzufügen eine `Imports` Anweisung, um ein Modul, das die Sichtbarkeit der Switch-Namespaces innerhalb des Moduls steuert.</span><span class="sxs-lookup"><span data-stu-id="5666c-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="5666c-108">Die `Imports` -Anweisung stellt einen Kontextbereich, die nur den Teil eines eindeutigen Verweises zum Namespace verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="5666c-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="5666c-109">Die `Imports` Anweisung hat die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="5666c-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="5666c-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="5666c-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="5666c-111">`Aliasname`bezieht sich auf einen kurzen Namen, den Sie innerhalb des Codes verwenden können, um auf einen importierten Namespace zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="5666c-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="5666c-112">`Namespace`ist ein Namespace, die verfügbar sind, entweder durch einen Projektverweis, durch eine Definition innerhalb des Projekts oder durch eine vorherige `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5666c-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="5666c-113">Ein Modul kann eine beliebige Anzahl von enthalten `Imports` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="5666c-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="5666c-114">Müssen sie nach jedem erscheinen `Option` -Anweisungen, falls vorhanden, aber vor allem anderen Code.</span><span class="sxs-lookup"><span data-stu-id="5666c-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5666c-115">Verwechseln Sie nicht die Projektverweise mit den `Imports` Anweisung oder der `Declare` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5666c-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="5666c-116">Projektverweisen werden externe Objekte, z. B. Objekte in Assemblys, auf [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Projekte.</span><span class="sxs-lookup"><span data-stu-id="5666c-116">Project references make external objects, such as objects in assemblies, available to [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] projects.</span></span> <span data-ttu-id="5666c-117">Die `Imports` Anweisung wird verwendet, um den Zugriff auf Projektverweise zu vereinfachen, bietet jedoch keinen Zugriff auf diese Objekte.</span><span class="sxs-lookup"><span data-stu-id="5666c-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="5666c-118">Die `Declare` -Anweisung verwendet, um einen Verweis auf eine externe Prozedur in einer Dynamic Link Library (DLL) zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="5666c-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="5666c-119">Verwenden von Aliasen mit der Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5666c-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="5666c-120">Die `Imports` -Anweisung erleichtert Zugriff auf Methoden von Klassen durch den Wegfall um explizit die vollqualifizierten Namen von verweisen.</span><span class="sxs-lookup"><span data-stu-id="5666c-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="5666c-121">Aliase können Sie nur einen Teil eines Namespace einen benutzerfreundlicheren Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5666c-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="5666c-122">Beispielsweise ist der Wagenrücklauf/Zeilenvorschub Sequenz, die bewirkt, dass ein einzelnes Stück Text, der in mehreren Zeilen angezeigt werden Teil der <xref:Microsoft.VisualBasic.ControlChars>-Modul in die <xref:Microsoft.VisualBasic?displayProperty=fullName>Namespace.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="5666c-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="5666c-123">Um diese Konstante in einem Programm ohne Alias verwenden, müssen Sie den folgenden Code eingeben:</span><span class="sxs-lookup"><span data-stu-id="5666c-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 <span data-ttu-id="5666c-124">[!code-vb[VbVbalrApplication&3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5666c-124">[!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="5666c-125">`Imports`Anweisungen muss immer die ersten Zeilen direkt nach einem `Option` Anweisungen in einem Modul.</span><span class="sxs-lookup"><span data-stu-id="5666c-125">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="5666c-126">Das folgende Codefragment zeigt, wie zum Importieren und Zuweisen eines Alias für die <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>Modul:</xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5666c-126">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName> module:</span></span>  
  
 <span data-ttu-id="5666c-127">[!code-vb[VbVbalrApplication&4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5666c-127">[!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]</span></span>  
  
 <span data-ttu-id="5666c-128">Zukünftige Verweise auf diesen Namespace können wesentlich kürzer sein:</span><span class="sxs-lookup"><span data-stu-id="5666c-128">Future references to this namespace can be considerably shorter:</span></span>  
  
 <span data-ttu-id="5666c-129">[!code-vb[VbVbalrApplication&5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="5666c-129">[!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="5666c-130">Wenn eine `Imports` -Anweisung keinen Aliasnamen, den importierten Namespace definierte Elemente ohne Qualifikation im Modul verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5666c-130">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="5666c-131">Wenn der Aliasname angegeben ist, muss er für Namen in diesem Namespace enthaltenen als Qualifizierer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5666c-131">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5666c-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5666c-132">See Also</span></span>  
 <span data-ttu-id="5666c-133"><xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="5666c-133"><xref:Microsoft.VisualBasic.ControlChars></span></span>   
 <span data-ttu-id="5666c-134"><xref:Microsoft.VisualBasic></xref:Microsoft.VisualBasic></span><span class="sxs-lookup"><span data-stu-id="5666c-134"><xref:Microsoft.VisualBasic></span></span>   
<span data-ttu-id="5666c-135"> [NIB: Vorgehensweise: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="5666c-135"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="5666c-136"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="5666c-136"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="5666c-137"> [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="5666c-137"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="5666c-138"> [Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span><span class="sxs-lookup"><span data-stu-id="5666c-138"> [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span></span>  
<span data-ttu-id="5666c-139"> [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span><span class="sxs-lookup"><span data-stu-id="5666c-139"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span></span>
