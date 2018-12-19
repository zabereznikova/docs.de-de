---
title: Private Konstruktoren – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: a0ff8f69f7725b40eaac01acef74857c2a99247c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240501"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="51bff-102">Private Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="51bff-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="51bff-103">Ein privater Konstruktor ist ein spezieller Instanzenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="51bff-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="51bff-104">Er wird im Allgemeinen in Klassen verwenden, die nur statische Member enthalten.</span><span class="sxs-lookup"><span data-stu-id="51bff-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="51bff-105">Wenn eine Klasse einen oder mehrere private und keine öffentlichen Konstruktoren besitzt, können andere Klassen (außer geschachtelte Klassen) keine Instanzen dieser Klasse erstellen.</span><span class="sxs-lookup"><span data-stu-id="51bff-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="51bff-106">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="51bff-106">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 <span data-ttu-id="51bff-107">Die Deklaration des leeren Konstruktors verhindert die automatische Erstellung eines Standardkonstruktors.</span><span class="sxs-lookup"><span data-stu-id="51bff-107">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="51bff-108">Beachten Sie, dass wenn Sie keinen Zugriffsmodifizierer mit dem Konstruktor verwenden, der Konstruktor standardmäßig weiterhin privat ist.</span><span class="sxs-lookup"><span data-stu-id="51bff-108">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="51bff-109">Allerdings werden die [privaten](../../../csharp/language-reference/keywords/private.md) Modifizierer normalerweise ausdrücklich verwendet, um klarzustellen, dass die Klasse nicht instanziiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="51bff-109">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="51bff-110">Private Konstruktoren werden verwendet, um das Erstellen von Instanzen einer Klasse zu verhindern, wenn es keine Instanzfelder oder -methoden wie die <xref:System.Math>-Klasse gibt oder wenn eine Methode aufgerufen wird, um eine Instanz einer Klasse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="51bff-110">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="51bff-111">Wenn alle Methoden in der Klasse statisch sind, erwägen Sie es, die komplette Klasse statisch zu machen.</span><span class="sxs-lookup"><span data-stu-id="51bff-111">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="51bff-112">Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="51bff-112">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51bff-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51bff-113">Example</span></span>  
 <span data-ttu-id="51bff-114">Folgendes ist ein Beispiel einer Klasse, die einen privaten Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="51bff-114">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 <span data-ttu-id="51bff-115">Beachten Sie, dass wenn Sie die Auskommentierung der folgenden Anweisung aus dem Beispiel aufheben, ein Fehler erzeugt wird, weil auf den Konstruktor aufgrund seiner Schutzebene nicht zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="51bff-115">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="51bff-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="51bff-116">C# Language Specification</span></span>  

<span data-ttu-id="51bff-117">Weitere Informationen erhalten Sie unter [Private Konstruktoren](~/_csharplang/spec/classes.md#private-constructors) in der [C#-Sprachspezifikation](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="51bff-117">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="51bff-118">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="51bff-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="51bff-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51bff-119">See Also</span></span>

- [<span data-ttu-id="51bff-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="51bff-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="51bff-121">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="51bff-121">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="51bff-122">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="51bff-122">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [<span data-ttu-id="51bff-123">Finalizer</span><span class="sxs-lookup"><span data-stu-id="51bff-123">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
- [<span data-ttu-id="51bff-124">private</span><span class="sxs-lookup"><span data-stu-id="51bff-124">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="51bff-125">public</span><span class="sxs-lookup"><span data-stu-id="51bff-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)
