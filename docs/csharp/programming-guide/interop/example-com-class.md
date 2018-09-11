---
title: COM-Beispielklasse (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
ms.openlocfilehash: f8f4a9ebaf41a0787e17685a60d3e847f2aca0c2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43415461"
---
# <a name="example-com-class-c-programming-guide"></a><span data-ttu-id="73865-102">COM-Beispielklasse (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="73865-102">Example COM Class (C# Programming Guide)</span></span>
<span data-ttu-id="73865-103">Das Folgende ist ein Beispiel für eine Klasse, die Sie als COM-Objekt offenlegen würden.</span><span class="sxs-lookup"><span data-stu-id="73865-103">The following is an example of a class that you would expose as a COM object.</span></span> <span data-ttu-id="73865-104">Nachdem dieser Code in eine CS-Datei platziert und Ihrem Projekt hinzugefügt wurde, legen Sie die Eigenschaft **für COM-Interop registrieren** auf **TRUE** fest.</span><span class="sxs-lookup"><span data-stu-id="73865-104">After this code has been placed in a .cs file and added to your project, set the **Register for COM Interop** property to **True**.</span></span> <span data-ttu-id="73865-105">Weitere Informationen finden Sie unter [Vorgehensweise: Registrieren einer Komponente für COM-Interop](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="73865-105">For more information, see [How to: Register a Component for COM Interop](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).</span></span>
  
 <span data-ttu-id="73865-106">Das Verfügbarmachen von Visual C#-Objekten für COM erfordert die Deklaration einer Klassenschnittstelle, einer Ereignisschnittstelle (wenn dies erforderlich ist) und die Klasse selbst.</span><span class="sxs-lookup"><span data-stu-id="73865-106">Exposing Visual C# objects to COM requires declaring a class interface, an events interface if it is required, and the class itself.</span></span> <span data-ttu-id="73865-107">Klassenmember müssen diesen Regeln folgen, um für COM sichtbar zu sein:</span><span class="sxs-lookup"><span data-stu-id="73865-107">Class members must follow these rules to be visible to COM:</span></span>  
  
-   <span data-ttu-id="73865-108">Die Klasse muss öffentlich sein.</span><span class="sxs-lookup"><span data-stu-id="73865-108">The class must be public.</span></span>  
  
-   <span data-ttu-id="73865-109">Eigenschaften, Methoden und Ereignisse müssen öffentlich sein.</span><span class="sxs-lookup"><span data-stu-id="73865-109">Properties, methods, and events must be public.</span></span>  
  
-   <span data-ttu-id="73865-110">Eigenschaften und Methoden müssen auf der Klassenschnittstelle deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="73865-110">Properties and methods must be declared on the class interface.</span></span>  
  
-   <span data-ttu-id="73865-111">Ereignisse müssen in der Ereignisschnittstelle deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="73865-111">Events must be declared in the event interface.</span></span>  
  
 <span data-ttu-id="73865-112">Andere öffentliche Member in der Klasse, die nicht in diesen Schnittstellen deklariert sind, werden für COM nicht sichtbar sein, aber für andere .NET Framework-Objekte werden sie sichtbar sein.</span><span class="sxs-lookup"><span data-stu-id="73865-112">Other public members in the class that are not declared in these interfaces will not be visible to COM, but they will be visible to other .NET Framework objects.</span></span>  
  
 <span data-ttu-id="73865-113">Um Eigenschaften und Methoden für COM verfügbar zu machen, müssen Sie diese auf der Klassenschnittstelle deklarieren, sie mit einem `DispId`-Attribut markieren und sie in der Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="73865-113">To expose properties and methods to COM, you must declare them on the class interface and mark them with a `DispId` attribute, and implement them in the class.</span></span> <span data-ttu-id="73865-114">Die Reihenfolge, in der die Elemente in der Schnittstelle deklariert werden, ist die für die COM-Vtable verwendete Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="73865-114">The order in which the members are declared in the interface is the order used for the COM vtable.</span></span>  
  
 <span data-ttu-id="73865-115">Um Ereignisse aus Ihrer Klasse verfügbar zu machen, müssen Sie diese auf der Ereignisschnittstelle deklarieren und sie mit einem `DispId`-Attribut markieren.</span><span class="sxs-lookup"><span data-stu-id="73865-115">To expose events from your class, you must declare them on the events interface and mark them with a `DispId` attribute.</span></span> <span data-ttu-id="73865-116">Die Klasse sollte diese Schnittstelle nicht implementieren.</span><span class="sxs-lookup"><span data-stu-id="73865-116">The class should not implement this interface.</span></span>  
  
 <span data-ttu-id="73865-117">Die Klasse implementiert die Klassenschnittstelle. Es kann mehr als eine Schnittstelle implementieren, aber die erste Implementierung ist die Standard-Klassenschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="73865-117">The class implements the class interface; it can implement more than one interface, but the first implementation will be the default class interface.</span></span> <span data-ttu-id="73865-118">Implementieren Sie die Methoden und Eigenschaften hier, die Sie für COM verfügbar gemacht haben.</span><span class="sxs-lookup"><span data-stu-id="73865-118">Implement the methods and properties exposed to COM here.</span></span> <span data-ttu-id="73865-119">Sie müssen als öffentlich markiert sein und den Deklarationen in der Klassenschnittstelle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="73865-119">They must be marked public and must match the declarations in the class interface.</span></span> <span data-ttu-id="73865-120">Deklarieren Sie außerdem die von der Klasse hier ausgelösten Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="73865-120">Also, declare the events raised by the class here.</span></span> <span data-ttu-id="73865-121">Sie müssen als öffentlich markiert sein und den Deklarationen in der Klassenschnittstelle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="73865-121">They must be marked public and must match the declarations in the events interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73865-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73865-122">Example</span></span>  
 [!code-csharp[csProgGuideInterop#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/example-com-class_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="73865-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73865-123">See Also</span></span>  
 [<span data-ttu-id="73865-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="73865-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="73865-125">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="73865-125">Interoperability</span></span>](../../../csharp/programming-guide/interop/index.md)  
 [<span data-ttu-id="73865-126">Seite „Erstellen“, Projekt-Designer (C#)</span><span class="sxs-lookup"><span data-stu-id="73865-126">Build Page, Project Designer (C#)</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)
