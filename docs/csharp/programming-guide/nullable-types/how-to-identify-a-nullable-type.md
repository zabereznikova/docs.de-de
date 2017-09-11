---
title: "Gewusst wie: Identifizieren eines Typs, der NULL-Werte zulässt (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
caps.latest.revision: 7
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
ms.openlocfilehash: c9e05bfe8be45e5b71a8db06ce4f2502c5397fd4
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="2d096-102">Gewusst wie: Identifizieren eines Typs, der NULL-Werte zulässt (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2d096-102">How to: Identify a Nullable Type (C# Programming Guide)</span></span>
<span data-ttu-id="2d096-103">Sie können den C#-Operator [typeof](../../../csharp/language-reference/keywords/typeof.md) zum Erstellen eines <xref:System.Type>-Objekts verwenden, der einen Nullable-Typ darstellt:</span><span class="sxs-lookup"><span data-stu-id="2d096-103">You can use the C# [typeof](../../../csharp/language-reference/keywords/typeof.md) operator to create a <xref:System.Type> object that represents a Nullable type:</span></span>  
  
```  
System.Type type = typeof(int?);  
```  
  
 <span data-ttu-id="2d096-104">Sie können auch die Klassen und Methoden des <xref:System.Reflection>-Namespace verwenden, um <xref:System.Type>-Objekte zu generieren, die Nullable-Typen darstellen.</span><span class="sxs-lookup"><span data-stu-id="2d096-104">You can also use the classes and methods of the <xref:System.Reflection> namespace to generate <xref:System.Type> objects that represent Nullable types.</span></span> <span data-ttu-id="2d096-105">Wenn Sie jedoch versuchen, Typinformationen von Nullable-Variablen zur Laufzeit abzurufen, indem Sie die <xref:System.Object.GetType%2A>-Methode oder den `is`-Operator verwenden, ist das Ergebnis ein <xref:System.Type>-Objekt, das den zugrunde liegenden Typ und nicht den Nullable-Typ selbst darstellt.</span><span class="sxs-lookup"><span data-stu-id="2d096-105">However, if you try to obtain type information from Nullable variables at runtime by using the <xref:System.Object.GetType%2A> method or the `is` operator, the result is a <xref:System.Type> object that represents the underlying type, not the Nullable type itself.</span></span>  
  
 <span data-ttu-id="2d096-106">Das Aufrufen von `GetType` auf einem Nullable-Typ führt dazu, dass ein Boxing-Vorgang ausgeführt wird, wenn der Typ impliziert in <xref:System.Object> konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="2d096-106">Calling `GetType` on a Nullable type causes a boxing operation to be performed when the type is implicitly converted to <xref:System.Object>.</span></span> <span data-ttu-id="2d096-107">Aus diesem Grund gibt <xref:System.Object.GetType%2A> immer ein <xref:System.Type>-Objekt zurück, das den zugrunde liegenden Typ und nicht einen Nullable-Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="2d096-107">Therefore <xref:System.Object.GetType%2A> always returns a <xref:System.Type> object that represents the underlying type, not the Nullable type.</span></span>  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 <span data-ttu-id="2d096-108">Der C#-Operator [is](../../../csharp/language-reference/keywords/is.md) wird auch auf dem zugrunde liegenden Nullable-Typen betrieben.</span><span class="sxs-lookup"><span data-stu-id="2d096-108">The C# [is](../../../csharp/language-reference/keywords/is.md) operator also operates on a Nullable's underlying type.</span></span> <span data-ttu-id="2d096-109">Aus diesem Grund können Sie `is` nicht verwenden, um zu bestimmen, ob eine Variable ein Nullable-Typ ist.</span><span class="sxs-lookup"><span data-stu-id="2d096-109">Therefore you cannot use `is` to determine whether a variable is a Nullable type.</span></span> <span data-ttu-id="2d096-110">Das folgende Beispiel zeigt, dass der `is`-Operator eine Nullable-Variable \<int> als „int“ behandelt.</span><span class="sxs-lookup"><span data-stu-id="2d096-110">The following example shows that the `is` operator treats a Nullable\<int> variable as an int.</span></span>  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## <a name="example"></a><span data-ttu-id="2d096-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d096-111">Example</span></span>  
 <span data-ttu-id="2d096-112">Verwenden Sie den folgenden Code, um zu bestimmen, ob ein <xref:System.Type>-Objekt einen Nullable-Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="2d096-112">Use the following code to determine whether a <xref:System.Type> object represents a Nullable type.</span></span> <span data-ttu-id="2d096-113">Denken Sie daran, dass dieser Code immer FALSE zurückgibt, wenn das `Type`-Objekt von einem Aufruf auf <xref:System.Object.GetType%2A> zurückgegeben wurde, so wie zuvor in diesem Thema beschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="2d096-113">Remember that this code always returns false if the `Type` object was returned from a call to <xref:System.Object.GetType%2A>, as explained earlier in this topic.</span></span>  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d096-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d096-114">See Also</span></span>  
 <span data-ttu-id="2d096-115">[Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="2d096-115">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="2d096-116">Boxing von Typen mit Nullwerten</span><span class="sxs-lookup"><span data-stu-id="2d096-116">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)

