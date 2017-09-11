---
title: Automatisch implementierte Eigenschaften (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
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
ms.openlocfilehash: 92e0037b73f1054673ea8060b71af5bd4db13ca3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="ef018-102">Automatisch implementierte Eigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ef018-102">Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="ef018-103">In C# 3.0 und höher werden Eigenschaftsdeklarationen durch automatisch implementierte Eigenschaften präziser, wenn in den Eigenschaftenzugriffsmethoden keine zusätzliche Logik erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ef018-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="ef018-104">Sie können damit auch Clientcode aktivieren, um Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ef018-104">They also enable client code to create objects.</span></span> <span data-ttu-id="ef018-105">Wenn Sie eine Eigenschaft wie im folgenden Beispiel gezeigt deklarieren, erstellt der Compiler ein privates, anonymes, dahinter liegendes Feld, auf das nur über `get` und `set`-Accessoren zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ef018-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef018-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef018-106">Example</span></span>  
 <span data-ttu-id="ef018-107">Das folgende Beispiel zeigt eine einfache Klasse, die über einige automatisch implementierte Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="ef018-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  
  
 <span data-ttu-id="ef018-108">[!code-cs[csProgGuideLINQ#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ef018-108">[!code-cs[csProgGuideLINQ#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]</span></span>  
  
 <span data-ttu-id="ef018-109">In C#-6 und höher können Sie automatisch implementierte Eigenschaften entsprechend auf Felder initialisieren:</span><span class="sxs-lookup"><span data-stu-id="ef018-109">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 <span data-ttu-id="ef018-110">Die im vorherigen Beispiel gezeigte Klasse kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ef018-110">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="ef018-111">Clientcode kann die Werte in Objekten ändern, nachdem sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="ef018-111">Client code can change the values in objects after they are created.</span></span> <span data-ttu-id="ef018-112">In komplexen Klassen mit signifikantem Verhalten (Methoden) sowie Daten, ist es oft notwendig, öffentliche Eigenschaften zu haben.</span><span class="sxs-lookup"><span data-stu-id="ef018-112">In complex classes that contain significant behavior (methods) as well as data, it is often necessary to have public properties.</span></span> <span data-ttu-id="ef018-113">Bei kleinen Klassen oder Strukturen, die nur einen Satz von Werten (Daten) kapseln und nur wenig oder kein Verhalten besitzen, sollten Sie deshalb Objekte unveränderlich machen, entweder durch Deklarieren der Set-Zugriffsmethode [privat](../../../csharp/language-reference/keywords/private.md) (unveränderlich für Consumer) machen oder nur durch Deklarieren einer Get-Zugriffsmethode (unveränderlich überall außer im Konstruktor).</span><span class="sxs-lookup"><span data-stu-id="ef018-113">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../../csharp/language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="ef018-114">Weitere Informationen finden Sie unter[Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ef018-114">For more information, see [How to: Implement a Lightweight Class with Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="ef018-115">Attribute sind für automatisch implementierte Eigenschaften, jedoch offensichtlich nicht für die dahinter liegenden Felder zulässig, da diese nicht aus dem Quellcode zugänglich sind.</span><span class="sxs-lookup"><span data-stu-id="ef018-115">Attributes are permitted on auto-implemented properties but obviously not on the backing fields since those are not accessible from your source code.</span></span> <span data-ttu-id="ef018-116">Wenn Sie ein Attribut auf das dahinter liegende Feld einer Eigenschaft verwenden müssen, erstellen Sie einfach eine reguläre Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ef018-116">If you must use an attribute on the backing field of a property, just create a regular property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef018-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef018-117">See Also</span></span>  
 <span data-ttu-id="ef018-118">[Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="ef018-118">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="ef018-119">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="ef018-119">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

