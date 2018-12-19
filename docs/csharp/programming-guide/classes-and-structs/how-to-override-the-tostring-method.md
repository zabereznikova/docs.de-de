---
title: 'Vorgehensweise: Überschreiben der ToString-Methode – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 0be35b64e9df3ec2a78c62735b1b7072e092f073
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240735"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="f3a98-102">Vorgehensweise: Überschreiben der ToString-Methode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f3a98-102">How to: Override the ToString Method (C# Programming Guide)</span></span>
<span data-ttu-id="f3a98-103">In C# erben alle Klassen oder Strukturen implizit die <xref:System.Object>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f3a98-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="f3a98-104">Deshalb erhält jedes Objekt in C# die <xref:System.Object.ToString%2A>-Methode, die eine Zeichenfolgenrepräsentation dieses Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f3a98-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="f3a98-105">Alle Variablen des Typs `int` verfügen z.B über eine `ToString`-Methode, die es ihnen ermöglicht, ihren Inhalt als Zeichenfolge zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="f3a98-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 <span data-ttu-id="f3a98-106">Wenn Sie eine benutzerdefinierte Klasse oder Struktur erstellen, sollten Sie die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen, um Informationen zum Typ an den Clientcode bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f3a98-106">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="f3a98-107">Weitere Informationen zum Verwenden von Formatzeichenfolgen und anderen Arten von benutzerdefinierten Formaten mit der `ToString`-Methode finden Sie unter [Formatierung von Typen](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="f3a98-107">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f3a98-108">Wenn Sie sich entschieden haben, welche Informationen Sie über diese Methode bereitstellen möchten, beziehen Sie auch mit ein, ob Ihre Klasse oder Struktur von nicht vertrauenswürdigem Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f3a98-108">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="f3a98-109">Achten Sie darauf, dass Sie keine Informationen bereitstellen, die von böswilligem Code ausgenutzt werden könnten.</span><span class="sxs-lookup"><span data-stu-id="f3a98-109">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a><span data-ttu-id="f3a98-110">Außerkraftsetzen der ToString-Methode in Ihrer Klasse oder Struktur</span><span class="sxs-lookup"><span data-stu-id="f3a98-110">To override the ToString method in your class or struct</span></span>  
  
1.  <span data-ttu-id="f3a98-111">Deklarieren Sie eine `ToString`-Methode mit folgenden Modifizierern und Rückgabetypen:</span><span class="sxs-lookup"><span data-stu-id="f3a98-111">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  <span data-ttu-id="f3a98-112">Implementieren Sie die Methode, sodass sie eine Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f3a98-112">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="f3a98-113">Im folgenden Beispiel wird der Name der Klasse neben den für eine bestimmte Instanz der Klasse spezifischen Daten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f3a98-113">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     <span data-ttu-id="f3a98-114">Sie können die `ToString`-Methode auch wie im folgenden Beispiel gezeigt prüfen:</span><span class="sxs-lookup"><span data-stu-id="f3a98-114">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f3a98-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3a98-115">See Also</span></span>

- <xref:System.IFormattable>  
- [<span data-ttu-id="f3a98-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f3a98-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f3a98-117">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="f3a98-117">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="f3a98-118">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f3a98-118">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
- [<span data-ttu-id="f3a98-119">string</span><span class="sxs-lookup"><span data-stu-id="f3a98-119">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
- [<span data-ttu-id="f3a98-120">new</span><span class="sxs-lookup"><span data-stu-id="f3a98-120">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
- [<span data-ttu-id="f3a98-121">override</span><span class="sxs-lookup"><span data-stu-id="f3a98-121">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
- [<span data-ttu-id="f3a98-122">virtual</span><span class="sxs-lookup"><span data-stu-id="f3a98-122">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
- [<span data-ttu-id="f3a98-123">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="f3a98-123">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
