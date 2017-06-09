---
title: "Gewusst wie: Erstellen einer XML-Dokumentationsdatei mit CodeDOM | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Code Document Object Model (CodeDOM), Generieren einer XML-Dokumentation"
  - "CodeDOM, Generieren einer XML-Dokumentation"
  - "XML-Dokumentation, Erstellen mit CodeDOM"
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Erstellen einer XML-Dokumentationsdatei mit CodeDOM
Mit CodeDOM kann Code erstellt werden, der eine XML\-Dokumentation generiert.  Dieser Prozess umfasst das Erstellen des CodeDOM\-Diagramms, das die XML\-Dokumentationskommentare enthält, das Generieren des Codes und das Kompilieren des generierten Codes mit der Compileroption, die die XML\-Dokumentationsausgabe erstellt.  
  
### So erstellen Sie ein CodeDOM\-Diagramm, das XML\-Dokumentationskommentare enthält  
  
1.  Erstellen Sie eine <xref:System.CodeDom.CodeCompileUnit>, die das CodeDOM\-Diagramm für die Beispielanwendung enthält.  
  
2.  Mit dem <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A>\-Konstruktor und dem `docComment`\-Parameter, der auf `true` festgelegt ist, können Sie die Kommentarelemente und den Text der XML\-Dokumentation erstellen.  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### So generieren Sie den Code von CodeCompileUnit  
  
1.  Generieren Sie mit der <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>\-Methode den Code, und erstellen Sie eine zu kompilierende Quelldatei.  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### So kompilieren Sie den Code und generieren die Dokumentationsdatei  
  
1.  Fügen Sie die **\/doc**\-Compileroption der <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A>\-Eigenschaft eines <xref:System.CodeDom.Compiler.CompilerParameters>\-Objekts hinzu, und übergeben Sie das Objekt an die <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A>\-Methode, um die XML\-Dokumentationsdatei zu erstellen, wenn der Code kompiliert wird.  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## Beispiel  
 Im folgenden Codebeispiel wird ein CodeDOM\-Diagramm mit Dokumentationskommentaren erstellt, eine Codedatei aus dem Diagramm generiert, die Datei kompiliert und eine zugewiesene XML\-Dokumentationsdatei erstellt.  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 Im Codebeispiel wird die folgende XML\-Dokumentation in der Datei HelloWorldDoc.xml erstellt.  
  
```  
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
  
## Kompilieren des Codes  
  
-   Dieses Codebeispiel erfordert den `FullTrust`\-Berechtigungssatz, um erfolgreich ausgeführt werden zu können.  
  
## Siehe auch  
 [Documenting Your Code with XML](../Topic/Documenting%20Your%20Code%20with%20XML%20\(Visual%20Basic\).md)   
 [XML\-Dokumentationskommentare](../Topic/XML%20Documentation%20Comments%20\(C%23%20Programming%20Guide\).md)   
 [XML\-Dokumentation](../Topic/XML%20Documentation%20\(Visual%20C++\).md)