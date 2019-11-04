---
title: 'Vorgehensweise: Indizierte Eigenschaften bei der COM-Interop-Programmierung – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 0d4e85646a1e7f8c4ee9a73fbf7bf5a01b10b14b
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423218"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="11e74-102">Vorgehensweise: Indizierte Eigenschaften bei der COM-Interop-Programmierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="11e74-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="11e74-103">*Indizierte Eigenschaften* verbessern die Verarbeitung von COM-Eigenschaften mit Parametern in der C#-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="11e74-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="11e74-104">Indizierte Eigenschaften arbeiten zusammen mit anderen Funktionen in Visual C#, wie z.B. [benannte und optionale Argumente](../classes-and-structs/named-and-optional-arguments.md) und neuen Typinformationen ([dynamisch](../../language-reference/builtin-types/reference-types.md)) und [eingebettete Typinformationen](../../../standard/assembly/embed-types-visual-studio.md), um die Microsoft Office-Programmierung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="11e74-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../language-reference/builtin-types/reference-types.md)), and [embedded type information](../../../standard/assembly/embed-types-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="11e74-105">In früheren Versionen von C# waren Methoden nur als Eigenschaften zugänglich, wenn die `get`-Methode keine Parameter und die `set`-Methode nur einen Wertparameter hatte.</span><span class="sxs-lookup"><span data-stu-id="11e74-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="11e74-106">Allerdings erfüllen nicht alle COM-Eigenschaften diese Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="11e74-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="11e74-107">Die Eigenschaft <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> in Excel verfügt über eine `get`-Zugriffsmethode, für die ein Parameter für den Namen des Bereichs erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="11e74-107">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="11e74-108">Früher mussten Sie stattdessen die `get_Range`-Methode verwenden, weil Sie nicht direkt auf die `Range`-Methode zugreifen konnten. Dies wird in folgendem Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="11e74-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="11e74-109">Mit indizierte Eigenschaften können Sie stattdessen Folgendes schreiben:</span><span class="sxs-lookup"><span data-stu-id="11e74-109">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> <span data-ttu-id="11e74-110">Im vorherigen Beispiel wurde auch die Funktion [Optionale Argumente](../classes-and-structs/named-and-optional-arguments.md) verwendet, mit der Sie `Type.Missing` weglassen können.</span><span class="sxs-lookup"><span data-stu-id="11e74-110">The previous example also uses the [optional arguments](../classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="11e74-111">Für das Festlegen der `Value`-Eigenschaft eines <xref:Microsoft.Office.Interop.Excel.Range>-Objekts in C# 3.0 und früher sind zwei Argumente erforderlich.</span><span class="sxs-lookup"><span data-stu-id="11e74-111">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in C# 3.0 and earlier, two arguments are required.</span></span> <span data-ttu-id="11e74-112">Eines dieser Argumente stellt ein Argument für einen optionalen Parameter bereit, der den Typ des Bereichswerts angibt.</span><span class="sxs-lookup"><span data-stu-id="11e74-112">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="11e74-113">Das andere Argument stellt den Wert für die `Value`-Eigenschaft bereit.</span><span class="sxs-lookup"><span data-stu-id="11e74-113">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="11e74-114">In den folgenden Beispielen werden diese Techniken veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="11e74-114">The following examples illustrate these techniques.</span></span> <span data-ttu-id="11e74-115">Beide legen den Wert der Zelle A1 auf `Name` fest.</span><span class="sxs-lookup"><span data-stu-id="11e74-115">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="11e74-116">Mit indizierte Eigenschaften können Sie stattdessen folgenden Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="11e74-116">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="11e74-117">Sie können nicht Ihre eigenen indizierten Eigenschaften erstellen.</span><span class="sxs-lookup"><span data-stu-id="11e74-117">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="11e74-118">Die Funktion unterstützt nur die Nutzung vorhandener indizierter Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="11e74-118">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11e74-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="11e74-119">Example</span></span>  
 <span data-ttu-id="11e74-120">Der folgende Code veranschaulicht das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="11e74-120">The following code shows a complete example.</span></span> <span data-ttu-id="11e74-121">Weitere Informationen zum Einrichten eines Projekts, das auf die Office-API zugreift, finden Sie unter [Vorgehensweise: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen](./how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="11e74-121">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](./how-to-access-office-onterop-objects.md).</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="11e74-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11e74-122">See also</span></span>

- [<span data-ttu-id="11e74-123">Benannte und optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="11e74-123">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="11e74-124">dynamic</span><span class="sxs-lookup"><span data-stu-id="11e74-124">dynamic</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="11e74-125">Verwenden von dynamischen Typen</span><span class="sxs-lookup"><span data-stu-id="11e74-125">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="11e74-126">Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="11e74-126">How to: Use Named and Optional Arguments in Office Programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="11e74-127">Vorgehensweise: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen</span><span class="sxs-lookup"><span data-stu-id="11e74-127">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](./how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="11e74-128">Exemplarische Vorgehensweise: Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="11e74-128">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
