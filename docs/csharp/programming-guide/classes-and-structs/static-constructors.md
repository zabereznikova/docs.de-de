---
title: Statische Konstruktoren – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 6a990dbf26ac1a6bdc642442b9f4b75c05ee9635
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200116"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="a985a-102">Statische Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a985a-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="a985a-103">Ein statischer Konstruktor wird verwendet, um [static](../../../csharp/language-reference/keywords/static.md)-Daten zu initialisieren oder um eine bestimmte Aktion auszuführen, die nur einmal ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="a985a-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="a985a-104">Er wird automatisch aufgerufen, bevor die erste Instanz erstellt oder auf irgendwelche statischen Member verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a985a-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  
  
 <span data-ttu-id="a985a-105">Statische Konstruktoren verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a985a-105">Static constructors have the following properties:</span></span>  
  
-   <span data-ttu-id="a985a-106">Ein statischer Konstruktor kann nicht über Zugriffsmodifizierer oder Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="a985a-106">A static constructor does not take access modifiers or have parameters.</span></span>  
  
-   <span data-ttu-id="a985a-107">Ein statischer Konstruktor wird automatisch zum Initialisieren von [class](../../../csharp/language-reference/keywords/class.md) aufgerufen, bevor die erste Instanz erzeugt wird oder auf irgendwelche statischen Member verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a985a-107">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
-   <span data-ttu-id="a985a-108">Ein statischer Konstruktor kann nicht direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a985a-108">A static constructor cannot be called directly.</span></span>  
  
-   <span data-ttu-id="a985a-109">Der Benutzer hat keine Kontrolle, wenn der statische Konstruktor im Programm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a985a-109">The user has no control on when the static constructor is executed in the program.</span></span>  
  
-   <span data-ttu-id="a985a-110">Eine typische Verwendung statischer Konstruktoren besteht darin, wenn die Klasse eine Protokolldatei verwendet und der Konstruktor verwendet wird, um Einträge in dieser Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="a985a-110">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
-   <span data-ttu-id="a985a-111">Statische Konstruktoren sind auch beim Erstellen von Wrapperklassen für nicht verwalteten Code nützlich, wenn der Konstruktor die `LoadLibrary`-Methode aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="a985a-111">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
-   <span data-ttu-id="a985a-112">Wenn ein statischer Konstruktor eine Ausnahme auslöst, wird die Laufzeit ihn kein zweites Mal aufrufen, und der Typ bleibt für die Lebensdauer der Anwendungsdomäne, in der das Programm ausgeführt wird, nicht initialisiert.</span><span class="sxs-lookup"><span data-stu-id="a985a-112">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a985a-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a985a-113">Example</span></span>  
 <span data-ttu-id="a985a-114">In diesem Beispiel verfügt die Klasse `Bus` über einen statischen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="a985a-114">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="a985a-115">Wenn die erste Instanz von `Bus` erstellt wird (`bus1`), wird der statische Konstruktor zur Initialisierung der Klasse aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a985a-115">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="a985a-116">Die Beispielausgabe überprüft, ob der statische Konstruktor nur einmal ausgeführt wird, obwohl zwei Instanzen von `Bus` erstellt werden, und dass er vor dem Ausführen des Instanzkonstruktors ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a985a-116">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]  
  
## <a name="see-also"></a><span data-ttu-id="a985a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a985a-117">See also</span></span>

- [<span data-ttu-id="a985a-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a985a-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a985a-119">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="a985a-119">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="a985a-120">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="a985a-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="a985a-121">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="a985a-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="a985a-122">Finalizer</span><span class="sxs-lookup"><span data-stu-id="a985a-122">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
