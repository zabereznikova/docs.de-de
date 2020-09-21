---
title: Automatisch implementierte Eigenschaften – C#-Programmierhandbuch
description: Für eine automatisch implementierte Eigenschaft in C# erstellt der Compiler eine private, anonyme Unterstützungsvariable, auf die nur über Zugriffsmethoden „get“ und „set“ der Eigenschaft zugegriffen werden kann.
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 72f774d84266292412be9b954fc206debc8ac55e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555899"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="2be64-103">Automatisch implementierte Eigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2be64-103">Auto-Implemented Properties (C# Programming Guide)</span></span>

<span data-ttu-id="2be64-104">In C# 3.0 und höher werden Eigenschaftsdeklarationen durch automatisch implementierte Eigenschaften präziser, wenn in den Eigenschaftenzugriffsmethoden keine zusätzliche Logik erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2be64-104">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="2be64-105">Zudem ermöglichen sie Clientcode das Erstellen von Objekten.</span><span class="sxs-lookup"><span data-stu-id="2be64-105">They also enable client code to create objects.</span></span> <span data-ttu-id="2be64-106">Wenn Sie eine Eigenschaft wie im folgenden Beispiel gezeigt deklarieren, erstellt der Compiler ein privates, anonymes, dahinter liegendes Feld, auf das nur über `get` und `set`-Accessoren zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2be64-106">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>
  
## <a name="example"></a><span data-ttu-id="2be64-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2be64-107">Example</span></span>

<span data-ttu-id="2be64-108">Das folgende Beispiel zeigt eine einfache Klasse, die über einige automatisch implementierte Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="2be64-108">The following example shows a simple class that has some auto-implemented properties:</span></span>  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

<span data-ttu-id="2be64-109">Sie können keine automatisch implementierten Eigenschaften in Schnittstellen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="2be64-109">You can't declare auto-implemented properties in interfaces.</span></span> <span data-ttu-id="2be64-110">Automatisch implementierte Eigenschaften deklarieren ein Unterstützungsfeld für die private Instanz. Schnittstellen deklarieren möglicherweise keine Instanzfelder.</span><span class="sxs-lookup"><span data-stu-id="2be64-110">Auto-implemented properties declare a private instance backing field, and interfaces may not declare instance fields.</span></span> <span data-ttu-id="2be64-111">Beim Deklarieren einer Eigenschaft in einer Schnittstelle, ohne einen Text zu definieren, wird eine Eigenschaft mit Zugriffsmethoden deklariert, die von allen Typen implementiert werden muss, die die Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="2be64-111">Declaring a property in an interface without defining a body declares a property with accessors that must be implemented by each type that implements that interface.</span></span>

<span data-ttu-id="2be64-112">Ab C# 6 können Sie automatisch implementierte Eigenschaften ähnlich wie Felder initialisieren:</span><span class="sxs-lookup"><span data-stu-id="2be64-112">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  

```csharp  
public string FirstName { get; set; } = "Jane";  
```  

<span data-ttu-id="2be64-113">Die im vorherigen Beispiel gezeigte Klasse kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2be64-113">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="2be64-114">Der Clientcode kann die Werte in Objekten nach der Erstellung ändern.</span><span class="sxs-lookup"><span data-stu-id="2be64-114">Client code can change the values in objects after creation.</span></span> <span data-ttu-id="2be64-115">In komplexen Klassen mit signifikantem Verhalten (Methoden) sowie Daten, ist es oft notwendig, öffentliche Eigenschaften zu haben.</span><span class="sxs-lookup"><span data-stu-id="2be64-115">In complex classes that contain significant behavior (methods) as well as data, it's often necessary to have public properties.</span></span> <span data-ttu-id="2be64-116">Bei kleinen Klassen oder Strukturen, die nur einen Satz von Werten (Daten) kapseln und nur wenig oder kein Verhalten besitzen, sollten Sie deshalb Objekte unveränderlich machen, entweder durch Deklarieren der Set-Zugriffsmethode [privat](../../language-reference/keywords/private.md) (unveränderlich für Consumer) machen oder nur durch Deklarieren einer Get-Zugriffsmethode (unveränderlich überall außer im Konstruktor).</span><span class="sxs-lookup"><span data-stu-id="2be64-116">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="2be64-117">Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2be64-117">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2be64-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2be64-118">See also</span></span>

- [<span data-ttu-id="2be64-119">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2be64-119">Properties</span></span>](./properties.md)
- [<span data-ttu-id="2be64-120">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="2be64-120">Modifiers</span></span>](../../language-reference/keywords/index.md)
