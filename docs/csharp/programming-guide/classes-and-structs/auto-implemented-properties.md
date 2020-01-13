---
title: Automatisch implementierte Eigenschaften – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 76f16a66fbc01a6a69d91136cfbfe5805b91aea3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705638"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="082ec-102">Automatisch implementierte Eigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="082ec-102">Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="082ec-103">In C# 3.0 und höher werden Eigenschaftsdeklarationen durch automatisch implementierte Eigenschaften präziser, wenn in den Eigenschaftenzugriffsmethoden keine zusätzliche Logik erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="082ec-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="082ec-104">Zudem ermöglichen sie Clientcode das Erstellen von Objekten.</span><span class="sxs-lookup"><span data-stu-id="082ec-104">They also enable client code to create objects.</span></span> <span data-ttu-id="082ec-105">Wenn Sie eine Eigenschaft wie im folgenden Beispiel gezeigt deklarieren, erstellt der Compiler ein privates, anonymes, dahinter liegendes Feld, auf das nur über `get` und `set`-Accessoren zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="082ec-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="082ec-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="082ec-106">Example</span></span>  
 <span data-ttu-id="082ec-107">Das folgende Beispiel zeigt eine einfache Klasse, die über einige automatisch implementierte Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="082ec-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  
  
 <span data-ttu-id="082ec-108">Ab C# 6 können Sie automatisch implementierte Eigenschaften ähnlich wie Felder initialisieren:</span><span class="sxs-lookup"><span data-stu-id="082ec-108">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 <span data-ttu-id="082ec-109">Die im vorherigen Beispiel gezeigte Klasse kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="082ec-109">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="082ec-110">Clientcode kann die Werte in Objekten ändern, nachdem sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="082ec-110">Client code can change the values in objects after they are created.</span></span> <span data-ttu-id="082ec-111">In komplexen Klassen mit signifikantem Verhalten (Methoden) sowie Daten, ist es oft notwendig, öffentliche Eigenschaften zu haben.</span><span class="sxs-lookup"><span data-stu-id="082ec-111">In complex classes that contain significant behavior (methods) as well as data, it is often necessary to have public properties.</span></span> <span data-ttu-id="082ec-112">Bei kleinen Klassen oder Strukturen, die nur einen Satz von Werten (Daten) kapseln und nur wenig oder kein Verhalten besitzen, sollten Sie deshalb Objekte unveränderlich machen, entweder durch Deklarieren der Set-Zugriffsmethode [privat](../../language-reference/keywords/private.md) (unveränderlich für Consumer) machen oder nur durch Deklarieren einer Get-Zugriffsmethode (unveränderlich überall außer im Konstruktor).</span><span class="sxs-lookup"><span data-stu-id="082ec-112">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="082ec-113">Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="082ec-113">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="082ec-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="082ec-114">See also</span></span>

- [<span data-ttu-id="082ec-115">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="082ec-115">Properties</span></span>](./properties.md)
- [<span data-ttu-id="082ec-116">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="082ec-116">Modifiers</span></span>](/dotnet/csharp/language-reference/keywords)
