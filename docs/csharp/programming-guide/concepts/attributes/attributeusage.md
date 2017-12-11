---
title: AttributeUsage (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 22c45568-9a6a-4c2f-8480-f38c1caa0a99
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e9351ee10b523145ace1249bf17388da0cdba277
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2017
---
# <a name="attributeusage-c"></a><span data-ttu-id="c0408-102">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="c0408-102">AttributeUsage (C#)</span></span>
<span data-ttu-id="c0408-103">Bestimmt, wie eine benutzerdefinierte Attributklasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0408-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="c0408-104">`AttributeUsage` ist ein Attribut, dass auf benutzerdefinierte Attributdefinitionen zur Steuerung der Anwendung neuer Attribute angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0408-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="c0408-105">Die Standardeinstellungen sehen wie folgt aus, wenn Sie explizit angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="c0408-105">The default settings look like this when applied explicitly:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All,  
                   AllowMultiple = false,  
                   Inherited = true)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="c0408-106">In diesem Beispiel kann die Klasse `NewAttribute` auf jede attributfähige Codeentität angewendet werden; allerdings nur einmal pro Entität.</span><span class="sxs-lookup"><span data-stu-id="c0408-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="c0408-107">Wenn sie auf eine Basisklasse angewendet wird, wird sie an eine abgeleitete Klasse vererbt.</span><span class="sxs-lookup"><span data-stu-id="c0408-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="c0408-108">Die Argumente `AllowMultiple` und `Inherited` sind optional, sodass dieser Code die gleiche Wirkung hat:</span><span class="sxs-lookup"><span data-stu-id="c0408-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="c0408-109">Das erste `AttributeUsage`-Argument muss mindestens ein Element der <xref:System.AttributeTargets>-Enumeration sein.</span><span class="sxs-lookup"><span data-stu-id="c0408-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="c0408-110">Mehrere Zieltypen können mithilfe des OR-Operator wie folgt verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="c0408-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Property | AttributeTargets.Field)]  
class NewPropertyOrFieldAttribute : Attribute { }  
```  
  
 <span data-ttu-id="c0408-111">Wenn das `AllowMultiple`-Argument auf `true` festgelegt ist, kann das daraus entstehende Attribut wie folgt mehr als einmal auf eine einzelne Entität angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="c0408-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]  
class MultiUseAttr : Attribute { }  
  
[MultiUseAttr]  
[MultiUseAttr]  
class Class1 { }  
  
[MultiUseAttr, MultiUseAttr]  
class Class2 { }  
```  
  
 <span data-ttu-id="c0408-112">In diesem Fall kann `MultiUseAttr` wiederholt angewendet werden, da `AllowMultiple` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c0408-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="c0408-113">Beide gezeigten Formate für das Anwenden von mehreren Attributen sind gültig.</span><span class="sxs-lookup"><span data-stu-id="c0408-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="c0408-114">Wenn `Inherited` auf `false` festgelegt ist, wird das Attribut nicht an die von der attribuierten Klasse abgeleiteten Klassen vererbt.</span><span class="sxs-lookup"><span data-stu-id="c0408-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="c0408-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c0408-115">For example:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, Inherited = false)]  
class Attr1 : Attribute { }  
  
[Attr1]  
class BClass { }  
  
class DClass : BClass { }  
```  
  
 <span data-ttu-id="c0408-116">In diesem Fall wird `Attr1` nicht durch Vererbung auf `DClass` angewendet.</span><span class="sxs-lookup"><span data-stu-id="c0408-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0408-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c0408-117">Remarks</span></span>  
 <span data-ttu-id="c0408-118">Das `AttributeUsage`-Attribut ist für die einmalige Nutzung bestimmt; es kann nicht mehr als einmal auf dieselbe Klasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0408-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="c0408-119">`AttributeUsage` ist ein Alias für <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c0408-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="c0408-120">Weitere Informationen finden Sie unter [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="c0408-120">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0408-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0408-121">Example</span></span>  
 <span data-ttu-id="c0408-122">In folgendem Beispiel wird die Wirkung der Argumente `Inherited` und `AllowMultiple` auf das Attribut `AttributeUsage` und die Enumeration benutzerdefinierter Attribute veranschaulicht, die auf eine Klasse angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="c0408-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
```csharp  
using System;  

// Create some custom attributes:  
[AttributeUsage(System.AttributeTargets.Class, Inherited = false)]  
class A1 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class)]  
class A2 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class, AllowMultiple = true)]  
class A3 : System.Attribute { }  
  
// Apply custom attributes to classes:  
[A1, A2]  
class BaseClass { }  
  
[A3, A3]  
class DerivedClass : BaseClass { }  
  
public class TestAttributeUsage  
{  
    static void Main()  
    {  
        BaseClass b = new BaseClass();  
        DerivedClass d = new DerivedClass();  
  
        // Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:");  
        object[] attrs = b.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
  
        Console.WriteLine("Attributes on Derived Class:");  
        attrs = d.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
    }  
}  
```  
  
## <a name="sample-output"></a><span data-ttu-id="c0408-123">Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="c0408-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0408-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0408-124">See Also</span></span>  
 <xref:System.Attribute>  
 <xref:System.Reflection>  
 [<span data-ttu-id="c0408-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c0408-125">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c0408-126">Attribute</span><span class="sxs-lookup"><span data-stu-id="c0408-126">Attributes</span></span>](../../../../../docs/standard/attributes/index.md)  
 [<span data-ttu-id="c0408-127">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="c0408-127">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="c0408-128">Attribute</span><span class="sxs-lookup"><span data-stu-id="c0408-128">Attributes</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="c0408-129">Erstellen benutzerdefinierter Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="c0408-129">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="c0408-130">Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))</span><span class="sxs-lookup"><span data-stu-id="c0408-130">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
