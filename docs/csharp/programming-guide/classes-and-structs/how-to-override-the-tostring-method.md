---
title: 'Gewusst wie: Überschreiben der ToString-Methode – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie die ToString-Methode in C# überschreiben. Jede Klasse oder Struktur erbt ein Objekt und ruft „ToString“ ab. Dadurch wird eine Zeichenfolgendarstellung dieses Objekts zurückgegeben.
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: de56ea10ea15f497f9375c2449acbae1d0c8978a
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099262"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="3b193-104">Gewusst wie: Überschreiben der ToString-Methode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3b193-104">How to override the ToString method (C# Programming Guide)</span></span>

<span data-ttu-id="3b193-105">In C# erben alle Klassen oder Strukturen implizit die <xref:System.Object>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3b193-105">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="3b193-106">Deshalb erhält jedes Objekt in C# die <xref:System.Object.ToString%2A>-Methode, die eine Zeichenfolgenrepräsentation dieses Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3b193-106">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="3b193-107">Alle Variablen des Typs `int` verfügen z.B über eine `ToString`-Methode, die es ihnen ermöglicht, ihren Inhalt als Zeichenfolge zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="3b193-107">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 <span data-ttu-id="3b193-108">Wenn Sie eine benutzerdefinierte Klasse oder Struktur erstellen, sollten Sie die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen, um Informationen zum Typ an den Clientcode bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3b193-108">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="3b193-109">Weitere Informationen zum Verwenden von Formatzeichenfolgen und anderen Arten von benutzerdefinierten Formaten mit der `ToString`-Methode finden Sie unter [Formatierung von Typen](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="3b193-109">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3b193-110">Wenn Sie sich entschieden haben, welche Informationen Sie über diese Methode bereitstellen möchten, beziehen Sie auch mit ein, ob Ihre Klasse oder Struktur von nicht vertrauenswürdigem Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b193-110">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="3b193-111">Achten Sie darauf, dass Sie keine Informationen bereitstellen, die von böswilligem Code ausgenutzt werden könnten.</span><span class="sxs-lookup"><span data-stu-id="3b193-111">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
<span data-ttu-id="3b193-112">Außerkraftsetzen der `ToString`-Methode in Ihrer Klasse oder Struktur:</span><span class="sxs-lookup"><span data-stu-id="3b193-112">To override the `ToString` method in your class or struct:</span></span>
  
1. <span data-ttu-id="3b193-113">Deklarieren Sie eine `ToString`-Methode mit folgenden Modifizierern und Rückgabetypen:</span><span class="sxs-lookup"><span data-stu-id="3b193-113">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. <span data-ttu-id="3b193-114">Implementieren Sie die Methode, sodass sie eine Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3b193-114">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="3b193-115">Im folgenden Beispiel wird der Name der Klasse neben den für eine bestimmte Instanz der Klasse spezifischen Daten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b193-115">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     <span data-ttu-id="3b193-116">Sie können die `ToString`-Methode auch wie im folgenden Beispiel gezeigt prüfen:</span><span class="sxs-lookup"><span data-stu-id="3b193-116">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="3b193-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b193-117">See also</span></span>

- <xref:System.IFormattable>
- [<span data-ttu-id="3b193-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3b193-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3b193-119">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="3b193-119">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="3b193-120">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="3b193-120">Strings</span></span>](../strings/index.md)
- [<span data-ttu-id="3b193-121">string</span><span class="sxs-lookup"><span data-stu-id="3b193-121">string</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="3b193-122">override</span><span class="sxs-lookup"><span data-stu-id="3b193-122">override</span></span>](../../language-reference/keywords/override.md)
- [<span data-ttu-id="3b193-123">virtual</span><span class="sxs-lookup"><span data-stu-id="3b193-123">virtual</span></span>](../../language-reference/keywords/virtual.md)
- [<span data-ttu-id="3b193-124">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="3b193-124">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
