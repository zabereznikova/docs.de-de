---
title: Anwenden von Attributen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- attributes [.NET Framework], applying
ms.assetid: dd7604eb-9fa3-4b60-b2dd-b47739fa3148
ms.openlocfilehash: 14cd6fef80ff9ae3a9d78531785edab0da7cc6b9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130916"
---
# <a name="applying-attributes"></a><span data-ttu-id="e33e1-102">Anwenden von Attributen</span><span class="sxs-lookup"><span data-stu-id="e33e1-102">Applying Attributes</span></span>
<span data-ttu-id="e33e1-103">Mit dem folgenden Verfahren wenden Sie ein Attribut auf ein Codeelement an.</span><span class="sxs-lookup"><span data-stu-id="e33e1-103">Use the following process to apply an attribute to an element of your code.</span></span>  
  
1. <span data-ttu-id="e33e1-104">Definieren Sie ein neues Attribut, oder verwenden Sie ein vorhandenes Attribut, indem Sie den entsprechenden Namespace aus .NET Framework importieren.</span><span class="sxs-lookup"><span data-stu-id="e33e1-104">Define a new attribute or use an existing attribute by importing its namespace from the .NET Framework.</span></span>  
  
2. <span data-ttu-id="e33e1-105">Wenden Sie das Attribut auf das Codeelement an, indem Sie es direkt vor dem Element platzieren.</span><span class="sxs-lookup"><span data-stu-id="e33e1-105">Apply the attribute to the code element by placing it immediately before the element.</span></span>  
  
     <span data-ttu-id="e33e1-106">Jede Sprache verfügt über eine eigene Attributsyntax.</span><span class="sxs-lookup"><span data-stu-id="e33e1-106">Each language has its own attribute syntax.</span></span> <span data-ttu-id="e33e1-107">In C++ und C# ist das Attribut von eckigen Klammern umgeben und durch einen Leerraum, der einen Zeilenumbruch umfassen kann, vom Element getrennt.</span><span class="sxs-lookup"><span data-stu-id="e33e1-107">In C++ and C#, the attribute is surrounded by square brackets and separated from the element by white space, which can include a line break.</span></span> <span data-ttu-id="e33e1-108">In Visual Basic ist das Attribut von spitzen Klammern umgeben, und es muss sich in derselben logischen Zeile befinden. Mithilfe des Zeilenfortsetzungszeichens kann bei Bedarf ein Zeilenumbruch eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e33e1-108">In Visual Basic, the attribute is surrounded by angle brackets and must be on the same logical line; the line continuation character can be used if a line break is desired.</span></span>
  
3. <span data-ttu-id="e33e1-109">Geben Sie positionelle Parameter und benannte Parameter für das Attribut an.</span><span class="sxs-lookup"><span data-stu-id="e33e1-109">Specify positional parameters and named parameters for the attribute.</span></span>  
  
     <span data-ttu-id="e33e1-110">Positionelle Parameter sind erforderlich und müssen vor benannten Parametern stehen. Sie entsprechen den Parametern eines der Attributkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="e33e1-110">Positional parameters are required and must come before any named parameters; they correspond to the parameters of one of the attribute's constructors.</span></span> <span data-ttu-id="e33e1-111">Benannte Parameter sind optional und entsprechen Lese-/Schreibeigenschaften des Attributs.</span><span class="sxs-lookup"><span data-stu-id="e33e1-111">Named parameters are optional and correspond to read/write properties of the attribute.</span></span> <span data-ttu-id="e33e1-112">Geben Sie in C++ und C# für jeden optionalen Parameter `name`=`value` an, wobei `name` der Name der Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="e33e1-112">In C++, and C#, specify `name`=`value` for each optional parameter, where `name` is the name of the property.</span></span> <span data-ttu-id="e33e1-113">In Visual Basic geben Sie `name`:=`value` an.</span><span class="sxs-lookup"><span data-stu-id="e33e1-113">In Visual Basic, specify `name`:=`value`.</span></span>  
  
 <span data-ttu-id="e33e1-114">Das Attribut wird beim Kompilieren von Code in Metadaten ausgegeben und ist über die Reflexionsdienste der Laufzeit für die Common Language Runtime sowie beliebige weitere benutzerdefinierte Tools und Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e33e1-114">The attribute is emitted into metadata when you compile your code and is available to the common language runtime and any custom tool or application through the runtime reflection services.</span></span>  
  
 <span data-ttu-id="e33e1-115">Attributnamen enden üblicherweise auf "Attribute".</span><span class="sxs-lookup"><span data-stu-id="e33e1-115">By convention, all attribute names end with Attribute.</span></span> <span data-ttu-id="e33e1-116">Verschiedene Sprachen, die die Laufzeit unterstützen, z. B. Visual Basic und C#, erfordern jedoch nicht die vollständige Angabe eines Attributnamens.</span><span class="sxs-lookup"><span data-stu-id="e33e1-116">However, several languages that target the runtime, such as Visual Basic and C#, do not require you to specify the full name of an attribute.</span></span> <span data-ttu-id="e33e1-117">Wenn Sie z.B. <xref:System.ObsoleteAttribute?displayProperty=nameWithType> initialisieren möchten, müssen Sie lediglich mit **Veraltet** darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="e33e1-117">For example, if you want to initialize <xref:System.ObsoleteAttribute?displayProperty=nameWithType>, you only need to reference it as **Obsolete**.</span></span>  
  
