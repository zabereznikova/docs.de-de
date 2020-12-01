---
title: Verwenden von CodeDOM
description: Hier erfahren Sie, wie Sie das Code Document Object Model (CodeDOM) verwenden, über das Typen zur Verfügung stehen, die viele gängige Typen von Quellcodeelementen darstellen, um einen Objektgraphen zusammenzustellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- Code Document Object Model
- Code Document Object Model, graphs
- types, CodeDOM
- namespaces [.NET Framework], CodeDOM
- templated code generation
- dynamically representing source code
- source code models
- CodeDOM
- graphing with CodeDOM
- dynamic compilation
- code generators
- CodeDOM, graphs
ms.assetid: 0444ddf3-c3f6-44ed-a999-f710d9c3e0cf
ms.openlocfilehash: f2481aa0423615f5f5925bde7cae3ad170ca8533
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259179"
---
# <a name="using-the-codedom"></a><span data-ttu-id="7c6d6-103">Verwenden von CodeDOM</span><span class="sxs-lookup"><span data-stu-id="7c6d6-103">Using the CodeDOM</span></span>

<span data-ttu-id="7c6d6-104">CodeDOM stellt Typen bereit, die zahlreiche häufig verwendete Quellcodeelemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-104">The CodeDOM provides types that represent many common types of source code elements.</span></span> <span data-ttu-id="7c6d6-105">Ein Programm kann entworfen werden, das ein Quellcodemodell mithilfe von CodeDOM-Elementen erstellt, um ein Objektdiagramm zusammenzustellen.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-105">You can design a program that builds a source code model using CodeDOM elements to assemble an object graph.</span></span> <span data-ttu-id="7c6d6-106">Dieses Objektdiagramm kann mit einem CodeDOM-Code-Generator für eine unterstützte Programmiersprache als Quellcode gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-106">This object graph can be rendered as source code using a CodeDOM code generator for a supported programming language.</span></span> <span data-ttu-id="7c6d6-107">CodeDOM kann auch verwendet werden, um Quellcode in eine binäre Assembly zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-107">The CodeDOM can also be used to compile source code into a binary assembly.</span></span>  
  
 <span data-ttu-id="7c6d6-108">Im Folgenden werden einige häufige Verwendungsmöglichkeiten von CodeDOM aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="7c6d6-108">Some common uses for the CodeDOM include:</span></span>  
  
- <span data-ttu-id="7c6d6-109">Generieren von Code mit Vorlagen: Generieren von Code für ASP.NET, XML-Clientproxys für Webdienste, Code-Assistenten, Designer oder Mechanismen zur Ausgabe von Code.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-109">Templated code generation: generating code for ASP.NET, XML Web services client proxies, code wizards, designers, or other code-emitting mechanisms.</span></span>  
  
- <span data-ttu-id="7c6d6-110">Dynamische Kompilierung: Unterstützen der Codekompilierung in einer oder in mehreren Sprachen.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-110">Dynamic compilation: supporting code compilation in single or multiple languages.</span></span>  
  
## <a name="building-a-codedom-graph"></a><span data-ttu-id="7c6d6-111">Erstellen eines CodeDOM-Diagramms</span><span class="sxs-lookup"><span data-stu-id="7c6d6-111">Building a CodeDOM Graph</span></span>  

 <span data-ttu-id="7c6d6-112">Der <xref:System.CodeDom>-Namespace stellt Klassen zur Verfügung, die die logische Struktur von Quellcode unabhängig von der Syntax der Sprache darstellen können.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-112">The <xref:System.CodeDom> namespace provides classes for representing the logical structure of source code, independent of language syntax.</span></span>  
  
### <a name="the-structure-of-a-codedom-graph"></a><span data-ttu-id="7c6d6-113">Die Struktur eines CodeDOM-Diagramms</span><span class="sxs-lookup"><span data-stu-id="7c6d6-113">The Structure of a CodeDOM Graph</span></span>  

 <span data-ttu-id="7c6d6-114">Die Struktur eines CodeDOM-Diagramms ist mit der Struktur von Containern vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-114">The structure of a CodeDOM graph is like a tree of containers.</span></span> <span data-ttu-id="7c6d6-115">Der oberste Container bzw. Stammcontainer der einzelnen kompilierbaren CodeDOM-Diagramme ist eine <xref:System.CodeDom.CodeCompileUnit>.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-115">The top-most, or root, container of each compilable CodeDOM graph is a <xref:System.CodeDom.CodeCompileUnit>.</span></span> <span data-ttu-id="7c6d6-116">Jedes Element des Quellcodemodells muss durch eine <xref:System.CodeDom.CodeObject>-Eigenschaft mit dem Diagramm verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-116">Every element of your source code model must be linked into the graph through a property of a <xref:System.CodeDom.CodeObject> in the graph.</span></span>  
  
