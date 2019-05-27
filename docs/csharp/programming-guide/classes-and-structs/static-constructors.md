---
title: Statische Konstruktoren – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 110d83caad0c588fa899a4129897784e9c74aab8
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881913"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="aff9a-102">Statische Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="aff9a-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="aff9a-103">Ein statischer Konstruktor wird verwendet, um [static](../../../csharp/language-reference/keywords/static.md)-Daten zu initialisieren oder um eine bestimmte Aktion auszuführen, die nur einmal ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="aff9a-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="aff9a-104">Er wird automatisch aufgerufen, bevor die erste Instanz erstellt oder auf irgendwelche statischen Member verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="aff9a-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  
  
 <span data-ttu-id="aff9a-105">Statische Konstruktoren verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="aff9a-105">Static constructors have the following properties:</span></span>  
  
- <span data-ttu-id="aff9a-106">Ein statischer Konstruktor kann nicht über Zugriffsmodifizierer oder Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="aff9a-106">A static constructor does not take access modifiers or have parameters.</span></span>  
  
- <span data-ttu-id="aff9a-107">Ein statischer Konstruktor wird automatisch zum Initialisieren von [class](../../../csharp/language-reference/keywords/class.md) aufgerufen, bevor die erste Instanz erzeugt wird oder auf irgendwelche statischen Member verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="aff9a-107">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span> <span data-ttu-id="aff9a-108">Beachten Sie, dass der statische Konstruktor eines Typs aufgerufen wird, wenn eine statische Methode, die einem Ereignis oder Delegaten zugewiesen ist, aufgerufen wird. Dies erfolgt nicht während der Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="aff9a-108">Note that a type's static constructor is called when a static method assigned to an event or a delegate is invoked and not when it is assigned.</span></span>
  
- <span data-ttu-id="aff9a-109">Ein statischer Konstruktor kann nicht direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="aff9a-109">A static constructor cannot be called directly.</span></span>  
  
- <span data-ttu-id="aff9a-110">Der Benutzer hat keine Kontrolle, wenn der statische Konstruktor im Programm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="aff9a-110">The user has no control on when the static constructor is executed in the program.</span></span>  
  
- <span data-ttu-id="aff9a-111">Eine typische Verwendung statischer Konstruktoren besteht darin, wenn die Klasse eine Protokolldatei verwendet und der Konstruktor verwendet wird, um Einträge in dieser Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="aff9a-111">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
- <span data-ttu-id="aff9a-112">Statische Konstruktoren sind auch beim Erstellen von Wrapperklassen für nicht verwalteten Code nützlich, wenn der Konstruktor die `LoadLibrary`-Methode aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="aff9a-112">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
- <span data-ttu-id="aff9a-113">Wenn ein statischer Konstruktor eine Ausnahme auslöst, wird die Laufzeit ihn kein zweites Mal aufrufen, und der Typ bleibt für die Lebensdauer der Anwendungsdomäne, in der das Programm ausgeführt wird, nicht initialisiert.</span><span class="sxs-lookup"><span data-stu-id="aff9a-113">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aff9a-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aff9a-114">Example</span></span>  
 <span data-ttu-id="aff9a-115">In diesem Beispiel verfügt die Klasse `Bus` über einen statischen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="aff9a-115">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="aff9a-116">Wenn die erste Instanz von `Bus` erstellt wird (`bus1`), wird der statische Konstruktor zur Initialisierung der Klasse aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="aff9a-116">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="aff9a-117">Die Beispielausgabe überprüft, ob der statische Konstruktor nur einmal ausgeführt wird, obwohl zwei Instanzen von `Bus` erstellt werden, und dass er vor dem Ausführen des Instanzkonstruktors ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="aff9a-117">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]  
  
## <a name="see-also"></a><span data-ttu-id="aff9a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aff9a-118">See also</span></span>

- [<span data-ttu-id="aff9a-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="aff9a-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="aff9a-120">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="aff9a-120">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="aff9a-121">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="aff9a-121">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="aff9a-122">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="aff9a-122">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="aff9a-123">Finalizer</span><span class="sxs-lookup"><span data-stu-id="aff9a-123">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
