---
title: 'Gewusst wie: Ablegen mehrerer Werte in einer Variablen (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c8c567ec2ba01d094819c98a2937af75cd105956
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="9fda4-102">Gewusst wie: Ablegen mehrerer Werte in einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fda4-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>
<span data-ttu-id="9fda4-103">Eine Variable enthält mehr als einen Wert aus, wenn Sie vom deklariert eine *zusammengesetzten Datentyp*.</span><span class="sxs-lookup"><span data-stu-id="9fda4-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>  
  
 <span data-ttu-id="9fda4-104">[Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) umfassen Strukturen, Arrays und Klassen.</span><span class="sxs-lookup"><span data-stu-id="9fda4-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="9fda4-105">Eine Variable eines zusammengesetzten Datentyps kann eine Kombination von elementare Datentypen und anderen zusammengesetzten Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9fda4-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="9fda4-106">Strukturen und Klassen können sowohl Code als auch Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="9fda4-106">Structures and classes can hold code as well as data.</span></span>  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="9fda4-107">Um mehr als einen Wert in einer Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9fda4-107">To hold more than one value in a variable</span></span>  
  
1.  <span data-ttu-id="9fda4-108">Bestimmen des Typs zusammengesetzte Datenelemente für die Variable verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9fda4-108">Determine what composite data type you want to use for your variable.</span></span>  
  
2.  <span data-ttu-id="9fda4-109">Wenn der zusammengesetzte Datentyp noch nicht definiert ist, definieren Sie ihn so, dass die Variable, die sie verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="9fda4-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>  
  
    -   <span data-ttu-id="9fda4-110">Definieren Sie eine Struktur mit einem [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9fda4-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
    -   <span data-ttu-id="9fda4-111">Definieren Sie ein Array mit einem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9fda4-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
    -   <span data-ttu-id="9fda4-112">Definieren Sie eine Klasse mit einem [Class-Anweisung](../../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9fda4-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
3.  <span data-ttu-id="9fda4-113">Deklarieren Sie die Variable mit einem `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9fda4-113">Declare your variable with a `Dim` statement.</span></span>  
  
4.  <span data-ttu-id="9fda4-114">Gehen Sie vor dem Variablennamen ein `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="9fda4-114">Follow the variable name with an `As` clause.</span></span>  
  
5.  <span data-ttu-id="9fda4-115">Führen Sie die `As` Schlüsselwort mit dem Namen des entsprechenden zusammengesetzten-Datentyps.</span><span class="sxs-lookup"><span data-stu-id="9fda4-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fda4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fda4-116">See Also</span></span>  
 [<span data-ttu-id="9fda4-117">Datentypen</span><span class="sxs-lookup"><span data-stu-id="9fda4-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="9fda4-118">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="9fda4-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="9fda4-119">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="9fda4-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="9fda4-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="9fda4-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="9fda4-121">Arrays</span><span class="sxs-lookup"><span data-stu-id="9fda4-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="9fda4-122">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="9fda4-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="9fda4-123">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="9fda4-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
