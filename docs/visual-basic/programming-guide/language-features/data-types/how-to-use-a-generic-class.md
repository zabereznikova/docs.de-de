---
title: 'Gewusst wie: Verwenden einer generischen Klasse (Visual Basic) | Microsoft-Dokumentation'
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
- type parameters, defining
- data type arguments, defining
- arguments [Visual Basic], data types
- Of keyword, using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters, type
- types [Visual Basic], generic
- parameters, generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters, data type
- data type parameters, defining
- type arguments, defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d6f5f941887dfc1f93221be1c184f0dcc2789352
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-use-a-generic-class-visual-basic"></a><span data-ttu-id="97fd8-102">Gewusst wie: Verwenden einer generischen Klasse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97fd8-102">How to: Use a Generic Class (Visual Basic)</span></span>
<span data-ttu-id="97fd8-103">Eine Klasse, die *Typparameter* akzeptiert, wird *generische Klasse*genannt.</span><span class="sxs-lookup"><span data-stu-id="97fd8-103">A class that takes *type parameters* is called a *generic class*.</span></span> <span data-ttu-id="97fd8-104">Wenn Sie eine generische Klasse verwenden, können Sie daraus eine *erzeugte Klasse* generieren, indem Sie ein *Typargument* für jeden dieser Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="97fd8-104">If you are using a generic class, you can generate a *constructed class* from it by supplying a *type argument* for each of these parameters.</span></span> <span data-ttu-id="97fd8-105">Sie können dann eine Variable vom Typ der erzeugten Klasse deklarieren, und Sie können eine Instanz der erzeugten Klasse erstellen und dieser Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="97fd8-105">You can then declare a variable of the constructed class type, and you can create an instance of the constructed class and assign it to that variable.</span></span>  
  
 <span data-ttu-id="97fd8-106">Zusätzlich zu generischen Klassen können Sie auch generische Strukturen, Schnittstellen, Prozeduren und Delegaten definieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="97fd8-106">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
 <span data-ttu-id="97fd8-107">Beim folgenden Verfahren wird eine generische Klasse verwendet, die in [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] definiert ist, und eine Instanz daraus erstellt.</span><span class="sxs-lookup"><span data-stu-id="97fd8-107">The following procedure takes a generic class defined in the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] and creates an instance from it.</span></span>  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a><span data-ttu-id="97fd8-108">Eine Klasse verwenden, die einen Typparameter braucht</span><span class="sxs-lookup"><span data-stu-id="97fd8-108">To use a class that takes a type parameter</span></span>  
  
1.  <span data-ttu-id="97fd8-109">Fügen Sie am Anfang der Quelldatei, ein [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) zum Importieren der <xref:System.Collections.Generic?displayProperty=fullName>Namespace.</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="97fd8-109">At the beginning of your source file, include an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import the <xref:System.Collections.Generic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="97fd8-110">Dadurch können Sie zum Verweisen auf die <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>Klasse, ohne sie zur Unterscheidung von anderen Warteschlangeklassen wie z. B. <xref:System.Collections.Queue?displayProperty=fullName>.</xref:System.Collections.Queue?displayProperty=fullName> vollständig qualifizieren zu müssen</xref:System.Collections.Generic.Queue%601?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="97fd8-110">This allows you to refer to the <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> class without having to fully qualify it to differentiate it from other queue classes such as <xref:System.Collections.Queue?displayProperty=fullName>.</span></span>  
  
2.  <span data-ttu-id="97fd8-111">Erstellen Sie das Objekt auf die übliche Weise, aber fügen Sie sofort nach dem Klassennamen `(Of` `type``)` hinzu.</span><span class="sxs-lookup"><span data-stu-id="97fd8-111">Create the object in the normal way, but add `(Of` `type``)` immediately after the class name.</span></span>  
  
     <span data-ttu-id="97fd8-112">Im folgenden Beispiel wird dieselbe Klasse (<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>) zwei Queue-Objekte erstellen, die Artikel mit unterschiedlichen Datentypen enthalten.</xref:System.Collections.Generic.Queue%601?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="97fd8-112">The following example uses the same class (<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>) to create two queue objects that hold items of different data types.</span></span> <span data-ttu-id="97fd8-113">Es fügt Elemente am Ende jeder Warteschlange ein und entfernt und zeigt Elemente am Beginn jeder Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="97fd8-113">It adds items to the end of each queue and then removes and displays items from the front of each queue.</span></span>  
  
     <span data-ttu-id="97fd8-114">[!code-vb[VbVbalrDataTypes&#9;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="97fd8-114">[!code-vb[VbVbalrDataTypes#9](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97fd8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97fd8-115">See Also</span></span>  
 <span data-ttu-id="97fd8-116">[Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="97fd8-116">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="97fd8-117"> [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="97fd8-117"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="97fd8-118"> [Sprachunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) </span><span class="sxs-lookup"><span data-stu-id="97fd8-118"> [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) </span></span>  
<span data-ttu-id="97fd8-119"> [Of](../../../../visual-basic/language-reference/statements/of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="97fd8-119"> [Of](../../../../visual-basic/language-reference/statements/of-clause.md) </span></span>  
<span data-ttu-id="97fd8-120"> [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="97fd8-120"> [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="97fd8-121"> [Gewusst wie: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="97fd8-121"> [How to: Define a Class That Can Provide Identical Functionality on Different Data Types](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md) </span></span>  
<span data-ttu-id="97fd8-122"> [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)</span><span class="sxs-lookup"><span data-stu-id="97fd8-122"> [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)</span></span>
