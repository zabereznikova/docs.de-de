---
title: 'Vorgehensweise: Verwenden einer generischen Klasse'
ms.date: 07/20/2015
helpviewer_keywords:
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters [Visual Basic], data type
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
ms.openlocfilehash: 87ba5132afe9f5a7cd6fb33d716c670f4812c7e2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077110"
---
# <a name="how-to-use-a-generic-class-visual-basic"></a><span data-ttu-id="b16d8-102">Gewusst wie: Verwenden einer generischen Klasse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b16d8-102">How to: Use a Generic Class (Visual Basic)</span></span>

<span data-ttu-id="b16d8-103">Eine Klasse, die *Typparameter* akzeptiert, wird *generische Klasse*genannt.</span><span class="sxs-lookup"><span data-stu-id="b16d8-103">A class that takes *type parameters* is called a *generic class*.</span></span> <span data-ttu-id="b16d8-104">Wenn Sie eine generische Klasse verwenden, können Sie daraus eine *erzeugte Klasse* generieren, indem Sie ein *Typargument* für jeden dieser Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="b16d8-104">If you are using a generic class, you can generate a *constructed class* from it by supplying a *type argument* for each of these parameters.</span></span> <span data-ttu-id="b16d8-105">Sie können dann eine Variable vom Typ der erzeugten Klasse deklarieren, und Sie können eine Instanz der erzeugten Klasse erstellen und dieser Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b16d8-105">You can then declare a variable of the constructed class type, and you can create an instance of the constructed class and assign it to that variable.</span></span>  
  
 <span data-ttu-id="b16d8-106">Zusätzlich zu generischen Klassen können Sie auch generische Strukturen, Schnittstellen, Prozeduren und Delegaten definieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="b16d8-106">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
 <span data-ttu-id="b16d8-107">Im folgenden Verfahren wird eine generische Klasse, die in der .NET Framework definiert ist, und eine Instanz daraus erstellt.</span><span class="sxs-lookup"><span data-stu-id="b16d8-107">The following procedure takes a generic class defined in the .NET Framework and creates an instance from it.</span></span>  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a><span data-ttu-id="b16d8-108">Eine Klasse verwenden, die einen Typparameter braucht</span><span class="sxs-lookup"><span data-stu-id="b16d8-108">To use a class that takes a type parameter</span></span>  
  
1. <span data-ttu-id="b16d8-109">Fügen Sie am Anfang der Quelldatei eine [Imports-Anweisung (.NET-Namespace und-Typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) ein, um den <xref:System.Collections.Generic?displayProperty=nameWithType> Namespace zu importieren.</span><span class="sxs-lookup"><span data-stu-id="b16d8-109">At the beginning of your source file, include an [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) to import the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="b16d8-110">Dadurch können Sie auf die <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>-Klasse verweisen, ohne sie zur Unterscheidung von anderen Warteschlangenklassen wie z.B. <xref:System.Collections.Queue?displayProperty=nameWithType> vollständig qualifizieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="b16d8-110">This allows you to refer to the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class without having to fully qualify it to differentiate it from other queue classes such as <xref:System.Collections.Queue?displayProperty=nameWithType>.</span></span>  
  
2. <span data-ttu-id="b16d8-111">Erstellen Sie das Objekt auf die übliche Weise, aber fügen Sie sofort nach dem Klassennamen `(Of type)` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b16d8-111">Create the object in the normal way, but add `(Of type)` immediately after the class name.</span></span>  
  
     <span data-ttu-id="b16d8-112">Im folgenden Beispiel wird dieselbe Klasse (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) verwendet, um zwei Warteschlangenobjekte zu erstellen, die Artikel mit unterschiedlichen Datentypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b16d8-112">The following example uses the same class (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) to create two queue objects that hold items of different data types.</span></span> <span data-ttu-id="b16d8-113">Es fügt Elemente am Ende jeder Warteschlange ein und entfernt und zeigt Elemente am Beginn jeder Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="b16d8-113">It adds items to the end of each queue and then removes and displays items from the front of each queue.</span></span>  
  
     [!code-vb[VbVbalrDataTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="b16d8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b16d8-114">See also</span></span>

- [<span data-ttu-id="b16d8-115">Datentypen</span><span class="sxs-lookup"><span data-stu-id="b16d8-115">Data Types</span></span>](index.md)
- [<span data-ttu-id="b16d8-116">Generische Typen in Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b16d8-116">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="b16d8-117">Sprachunabhängigkeit und sprachunabhängige Komponenten</span><span class="sxs-lookup"><span data-stu-id="b16d8-117">Language Independence and Language-Independent Components</span></span>](../../../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="b16d8-118">Natürlich</span><span class="sxs-lookup"><span data-stu-id="b16d8-118">Of</span></span>](../../../language-reference/statements/of-clause.md)
- [<span data-ttu-id="b16d8-119">Imports-Anweisung (.NET-Namespace und Typ)</span><span class="sxs-lookup"><span data-stu-id="b16d8-119">Imports Statement (.NET Namespace and Type)</span></span>](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="b16d8-120">Vorgehensweise: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann</span><span class="sxs-lookup"><span data-stu-id="b16d8-120">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="b16d8-121">Iteratoren</span><span class="sxs-lookup"><span data-stu-id="b16d8-121">Iterators</span></span>](../../concepts/iterators.md)
