---
title: Private Konstruktoren (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: 1338a6efbe03522093899009178b6f31e558d8dd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45646995"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="39fa1-102">Private Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="39fa1-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="39fa1-103">Ein privater Konstruktor ist ein spezieller Instanzenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="39fa1-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="39fa1-104">Er wird im Allgemeinen in Klassen verwenden, die nur statische Member enthalten.</span><span class="sxs-lookup"><span data-stu-id="39fa1-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="39fa1-105">Wenn eine Klasse einen oder mehrere private und keine öffentlichen Konstruktoren besitzt, können andere Klassen (außer geschachtelte Klassen) keine Instanzen dieser Klasse erstellen.</span><span class="sxs-lookup"><span data-stu-id="39fa1-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="39fa1-106">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39fa1-106">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 <span data-ttu-id="39fa1-107">Die Deklaration des leeren Konstruktors verhindert die automatische Erstellung eines Standardkonstruktors.</span><span class="sxs-lookup"><span data-stu-id="39fa1-107">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="39fa1-108">Beachten Sie, dass wenn Sie keinen Zugriffsmodifizierer mit dem Konstruktor verwenden, der Konstruktor standardmäßig weiterhin privat ist.</span><span class="sxs-lookup"><span data-stu-id="39fa1-108">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="39fa1-109">Allerdings werden die [privaten](../../../csharp/language-reference/keywords/private.md) Modifizierer normalerweise ausdrücklich verwendet, um klarzustellen, dass die Klasse nicht instanziiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="39fa1-109">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="39fa1-110">Private Konstruktoren werden verwendet, um das Erstellen von Instanzen einer Klasse zu verhindern, wenn es keine Instanzfelder oder -methoden wie die <xref:System.Math>-Klasse gibt oder wenn eine Methode aufgerufen wird, um eine Instanz einer Klasse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="39fa1-110">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="39fa1-111">Wenn alle Methoden in der Klasse statisch sind, erwägen Sie es, die komplette Klasse statisch zu machen.</span><span class="sxs-lookup"><span data-stu-id="39fa1-111">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="39fa1-112">Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="39fa1-112">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="39fa1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39fa1-113">Example</span></span>  
 <span data-ttu-id="39fa1-114">Folgendes ist ein Beispiel einer Klasse, die einen privaten Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="39fa1-114">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 <span data-ttu-id="39fa1-115">Beachten Sie, dass wenn Sie die Auskommentierung der folgenden Anweisung aus dem Beispiel aufheben, ein Fehler erzeugt wird, weil auf den Konstruktor aufgrund seiner Schutzebene nicht zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="39fa1-115">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="39fa1-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="39fa1-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="39fa1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39fa1-117">See Also</span></span>

- [<span data-ttu-id="39fa1-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="39fa1-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="39fa1-119">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="39fa1-119">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="39fa1-120">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="39fa1-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [<span data-ttu-id="39fa1-121">Finalizer</span><span class="sxs-lookup"><span data-stu-id="39fa1-121">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
- [<span data-ttu-id="39fa1-122">private</span><span class="sxs-lookup"><span data-stu-id="39fa1-122">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="39fa1-123">public</span><span class="sxs-lookup"><span data-stu-id="39fa1-123">public</span></span>](../../../csharp/language-reference/keywords/public.md)
