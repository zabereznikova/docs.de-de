---
title: 'Vorgehensweise: Erstellen einer Klasse mit CodeDOM'
description: In diesem ausführlichen Beispiel wird erläutert, wie Sie mit dem Code Document Object Model (CodeDOM) eine Klasse erstellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Code Document Object Model, graphs
- Code Document Object Model, creating classes
- graphing with CodeDOM
- CodeDOM, creating classes
- CodeDOM, graphs
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
ms.openlocfilehash: 3d7151d384402dba6fbb5da8fe54621346251f7b
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865306"
---
# <a name="how-to-create-a-class-using-codedom"></a><span data-ttu-id="c7dbb-103">Vorgehensweise: Erstellen einer Klasse mit CodeDOM</span><span class="sxs-lookup"><span data-stu-id="c7dbb-103">How to: Create a Class Using CodeDOM</span></span>
<span data-ttu-id="c7dbb-104">Die folgenden Verfahren stellen dar, wie ein CodeDOM-Diagramm erstellt und kompiliert, das eine Klasse erstellt, die zwei Felder, drei Eigenschaften, eine Methode, einen Konstruktor und einen Einstiegspunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-104">The following procedures illustrate how to create and compile a CodeDOM graph that generates a class containing two fields, three properties, a method, a constructor, and an entry point.</span></span>  
  
1. <span data-ttu-id="c7dbb-105">Erstellen Sie eine Konsolenanwendung, die den CodeDOM-Code zum Generieren des Quellcodes für eine Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-105">Create a console application that will use CodeDOM code to generate the source code for a class.</span></span>  
  
     <span data-ttu-id="c7dbb-106">In diesem Beispiel heißt die generierende Klasse `Sample`, und der generierte Code ist eine Klasse namens `CodeDOMCreatedClass` in einer Datei namens „SampleCode“.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-106">In this example, the generating class is named `Sample`, and the generated code is a class named `CodeDOMCreatedClass` in a file named SampleCode.</span></span>  
  
