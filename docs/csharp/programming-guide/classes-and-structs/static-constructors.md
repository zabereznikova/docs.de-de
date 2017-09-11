---
title: Statische Konstruktoren (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
caps.latest.revision: 23
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
ms.openlocfilehash: 73df76c61f393bf5fe09af66935acfbac4b5663f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="0cb27-102">Statische Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0cb27-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="0cb27-103">Ein statischer Konstruktor wird verwendet, um [static](../../../csharp/language-reference/keywords/static.md)-Daten zu initialisieren oder um eine bestimmte Aktion auszuführen, die nur einmal ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="0cb27-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="0cb27-104">Er wird automatisch aufgerufen, bevor die erste Instanz erstellt oder auf irgendwelche statischen Member verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0cb27-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 <span data-ttu-id="0cb27-105">[!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0cb27-105">[!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="0cb27-106">Statische Konstruktoren verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="0cb27-106">Static constructors have the following properties:</span></span>  
  
-   <span data-ttu-id="0cb27-107">Ein statischer Konstruktor kann nicht über Zugriffsmodifizierer oder Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="0cb27-107">A static constructor does not take access modifiers or have parameters.</span></span>  
  
-   <span data-ttu-id="0cb27-108">Ein statischer Konstruktor wird automatisch zum Initialisieren von [class](../../../csharp/language-reference/keywords/class.md) aufgerufen, bevor die erste Instanz erzeugt wird oder auf irgendwelche statischen Member verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0cb27-108">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
-   <span data-ttu-id="0cb27-109">Ein statischer Konstruktor kann nicht direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0cb27-109">A static constructor cannot be called directly.</span></span>  
  
-   <span data-ttu-id="0cb27-110">Der Benutzer hat keine Kontrolle, wenn der statische Konstruktor im Programm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0cb27-110">The user has no control on when the static constructor is executed in the program.</span></span>  
  
-   <span data-ttu-id="0cb27-111">Eine typische Verwendung statischer Konstruktoren besteht darin, wenn die Klasse eine Protokolldatei verwendet und der Konstruktor verwendet wird, um Einträge in dieser Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="0cb27-111">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
-   <span data-ttu-id="0cb27-112">Statische Konstruktoren sind auch beim Erstellen von Wrapperklassen für nicht verwalteten Code nützlich, wenn der Konstruktor die `LoadLibrary`-Methode aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="0cb27-112">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
-   <span data-ttu-id="0cb27-113">Wenn ein statischer Konstruktor eine Ausnahme auslöst, wird die Laufzeit ihn kein zweites Mal aufrufen, und der Typ bleibt für die Lebensdauer der Anwendungsdomäne, in der das Programm ausgeführt wird, nicht initialisiert.</span><span class="sxs-lookup"><span data-stu-id="0cb27-113">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cb27-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0cb27-114">Example</span></span>  
 <span data-ttu-id="0cb27-115">In diesem Beispiel verfügt die Klasse `Bus` über einen statischen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="0cb27-115">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="0cb27-116">Wenn die erste Instanz von `Bus` erstellt wird (`bus1`), wird der statische Konstruktor zur Initialisierung der Klasse aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0cb27-116">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="0cb27-117">Die Beispielausgabe überprüft, ob der statische Konstruktor nur einmal ausgeführt wird, obwohl zwei Instanzen von `Bus` erstellt werden, und dass er vor dem Ausführen des Instanzkonstruktors ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0cb27-117">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 <span data-ttu-id="0cb27-118">[!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0cb27-118">[!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb27-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cb27-119">See Also</span></span>  
 <span data-ttu-id="0cb27-120">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0cb27-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0cb27-121">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="0cb27-121">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="0cb27-122">[Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="0cb27-122">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="0cb27-123">[Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="0cb27-123">[Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span></span>  
 [<span data-ttu-id="0cb27-124">Finalizer</span><span class="sxs-lookup"><span data-stu-id="0cb27-124">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

