---
title: "Beschränkungen in Visual Basic | Microsoft-Dokumentation"
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
- limits
- limitations, Visual Basic
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
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
ms.openlocfilehash: a3bd551ade2f0c55cd943cfbd353b09dfede4063
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-limitations"></a><span data-ttu-id="13879-102">Beschränkungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13879-102">Visual Basic Limitations</span></span>
<span data-ttu-id="13879-103">Frühere Versionen von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erzwungen Grenzen in Code, z. B. die Länge der Namen von Variablen, die zulässige Anzahl von Variablen in Modulen und Modulgröße.</span><span class="sxs-lookup"><span data-stu-id="13879-103">Earlier versions of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="13879-104">In [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], wurden haben diese Einschränkungen gelockert, was Ihnen mehr Freiheit beim Schreiben und Anordnen von Code.</span><span class="sxs-lookup"><span data-stu-id="13879-104">In [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="13879-105">Physische Grenzen hängen eher auf die Laufzeit Arbeitsspeicher als Gesichtspunkten während der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="13879-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="13879-106">Wenn Sie angemessen Programmierverfahren verwenden und teilen Sie umfangreiche in mehrere Klassen und Module, es ist sehr geringe Chance, beim Auftreten eines internen [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="13879-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] limitation.</span></span>  
  
 <span data-ttu-id="13879-107">Es folgen einige Einschränkungen, die in extremen Fällen auftreten:</span><span class="sxs-lookup"><span data-stu-id="13879-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="13879-108">**Länge des Namens.**</span><span class="sxs-lookup"><span data-stu-id="13879-108">**Name Length.**</span></span> <span data-ttu-id="13879-109">Es gibt eine maximale Anzahl von Zeichen für den Namen jedes deklarierten Programmierelements.</span><span class="sxs-lookup"><span data-stu-id="13879-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="13879-110">Dieser Maximalwert gilt für eine gesamte Qualifizierungspfad, wenn der Elementname qualifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="13879-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="13879-111">Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="13879-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="13879-112">**Zeilenlänge.**</span><span class="sxs-lookup"><span data-stu-id="13879-112">**Line Length.**</span></span> <span data-ttu-id="13879-113">Es ist maximal 65.535 Zeichen in eine physikalische Zeile von Quellcode.</span><span class="sxs-lookup"><span data-stu-id="13879-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="13879-114">Die logische Quellcodezeile kann länger, wenn Sie das Zeilenfortsetzungszeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="13879-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="13879-115">Finden Sie unter [wie: umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="13879-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="13879-116">**Dimensionen des Arrays.**</span><span class="sxs-lookup"><span data-stu-id="13879-116">**Array Dimensions.**</span></span> <span data-ttu-id="13879-117">Es wird eine maximale Anzahl von Dimensionen, die Sie für ein Array deklarieren können.</span><span class="sxs-lookup"><span data-stu-id="13879-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="13879-118">Auf diese Weise wie viele Indizes, die Sie verwenden können, auf ein Arrayelement angeben.</span><span class="sxs-lookup"><span data-stu-id="13879-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="13879-119">Finden Sie unter [Array-Dimensionen in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="13879-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="13879-120">**Länge der Zeichenfolge.**</span><span class="sxs-lookup"><span data-stu-id="13879-120">**String Length.**</span></span> <span data-ttu-id="13879-121">Es gibt eine maximale Anzahl von Unicode-Zeichen, die in einer einzelnen Zeichenfolge gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="13879-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="13879-122">Finden Sie unter [String-Datentyp](../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="13879-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="13879-123">**Zeichenfolgenlänge Umgebung.**</span><span class="sxs-lookup"><span data-stu-id="13879-123">**Environment String Length.**</span></span> <span data-ttu-id="13879-124">Es gibt ein Maximum von Umgebungszeichenfolgen als Befehlszeilenargument verwendet 32768 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="13879-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="13879-125">Dies ist eine Einschränkung auf allen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="13879-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13879-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13879-126">See Also</span></span>  
 <span data-ttu-id="13879-127">[Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="13879-127">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="13879-128"> [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)</span><span class="sxs-lookup"><span data-stu-id="13879-128"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)</span></span>
