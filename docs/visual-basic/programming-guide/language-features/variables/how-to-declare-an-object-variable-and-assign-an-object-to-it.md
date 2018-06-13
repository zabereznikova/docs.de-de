---
title: 'Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 1f38c90f0571b3fc73c4c89812092cdada936d84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648875"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="0bbf0-102">Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0bbf0-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>
<span data-ttu-id="0bbf0-103">Sie deklarieren eine Variable vom der [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md) durch Angabe `As Object` in einem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0bbf0-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="0bbf0-104">Sie können ein Objekt auf eine solche Variable zuweisen, durch das Objekt hinter dem Gleichheitszeichen aufzunehmen (`=`) in einer Zuordnung-Anweisung oder Initialisierung-Klausel.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bbf0-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0bbf0-105">Example</span></span>  
 <span data-ttu-id="0bbf0-106">Das folgende Beispiel deklariert eine `Object` -Variable und weist dieser aktuellen Instanz.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 <span data-ttu-id="0bbf0-107">Sie können die Deklaration und Zuweisung kombinieren, durch die Initialisierung der Variablen als Teil der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="0bbf0-108">Im folgende Beispiel entspricht im vorangehenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-108">The following example is equivalent to the preceding example.</span></span>  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0bbf0-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0bbf0-109">Compiling the Code</span></span>  
 <span data-ttu-id="0bbf0-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0bbf0-110">This example requires:</span></span>  
  
-   <span data-ttu-id="0bbf0-111">Einen Verweis auf den <xref:System>-Namespace</span><span class="sxs-lookup"><span data-stu-id="0bbf0-111">A reference to the <xref:System> namespace.</span></span>  
  
-   <span data-ttu-id="0bbf0-112">Eine Klasse, Struktur oder Modul, in dem Ablegen der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-112">A class, structure, or module in which to put the `Dim` statement.</span></span>  
  
-   <span data-ttu-id="0bbf0-113">Eine Prozedur, in dem die zuweisungsanweisung abgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-113">A procedure in which to put the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bbf0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bbf0-114">See Also</span></span>  
 [<span data-ttu-id="0bbf0-115">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="0bbf0-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="0bbf0-116">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="0bbf0-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="0bbf0-117">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="0bbf0-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="0bbf0-118">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="0bbf0-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="0bbf0-119">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0bbf0-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="0bbf0-120">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="0bbf0-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="0bbf0-121">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0bbf0-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
