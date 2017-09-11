---
title: using-Anweisung (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: 31
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
ms.openlocfilehash: 1129efd8a1c4058a9648eab61f98cdcef7e9f2f7
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="using-directive-c-reference"></a><span data-ttu-id="b5553-102">using-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b5553-102">using Directive (C# Reference)</span></span>
<span data-ttu-id="b5553-103">Die `using`-Direktive hat drei Verwendungszwecke:</span><span class="sxs-lookup"><span data-stu-id="b5553-103">The `using` directive has three uses:</span></span>  
  
-   <span data-ttu-id="b5553-104">Sie ermöglicht die Verwendung von Typen in einem Namespace, sodass Sie die Verwendung eines Typs in diesem Namespace nicht qualifizieren müssen:</span><span class="sxs-lookup"><span data-stu-id="b5553-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   <span data-ttu-id="b5553-105">Ermöglicht den Zugriff auf statische Member eines Typs, ohne den Zugriff mit dem Typnamen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="b5553-105">To allow you to access static members of a type without having to qualify the access with the type name.</span></span> 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    <span data-ttu-id="b5553-106">Weitere Informationen finden Sie unter [using static-Direktive (C#-Referenz)](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="b5553-106">For more information, see the [using static directive](using-static.md).</span></span>

-   <span data-ttu-id="b5553-107">Erstellen eines Alias für einen Namespace oder Typ.</span><span class="sxs-lookup"><span data-stu-id="b5553-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="b5553-108">Dies wird als *using-Aliasdirektive* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b5553-108">This is called a *using alias directive*.</span></span>  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 <span data-ttu-id="b5553-109">Das `using`-Schlüsselwort wird auch zum Erstellen von *using-Anweisungen* verwendet, mit denen sichergestellt wird, dass <xref:System.IDisposable>-Objekte wie Dateien und Schriftarten richtig verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b5553-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="b5553-110">Weitere Informationen finden Sie unter [using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b5553-110">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
## <a name="using-static-type"></a><span data-ttu-id="b5553-111">Verwenden statischer Typen</span><span class="sxs-lookup"><span data-stu-id="b5553-111">Using Static Type</span></span>  
 <span data-ttu-id="b5553-112">Sie können auf statische Member eines Typs zugreifen, ohne den Zugriff mit dem Typnamen zu qualifizieren:</span><span class="sxs-lookup"><span data-stu-id="b5553-112">You can access static members of a type without having to qualify the access with the type name:</span></span>  
  
```csharp  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="b5553-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5553-113">Remarks</span></span>  
 <span data-ttu-id="b5553-114">Der Bereich einer `using`-Direktive ist auf die Datei beschränkt, in der er enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b5553-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>  
  
 <span data-ttu-id="b5553-115">Erstellen Sie einen `using`-Alias, um das Qualifizieren eines Bezeichners in einen Namespace oder Typ zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="b5553-115">Create a `using` alias to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="b5553-116">Der rechten Seite einer using-Aliasdirektive muss immer ein vollqualifizierter Typ sein, unabhängig von den using-Direktiven davor.</span><span class="sxs-lookup"><span data-stu-id="b5553-116">The right side of a using alias directive must always be a fully-qualified type regardless of the using directives that come before it.</span></span>  
  
 <span data-ttu-id="b5553-117">Erstellen Sie eine `using`-Direktive, um die Typen in einem Namespace zu verwenden, ohne den Namespace angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="b5553-117">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="b5553-118">Eine `using`-Direktive ermöglicht Ihnen nicht den Zugriff auf Namespaces, die im angegebenen Namespace geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="b5553-118">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>  
  
 <span data-ttu-id="b5553-119">Gibt zwei Kategorien von Namespaces: benutzerdefinierte und systemdefinierte Namespaces.</span><span class="sxs-lookup"><span data-stu-id="b5553-119">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="b5553-120">Benutzerdefinierte Namespaces sind Namespaces, die im Code definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b5553-120">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="b5553-121">Eine Liste der systemdefinierten Namespaces finden Sie unter [.NET Framework-Klassenbibliothek](http://go.microsoft.com/fwlink/?LinkID=227195).</span><span class="sxs-lookup"><span data-stu-id="b5553-121">For a list of the system-defined namespaces, see [.NET Framework Class Library](http://go.microsoft.com/fwlink/?LinkID=227195).</span></span>  
  
 <span data-ttu-id="b5553-122">Beispiele für das Verweisen auf Methoden in anderen Assemblys finden Sie unter [Erstellen und Verwenden von C#-DLLs](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span><span class="sxs-lookup"><span data-stu-id="b5553-122">For examples on referencing methods in other assemblies, see [Creating and Using C# DLLs](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="b5553-123">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="b5553-123">Example 1</span></span>  
  
 <span data-ttu-id="b5553-124">Das folgende Beispiel zeigt, wie Sie einen `using`-Alias für einen Namespace definieren und verwenden:</span><span class="sxs-lookup"><span data-stu-id="b5553-124">The following example shows how to define and use a `using` alias for a namespace:</span></span>  
  
 <span data-ttu-id="b5553-125">[!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b5553-125">[!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]</span></span>  
  
 <span data-ttu-id="b5553-126">Eine using-Aliasanweisung kann auf der rechten Seite nicht über einen offenen generischen Typen verfügen.</span><span class="sxs-lookup"><span data-stu-id="b5553-126">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="b5553-127">Sie können zum Beispiel keinen using-Alias für „List\<T>“ erstellen, jedoch für „List\<int>“.</span><span class="sxs-lookup"><span data-stu-id="b5553-127">For example, you cannot create a using alias for a List\<T>, but you can create one for a List\<int>.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="b5553-128">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="b5553-128">Example 2</span></span>  
  
 <span data-ttu-id="b5553-129">Das folgende Beispiel zeigt, wie Sie eine `using`-Direktive und einen `using`-Alias für eine Klasse definieren:</span><span class="sxs-lookup"><span data-stu-id="b5553-129">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>  
  
 <span data-ttu-id="b5553-130">[!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b5553-130">[!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b5553-131">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="b5553-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b5553-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5553-132">See Also</span></span>  
 <span data-ttu-id="b5553-133">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b5553-133">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b5553-134">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b5553-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b5553-135">[Using-Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="b5553-135">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
 <span data-ttu-id="b5553-136">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="b5553-136">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="b5553-137">[Namespace Keywords (Schlüsselwörter des Namespace)](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="b5553-137">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="b5553-138">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="b5553-138">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 [<span data-ttu-id="b5553-139">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b5553-139">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