2. <span data-ttu-id="c7dbb-107">Initialisieren Sie in der generierenden Klasse das CodeDOM-Diagramm, und verwenden Sie CodeDOM-Methoden, um die Member, den Konstruktor und den Einstiegspunkt (`Main`-Methode) der generierten Klasse zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-107">In the generating class, initialize the CodeDOM graph and use CodeDOM methods to define the members, constructor, and entry point (`Main` method) of the generated class.</span></span>  
  
     <span data-ttu-id="c7dbb-108">In diesem Beispiel verfügt die generierte Klasse über zwei Felder, drei Eigenschaften, einen Konstruktor, eine Methode und eine `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-108">In this example, the generated class has two fields, three properties, a constructor, a method, and a `Main` method.</span></span>  
  
3. <span data-ttu-id="c7dbb-109">Erstellen Sie in der generierenden Klasse einen sprachspezifischen Codeanbieter, und rufen Sie dessen <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>-Methode auf, um den Code aus dem Diagramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-109">In the generating class, create a language-specific code provider and call its <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code from the graph.</span></span>  
  
4. <span data-ttu-id="c7dbb-110">Kompilieren Sie die Anwendung, und führen Sie sie aus, um den Code zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-110">Compile and execute the application to generate the code.</span></span>  
  
     <span data-ttu-id="c7dbb-111">In diesem Beispiel befindet sich der generierte Code in einer Datei namens „SampleCode“.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-111">In this example, the generated code is in a file named SampleCode.</span></span> <span data-ttu-id="c7dbb-112">Kompilieren Sie diesen Code, und führen Sie ihn aus, um die Beispielausgabe zu sehen.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-112">Compile and execute that code to see the sample output.</span></span>  
  
### <a name="to-create-the-application-that-will-execute-the-codedom-code"></a><span data-ttu-id="c7dbb-113">So erstellen Sie die Anwendung, die den CodeDOM-Code ausführen wird</span><span class="sxs-lookup"><span data-stu-id="c7dbb-113">To create the application that will execute the CodeDOM code</span></span>  
  
- <span data-ttu-id="c7dbb-114">Erstellen Sie eine Konsolenanwendungsklasse, die den CodeDOM-Code enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-114">Create a console application class to contain the CodeDOM code.</span></span> <span data-ttu-id="c7dbb-115">Definieren Sie die globalen Felder, die in der Klasse verwendet werden sollen, um die Assembly (<xref:System.CodeDom.CodeCompileUnit>) und die Klasse (<xref:System.CodeDom.CodeTypeDeclaration>) zu verweisen, den Namen der generierten Quelldatei anzugeben und die `Main`-Methode zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-115">Define the global fields that are to be used in the class to reference the assembly (<xref:System.CodeDom.CodeCompileUnit>) and class (<xref:System.CodeDom.CodeTypeDeclaration>), specify the name of the generated source file, and declare the `Main` method.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### <a name="to-initialize-the-codedom-graph"></a><span data-ttu-id="c7dbb-116">So initialisieren Sie das CodeDOM-Diagramm</span><span class="sxs-lookup"><span data-stu-id="c7dbb-116">To initialize the CodeDOM graph</span></span>  
  
- <span data-ttu-id="c7dbb-117">Initialisieren Sie im Konstruktor für die Konsolenanwendungsklasse die Assembly und Klasse, und fügen Sie dem CodeDOM-Diagramm die passenden Deklarationen hinzu.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-117">In the constructor for the console application class, initialize the assembly and class, and add the appropriate declarations to the CodeDOM graph.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### <a name="to-add-members-to-the-codedom-graph"></a><span data-ttu-id="c7dbb-118">So fügen Sie dem CodeDOM-Diagramm Member hinzu</span><span class="sxs-lookup"><span data-stu-id="c7dbb-118">To add members to the CodeDOM graph</span></span>  
  
- <span data-ttu-id="c7dbb-119">Fügen Sie dem CodeDOM-Diagramm Felder hinzu, indem Sie der <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>-Eigenschaft der Klasse <xref:System.CodeDom.CodeMemberField>-Objekte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-119">Add fields to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberField> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
- <span data-ttu-id="c7dbb-120">Fügen Sie dem CodeDOM-Diagramm Eigenschaften hinzu, indem Sie der <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>-Eigenschaft der Klasse <xref:System.CodeDom.CodeMemberProperty>-Objekte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-120">Add properties to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberProperty> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
- <span data-ttu-id="c7dbb-121">Fügen Sie dem CodeDOM-Diagramm eine Methode hinzu, indem Sie der <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>-Eigenschaft der Klasse <xref:System.CodeDom.CodeMemberMethod>-Objekte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-121">Add a method to the CodeDOM graph by adding a <xref:System.CodeDom.CodeMemberMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
- <span data-ttu-id="c7dbb-122">Fügen Sie dem CodeDOM-Diagramm einen Konstruktor hinzu, indem Sie der <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>-Eigenschaft der Klasse <xref:System.CodeDom.CodeConstructor>-Objekte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-122">Add a constructor to the CodeDOM graph by adding a <xref:System.CodeDom.CodeConstructor> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
- <span data-ttu-id="c7dbb-123">Fügen Sie dem CodeDOM-Diagramm einen Einstiegspunkt hinzu, indem Sie der <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>-Eigenschaft der Klasse <xref:System.CodeDom.CodeEntryPointMethod>-Objekte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-123">Add an entry point to the CodeDOM graph by adding a <xref:System.CodeDom.CodeEntryPointMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### <a name="to-generate-the-code-from-the-codedom-graph"></a><span data-ttu-id="c7dbb-124">So generieren Sie den Code aus dem CodeDOM-Diagramm</span><span class="sxs-lookup"><span data-stu-id="c7dbb-124">To generate the code from the CodeDOM graph</span></span>  
  
- <span data-ttu-id="c7dbb-125">Generieren Sie Quellcode aus dem CodeDOM-Diagramm, indem Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-125">Generate source code from the CodeDOM graph by calling the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### <a name="to-create-the-graph-and-generate-the-code"></a><span data-ttu-id="c7dbb-126">So erstellen Sie das Diagramm und generieren den Code</span><span class="sxs-lookup"><span data-stu-id="c7dbb-126">To create the graph and generate the code</span></span>  
  
1. <span data-ttu-id="c7dbb-127">Fügen Sie die in den vorherigen Schritten erstellten Methoden der `Main`-Methode, die im ersten Schritt definiert ist, hinzu.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-127">Add the methods created in the preceding steps to the `Main` method defined in the first step.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2. <span data-ttu-id="c7dbb-128">Kompilieren Sie die generierende Klasse, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-128">Compile and execute the generating class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7dbb-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7dbb-129">Example</span></span>  
 <span data-ttu-id="c7dbb-130">Im folgenden Codebeispiel wird der Code aus den vorherigen Schritten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-130">The following code example shows the code from the preceding steps.</span></span>  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 <span data-ttu-id="c7dbb-131">Wenn das vorherige Beispiel kompiliert und ausgeführt wird, wird der folgende Quellcode erstellt.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-131">When the preceding example is compiled and executed, it produces the following source code.</span></span>  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 <span data-ttu-id="c7dbb-132">Der generierte Quellcode erstellt die folgende Ausgabe, wenn er kompiliert und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-132">The generated source code produces the following output when compiled and executed.</span></span>  
  
```output
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7dbb-133">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c7dbb-133">Compiling the Code</span></span>  
  
- <span data-ttu-id="c7dbb-134">Dieses Codebeispiel benötigt die festgelegte `FullTrust`-Berechtigung, damit es erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-134">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7dbb-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7dbb-135">See also</span></span>

- [<span data-ttu-id="c7dbb-136">Verwenden von CodeDOM</span><span class="sxs-lookup"><span data-stu-id="c7dbb-136">Using the CodeDOM</span></span>](using-the-codedom.md)
- [<span data-ttu-id="c7dbb-137">Generieren und Kompilieren von Quellcode aus einem CodeDOM-Diagramm</span><span class="sxs-lookup"><span data-stu-id="c7dbb-137">Generating and Compiling Source Code from a CodeDOM Graph</span></span>](generating-and-compiling-source-code-from-a-codedom-graph.md)
