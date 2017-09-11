---
title: "Gewusst wie: Definieren eines Parameters für eine Prozedur (Visual Basic) | Microsoft-Dokumentation"
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
- procedure parameters, defining data types for
- procedures, parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters, defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
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
ms.openlocfilehash: 5a29bab1c18920d293c51d83d4d8cffdcefe936c
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="626c3-102">Gewusst wie: Definieren eines Parameters für eine Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="626c3-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="626c3-103">Ein *Parameter* kann der aufrufenden Code einen Wert an die Prozedur übergeben werden, wenn er aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="626c3-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="626c3-104">Sie deklarieren jeden Parameter für eine Prozedur, wie Sie eine Variable deklarieren, die den Namen und den Datentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="626c3-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="626c3-105">Sie auch angeben, den Mechanismus übergeben, und gibt an, ob der Parameter optional ist.</span><span class="sxs-lookup"><span data-stu-id="626c3-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="626c3-106">Weitere Informationen finden Sie unter [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="626c3-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="626c3-107">Definieren Sie einen Prozedurparameter</span><span class="sxs-lookup"><span data-stu-id="626c3-107">To define a procedure parameter</span></span>  
  
1.  <span data-ttu-id="626c3-108">Fügen Sie in der Prozedurdeklaration den Parameternamen, die Prozedur die Parameterliste, trennen es von anderen Parametern durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="626c3-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2.  <span data-ttu-id="626c3-109">Entscheiden Sie, den Datentyp des Parameters.</span><span class="sxs-lookup"><span data-stu-id="626c3-109">Decide the data type of the parameter.</span></span>  
  
3.  <span data-ttu-id="626c3-110">Führen Sie den Parameternamen ein `As` -Klausel, um den Datentyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="626c3-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4.  <span data-ttu-id="626c3-111">Entscheiden Sie, die Übergabemechanismus für den Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="626c3-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="626c3-112">Normalerweise übergeben Sie Parameter als Wert, es sei denn, Sie möchten, dass das Verfahren, um den Wert in den aufrufenden Code ändern können.</span><span class="sxs-lookup"><span data-stu-id="626c3-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5.  <span data-ttu-id="626c3-113">Vor den Parameternamen stehen [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) an die Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="626c3-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="626c3-114">Weitere Informationen finden Sie unter [Unterschiede zwischen übergeben von Argumenten nach Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="626c3-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6.  <span data-ttu-id="626c3-115">Wenn der Parameter optional ist, vor der Übergabemechanismus mit [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) , und führen Sie den Datentyp des Parameters mit einem Gleichheitszeichen (`=`) und einen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="626c3-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="626c3-116">Im folgende Beispiel wird die Gliederung definiert eine `Sub` -Prozedur mit drei Parametern.</span><span class="sxs-lookup"><span data-stu-id="626c3-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="626c3-117">Die ersten beiden sind erforderlich, und der dritte ist optional.</span><span class="sxs-lookup"><span data-stu-id="626c3-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="626c3-118">Die Parameterdeklarationen werden in der Parameterliste durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="626c3-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     <span data-ttu-id="626c3-119">[!code-vb[VbVbcnProcedures&33;](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="626c3-119">[!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="626c3-120">Der erste Parameter nimmt ein `customer` -Objekt, und `updateCustomer` können direkt aktualisieren, die Variable übergeben `c` , da das Argument übergeben wird [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span><span class="sxs-lookup"><span data-stu-id="626c3-120">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="626c3-121">Das Verfahren kann die Werte der beiden letzten Argumente nicht ändern, da sie übergeben werden [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="626c3-121">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="626c3-122">Wenn der aufrufende Code keinen Wert für bereitstellt der `level` Parameter [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] wird auf den Standardwert 0.</span><span class="sxs-lookup"><span data-stu-id="626c3-122">If the calling code does not supply a value for the `level` parameter, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="626c3-123">Wenn die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `Off`, `As` -Klausel ist optional, wenn Sie einen Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="626c3-123">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="626c3-124">Allerdings verwendet einen Parameter einer `As` -Klausel, diese müssen verwenden.</span><span class="sxs-lookup"><span data-stu-id="626c3-124">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="626c3-125">Wenn der Schalter für die Typprüfung ist `On`, die `As` -Klausel ist für jede Parameterdefinition erforderlich.</span><span class="sxs-lookup"><span data-stu-id="626c3-125">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="626c3-126">Die Angabe von Datentypen für alle Programmierelemente wird als bezeichnet *starke Typisierung*.</span><span class="sxs-lookup"><span data-stu-id="626c3-126">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="626c3-127">Wenn Sie die Option `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erzwingt eine starke Typisierung.</span><span class="sxs-lookup"><span data-stu-id="626c3-127">When you set `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enforces strong typing.</span></span> <span data-ttu-id="626c3-128">Dies wird, aus den folgenden Gründen empfohlen:</span><span class="sxs-lookup"><span data-stu-id="626c3-128">This is strongly recommended, for the following reasons:</span></span>  
  
    -   <span data-ttu-id="626c3-129">Sie können IntelliSense-Unterstützung für die Variablen und Parameter.</span><span class="sxs-lookup"><span data-stu-id="626c3-129">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="626c3-130">Dadurch können Sie die Eigenschaften und andere Member zu sehen, wie Sie in Ihrem Code eingeben.</span><span class="sxs-lookup"><span data-stu-id="626c3-130">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    -   <span data-ttu-id="626c3-131">Sie können den Compiler an, zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="626c3-131">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="626c3-132">Auf diese Weise catch-Anweisungen, die zur Laufzeit aufgrund von Fehlern, z. B. Überlauf fehlschlagen können.</span><span class="sxs-lookup"><span data-stu-id="626c3-132">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="626c3-133">Es fängt auch Aufrufe von Methoden für Objekte, die diese nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="626c3-133">It also catches calls to methods on objects that do not support them.</span></span>  
  
    -   <span data-ttu-id="626c3-134">Schnellere Ausführung des Codes führt.</span><span class="sxs-lookup"><span data-stu-id="626c3-134">It results in faster execution of your code.</span></span> <span data-ttu-id="626c3-135">Ein Grund hierfür ist, die, wenn Sie nicht für ein Programmierelement einen Datentyp angeben der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler weist es den `Object` Typ.</span><span class="sxs-lookup"><span data-stu-id="626c3-135">One reason for this is that if you do not specify a data type for a programming element, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler assigns it the `Object` type.</span></span> <span data-ttu-id="626c3-136">Der kompilierte Code möglicherweise Konvertieren zwischen `Object` und anderen Datentypen, die Leistung reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="626c3-136">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="626c3-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="626c3-137">See Also</span></span>  
 <span data-ttu-id="626c3-138">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="626c3-138">[Procedures](./index.md) </span></span>  
<span data-ttu-id="626c3-139"> [Sub-Prozeduren](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="626c3-139"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="626c3-140"> [Function-Prozeduren](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="626c3-140"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="626c3-141"> [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="626c3-141"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="626c3-142"> [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="626c3-142"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="626c3-143"> [Rekursive Prozeduren](./recursive-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="626c3-143"> [Recursive Procedures](./recursive-procedures.md) </span></span>  
<span data-ttu-id="626c3-144"> [Prozedurüberladung](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="626c3-144"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="626c3-145"> [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="626c3-145"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="626c3-146"> [Objektorientierte Programmierung](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span><span class="sxs-lookup"><span data-stu-id="626c3-146"> [Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span></span>
