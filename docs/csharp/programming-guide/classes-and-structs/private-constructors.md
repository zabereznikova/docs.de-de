---
title: Private Konstruktoren – C#-Programmierhandbuch
description: Ein privater Konstruktor ist ein spezieller Instanzkonstruktor in C#, der verwendet wird, um einzuschränken, wie ein Objekt erstellt werden kann. Sie können mit Factorymethoden oder anderen Konstruktionsausdrücken verwendet werden.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: a6b86ccb870da0262bcbc516e176e00d17724f9f
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864058"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="fa9e0-104">Private Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fa9e0-104">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="fa9e0-105">Ein privater Konstruktor ist ein spezieller Instanzenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="fa9e0-105">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="fa9e0-106">Er wird im Allgemeinen in Klassen verwenden, die nur statische Member enthalten.</span><span class="sxs-lookup"><span data-stu-id="fa9e0-106">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="fa9e0-107">Wenn eine Klasse einen oder mehrere private und keine öffentlichen Konstruktoren besitzt, können andere Klassen (außer geschachtelte Klassen) keine Instanzen dieser Klasse erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa9e0-107">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="fa9e0-108">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fa9e0-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="fa9e0-109">Die Deklaration des leeren Konstruktors verhindert die automatische Erstellung eines parameterlosen Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="fa9e0-109">The declaration of the empty constructor prevents the automatic generation of a parameterless constructor.</span></span> <span data-ttu-id="fa9e0-110">Beachten Sie, dass wenn Sie keinen Zugriffsmodifizierer mit dem Konstruktor verwenden, der Konstruktor standardmäßig weiterhin privat ist.</span><span class="sxs-lookup"><span data-stu-id="fa9e0-110">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="fa9e0-111">Allerdings werden die [privaten](../../language-reference/keywords/private.md) Modifizierer normalerweise ausdrücklich verwendet, um klarzustellen, dass die Klasse nicht instanziiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="fa9e0-111">However, the [private](../../language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="fa9e0-112">Private Konstruktoren werden verwendet, um das Erstellen von Instanzen einer Klasse zu verhindern, wenn es keine Instanzfelder oder -methoden wie die <xref:System.Math>-Klasse gibt oder wenn eine Methode aufgerufen wird, um eine Instanz einer Klasse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fa9e0-112">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="fa9e0-113">Wenn alle Methoden in der Klasse statisch sind, erwägen Sie es, die komplette Klasse statisch zu machen.</span><span class="sxs-lookup"><span data-stu-id="fa9e0-113">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="fa9e0-114">Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="fa9e0-114">For more information see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa9e0-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa9e0-115">Example</span></span>  
 <span data-ttu-id="fa9e0-116">Folgendes ist ein Beispiel einer Klasse, die einen privaten Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa9e0-116">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#12)]  
  
 <span data-ttu-id="fa9e0-117">Beachten Sie, dass wenn Sie die Auskommentierung der folgenden Anweisung aus dem Beispiel aufheben, ein Fehler erzeugt wird, weil auf den Konstruktor aufgrund seiner Schutzebene nicht zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="fa9e0-117">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#13)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="fa9e0-118">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="fa9e0-118">C# Language Specification</span></span>  

<span data-ttu-id="fa9e0-119">Weitere Informationen erhalten Sie unter [Private Konstruktoren](~/_csharplang/spec/classes.md#private-constructors) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="fa9e0-119">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="fa9e0-120">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="fa9e0-120">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fa9e0-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa9e0-121">See also</span></span>

- [<span data-ttu-id="fa9e0-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fa9e0-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fa9e0-123">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="fa9e0-123">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="fa9e0-124">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="fa9e0-124">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="fa9e0-125">Finalizer</span><span class="sxs-lookup"><span data-stu-id="fa9e0-125">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="fa9e0-126">private</span><span class="sxs-lookup"><span data-stu-id="fa9e0-126">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="fa9e0-127">public</span><span class="sxs-lookup"><span data-stu-id="fa9e0-127">public</span></span>](../../language-reference/keywords/public.md)
