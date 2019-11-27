---
title: Verschiedene Typen von Methoden zur Zeichenfolgenbearbeitung
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: a02278abfb71efb2f31f239a89a22ad1c8ee7a18
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346273"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="41a33-102">Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41a33-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="41a33-103">Es gibt verschiedene Möglichkeiten, ihre Zeichen folgen zu analysieren und zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="41a33-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="41a33-104">Einige der Methoden sind Teil der Visual Basic Sprache, andere sind in der `String`-Klasse enthalten.</span><span class="sxs-lookup"><span data-stu-id="41a33-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="41a33-105">Visual Basic Sprache und .NET Framework</span><span class="sxs-lookup"><span data-stu-id="41a33-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="41a33-106">Visual Basic Methoden werden als inhärente Funktionen der Sprache verwendet.</span><span class="sxs-lookup"><span data-stu-id="41a33-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="41a33-107">Sie können ohne Qualifizierung in Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="41a33-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="41a33-108">Das folgende Beispiel zeigt die typische Verwendung eines Befehls zur Zeichen folgen Bearbeitung (Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="41a33-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="41a33-109">In diesem Beispiel führt die `Mid`-Funktion einen direkten Vorgang auf `aString` aus und weist den Wert `bString`zu.</span><span class="sxs-lookup"><span data-stu-id="41a33-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="41a33-110">Eine Liste der Methoden zur Bearbeitung von Visual Basic Zeichen folgen finden Sie unter [Zusammenfassung der Zeichen folgen Bearbeitung](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="41a33-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="41a33-111">Freigegebene Methoden und Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="41a33-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="41a33-112">Sie können Zeichen folgen auch mit den Methoden der `String`-Klasse bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="41a33-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="41a33-113">Es gibt zwei Arten von Methoden in `String`: frei *gegebene* Methoden und *Instanzmethoden* .</span><span class="sxs-lookup"><span data-stu-id="41a33-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="41a33-114">Freigegebene Methoden</span><span class="sxs-lookup"><span data-stu-id="41a33-114">Shared Methods</span></span>  
 <span data-ttu-id="41a33-115">Eine freigegebene Methode ist eine Methode, die sich aus der `String` Klasse selbst ergibt und keine Instanz dieser Klasse erfordert.</span><span class="sxs-lookup"><span data-stu-id="41a33-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="41a33-116">Diese Methoden können mit dem Namen der Klasse (`String`) und nicht mit einer Instanz der `String` Klasse qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="41a33-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="41a33-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41a33-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="41a33-118">Im vorherigen Beispiel handelt es sich bei der <xref:System.String.Copy%2A?displayProperty=nameWithType>-Methode um eine statische Methode, die auf einen Ausdruck angewendet wird, den Sie erhält, und der sich ergebende Wert `bString`zuweist.</span><span class="sxs-lookup"><span data-stu-id="41a33-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="41a33-119">Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="41a33-119">Instance Methods</span></span>  
 <span data-ttu-id="41a33-120">Instanzmethoden werden im Gegensatz zu einer bestimmten Instanz von `String` und müssen mit dem Instanznamen qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="41a33-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="41a33-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41a33-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="41a33-122">In diesem Beispiel ist die <xref:System.String.Substring%2A?displayProperty=nameWithType>-Methode eine Methode der-Instanz `String` (d. h. `aString`).</span><span class="sxs-lookup"><span data-stu-id="41a33-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="41a33-123">Er führt einen Vorgang auf `aString` aus und weist diesen Wert `bString`zu.</span><span class="sxs-lookup"><span data-stu-id="41a33-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="41a33-124">Weitere Informationen finden Sie in der Dokumentation für die <xref:System.String>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="41a33-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a33-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41a33-125">See also</span></span>

- [<span data-ttu-id="41a33-126">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41a33-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
