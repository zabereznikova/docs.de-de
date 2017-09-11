---
title: "Gewusst wie: Überschreiben der ToString-Methode (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: 21
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
ms.openlocfilehash: 60cec855286a3bb572a0bacd08c0f7920a1fc912
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="9e568-102">Gewusst wie: Überschreiben der ToString-Methode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9e568-102">How to: Override the ToString Method (C# Programming Guide)</span></span>
<span data-ttu-id="9e568-103">In C# erben alle Klassen oder Strukturen implizit die <xref:System.Object>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9e568-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="9e568-104">Deshalb erhält jedes Objekt in C# die <xref:System.Object.ToString%2A>-Methode, die eine Zeichenfolgenrepräsentation dieses Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9e568-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="9e568-105">Alle Variablen des Typs `int` verfügen z.B über eine `ToString`-Methode, die es ihnen ermöglicht, ihren Inhalt als Zeichenfolge zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="9e568-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 <span data-ttu-id="9e568-106">[!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9e568-106">[!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]</span></span>  
  
 <span data-ttu-id="9e568-107">Wenn Sie eine benutzerdefinierte Klasse oder Struktur erstellen, sollten Sie die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen, um Informationen zum Typ an den Clientcode bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9e568-107">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="9e568-108">Weitere Informationen zum Verwenden von Formatzeichenfolgen und anderen Arten von benutzerdefinierten Formaten mit der `ToString`-Methode finden Sie unter [Formatierung von Typen](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="9e568-108">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9e568-109">Wenn Sie sich entschieden haben, welche Informationen Sie über diese Methode bereitstellen möchten, beziehen Sie auch mit ein, ob Ihre Klasse oder Struktur von nicht vertrauenswürdigem Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e568-109">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="9e568-110">Achten Sie darauf, dass Sie keine Informationen bereitstellen, die von böswilligem Code ausgenutzt werden könnten.</span><span class="sxs-lookup"><span data-stu-id="9e568-110">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a><span data-ttu-id="9e568-111">Außerkraftsetzen der ToString-Methode in Ihrer Klasse oder Struktur</span><span class="sxs-lookup"><span data-stu-id="9e568-111">To override the ToString method in your class or struct</span></span>  
  
1.  <span data-ttu-id="9e568-112">Deklarieren Sie eine `ToString`-Methode mit folgenden Modifizierern und Rückgabetypen:</span><span class="sxs-lookup"><span data-stu-id="9e568-112">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  <span data-ttu-id="9e568-113">Implementieren Sie die Methode, sodass sie eine Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9e568-113">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="9e568-114">Im folgenden Beispiel wird der Name der Klasse neben den für eine bestimmte Instanz der Klasse spezifischen Daten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9e568-114">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     <span data-ttu-id="9e568-115">[!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9e568-115">[!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]</span></span>  
  
     <span data-ttu-id="9e568-116">Sie können die `ToString`-Methode auch wie im folgenden Beispiel gezeigt prüfen:</span><span class="sxs-lookup"><span data-stu-id="9e568-116">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     <span data-ttu-id="9e568-117">[!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="9e568-117">[!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e568-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e568-118">See Also</span></span>  
 <span data-ttu-id="9e568-119"><xref:System.IFormattable></span><span class="sxs-lookup"><span data-stu-id="9e568-119"><xref:System.IFormattable></span></span>   
 <span data-ttu-id="9e568-120">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9e568-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9e568-121">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="9e568-121">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="9e568-122">[Zeichenfolgen](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="9e568-122">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="9e568-123">[string](../../../csharp/language-reference/keywords/string.md) </span><span class="sxs-lookup"><span data-stu-id="9e568-123">[string](../../../csharp/language-reference/keywords/string.md) </span></span>  
 <span data-ttu-id="9e568-124">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="9e568-124">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 <span data-ttu-id="9e568-125">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="9e568-125">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 <span data-ttu-id="9e568-126">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span><span class="sxs-lookup"><span data-stu-id="9e568-126">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span></span>  
 [<span data-ttu-id="9e568-127">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="9e568-127">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)

