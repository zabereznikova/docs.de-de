---
title: Boxing von Typen, die NULL-Werte zulassen (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
ms.openlocfilehash: e2c7602bf45f1861d3a32a73824e9fedf0a4d29d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334755"
---
# <a name="boxing-nullable-types-c-programming-guide"></a><span data-ttu-id="ced3f-102">Boxing von Typen, die NULL-Werte zulassen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ced3f-102">Boxing Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="ced3f-103">Objekte, die auf Typen basieren, die NULL-Werte zulassen, werden nur dann umschlossen, wenn das Objekt ungleich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="ced3f-103">Objects based on nullable types are only boxed if the object is non-null.</span></span> <span data-ttu-id="ced3f-104">Wenn <xref:System.Nullable%601.HasValue%2A> `false` ist, wird der Objektverweis `null` zugewiesen, anstatt dass er geboxt wird.</span><span class="sxs-lookup"><span data-stu-id="ced3f-104">If <xref:System.Nullable%601.HasValue%2A> is `false`, the object reference is assigned to `null` instead of boxing.</span></span> <span data-ttu-id="ced3f-105">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ced3f-105">For example:</span></span>  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 <span data-ttu-id="ced3f-106">Wenn das Objekt ungleich NULL und <xref:System.Nullable%601.HasValue%2A> `true` ist, kommt es zum Boxing. Allerdings wird nur der zugrunde liegende Typ, auf dem das auf NULL festlegbare Objekt basiert, geboxt.</span><span class="sxs-lookup"><span data-stu-id="ced3f-106">If the object is non-null -- if <xref:System.Nullable%601.HasValue%2A> is `true` -- then boxing occurs, but only the underlying type that the nullable object is based on is boxed.</span></span> <span data-ttu-id="ced3f-107">Das Boxing eines nicht auf NULL festlegbaren Werttyps umschließt den Werttyp selbst und nicht das <xref:System.Nullable%601?displayProperty=nameWithType>-Objekt, das den Werttyp umschließt.</span><span class="sxs-lookup"><span data-stu-id="ced3f-107">Boxing a non-null nullable value type boxes the value type itself, not the <xref:System.Nullable%601?displayProperty=nameWithType> that wraps the value type.</span></span> <span data-ttu-id="ced3f-108">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ced3f-108">For example:</span></span>  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 <span data-ttu-id="ced3f-109">Die beiden geboxten Objekte stimmen mit Objekten überein, die beim Boxing von nicht auf NULL festlegbaren Typen entstehen.</span><span class="sxs-lookup"><span data-stu-id="ced3f-109">The two boxed objects are identical to those created by boxing non-nullable types.</span></span> <span data-ttu-id="ced3f-110">Sie können, genauso wie nicht auf NULL festlegbare Typen, in auf NULL festlegbare Typen „ausgewickelt“ werden, so wie in folgendem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ced3f-110">And, just like non-nullable boxed types, they can be unboxed into nullable types, as in the following example:</span></span>  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a><span data-ttu-id="ced3f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ced3f-111">Remarks</span></span>  
 <span data-ttu-id="ced3f-112">Das Verhalten von umschlossenen, auf NULL festlegbaren Typen hat zwei Vorteile:</span><span class="sxs-lookup"><span data-stu-id="ced3f-112">The behavior of nullable types when boxed provides two advantages:</span></span>  
  
1.  <span data-ttu-id="ced3f-113">Auf NULL festlegbare Objekte und ihre umschlossenen Gegenstücke könne auf NULL getestet werden:</span><span class="sxs-lookup"><span data-stu-id="ced3f-113">Nullable objects and their boxed counterpart can be tested for null:</span></span>  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  <span data-ttu-id="ced3f-114">Umschlossene, auf NULL festlegbare Typen unterstützen die Funktionen des zugrundeliegenden Typs vollständig:</span><span class="sxs-lookup"><span data-stu-id="ced3f-114">Boxed nullable types fully support the functionality of the underlying type:</span></span>  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ced3f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ced3f-115">See Also</span></span>  
 [<span data-ttu-id="ced3f-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ced3f-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ced3f-117">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="ced3f-117">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="ced3f-118">Gewusst wie: Identifizieren eines Typs mit Nullwerten</span><span class="sxs-lookup"><span data-stu-id="ced3f-118">How to: Identify a Nullable Type</span></span>](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)
