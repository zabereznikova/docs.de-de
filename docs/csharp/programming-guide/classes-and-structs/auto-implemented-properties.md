---
title: Automatisch implementierte Eigenschaften – C#-Programmierhandbuch
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 791455c1eaef752da2b551e20187d390ca6c65e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170324"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="08a1e-102">Automatisch implementierte Eigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="08a1e-102">Auto-Implemented Properties (C# Programming Guide)</span></span>

<span data-ttu-id="08a1e-103">In C# 3.0 und höher werden Eigenschaftsdeklarationen durch automatisch implementierte Eigenschaften präziser, wenn in den Eigenschaftenzugriffsmethoden keine zusätzliche Logik erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="08a1e-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="08a1e-104">Zudem ermöglichen sie Clientcode das Erstellen von Objekten.</span><span class="sxs-lookup"><span data-stu-id="08a1e-104">They also enable client code to create objects.</span></span> <span data-ttu-id="08a1e-105">Wenn Sie eine Eigenschaft wie im folgenden Beispiel gezeigt deklarieren, erstellt der Compiler ein privates, anonymes, dahinter liegendes Feld, auf das nur über `get` und `set`-Accessoren zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="08a1e-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>
  
## <a name="example"></a><span data-ttu-id="08a1e-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08a1e-106">Example</span></span>

<span data-ttu-id="08a1e-107">Das folgende Beispiel zeigt eine einfache Klasse, die über einige automatisch implementierte Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="08a1e-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

<span data-ttu-id="08a1e-108">Sie können keine automatisch implementierten Eigenschaften in Schnittstellen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="08a1e-108">You can't declare auto-implemented properties in interfaces.</span></span> <span data-ttu-id="08a1e-109">Automatisch implementierte Eigenschaften deklarieren ein Unterstützungsfeld für die private Instanz. Schnittstellen deklarieren möglicherweise keine Instanzfelder.</span><span class="sxs-lookup"><span data-stu-id="08a1e-109">Auto-implemented properties declare a private instance backing field, and interfaces may not declare instance fields.</span></span> <span data-ttu-id="08a1e-110">Beim Deklarieren einer Eigenschaft in einer Schnittstelle, ohne einen Text zu definieren, wird eine Eigenschaft mit Zugriffsmethoden deklariert, die von allen Typen implementiert werden muss, die die Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="08a1e-110">Declaring a property in an interface without defining a body declares a property with accessors that must be implemented by each type that implements that interface.</span></span>

<span data-ttu-id="08a1e-111">Ab C# 6 können Sie automatisch implementierte Eigenschaften ähnlich wie Felder initialisieren:</span><span class="sxs-lookup"><span data-stu-id="08a1e-111">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  

```csharp  
public string FirstName { get; set; } = "Jane";  
```  

<span data-ttu-id="08a1e-112">Die im vorherigen Beispiel gezeigte Klasse kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="08a1e-112">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="08a1e-113">Der Clientcode kann die Werte in Objekten nach der Erstellung ändern.</span><span class="sxs-lookup"><span data-stu-id="08a1e-113">Client code can change the values in objects after creation.</span></span> <span data-ttu-id="08a1e-114">In komplexen Klassen mit signifikantem Verhalten (Methoden) sowie Daten, ist es oft notwendig, öffentliche Eigenschaften zu haben.</span><span class="sxs-lookup"><span data-stu-id="08a1e-114">In complex classes that contain significant behavior (methods) as well as data, it's often necessary to have public properties.</span></span> <span data-ttu-id="08a1e-115">Bei kleinen Klassen oder Strukturen, die nur einen Satz von Werten (Daten) kapseln und nur wenig oder kein Verhalten besitzen, sollten Sie deshalb Objekte unveränderlich machen, entweder durch Deklarieren der Set-Zugriffsmethode [privat](../../language-reference/keywords/private.md) (unveränderlich für Consumer) machen oder nur durch Deklarieren einer Get-Zugriffsmethode (unveränderlich überall außer im Konstruktor).</span><span class="sxs-lookup"><span data-stu-id="08a1e-115">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="08a1e-116">Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="08a1e-116">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="08a1e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08a1e-117">See also</span></span>

- [<span data-ttu-id="08a1e-118">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="08a1e-118">Properties</span></span>](./properties.md)
- [<span data-ttu-id="08a1e-119">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="08a1e-119">Modifiers</span></span>](/dotnet/csharp/language-reference/keywords)
