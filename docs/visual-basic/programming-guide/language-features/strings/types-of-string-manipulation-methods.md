---
title: Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 11903e067c064f129ecd2df80244edb6741c73be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="1cbf8-102">Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cbf8-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="1cbf8-103">Es gibt verschiedene Möglichkeiten, analysieren und Bearbeiten von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="1cbf8-104">Einige der Methoden sind Teil der Sprache Visual Basic und andere sind Bestandteil der `String` Klasse.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="1cbf8-105">Sprache Visual Basic und .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1cbf8-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="1cbf8-106">Visual Basic-Methoden werden als inhärenten Funktionen der Sprache verwendet.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="1cbf8-107">Sie können ohne Qualifizierung in Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="1cbf8-108">Das folgende Beispiel zeigt die typische Verwendung eines Visual Basic zeichenfolgenbearbeitung Befehls:</span><span class="sxs-lookup"><span data-stu-id="1cbf8-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 <span data-ttu-id="1cbf8-109">In diesem Beispiel wird die `Mid` Funktion führt eine direkte Operation auf `aString` und weist den Wert `bString`.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="1cbf8-110">Eine Liste der Visual Basic-Zeichenfolgenbearbeitungsmethoden, finden Sie unter [Zeichenfolgenbearbeitung: Zusammenfassung](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="1cbf8-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="1cbf8-111">Freigegebener Methoden und Instanzenmethoden</span><span class="sxs-lookup"><span data-stu-id="1cbf8-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="1cbf8-112">Kann auch das Bearbeiten von Zeichenfolgen mit den Methoden von der `String` Klasse.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="1cbf8-113">Es gibt zwei Arten von Methoden in `String`: *freigegebenen* Methoden und *Instanz* Methoden.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="1cbf8-114">Shared-Methoden</span><span class="sxs-lookup"><span data-stu-id="1cbf8-114">Shared Methods</span></span>  
 <span data-ttu-id="1cbf8-115">Eine freigegebene Methode ist eine Methode, die aus resultiert der `String` selbst dar und erfordert eine Instanz dieser Klasse funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="1cbf8-116">Diese Methoden können mit dem Namen der Klasse qualifiziert werden (`String`) anstatt mit einer Instanz von der `String` Klasse.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="1cbf8-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1cbf8-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 <span data-ttu-id="1cbf8-118">Im vorherigen Beispiel der <xref:System.String.Copy%2A?displayProperty=nameWithType> Methode ist eine statische Methode nimmt einen Ausdruck als Argument fungiert es erhält und weist den resultierenden Wert an `bString`.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="1cbf8-119">Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="1cbf8-119">Instance Methods</span></span>  
 <span data-ttu-id="1cbf8-120">Instanzmethoden, entstammen, im Gegensatz dazu eine bestimmte Instanz des `String` und muss mit dem Instanznamen qualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="1cbf8-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1cbf8-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 <span data-ttu-id="1cbf8-122">In diesem Beispiel wird die <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode ist eine Methode der Instanz von `String` (d. h. `aString`).</span><span class="sxs-lookup"><span data-stu-id="1cbf8-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="1cbf8-123">Es führt eine Operation auf `aString` und weist diesen Wert `bString`.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="1cbf8-124">Weitere Informationen finden Sie in der Dokumentation für die <xref:System.String> Klasse.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cbf8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cbf8-125">See Also</span></span>  
 [<span data-ttu-id="1cbf8-126">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cbf8-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
