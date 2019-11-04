---
title: 'Vorgehensweise: Überschreiben der ToString-Methode – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 9dd567e537768ceb8b9f61ce58dccd443db38ec7
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419339"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="63089-102">Vorgehensweise: Überschreiben der ToString-Methode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="63089-102">How to: Override the ToString Method (C# Programming Guide)</span></span>

<span data-ttu-id="63089-103">In C# erben alle Klassen oder Strukturen implizit die <xref:System.Object>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="63089-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="63089-104">Deshalb erhält jedes Objekt in C# die <xref:System.Object.ToString%2A>-Methode, die eine Zeichenfolgenrepräsentation dieses Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="63089-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="63089-105">Alle Variablen des Typs `int` verfügen z.B über eine `ToString`-Methode, die es ihnen ermöglicht, ihren Inhalt als Zeichenfolge zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="63089-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 <span data-ttu-id="63089-106">Wenn Sie eine benutzerdefinierte Klasse oder Struktur erstellen, sollten Sie die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen, um Informationen zum Typ an den Clientcode bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="63089-106">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="63089-107">Weitere Informationen zum Verwenden von Formatzeichenfolgen und anderen Arten von benutzerdefinierten Formaten mit der `ToString`-Methode finden Sie unter [Formatierung von Typen](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="63089-107">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="63089-108">Wenn Sie sich entschieden haben, welche Informationen Sie über diese Methode bereitstellen möchten, beziehen Sie auch mit ein, ob Ihre Klasse oder Struktur von nicht vertrauenswürdigem Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="63089-108">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="63089-109">Achten Sie darauf, dass Sie keine Informationen bereitstellen, die von böswilligem Code ausgenutzt werden könnten.</span><span class="sxs-lookup"><span data-stu-id="63089-109">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
<span data-ttu-id="63089-110">Außerkraftsetzen der `ToString`-Methode in Ihrer Klasse oder Struktur:</span><span class="sxs-lookup"><span data-stu-id="63089-110">To override the `ToString` method in your class or struct:</span></span>
  
1. <span data-ttu-id="63089-111">Deklarieren Sie eine `ToString`-Methode mit folgenden Modifizierern und Rückgabetypen:</span><span class="sxs-lookup"><span data-stu-id="63089-111">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. <span data-ttu-id="63089-112">Implementieren Sie die Methode, sodass sie eine Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="63089-112">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="63089-113">Im folgenden Beispiel wird der Name der Klasse neben den für eine bestimmte Instanz der Klasse spezifischen Daten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63089-113">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     <span data-ttu-id="63089-114">Sie können die `ToString`-Methode auch wie im folgenden Beispiel gezeigt prüfen:</span><span class="sxs-lookup"><span data-stu-id="63089-114">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="63089-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63089-115">See also</span></span>

- <xref:System.IFormattable>
- [<span data-ttu-id="63089-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="63089-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="63089-117">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="63089-117">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="63089-118">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="63089-118">Strings</span></span>](../strings/index.md)
- [<span data-ttu-id="63089-119">string</span><span class="sxs-lookup"><span data-stu-id="63089-119">string</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="63089-120">override</span><span class="sxs-lookup"><span data-stu-id="63089-120">override</span></span>](../../language-reference/keywords/override.md)
- [<span data-ttu-id="63089-121">virtual</span><span class="sxs-lookup"><span data-stu-id="63089-121">virtual</span></span>](../../language-reference/keywords/virtual.md)
- [<span data-ttu-id="63089-122">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="63089-122">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