### <a name="building-a-source-code-model-for-a-sample-hello-world-program"></a><span data-ttu-id="7c6d6-117">Erstellen eines Quellcodemodells für ein Hello World-Beispielprogramm</span><span class="sxs-lookup"><span data-stu-id="7c6d6-117">Building a Source Code Model for a Sample Hello World Program</span></span>  

 <span data-ttu-id="7c6d6-118">Die folgende exemplarische Vorgehensweise bietet ein Beispiel für das Erstellen eines CodeDOM-Objektdiagramms, das den Code einer einfachen Hello World-Anwendung wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-118">The following walkthrough provides an example of how to build a CodeDOM object graph that represents the code for a simple Hello World application.</span></span> <span data-ttu-id="7c6d6-119">Den vollständigen Quellcode für dieses Codebeispiel finden Sie im Thema <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-119">For the complete source code for this code example, see the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> topic.</span></span>  
  
#### <a name="creating-a-compile-unit"></a><span data-ttu-id="7c6d6-120">Erstellen einer Kompilierungseinheit</span><span class="sxs-lookup"><span data-stu-id="7c6d6-120">Creating a compile unit</span></span>  

 <span data-ttu-id="7c6d6-121">CodeDOM definiert ein als <xref:System.CodeDom.CodeCompileUnit> bezeichnetes Objekt, das auf ein CodeDOM-Objektdiagramm verweisen kann, das ein Modell des zu kompilierenden Quellcodes darstellt.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-121">The CodeDOM defines an object called a <xref:System.CodeDom.CodeCompileUnit>, which can reference a CodeDOM object graph that models the source code to compile.</span></span> <span data-ttu-id="7c6d6-122">Eine **CodeCompileUnit** verfügt über Eigenschaften zum Speichern von Verweisen auf Attribute, Namespaces und Assemblys.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-122">A **CodeCompileUnit** has properties for storing references to attributes, namespaces, and assemblies.</span></span>  
  
 <span data-ttu-id="7c6d6-123">Die von der <xref:System.CodeDom.Compiler.CodeDomProvider>-Klasse abgeleiteten CodeDom-Anbieter enthalten Methoden zum Verarbeiten des Objektdiagramms, auf das von einer **CodeCompileUnit** verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-123">The CodeDom providers that derive from the <xref:System.CodeDom.Compiler.CodeDomProvider> class contain methods that process the object graph referenced by a **CodeCompileUnit**.</span></span>  
  
 <span data-ttu-id="7c6d6-124">Um ein Objektdiagramm für eine einfache Anwendung zu erstellen, müssen Sie das Quellcodemodell zusammenstellen und von einer **CodeCompileUnit** aus darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-124">To create an object graph for a simple application, you must assemble the source code model and reference it from a **CodeCompileUnit**.</span></span>  
  
 <span data-ttu-id="7c6d6-125">Mit der in diesem Beispiel gezeigten Syntax können Sie eine neue Kompilierungseinheit erstellen:</span><span class="sxs-lookup"><span data-stu-id="7c6d6-125">You can create a new compile unit with the syntax demonstrated in this example:</span></span>  
  
 [!code-cpp[CodeDomExample#12](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#12)]
 [!code-csharp[CodeDomExample#12](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#12)]
 [!code-vb[CodeDomExample#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#12)]  
  
 <span data-ttu-id="7c6d6-126">Eine <xref:System.CodeDom.CodeSnippetCompileUnit> kann einen Ausschnitt des Quellcodes enthalten, der sich bereits in der Zielsprache befindet, aber nicht in einer anderen Sprache gerendert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-126">A <xref:System.CodeDom.CodeSnippetCompileUnit> can contain a section of source code that is already in the target language, but cannot be rendered to another language.</span></span>  
  
#### <a name="defining-a-namespace"></a><span data-ttu-id="7c6d6-127">Definieren eines Namespaces</span><span class="sxs-lookup"><span data-stu-id="7c6d6-127">Defining a namespace</span></span>  

 <span data-ttu-id="7c6d6-128">Zum Definieren eines Namespaces erstellen Sie einen <xref:System.CodeDom.CodeNamespace> und weisen ihm mit dem entsprechenden Konstruktor oder durch Festlegen der **Name**-Eigenschaft einen Namen zu.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-128">To define a namespace, create a <xref:System.CodeDom.CodeNamespace> and assign a name for it using the appropriate constructor or by setting its **Name** property.</span></span>  
  
 [!code-cpp[CodeDomExample#13](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#13)]
 [!code-csharp[CodeDomExample#13](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#13)]
 [!code-vb[CodeDomExample#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#13)]  
  
#### <a name="importing-a-namespace"></a><span data-ttu-id="7c6d6-129">Importieren eines Namespaces</span><span class="sxs-lookup"><span data-stu-id="7c6d6-129">Importing a namespace</span></span>  

 <span data-ttu-id="7c6d6-130">Um dem Namespace eine Anweisung für den Namespaceimport hinzuzufügen, fügen Sie einen <xref:System.CodeDom.CodeNamespaceImport> hinzu, der den in die **CodeNamespace.Imports**-Auflistung zu importierenden Namespace angibt.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-130">To add a namespace import directive to the namespace, add a <xref:System.CodeDom.CodeNamespaceImport> that indicates the namespace to import to the **CodeNamespace.Imports** collection.</span></span>  
  
 <span data-ttu-id="7c6d6-131">Der folgende Code fügt der **Imports**-Auflistung von **CodeNamespace** mit der Bezeichnung `samples` einen Import für den **System**-Namespace hinzu:</span><span class="sxs-lookup"><span data-stu-id="7c6d6-131">The following code adds an import for the **System** namespace to the **Imports** collection of a **CodeNamespace** named `samples`:</span></span>  
  
 [!code-cpp[CodeDomExample#14](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#14)]
 [!code-csharp[CodeDomExample#14](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#14)]
 [!code-vb[CodeDomExample#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#14)]  
  
#### <a name="linking-code-elements-into-the-object-graph"></a><span data-ttu-id="7c6d6-132">Verknüpfen von Codeelementen mit dem Objektdiagramm</span><span class="sxs-lookup"><span data-stu-id="7c6d6-132">Linking code elements into the object graph</span></span>  

 <span data-ttu-id="7c6d6-133">Alle Codeelemente eines CodeDOM-Diagramms müssen durch eine Reihe von Verweisen zwischen Elementen, auf die von den Eigenschaften des Stammobjekts des Diagramms direkt verwiesen wird, mit der <xref:System.CodeDom.CodeCompileUnit> verknüpft werden, bei der es sich um das Stammelement der Struktur handelt.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-133">All code elements that form a CodeDOM graph must be linked to the <xref:System.CodeDom.CodeCompileUnit> that is the root element of the tree by a series of references between elements directly referenced from the properties of the root object of the graph.</span></span> <span data-ttu-id="7c6d6-134">Legen Sie ein Objekt auf eine Eigenschaft eines Containerobjekts fest, um einen Verweis vom Containerobjekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-134">Set an object to a property of a container object to establish a reference from the container object.</span></span>  
  
 <span data-ttu-id="7c6d6-135">Die folgende Anweisung fügt der **Namespaces**-Auflistungseigenschaft der Stamm-**CodeCompileUnit** den `samples`-**CodeNamespace** hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-135">The following statement adds the `samples` **CodeNamespace** to the **Namespaces** collection property of the root **CodeCompileUnit**.</span></span>  
  
 [!code-cpp[CodeDomExample#15](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#15)]
 [!code-csharp[CodeDomExample#15](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#15)]
 [!code-vb[CodeDomExample#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#15)]  
  
#### <a name="defining-a-type"></a><span data-ttu-id="7c6d6-136">Definieren eines Typs</span><span class="sxs-lookup"><span data-stu-id="7c6d6-136">Defining a type</span></span>  

 <span data-ttu-id="7c6d6-137">Um mit CodeDOM eine Klasse, Struktur, Schnittstelle oder Enumeration zu deklarieren, erstellen Sie eine neue <xref:System.CodeDom.CodeTypeDeclaration> und weisen ihr einen Namen zu.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-137">To declare a class, structure, interface, or enumeration using the CodeDOM, create a new <xref:System.CodeDom.CodeTypeDeclaration>, and assign it a name.</span></span> <span data-ttu-id="7c6d6-138">Das folgende Beispiel veranschaulicht dies. Die **Name**-Eigenschaft wird mithilfe einer Überladung des Konstruktors festgelegt:</span><span class="sxs-lookup"><span data-stu-id="7c6d6-138">The following example demonstrates this using a constructor overload to set the **Name** property:</span></span>  
  
 [!code-cpp[CodeDomExample#16](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#16)]
 [!code-csharp[CodeDomExample#16](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#16)]
 [!code-vb[CodeDomExample#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#16)]  
  
 <span data-ttu-id="7c6d6-139">Zum Hinzufügen eines Typs zu einem Namespace fügen Sie der **Types**-Auflistung von **CodeNamespace** eine <xref:System.CodeDom.CodeTypeDeclaration> hinzu, die den dem Namespace hinzuzufügenden Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-139">To add a type to a namespace, add a <xref:System.CodeDom.CodeTypeDeclaration> that represents the type to add to the namespace to the **Types** collection of a **CodeNamespace**.</span></span>  
  
 <span data-ttu-id="7c6d6-140">Das folgende Beispiel veranschaulicht das Hinzufügen der Klasse `class1` zum **CodeNamespace** mit dem Namen `samples`:</span><span class="sxs-lookup"><span data-stu-id="7c6d6-140">The following example demonstrates how to add a class named `class1` to a **CodeNamespace** named `samples`:</span></span>  
  
 [!code-cpp[CodeDomExample#17](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#17)]
 [!code-csharp[CodeDomExample#17](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#17)]
 [!code-vb[CodeDomExample#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#17)]  
  
#### <a name="adding-class-members-to-a-class"></a><span data-ttu-id="7c6d6-141">Hinzufügen von Klassenmembern zu einer Klasse</span><span class="sxs-lookup"><span data-stu-id="7c6d6-141">Adding class members to a class</span></span>  

 <span data-ttu-id="7c6d6-142">Der <xref:System.CodeDom>-Namespace stellt eine Vielzahl von Elementen bereit, mit denen Klassenmember dargestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-142">The <xref:System.CodeDom> namespace provides a variety of elements that can be used to represent class members.</span></span> <span data-ttu-id="7c6d6-143">Jeder Klassenmember kann der **Members**-Auflistung einer <xref:System.CodeDom.CodeTypeDeclaration> hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-143">Each class member can be added to the **Members** collection of a <xref:System.CodeDom.CodeTypeDeclaration>.</span></span>  
  
#### <a name="defining-a-code-entry-point-method-for-an-executable"></a><span data-ttu-id="7c6d6-144">Definieren einer Code-Einstiegspunktmethode für eine ausführbare Datei</span><span class="sxs-lookup"><span data-stu-id="7c6d6-144">Defining a code entry point method for an executable</span></span>  

 <span data-ttu-id="7c6d6-145">Wenn Sie den Code für ein ausführbares Programm erstellen, müssen Sie den Einstiegspunkt eines Programms angeben, indem Sie eine <xref:System.CodeDom.CodeEntryPointMethod> für die Darstellung der Methode erstellen, bei der die Programmausführung beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-145">If you are building code for an executable program, it is necessary to indicate the entry point of a program by creating a <xref:System.CodeDom.CodeEntryPointMethod> to represent the method at which program execution should begin.</span></span>  
  
 <span data-ttu-id="7c6d6-146">Im folgenden Beispiel wird das Definieren einer Einstiegspunktmethode veranschaulicht, die einen <xref:System.CodeDom.CodeMethodInvokeExpression> enthält, der **System.Console.WriteLine** aufruft, um „Hello World!“ auszugeben:</span><span class="sxs-lookup"><span data-stu-id="7c6d6-146">The following example demonstrates how to define an entry point method that contains a <xref:System.CodeDom.CodeMethodInvokeExpression> that calls **System.Console.WriteLine** to print "Hello World!":</span></span>  
  
 [!code-cpp[CodeDomExample#18](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#18)]
 [!code-csharp[CodeDomExample#18](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#18)]
 [!code-vb[CodeDomExample#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#18)]  
  
 <span data-ttu-id="7c6d6-147">Die folgende Anweisung fügt der **Members**-Auflistung von `class1` die Einstiegspunktmethode mit dem Namen `Start` hinzu:</span><span class="sxs-lookup"><span data-stu-id="7c6d6-147">The following statement adds the entry point method named `Start` to the **Members** collection of `class1`:</span></span>  
  
 [!code-cpp[CodeDomExample#19](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#19)]
 [!code-csharp[CodeDomExample#19](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#19)]
 [!code-vb[CodeDomExample#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#19)]  
  
 <span data-ttu-id="7c6d6-148">Die <xref:System.CodeDom.CodeCompileUnit> mit der Bezeichnung `compileUnit` enthält nun das CodeDOM-Diagramm für ein einfaches Hello World-Programm.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-148">Now the <xref:System.CodeDom.CodeCompileUnit> named `compileUnit` contains the CodeDOM graph for a simple Hello World program.</span></span> <span data-ttu-id="7c6d6-149">Weitere Informationen über das Generieren und Kompilieren von Code aus einem CodeDOM-Diagramm finden Sie unter [Generating Source Code and Compiling a Program from a CodeDOM Graph (Generieren von Quellcode und Kompilieren eines Programms aus einem CodeDOM-Diagramm)](generating-and-compiling-source-code-from-a-codedom-graph.md).</span><span class="sxs-lookup"><span data-stu-id="7c6d6-149">For information on generating and compiling code from a CodeDOM graph, see [Generating Source Code and Compiling a Program from a CodeDOM Graph](generating-and-compiling-source-code-from-a-codedom-graph.md).</span></span>  
  
### <a name="more-information-on-building-a-codedom-graph"></a><span data-ttu-id="7c6d6-150">Weitere Informationen zum Erstellen eines CodeDOM-Diagramms</span><span class="sxs-lookup"><span data-stu-id="7c6d6-150">More information on building a CodeDOM graph</span></span>  

 <span data-ttu-id="7c6d6-151">Von CodeDOM werden viele häufig verwendete Typen von Codeelementen in den Programmiersprachen unterstützt, die die Common Language Runtime unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-151">The CodeDOM supports the many common types of code elements found in programming languages that support the common language runtime.</span></span> <span data-ttu-id="7c6d6-152">CodeDOM zielt nicht darauf ab, für die Darstellung aller denkbaren Programmiersprachenfeatures Elemente bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-152">The CodeDOM was not designed to provide elements to represent all possible programming language features.</span></span> <span data-ttu-id="7c6d6-153">Code, der nicht einfach mit CodeDOM-Elementen dargestellt werden kann, kann in <xref:System.CodeDom.CodeSnippetExpression>, <xref:System.CodeDom.CodeSnippetStatement>, <xref:System.CodeDom.CodeSnippetTypeMember> oder <xref:System.CodeDom.CodeSnippetCompileUnit> gekapselt werden.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-153">Code that cannot be represented easily with CodeDOM elements can be encapsulated in a <xref:System.CodeDom.CodeSnippetExpression>, a <xref:System.CodeDom.CodeSnippetStatement>, a <xref:System.CodeDom.CodeSnippetTypeMember>, or a <xref:System.CodeDom.CodeSnippetCompileUnit>.</span></span> <span data-ttu-id="7c6d6-154">Allerdings kann CodeDOM die Codeausschnitte nicht automatisch in andere Sprachen übersetzen.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-154">However, snippets cannot be translated to other languages automatically by the CodeDOM.</span></span>  
  
 <span data-ttu-id="7c6d6-155">Eine Dokumentation aller CodeDOM-Typen finden Sie in der Referenzdokumentation zum <xref:System.CodeDom>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="7c6d6-155">For documentation for the each of the CodeDOM types, see the reference documentation for the <xref:System.CodeDom> namespace.</span></span>  
  
 <span data-ttu-id="7c6d6-156">Ein Übersichtsdiagramm, in dem das jeweils zum Darstellen eines bestimmten Codeelementtyps zu verwendende CodeDOM-Element gesucht werden kann, finden Sie in der [Kurzreferenz zu CodeDOM](/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7c6d6-156">For a quick chart to locate the CodeDOM element that represents a specific type of code element, see the [CodeDOM Quick Reference](/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)).</span></span>