## <a name="applying-an-attribute-to-a-method"></a><span data-ttu-id="e33e1-118">Anwenden eines Attributs auf eine Methode</span><span class="sxs-lookup"><span data-stu-id="e33e1-118">Applying an Attribute to a Method</span></span>  
 <span data-ttu-id="e33e1-119">Im folgenden Codebeispiel wird die Deklaration von **System.ObsoleteAttribute** dargestellt, mit dem Code als veraltet gekennzeichnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e33e1-119">The following code example shows how to declare **System.ObsoleteAttribute**, which marks code as obsolete.</span></span> <span data-ttu-id="e33e1-120">Die Zeichenfolge `"Will be removed in next version"` wird an das Attribut übergeben.</span><span class="sxs-lookup"><span data-stu-id="e33e1-120">The string `"Will be removed in next version"` is passed to the attribute.</span></span> <span data-ttu-id="e33e1-121">Dieses Attribut löst eine Compilerwarnung aus. Wenn vom Attribut beschriebener Code aufgerufen wird, wird die übergebene Zeichenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e33e1-121">This attribute causes a compiler warning that displays the passed string when code that the attribute describes is called.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#3)]
 [!code-csharp[Conceptual.Attributes.Usage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#3)]
 [!code-vb[Conceptual.Attributes.Usage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#3)]  
  
## <a name="applying-attributes-at-the-assembly-level"></a><span data-ttu-id="e33e1-122">Anwenden von Attributen auf Assemblyebene</span><span class="sxs-lookup"><span data-stu-id="e33e1-122">Applying Attributes at the Assembly Level</span></span>  
 <span data-ttu-id="e33e1-123">Wenn Sie ein Attribut auf Assemblyebene anwenden möchten, verwenden Sie das Schlüsselwort **assembly** (`Assembly` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="e33e1-123">If you want to apply an attribute at the assembly level, use the **assembly** (`Assembly` in Visual Basic) keyword.</span></span> <span data-ttu-id="e33e1-124">Im folgenden Codebeispiel wird **AssemblyTitleAttribute** auf Assemblyebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="e33e1-124">The following code shows the **AssemblyTitleAttribute** applied at the assembly level.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#2)]
 [!code-csharp[Conceptual.Attributes.Usage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#2)]
 [!code-vb[Conceptual.Attributes.Usage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#2)]  
  
 <span data-ttu-id="e33e1-125">Beim Anwenden dieses Attributs wird die Zeichenfolge `"My Assembly"` im Metadatenteil der Datei im Assemblymanifest platziert.</span><span class="sxs-lookup"><span data-stu-id="e33e1-125">When this attribute is applied, the string `"My Assembly"` is placed in the assembly manifest in the metadata portion of the file.</span></span> <span data-ttu-id="e33e1-126">Sie können das Attribut entweder mithilfe des [MSIL-Disassemblers (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) anzeigen lassen oder ein benutzerdefiniertes Programm erstellen, um das Attribut abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e33e1-126">You can view the attribute either by using the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by creating a custom program to retrieve the attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e33e1-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e33e1-127">See also</span></span>

- [<span data-ttu-id="e33e1-128">Attribute</span><span class="sxs-lookup"><span data-stu-id="e33e1-128">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- [<span data-ttu-id="e33e1-129">Abrufen von Informationen aus Attributen</span><span class="sxs-lookup"><span data-stu-id="e33e1-129">Retrieving Information Stored in Attributes</span></span>](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)
- [<span data-ttu-id="e33e1-130">Konzepte</span><span class="sxs-lookup"><span data-stu-id="e33e1-130">Concepts</span></span>](/cpp/windows/attributed-programming-concepts)
- [<span data-ttu-id="e33e1-131">Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="e33e1-131">Attributes (C#)</span></span>](../../csharp/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="e33e1-132">Übersicht über Attribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e33e1-132">Attributes overview (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/attributes/index.md)
