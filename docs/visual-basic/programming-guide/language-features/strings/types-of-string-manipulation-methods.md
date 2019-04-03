---
title: Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 44eb101ebdfeb316958a659107190ef1fc84df44
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821152"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="c1e35-102">Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1e35-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="c1e35-103">Es gibt mehrere Möglichkeiten, um zu analysieren und Bearbeiten von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="c1e35-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="c1e35-104">Einige der Methoden sind Teil der Visual Basic-Sprache und andere sind Bestandteil der `String` Klasse.</span><span class="sxs-lookup"><span data-stu-id="c1e35-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="c1e35-105">Visual Basic-Sprache und .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c1e35-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="c1e35-106">Visual Basic-Methoden werden als enthaltenen Funktionen der Sprache verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1e35-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="c1e35-107">Sie können ohne Qualifikation in Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1e35-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="c1e35-108">Das folgende Beispiel zeigt die typische Verwendung von einem Visual Basic-zeichenfolgenbearbeitung Befehl:</span><span class="sxs-lookup"><span data-stu-id="c1e35-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="c1e35-109">In diesem Beispiel die `Mid` Funktion führt eine direkte Operation für `aString` und weist den Wert `bString`.</span><span class="sxs-lookup"><span data-stu-id="c1e35-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="c1e35-110">Eine Liste der Methoden zur zeichenfolgenbearbeitung Visual Basic, finden Sie unter [Zeichenfolgenbearbeitung: Zusammenfassung](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="c1e35-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="c1e35-111">Freigegebener Methoden und Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="c1e35-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="c1e35-112">Kann auch das Bearbeiten von Zeichenfolgen mit den Methoden der `String` Klasse.</span><span class="sxs-lookup"><span data-stu-id="c1e35-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="c1e35-113">Es gibt zwei Arten von Methoden in `String`: *freigegebenen* Methoden und *Instanz* Methoden.</span><span class="sxs-lookup"><span data-stu-id="c1e35-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="c1e35-114">Freigegebene Methoden</span><span class="sxs-lookup"><span data-stu-id="c1e35-114">Shared Methods</span></span>  
 <span data-ttu-id="c1e35-115">Eine freigegebene Methode ist eine Methode, die vom herrührt der `String` selbst und erfordert eine Instanz dieser Klasse funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="c1e35-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="c1e35-116">Diese Methoden können mit dem Namen der Klasse qualifiziert sein (`String`) statt mit einer Instanz von der `String` Klasse.</span><span class="sxs-lookup"><span data-stu-id="c1e35-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="c1e35-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c1e35-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="c1e35-118">Im vorherigen Beispiel das <xref:System.String.Copy%2A?displayProperty=nameWithType> Methode ist eine statische Methode, die auf einen Ausdruck angewendet wird und weist den resultierenden Wert an `bString`.</span><span class="sxs-lookup"><span data-stu-id="c1e35-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="c1e35-119">Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="c1e35-119">Instance Methods</span></span>  
 <span data-ttu-id="c1e35-120">Stem-Instanzenmethoden, im Gegensatz dazu, von einer bestimmten Instanz von `String` und muss mit dem Namen qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="c1e35-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="c1e35-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c1e35-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="c1e35-122">In diesem Beispiel die <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode ist eine Methode der Instanz von `String` (d. h. `aString`).</span><span class="sxs-lookup"><span data-stu-id="c1e35-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="c1e35-123">Er führt einen Vorgang auf `aString` und weist diesen Wert `bString`.</span><span class="sxs-lookup"><span data-stu-id="c1e35-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="c1e35-124">Weitere Informationen finden Sie in der Dokumentation für die <xref:System.String> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c1e35-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1e35-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1e35-125">See also</span></span>

- [<span data-ttu-id="c1e35-126">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1e35-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
