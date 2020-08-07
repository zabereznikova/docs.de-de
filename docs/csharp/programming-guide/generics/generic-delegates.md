---
title: Generische Delegaten – C#-Programmierhandbuch
description: Erfahren Sie mehr über die Verwendung generischer Delegaten in C#. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: d99271ca9f12e95743d633caac16aaa4151e9c41
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301904"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="6980f-104">Generische Delegaten (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6980f-104">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="6980f-105">Ein [Delegat](../../language-reference/builtin-types/reference-types.md) kann seine eigenen Typparameter definieren.</span><span class="sxs-lookup"><span data-stu-id="6980f-105">A [delegate](../../language-reference/builtin-types/reference-types.md) can define its own type parameters.</span></span> <span data-ttu-id="6980f-106">Wie im folgenden Beispiel gezeigt, kann Code, der auf den generischen Delegaten verweist, das Typargument zum Erstellen eines geschlossenen konstruierten Typs angeben, genau wie wenn eine generische Klasse instanziiert oder eine generische Methode aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="6980f-106">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 <span data-ttu-id="6980f-107">C# 2.0 verfügt über ein neues Feature. Dieses Feature wird als Methodengruppenkonvertierung bezeichnet und gilt sowohl für konkrete als auch für generische Delegattypen. Damit können Sie die vorhergehende Zeile mit folgender vereinfachter Syntax schreiben:</span><span class="sxs-lookup"><span data-stu-id="6980f-107">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 <span data-ttu-id="6980f-108">Delegaten, die innerhalb einer generischen Klasse definiert sind, können die Typparameter der generischen Klasse auf die gleiche Weise wie Klassenmethoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="6980f-108">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 <span data-ttu-id="6980f-109">Code, der auf den Delegaten verweist, muss das Typargument der enthaltenden Klasse wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="6980f-109">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 <span data-ttu-id="6980f-110">Generische Delegaten sind besonders nützlich zum Definieren von Ereignissen, die auf dem typischen Entwurfsmuster basieren, denn das Absenderargument kann mit starker Typisierung versehen werden und muss nicht länger in das bzw. aus dem <xref:System.Object> umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6980f-110">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a><span data-ttu-id="6980f-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6980f-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="6980f-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6980f-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6980f-113">Einführung in Generics</span><span class="sxs-lookup"><span data-stu-id="6980f-113">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="6980f-114">Generische Methoden</span><span class="sxs-lookup"><span data-stu-id="6980f-114">Generic Methods</span></span>](./generic-methods.md)
- [<span data-ttu-id="6980f-115">Generische Klassen</span><span class="sxs-lookup"><span data-stu-id="6980f-115">Generic Classes</span></span>](./generic-classes.md)
- [<span data-ttu-id="6980f-116">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6980f-116">Generic Interfaces</span></span>](./generic-interfaces.md)
- [<span data-ttu-id="6980f-117">Delegaten</span><span class="sxs-lookup"><span data-stu-id="6980f-117">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="6980f-118">Generics</span><span class="sxs-lookup"><span data-stu-id="6980f-118">Generics</span></span>](../../../standard/generics/index.md)
