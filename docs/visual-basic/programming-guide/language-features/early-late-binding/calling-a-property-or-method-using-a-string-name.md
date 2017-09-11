---
title: Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen (Visual Basic) | Microsoft-Dokumentation
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
- passing operators
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls, strings
- methods [Visual Basic], calling with string names
- calling methods, string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: 17
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
ms.openlocfilehash: 6de5e655b3d4d42283b81507d7f08e0eb0b9424d
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="d74e3-102">Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d74e3-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="d74e3-103">In den meisten Fällen können Sie die Eigenschaften und Methoden eines Objekts zur Entwurfszeit zu ermitteln und Code schreiben, um sie zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="d74e3-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="d74e3-104">Jedoch in einigen Fällen Sie möglicherweise nicht über Eigenschaften und Methoden eines Objekts im Voraus wissen, oder Sie sollten nur die Flexibilität, dass einen Benutzer für das Festlegen von Eigenschaften oder Methoden zur Laufzeit ausführen.</span><span class="sxs-lookup"><span data-stu-id="d74e3-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="d74e3-105">CallByName-Funktion</span><span class="sxs-lookup"><span data-stu-id="d74e3-105">CallByName Function</span></span>  
 <span data-ttu-id="d74e3-106">Betrachten Sie z. B. eine Clientanwendung, die vom Benutzer eingegeben wird, übergeben Sie einen Operator für eine COM-Komponente Ausdrücke auswertet.</span><span class="sxs-lookup"><span data-stu-id="d74e3-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="d74e3-107">Angenommen Sie, Sie werden ständig neue Funktionen hinzufügen, auf die Komponente, die neue Operatoren benötigen.</span><span class="sxs-lookup"><span data-stu-id="d74e3-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="d74e3-108">Wenn Sie standard für den Objektzugriff verwenden, müssen Sie erneut kompilieren und verteilen die Client-Anwendung, die neuen Operatoren verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d74e3-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="d74e3-109">Um dies zu vermeiden, können Sie die `CallByName` Funktion, um die neuen Operatoren als Zeichenfolge übergeben, ohne die Anwendung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d74e3-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="d74e3-110">Die `CallByName` -Funktion können Sie eine Zeichenfolge verwenden, um eine Eigenschaft oder Methode zur Laufzeit angeben.</span><span class="sxs-lookup"><span data-stu-id="d74e3-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="d74e3-111">Die Signatur für die `CallByName` -Funktion sieht wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d74e3-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="d74e3-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span><span class="sxs-lookup"><span data-stu-id="d74e3-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="d74e3-113">Das erste Argument, *Objekt*, erhält den Namen des Objekts, auf die reagiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d74e3-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="d74e3-114">Die *Prozedurname* Argument akzeptiert eine Zeichenfolge mit dem Namen der Methode oder Eigenschaft Prozedur aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d74e3-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="d74e3-115">Die *Aufruftyp* Argument akzeptiert eine Konstante, die den Typ der aufzurufenden Prozedur darstellt: eine Methode (`Microsoft.VisualBasic.CallType.Method`), eine gelesene Eigenschaft (`Microsoft.VisualBasic.CallType.Get`), oder eine festgelegte Eigenschaft (`Microsoft.VisualBasic.CallType.Set`).</span><span class="sxs-lookup"><span data-stu-id="d74e3-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="d74e3-116">Die *Argumente* das optionale Argument akzeptiert ein Array vom Typ `Object` , die keine Argumente an die Prozedur enthält.</span><span class="sxs-lookup"><span data-stu-id="d74e3-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="d74e3-117">Sie können `CallByName` mit Klassen in der aktuellen Projektmappe jedoch am häufigsten verwendet, um den Zugriff auf COM-Objekte oder Objekte aus [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys.</span><span class="sxs-lookup"><span data-stu-id="d74e3-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies.</span></span>  
  
 <span data-ttu-id="d74e3-118">Angenommen, Sie einen Verweis auf eine Assembly hinzufügen, die eine Klasse namens enthält `MathClass`, das ist einer neue Funktion namens `SquareRoot`, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d74e3-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 <span data-ttu-id="d74e3-119">[!code-vb[VbVbalrOOP&#53;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d74e3-119">[!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]</span></span>  
  
 <span data-ttu-id="d74e3-120">Die Anwendung konnte Textfeld-Steuerelemente zum Steuerelement festzulegen, welche Methode aufgerufen wird und seine Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="d74e3-120">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="d74e3-121">Zum Beispiel wenn `TextBox1` enthält den Ausdruck ausgewertet werden soll, und `TextBox2` wird verwendet, um den Namen der Funktion eingeben, können Sie den folgenden Code zum Aufrufen der `SquareRoot` -Funktion für den Ausdruck in `TextBox1`:</span><span class="sxs-lookup"><span data-stu-id="d74e3-121">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 <span data-ttu-id="d74e3-122">[!code-vb[VbVbalrOOP&#54;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="d74e3-122">[!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]</span></span>  
  
 <span data-ttu-id="d74e3-123">Bei der Eingabe von "64" in `TextBox1`, in "SquareRoot" `TextBox2`, und rufen Sie dann die `CallMath` Prozedur, die Quadratwurzel der Zahl in `TextBox1` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="d74e3-123">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="d74e3-124">Der Code im Beispiel ruft die `SquareRoot` -Funktion (der akzeptiert einer Zeichenfolge, die den Ausdruck als ein erforderliches Argument enthält) und gibt "8" in `TextBox1` (die Quadratwurzel von 64).</span><span class="sxs-lookup"><span data-stu-id="d74e3-124">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="d74e3-125">Natürlich auch, wenn der Benutzer eine ungültige Zeichenfolge in eingibt `TextBox2`, wenn die Zeichenfolge den Namen einer Eigenschaft anstelle einer Methode enthält oder die Methode ein weiteres erforderliches Argument aufweist, ein Laufzeitfehler ausgegeben tritt.</span><span class="sxs-lookup"><span data-stu-id="d74e3-125">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="d74e3-126">Müssen Sie stabile Fehlerbehandlungscode hinzufügen, bei Verwendung von `CallByName` auf diese und andere Fehler zu erwarten.</span><span class="sxs-lookup"><span data-stu-id="d74e3-126">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d74e3-127">Während der `CallByName` Funktion kann in einigen Fällen nützlich sein, Sie sollten Leistungseinbußen – mit `CallByName` zum Aufrufen einer Prozedur ist etwas langsamer als eine spät gebundenen Aufruf.</span><span class="sxs-lookup"><span data-stu-id="d74e3-127">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="d74e3-128">Wenn Sie eine Funktion aufrufen, die wiederholt, z. B. in einer Schleife aufgerufen wird `CallByName` kann eine schwerwiegende Auswirkungen auf die Leistung haben.</span><span class="sxs-lookup"><span data-stu-id="d74e3-128">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74e3-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d74e3-129">See Also</span></span>  
 <span data-ttu-id="d74e3-130"><xref:Microsoft.VisualBasic.Interaction.CallByName%2A></xref:Microsoft.VisualBasic.Interaction.CallByName%2A></span><span class="sxs-lookup"><span data-stu-id="d74e3-130"><xref:Microsoft.VisualBasic.Interaction.CallByName%2A></span></span>   
<span data-ttu-id="d74e3-131"> [Bestimmen des Objekttyps](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)</span><span class="sxs-lookup"><span data-stu-id="d74e3-131"> [Determining Object Type](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)</span></span>
