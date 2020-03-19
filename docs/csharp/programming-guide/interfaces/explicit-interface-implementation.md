---
title: Explizite Schnittstellenimplementierung – C#-Programmierhandbuch
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: ea32a279b7c464174a7fada5ef93ccf62ef39884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167672"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="e9962-102">Explizite Schnittstellenimplementierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="e9962-102">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="e9962-103">Wenn eine [Klasse](../../language-reference/keywords/class.md) zwei Schnittstellen implementiert, die einen Member mit derselben Signatur enthalten, bewirkt die Implementierung dieses Members in der Klasse, dass beide Schnittstellen diesen Member als ihre Implementierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e9962-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="e9962-104">Im folgenden Beispiel rufen alle Aufrufe von `Paint` dieselbe Methode auf.</span><span class="sxs-lookup"><span data-stu-id="e9962-104">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="e9962-105">In diesem ersten Beispiel werden die Typen definiert:</span><span class="sxs-lookup"><span data-stu-id="e9962-105">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="e9962-106">Im folgenden Beispiel werden die Methoden aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="e9962-106">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="e9962-107">Wenn zwei Schnittstellenmember nicht dieselbe Funktion durchführen, führt dies zu einer fehlerhaften Implementierung von einer oder beiden Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="e9962-107">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="e9962-108">Ein Schnittstellenmember kann explizit implementiert werden. Hierzu wird ein Klassenmember erstellt, der nur über die Schnittstelle aufgerufen wird und spezifisch auf diese Schnittstelle ausgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e9962-108">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="e9962-109">Benennen Sie den Klassenmember hierzu mit dem Namen der Schnittstelle und einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="e9962-109">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="e9962-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e9962-110">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="e9962-111">Der Klassenmember `IControl.Paint` ist nur über die Schnittstelle `IControl` verfügbar, und `ISurface.Paint` ist nur über `ISurface` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e9962-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="e9962-112">Beide Methodenimplementierungen sind voneinander getrennt, und sie sind nicht direkt in der Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e9962-112">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="e9962-113">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e9962-113">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="e9962-114">Die explizite Implementierung wird auch zum Lösen von Konflikten verwendet, bei denen zwei Schnittstellen verschiedene Member mit demselben Namen deklarieren, z. B. eine Eigenschaft und eine Methode.</span><span class="sxs-lookup"><span data-stu-id="e9962-114">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="e9962-115">Zum Implementieren beider Schnittstellen muss eine Klasse die explizite Implementierung für die Eigenschaft `P`, die Methode `P` oder beide verwenden, um einen Compilerfehler zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e9962-115">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="e9962-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e9962-116">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="e9962-117">Ab [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods) können Sie eine Implementierung für in einer Schnittstelle deklarierte Mitglieder definieren.</span><span class="sxs-lookup"><span data-stu-id="e9962-117">Beginning with [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods), you can define an implementation for members declared in an interface.</span></span> <span data-ttu-id="e9962-118">Wenn eine Klasse eine Methodenimplementierung von einer Schnittstelle erbt, ist diese Methode nur über einen Verweis des Schnittstellentyps zugänglich.</span><span class="sxs-lookup"><span data-stu-id="e9962-118">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="e9962-119">Der geerbte Member wird nicht als Teil der öffentlichen Schnittstelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9962-119">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="e9962-120">Im folgenden Beispiel wird eine Standardimplementierung für eine Schnittstellenmethode definiert:</span><span class="sxs-lookup"><span data-stu-id="e9962-120">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="e9962-121">Im folgenden Beispiel wird die Standardimplementierung aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="e9962-121">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="e9962-122">Alle Klassen, die die `IControl`-Schnittstelle implementieren, können die Standardmethode `Paint` überschreiben: entweder als öffentliche Methode oder als explizite Schnittstellenimplementierung.</span><span class="sxs-lookup"><span data-stu-id="e9962-122">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9962-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9962-123">See also</span></span>

- [<span data-ttu-id="e9962-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e9962-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e9962-125">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="e9962-125">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="e9962-126">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e9962-126">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="e9962-127">Vererbung</span><span class="sxs-lookup"><span data-stu-id="e9962-127">Inheritance</span></span>](../classes-and-structs/inheritance.md)
