---
title: Einschränkungen
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: abe4acd5850aa6065bf4f6fd41bc610ede7ad13f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097955"
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="8cf60-102">Beschränkungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8cf60-102">Visual Basic Limitations</span></span>

<span data-ttu-id="8cf60-103">Frühere Versionen von Visual Basic erzwungene Grenzen im Code, wie z. b. die Länge der Variablennamen, die Anzahl der zulässigen Variablen in Modulen und die Modulgröße.</span><span class="sxs-lookup"><span data-stu-id="8cf60-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="8cf60-104">In Visual Basic .net wurden diese Einschränkungen gelockert, sodass Sie mehr Freiheit beim Schreiben und anordnen Ihres Codes haben.</span><span class="sxs-lookup"><span data-stu-id="8cf60-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="8cf60-105">Die physischen Grenzwerte sind mehr für den Lauf Zeit Arbeitsspeicher als bei Überlegungen zur Kompilierzeit voneinander abhängig.</span><span class="sxs-lookup"><span data-stu-id="8cf60-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="8cf60-106">Wenn Sie vorsichtige Programmierverfahren verwenden und große Anwendungen in mehrere Klassen und Module aufteilen, besteht die Wahrscheinlichkeit, dass eine interne Visual Basic Einschränkung auftritt.</span><span class="sxs-lookup"><span data-stu-id="8cf60-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="8cf60-107">Im folgenden finden Sie einige Einschränkungen, die in Extremfällen auftreten können:</span><span class="sxs-lookup"><span data-stu-id="8cf60-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
- <span data-ttu-id="8cf60-108">**Länge des Namens.**</span><span class="sxs-lookup"><span data-stu-id="8cf60-108">**Name Length.**</span></span> <span data-ttu-id="8cf60-109">Es gibt eine maximale Anzahl von Zeichen für den Namen aller deklarierten Programmier Elemente.</span><span class="sxs-lookup"><span data-stu-id="8cf60-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="8cf60-110">Dieser Höchstwert gilt für eine gesamte Qualifikations Zeichenfolge, wenn der Elementname qualifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="8cf60-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="8cf60-111">Siehe [Declared Element Names](../language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="8cf60-111">See [Declared Element Names](../language-features/declared-elements/declared-element-names.md).</span></span>  
  
- <span data-ttu-id="8cf60-112">**Zeilenlänge.**</span><span class="sxs-lookup"><span data-stu-id="8cf60-112">**Line Length.**</span></span> <span data-ttu-id="8cf60-113">In einer physischen Zeile des Quellcodes sind maximal 65535 Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8cf60-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="8cf60-114">Die logische Quell Code Zeile kann länger sein, wenn Sie Zeilen Fortsetzungs Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8cf60-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="8cf60-115">Siehe Gewusst [wie: unterbrechen und Kombinieren von Anweisungen im Code](how-to-break-and-combine-statements-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="8cf60-115">See [How to: Break and Combine Statements in Code](how-to-break-and-combine-statements-in-code.md).</span></span>  
  
- <span data-ttu-id="8cf60-116">**Array Dimensionen.**</span><span class="sxs-lookup"><span data-stu-id="8cf60-116">**Array Dimensions.**</span></span> <span data-ttu-id="8cf60-117">Es gibt eine maximale Anzahl von Dimensionen, die Sie für ein Array deklarieren können.</span><span class="sxs-lookup"><span data-stu-id="8cf60-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="8cf60-118">Dies schränkt die Anzahl der Indizes ein, die Sie verwenden können, um ein Array Element anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8cf60-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="8cf60-119">Weitere Informationen finden Sie [unter Array Dimensionen in Visual Basic](../language-features/arrays/array-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="8cf60-119">See [Array Dimensions in Visual Basic](../language-features/arrays/array-dimensions.md).</span></span>  
  
- <span data-ttu-id="8cf60-120">**Zeichen folgen Länge.**</span><span class="sxs-lookup"><span data-stu-id="8cf60-120">**String Length.**</span></span> <span data-ttu-id="8cf60-121">Es gibt eine maximale Anzahl von Unicode-Zeichen, die Sie in einer einzelnen Zeichenfolge speichern können.</span><span class="sxs-lookup"><span data-stu-id="8cf60-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="8cf60-122">Siehe [String-Datentyp](../../language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="8cf60-122">See [String Data Type](../../language-reference/data-types/string-data-type.md).</span></span>  
  
- <span data-ttu-id="8cf60-123">**Länge der Umgebungs Zeichenfolge.**</span><span class="sxs-lookup"><span data-stu-id="8cf60-123">**Environment String Length.**</span></span> <span data-ttu-id="8cf60-124">Für jede Umgebungs Zeichenfolge, die als Befehlszeilenargument verwendet wird, sind maximal 32768 Zeichen zulässig.</span><span class="sxs-lookup"><span data-stu-id="8cf60-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="8cf60-125">Dies ist eine Einschränkung auf allen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="8cf60-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf60-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cf60-126">See also</span></span>

- [<span data-ttu-id="8cf60-127">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="8cf60-127">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="8cf60-128">Benennungskonventionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8cf60-128">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
