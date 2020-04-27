---
title: 'Vorgehensweise: Erstellen einer XML-Dokumentationsdatei mit CodeDOM'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CodeDOM, generating XML documentation
- XML documentation, creating using CodeDOM
- Code Document Object Model, generating XML documentation
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
ms.openlocfilehash: a0ccb469a43c3a21a76eaf24fa7ce7b490dd5c4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180523"
---
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a><span data-ttu-id="810b7-102">Vorgehensweise: Erstellen einer XML-Dokumentationsdatei mit CodeDOM</span><span class="sxs-lookup"><span data-stu-id="810b7-102">How to: Create an XML Documentation File Using CodeDOM</span></span>
<span data-ttu-id="810b7-103">CodeDOM kann zum Erstellen von Code verwendet werden, der eine XML-Dokumentation erstellt.</span><span class="sxs-lookup"><span data-stu-id="810b7-103">CodeDOM can be used to create code that generates XML documentation.</span></span> <span data-ttu-id="810b7-104">Der Vorgang bringt die Erstellung des CodeDOM-Diagramms mit sich, das die XML-Dokumentationskommentare enthält, das Generieren des Codes und Kompilieren des generierten Codes mit der Compileroption, die die Ausgabe der XML-Dokumentation erstellt.</span><span class="sxs-lookup"><span data-stu-id="810b7-104">The process involves creating the CodeDOM graph that contains the XML documentation comments, generating the code, and compiling the generated code with the compiler option that creates the XML documentation output.</span></span>  
  
### <a name="to-create-a-codedom-graph-that-contains-xml-documentation-comments"></a><span data-ttu-id="810b7-105">SO erstellen Sie ein CodeDOM-Diagramm, das XML-Dokumentationskommentare enthält</span><span class="sxs-lookup"><span data-stu-id="810b7-105">To create a CodeDOM graph that contains XML documentation comments</span></span>  
  
1. <span data-ttu-id="810b7-106">Erstellen Sie eine <xref:System.CodeDom.CodeCompileUnit>, die das CodeDOM-Diagramm für die Beispielanwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="810b7-106">Create a <xref:System.CodeDom.CodeCompileUnit> containing the CodeDOM graph for the sample application.</span></span>  
  
2. <span data-ttu-id="810b7-107">Verwenden Sie den <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A>-Konstruktor mit dem `docComment`-Parameter, der auf `true` festgelegt ist, um die Kommentarelemente und den Kommentartext der XML-Dokumentation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="810b7-107">Use the <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> constructor with the `docComment` parameter set to `true` to create the XML documentation comment elements and text.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### <a name="to-generate-the-code-from-the-codecompileunit"></a><span data-ttu-id="810b7-108">So generieren Sie den Code aus der CodeCompileUnit</span><span class="sxs-lookup"><span data-stu-id="810b7-108">To generate the code from the CodeCompileUnit</span></span>  
  
1. <span data-ttu-id="810b7-109">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>-Methode, um den Code zu generieren und eine Quelldatei zu erstellen, die kompiliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="810b7-109">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code and create a source file to be compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### <a name="to-compile-the-code-and-generate-the-documentation-file"></a><span data-ttu-id="810b7-110">So kompilieren Sie den Code und generieren die Dokumentationsdatei</span><span class="sxs-lookup"><span data-stu-id="810b7-110">To compile the code and generate the documentation file</span></span>  
  
1. <span data-ttu-id="810b7-111">Fügen Sie die Compileroption **/doc** der <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A>-Eigenschaft eines <xref:System.CodeDom.Compiler.CompilerParameters>-Objekts hinzu, und übermitteln Sie das Objekt an die <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A>-Methode, um die XML-Dokumentationsdatei zu erstellen, wenn der Code kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="810b7-111">Add the **/doc** compiler option to the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property of a <xref:System.CodeDom.Compiler.CompilerParameters> object and pass the object to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method to create the XML documentation file when the code is compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="810b7-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="810b7-112">Example</span></span>  
 <span data-ttu-id="810b7-113">Das folgende Codebeispiel erstellt ein CodeDOM-Diagramm mit Dokumentationskommentaren, generiert eine Codedatei aus dem Diagramm und kompiliert die Datei und erstellt eine zugeordnete XML-Dokumentationsdatei.</span><span class="sxs-lookup"><span data-stu-id="810b7-113">The following code example creates a CodeDOM graph with documentation comments, generates a code file from the graph, and compiles the file and creates an associated XML documentation file.</span></span>  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 <span data-ttu-id="810b7-114">Das Codebeispiel erstellt die folgende XML-Dokumentation in der „HelloWorldDoc.xml“-Datei.</span><span class="sxs-lookup"><span data-stu-id="810b7-114">The code example creates the following XML documentation in the HelloWorldDoc.xml file.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="810b7-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="810b7-115">Compiling the Code</span></span>  
  
- <span data-ttu-id="810b7-116">Dieses Codebeispiel benötigt die festgelegte `FullTrust`-Berechtigung, damit es erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="810b7-116">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="810b7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="810b7-117">See also</span></span>

- [<span data-ttu-id="810b7-118">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="810b7-118">Documenting Your Code with XML</span></span>](../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="810b7-119">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="810b7-119">XML Documentation Comments</span></span>](../../csharp/programming-guide/xmldoc/index.md)
- [<span data-ttu-id="810b7-120">XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="810b7-120">XML Documentation</span></span>](/cpp/ide/xml-documentation-visual-cpp)
