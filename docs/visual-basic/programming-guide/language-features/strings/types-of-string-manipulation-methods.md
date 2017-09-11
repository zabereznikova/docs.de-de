---
title: Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic | Microsoft-Dokumentation
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
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
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
ms.openlocfilehash: 9c63ad0931ae2f3760576a792795b9fe0ab6a409
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="5250d-102">Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5250d-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="5250d-103">Es gibt verschiedene Zeichenfolgen zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="5250d-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="5250d-104">Einige Methoden sind Teil der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Sprache und andere sind Bestandteil der `String` Klasse.</span><span class="sxs-lookup"><span data-stu-id="5250d-104">Some of the methods are a part of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="5250d-105">Visual Basic-Sprache und .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5250d-105">Visual Basic Language and the .NET Framework</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="5250d-106">Methoden werden als inhärente Funktionen der Sprache verwendet.</span><span class="sxs-lookup"><span data-stu-id="5250d-106"> methods are used as inherent functions of the language.</span></span> <span data-ttu-id="5250d-107">Sie können ohne Qualifizierung in Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5250d-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="5250d-108">Das folgende Beispiel zeigt die standardmäßige Verwendung für eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Zeichenfolgenmanipulation Befehl:</span><span class="sxs-lookup"><span data-stu-id="5250d-108">The following example shows typical use of a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string-manipulation command:</span></span>  
  
 <span data-ttu-id="5250d-109">[!code-vb[VbVbalrStrings&#44;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5250d-109">[!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="5250d-110">In diesem Beispiel die `Mid` Funktion führt eine direkte Operation auf `aString` und weist den Wert `bString`.</span><span class="sxs-lookup"><span data-stu-id="5250d-110">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="5250d-111">Eine Liste der Visual Basic-Zeichenfolgenbearbeitungsmethoden, finden Sie unter [Zeichenfolgenbearbeitung: Zusammenfassung](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="5250d-111">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="5250d-112">Freigegebene Methoden und Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="5250d-112">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="5250d-113">Kann auch das Bearbeiten von Zeichenfolgen mit den Methoden von der `String` Klasse.</span><span class="sxs-lookup"><span data-stu-id="5250d-113">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="5250d-114">Es gibt zwei Arten von Methoden in `String`: *freigegebenen* Methoden und *Instanz* Methoden.</span><span class="sxs-lookup"><span data-stu-id="5250d-114">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="5250d-115">Freigegebene Methoden</span><span class="sxs-lookup"><span data-stu-id="5250d-115">Shared Methods</span></span>  
 <span data-ttu-id="5250d-116">Eine freigegebene Methode ist eine Methode, die vom herrührt der `String` selbst dar und erfordert eine Instanz der Klasse.</span><span class="sxs-lookup"><span data-stu-id="5250d-116">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="5250d-117">Diese Methoden können mit dem Namen der Klasse qualifiziert werden (`String`) anstatt mit einer Instanz von der `String` Klasse.</span><span class="sxs-lookup"><span data-stu-id="5250d-117">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="5250d-118">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5250d-118">For example:</span></span>  
  
 <span data-ttu-id="5250d-119">[!code-vb[VbVbalrStrings&#45;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5250d-119">[!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="5250d-120">Im vorherigen Beispiel ist die <xref:System.String.Copy%2A?displayProperty=fullName>Methode ist eine statische Methode, die auf einen Ausdruck angewendet wird und weist den resultierenden Wert `bString`.</xref:System.String.Copy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5250d-120">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=fullName> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="5250d-121">Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="5250d-121">Instance Methods</span></span>  
 <span data-ttu-id="5250d-122">Instanzmethoden, im Gegensatz dazu entstammen einer bestimmten Instanz von `String` und müssen mit dem Instanznamen qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="5250d-122">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="5250d-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5250d-123">For example:</span></span>  
  
 <span data-ttu-id="5250d-124">[!code-vb[VbVbalrStrings&#46;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="5250d-124">[!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="5250d-125">In diesem Beispiel die <xref:System.String.Substring%2A?displayProperty=fullName>Methode ist eine Methode der Instanz von `String` (d. h. `aString`).</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5250d-125">In this example, the <xref:System.String.Substring%2A?displayProperty=fullName> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="5250d-126">Sie führt eine Operation auf `aString` und weist diesen Wert `bString`.</span><span class="sxs-lookup"><span data-stu-id="5250d-126">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="5250d-127">Weitere Informationen finden Sie in der Dokumentation für die <xref:System.String>Klasse.</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="5250d-127">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5250d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5250d-128">See Also</span></span>  
 [<span data-ttu-id="5250d-129">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5250d-129">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
