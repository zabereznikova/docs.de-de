---
title: 'Gewusst wie: Erstellen einer XML-Dokumentationsdatei mit CodeDOM'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CodeDOM, generating XML documentation
- XML documentation, creating using CodeDOM
- Code Document Object Model, generating XML documentation
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7d5569fd22cc8469052cc318fd50a5f8ef94c1a9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a><span data-ttu-id="ad5e8-102">Gewusst wie: Erstellen einer XML-Dokumentationsdatei mit CodeDOM</span><span class="sxs-lookup"><span data-stu-id="ad5e8-102">How to: Create an XML Documentation File Using CodeDOM</span></span>
<span data-ttu-id="ad5e8-103">CodeDOM kann zum Erstellen von Code verwendet werden, der eine XML-Dokumentation erstellt.</span><span class="sxs-lookup"><span data-stu-id="ad5e8-103">CodeDOM can be used to create code that generates XML documentation.</span></span> <span data-ttu-id="ad5e8-104">Der Vorgang bringt die Erstellung des CodeDOM-Diagramms mit sich, das die XML-Dokumentationskommentare enthält, das Generieren des Codes und Kompilieren des generierten Codes mit der Compileroption, die die Ausgabe der XML-Dokumentation erstellt.</span><span class="sxs-lookup"><span data-stu-id="ad5e8-104">The process involves creating the CodeDOM graph that contains the XML documentation comments, generating the code, and compiling the generated code with the compiler option that creates the XML documentation output.</span></span>  
  
### <a name="to-create-a-codedom-graph-that-contains-xml-documentation-comments"></a><span data-ttu-id="ad5e8-105">SO erstellen Sie ein CodeDOM-Diagramm, das XML-Dokumentationskommentare enthält</span><span class="sxs-lookup"><span data-stu-id="ad5e8-105">To create a CodeDOM graph that contains XML documentation comments</span></span>  
  
1.  <span data-ttu-id="ad5e8-106">Erstellen Sie eine <xref:System.CodeDom.CodeCompileUnit>, die das CodeDOM-Diagramm für die Beispielanwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="ad5e8-106">Create a <xref:System.CodeDom.CodeCompileUnit> containing the CodeDOM graph for the sample application.</span></span>  
  
2.  <span data-ttu-id="ad5e8-107">Verwenden Sie den <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A>-Konstruktor mit dem `docComment`-Parameter, der auf `true` festgelegt ist, um die Kommentarelemente und den Kommentartext der XML-Dokumentation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ad5e8-107">Use the <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> constructor with the `docComment` parameter set to `true` to create the XML documentation comment elements and text.</span></span>  
  
     <span data-ttu-id="ad5e8-108">[!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)] [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="ad5e8-108">[!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]  [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]</span></span>  
  
### <a name="to-generate-the-code-from-the-codecompileunit"></a><span data-ttu-id="ad5e8-109">So generieren Sie den Code aus der CodeCompileUnit</span><span class="sxs-lookup"><span data-stu-id="ad5e8-109">To generate the code from the CodeCompileUnit</span></span>  
  
1.  <span data-ttu-id="ad5e8-110">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>-Methode, um den Code zu generieren und eine Quelldatei zu erstellen, die kompiliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad5e8-110">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code and create a source file to be compiled.</span></span>  
  
     <span data-ttu-id="ad5e8-111">[!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)] [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]</span><span class="sxs-lookup"><span data-stu-id="ad5e8-111">[!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]  [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]</span></span>  
  
### <a name="to-compile-the-code-and-generate-the-documentation-file"></a><span data-ttu-id="ad5e8-112">So kompilieren Sie den Code und generieren die Dokumentationsdatei</span><span class="sxs-lookup"><span data-stu-id="ad5e8-112">To compile the code and generate the documentation file</span></span>  
  
1.  <span data-ttu-id="ad5e8-113">Fügen Sie die Compileroption **/doc** der <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A>-Eigenschaft eines <xref:System.CodeDom.Compiler.CompilerParameters>-Objekts hinzu, und übermitteln Sie das Objekt an die <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A>-Methode, um die XML-Dokumentationsdatei zu erstellen, wenn der Code kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="ad5e8-113">Add the **/doc** compiler option to the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property of a <xref:System.CodeDom.Compiler.CompilerParameters> object and pass the object to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method to create the XML documentation file when the code is compiled.</span></span>  
  
     <span data-ttu-id="ad5e8-114">[!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)] [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]</span><span class="sxs-lookup"><span data-stu-id="ad5e8-114">[!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]  [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad5e8-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad5e8-115">Example</span></span>  
 <span data-ttu-id="ad5e8-116">Das folgende Codebeispiel erstellt ein CodeDOM-Diagramm mit Dokumentationskommentaren, generiert eine Codedatei aus dem Diagramm und kompiliert die Datei und erstellt eine zugeordnete XML-Dokumentationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ad5e8-116">The following code example creates a CodeDOM graph with documentation comments, generates a code file from the graph, and compiles the file and creates an associated XML documentation file.</span></span>  
  
 <span data-ttu-id="ad5e8-117">[!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)] [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="ad5e8-117">[!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)] [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]</span></span>  
  
 <span data-ttu-id="ad5e8-118">Das Codebeispiel erstellt die folgende XML-Dokumentation in der „HelloWorldDoc.xml“-Datei.</span><span class="sxs-lookup"><span data-stu-id="ad5e8-118">The code example creates the following XML documentation in the HelloWorldDoc.xml file.</span></span>  
  
```xml  
<?xml version="1.0" ?>   
<doc>  
  <assembly>  
    <name>HelloWorld</name>   
  </assembly>  
  <members>  
    <member name="T:Samples.Class1">  
      <summary>  
        Create a Hello World application.   
        <seealso cref="M:Samples.Class1.Main" />   
      </summary>  
    </member>  
    <member name="M:Samples.Class1.Main">  
      <summary>  
        Main method for HelloWorld application.   
        <para>Add a new paragraph to the description.</para>   
      </summary>  
    </member>  
  </members>  
</doc>  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad5e8-119">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ad5e8-119">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ad5e8-120">Dieses Codebeispiel benötigt die festgelegte `FullTrust`-Berechtigung, damit es erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ad5e8-120">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5e8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad5e8-121">See Also</span></span>  
 <span data-ttu-id="ad5e8-122">[Dokumentieren von Code mit XML](~/docs/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="ad5e8-122">[Documenting Your Code with XML](~/docs/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
 <span data-ttu-id="ad5e8-123">[XML-Dokumentationskommentare](~/docs/csharp/programming-guide/xmldoc/xml-documentation-comments.md) </span><span class="sxs-lookup"><span data-stu-id="ad5e8-123">[XML Documentation Comments](~/docs/csharp/programming-guide/xmldoc/xml-documentation-comments.md) </span></span>  
 [<span data-ttu-id="ad5e8-124">XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="ad5e8-124">XML Documentation</span></span>](/cpp/ide/xml-documentation-visual-cpp)

