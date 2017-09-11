---
title: 'Gewusst wie: Indizierte Eigenschaften bei der COM-Interop-Programmierung (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: 20
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
ms.openlocfilehash: 19e620415adefd6190d3896377eaf6a7cf944f28
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="c65f0-102">Gewusst wie: Indizierte Eigenschaften bei der COM-Interop-Programmierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c65f0-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="c65f0-103">*Indizierte Eigenschaften* verbessern die Verarbeitung von COM-Eigenschaften mit Parametern in der C#-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="c65f0-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="c65f0-104">Indizierte Eigenschaften arbeiten zusammen mit anderen Funktionen in Visual C#, wie z.B. [benannte und optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) und neuen Typinformationen ([dynamisch](../../../csharp/language-reference/keywords/dynamic.md)) und [eingebettete Typinformationen](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), um die Microsoft Office-Programmierung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="c65f0-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)), and [embedded type information](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="c65f0-105">In früheren Versionen von C# waren Methoden nur als Eigenschaften zugänglich, wenn die `get`-Methode keine Parameter und die `set`-Methode nur einen Wertparameter hatte.</span><span class="sxs-lookup"><span data-stu-id="c65f0-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="c65f0-106">Allerdings erfüllen nicht alle COM-Eigenschaften diese Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="c65f0-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="c65f0-107">Die Eigenschaft [Range](http://go.microsoft.com/fwlink/?LinkId=166053) in Excel verfügt über eine `get`-Zugriffsmethode, für die ein Parameter für den Namen des Bereichs erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c65f0-107">For example, the Excel [Range](http://go.microsoft.com/fwlink/?LinkId=166053) property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="c65f0-108">Früher mussten Sie stattdessen die `get_Range`-Methode verwenden, weil Sie nicht direkt auf die `Range`-Methode zugreifen konnten. Dies wird in folgendem Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c65f0-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 <span data-ttu-id="c65f0-109">[!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c65f0-109">[!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]</span></span>  
  
 <span data-ttu-id="c65f0-110">Mit indizierte Eigenschaften können Sie stattdessen Folgendes schreiben:</span><span class="sxs-lookup"><span data-stu-id="c65f0-110">Indexed properties enable you to write the following instead:</span></span>  
  
 <span data-ttu-id="c65f0-111">[!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c65f0-111">[!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c65f0-112">Im vorherigen Beispiel wurde auch die Funktion [Optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) verwendet, mit der Sie `Type.Missing` weglassen können.</span><span class="sxs-lookup"><span data-stu-id="c65f0-112">The previous example also uses the [optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="c65f0-113">Für das Festlegen der `Value`Eigenschaft des [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx)-Objekts in Visual C# 2008 oder früher sind zwei Argumente erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c65f0-113">Similarly to set the value of the `Value` property of a [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) object in Visual C# 2008 and earlier, two arguments are required.</span></span> <span data-ttu-id="c65f0-114">Eines dieser Argumente stellt ein Argument für einen optionalen Parameter bereit, der den Typ des Bereichswerts angibt.</span><span class="sxs-lookup"><span data-stu-id="c65f0-114">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="c65f0-115">Das andere Argument stellt den Wert für die `Value`-Eigenschaft bereit.</span><span class="sxs-lookup"><span data-stu-id="c65f0-115">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="c65f0-116">In den folgenden Beispielen werden diese Techniken veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c65f0-116">The following examples illustrate these techniques.</span></span> <span data-ttu-id="c65f0-117">Beide legen den Wert der Zelle A1 auf `Name` fest.</span><span class="sxs-lookup"><span data-stu-id="c65f0-117">Both set the value of the A1 cell to `Name`.</span></span>
  
 <span data-ttu-id="c65f0-118">[!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c65f0-118">[!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]</span></span>  
  
 <span data-ttu-id="c65f0-119">Mit indizierte Eigenschaften können Sie stattdessen folgenden Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="c65f0-119">Indexed properties enable you to write the following code instead.</span></span>  
  
 <span data-ttu-id="c65f0-120">[!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="c65f0-120">[!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]</span></span>  
  
 <span data-ttu-id="c65f0-121">Sie können nicht Ihre eigenen indizierten Eigenschaften erstellen.</span><span class="sxs-lookup"><span data-stu-id="c65f0-121">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="c65f0-122">Die Funktion unterstützt nur die Nutzung vorhandener indizierter Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c65f0-122">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c65f0-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c65f0-123">Example</span></span>  
 <span data-ttu-id="c65f0-124">Der folgende Code veranschaulicht das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c65f0-124">The following code shows a complete example.</span></span> <span data-ttu-id="c65f0-125">Weitere Informationen zum Einrichten eines Projekts, das auf die Office-API zugreift, finden Sie unter [Vorgehensweise: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="c65f0-125">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
 <span data-ttu-id="c65f0-126">[!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="c65f0-126">[!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65f0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c65f0-127">See Also</span></span>  
 <span data-ttu-id="c65f0-128">[Benannte und optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="c65f0-128">[Named and Optional Arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span></span>  
 <span data-ttu-id="c65f0-129">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="c65f0-129">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span></span>  
 <span data-ttu-id="c65f0-130">[Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="c65f0-130">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="c65f0-131">[Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span><span class="sxs-lookup"><span data-stu-id="c65f0-131">[How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span></span>  
 <span data-ttu-id="c65f0-132">[Vorgehensweise: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md) </span><span class="sxs-lookup"><span data-stu-id="c65f0-132">[How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md) </span></span>  
 [<span data-ttu-id="c65f0-133">Exemplarische Vorgehensweise: Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="c65f0-133">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)

