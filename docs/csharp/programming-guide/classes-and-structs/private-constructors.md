---
title: Private Konstruktoren (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1ccd3db5f95e3a237bb37d9e09c34f415fcfd752
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="bee54-102">Private Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="bee54-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="bee54-103">Ein privater Konstruktor ist ein spezieller Instanzenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="bee54-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="bee54-104">Er wird im Allgemeinen in Klassen verwenden, die nur statische Member enthalten.</span><span class="sxs-lookup"><span data-stu-id="bee54-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="bee54-105">Wenn eine Klasse einen oder mehrere private und keine öffentlichen Konstruktoren besitzt, können andere Klassen (außer geschachtelte Klassen) keine Instanzen dieser Klasse erstellen.</span><span class="sxs-lookup"><span data-stu-id="bee54-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="bee54-106">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bee54-106">For example:</span></span>  
  
 <span data-ttu-id="bee54-107">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bee54-107">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="bee54-108">Die Deklaration des leeren Konstruktors verhindert die automatische Erstellung eines Standardkonstruktors.</span><span class="sxs-lookup"><span data-stu-id="bee54-108">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="bee54-109">Beachten Sie, dass wenn Sie keinen Zugriffsmodifizierer mit dem Konstruktor verwenden, der Konstruktor standardmäßig weiterhin privat ist.</span><span class="sxs-lookup"><span data-stu-id="bee54-109">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="bee54-110">Allerdings werden die [privaten](../../../csharp/language-reference/keywords/private.md) Modifizierer normalerweise ausdrücklich verwendet, um klarzustellen, dass die Klasse nicht instanziiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bee54-110">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="bee54-111">Private Konstruktoren werden verwendet, um das Erstellen von Instanzen einer Klasse zu verhindern, wenn es keine Instanzfelder oder -methoden wie die <xref:System.Math>-Klasse gibt oder wenn eine Methode aufgerufen wird, um eine Instanz einer Klasse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bee54-111">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="bee54-112">Wenn alle Methoden in der Klasse statisch sind, erwägen Sie es, die komplette Klasse statisch zu machen.</span><span class="sxs-lookup"><span data-stu-id="bee54-112">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="bee54-113">Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="bee54-113">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bee54-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bee54-114">Example</span></span>  
 <span data-ttu-id="bee54-115">Folgendes ist ein Beispiel einer Klasse, die einen privaten Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="bee54-115">The following is an example of a class using a private constructor.</span></span>  
  
 <span data-ttu-id="bee54-116">[!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bee54-116">[!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="bee54-117">Beachten Sie, dass wenn Sie die Auskommentierung der folgenden Anweisung aus dem Beispiel aufheben, ein Fehler erzeugt wird, weil auf den Konstruktor aufgrund seiner Schutzebene nicht zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="bee54-117">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 <span data-ttu-id="bee54-118">[!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="bee54-118">[!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="bee54-119">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="bee54-119">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bee54-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bee54-120">See Also</span></span>  
 <span data-ttu-id="bee54-121">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bee54-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bee54-122">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="bee54-122">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="bee54-123">[Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="bee54-123">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="bee54-124">[Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="bee54-124">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 <span data-ttu-id="bee54-125">[Private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="bee54-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 [<span data-ttu-id="bee54-126">public</span><span class="sxs-lookup"><span data-stu-id="bee54-126">public</span></span>](../../../csharp/language-reference/keywords/public.md)

