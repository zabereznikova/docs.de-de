---
title: "Beschränkungen in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 97a2e162b9f1a673fbe805a5d2ef1421cd423a4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="9f389-102">Beschränkungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f389-102">Visual Basic Limitations</span></span>
<span data-ttu-id="9f389-103">Frühere Versionen von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] erzwungen Grenzen in Code, z. B. die Länge der Variablennamen, die Anzahl der Variablen in Modulen und Modulgröße zulässig.</span><span class="sxs-lookup"><span data-stu-id="9f389-103">Earlier versions of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="9f389-104">In Visual Basic .NET und wurden diese Einschränkungen gelockert wurde und Sie haben mehr Freiheit beim Schreiben und Einfügen von Code.</span><span class="sxs-lookup"><span data-stu-id="9f389-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="9f389-105">Physische Grenzen sind mehr auf die Laufzeit Arbeitsspeicher als Zeitpunkt der Kompilierung Leistungsaspekten abhängig.</span><span class="sxs-lookup"><span data-stu-id="9f389-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="9f389-106">Wenn umsichtige Programmierstil hin, und Sie große Anwendungen in mehrere Klassen und Module unterteilen, dann ist es sehr geringer Wahrscheinlichkeit eine interne [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="9f389-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] limitation.</span></span>  
  
 <span data-ttu-id="9f389-107">Es folgen einige Einschränkungen, die Sie in extremen Fällen auftreten:</span><span class="sxs-lookup"><span data-stu-id="9f389-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="9f389-108">**Länge des Namens.**</span><span class="sxs-lookup"><span data-stu-id="9f389-108">**Name Length.**</span></span> <span data-ttu-id="9f389-109">Es wird eine maximale Anzahl von Zeichen für den Namen jedes deklarierten Programmierelements.</span><span class="sxs-lookup"><span data-stu-id="9f389-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="9f389-110">Dieser Maximalwert gilt für eine gesamte Qualifizierungspfad auf, wenn der Elementname qualifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="9f389-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="9f389-111">Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="9f389-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="9f389-112">**Zeilenlänge.**</span><span class="sxs-lookup"><span data-stu-id="9f389-112">**Line Length.**</span></span> <span data-ttu-id="9f389-113">Es gibt ein Maximum von 65535 Zeichen in eine physische Zeile des Quellcodes.</span><span class="sxs-lookup"><span data-stu-id="9f389-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="9f389-114">Die logische Quellcodezeile kann mehr Zeit, wenn Sie das Zeilenfortsetzungszeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f389-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="9f389-115">Finden Sie unter [wie: umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="9f389-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="9f389-116">**Dimensionen des Arrays.**</span><span class="sxs-lookup"><span data-stu-id="9f389-116">**Array Dimensions.**</span></span> <span data-ttu-id="9f389-117">Es wird eine maximale Anzahl von Dimensionen, die Sie für ein Array zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="9f389-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="9f389-118">Dies schränkt wie viele Indizes, die Sie verwenden können, um ein Arrayelement anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9f389-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="9f389-119">Finden Sie unter [Dimensionen in Visual Basic-Array](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="9f389-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="9f389-120">**Länge der Zeichenfolge.**</span><span class="sxs-lookup"><span data-stu-id="9f389-120">**String Length.**</span></span> <span data-ttu-id="9f389-121">Es wird eine maximale Anzahl von Unicode-Zeichen, die in einer einzelnen Zeichenfolge gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="9f389-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="9f389-122">Finden Sie unter [Zeichenfolgendatentyp](../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="9f389-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="9f389-123">**Umgebung String-length-Funktion.**</span><span class="sxs-lookup"><span data-stu-id="9f389-123">**Environment String Length.**</span></span> <span data-ttu-id="9f389-124">Es ist ein Maximum von 32768 Zeichen für eine beliebige Umgebungszeichenfolge als Befehlszeilenargument verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f389-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="9f389-125">Dies ist eine Einschränkung auf allen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="9f389-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f389-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f389-126">See Also</span></span>  
 [<span data-ttu-id="9f389-127">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="9f389-127">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="9f389-128">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="9f389-128">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
