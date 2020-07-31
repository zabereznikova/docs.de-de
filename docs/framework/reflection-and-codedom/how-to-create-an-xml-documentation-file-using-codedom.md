---
title: 'Vorgehensweise: Erstellen einer XML-Dokumentationsdatei mit CodeDOM'
description: In diesem ausführlichen Beispiel erfahren Sie, wie Sie Code erstellen, mit dem eine XML-Dokumentationsdatei mit dem Code Document Object Model (CodeDom) erstellt wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CodeDOM, generating XML documentation
- XML documentation, creating using CodeDOM
- Code Document Object Model, generating XML documentation
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
ms.openlocfilehash: f905b996910c6cfbc62378cc4cd6bb8c0e0e6fd4
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865150"
---
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a>Vorgehensweise: Erstellen einer XML-Dokumentation mit CodeDOM

CodeDOM kann zum Erstellen von Code verwendet werden, der eine XML-Dokumentation erstellt. Der Vorgang bringt die Erstellung des CodeDOM-Diagramms mit sich, das die XML-Dokumentationskommentare enthält, das Generieren des Codes und Kompilieren des generierten Codes mit der Compileroption, die die Ausgabe der XML-Dokumentation erstellt.  
  
## <a name="create-a-codedom-graph"></a>Erstellen eines CodeDOM-Graphen
  
1. Erstellen Sie eine <xref:System.CodeDom.CodeCompileUnit>, die das CodeDOM-Diagramm für die Beispielanwendung enthält.  
  
2. Verwenden Sie den <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A>-Konstruktor mit dem `docComment`-Parameter, der auf `true` festgelegt ist, um die Kommentarelemente und den Kommentartext der XML-Dokumentation zu erstellen.  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### <a name="generate-the-code-from-the-codecompileunit"></a>Generieren des Codes aus der CodeCompileUnit
  
1. Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>-Methode, um den Code zu generieren und eine Quelldatei zu erstellen, die kompiliert werden soll.  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### <a name="compile-the-code-and-generate-the-documentation-file"></a>Kompilieren des Codes und Generieren der Dokumentationsdatei
  
1. Fügen Sie die Compileroption **/doc** der <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A>-Eigenschaft eines <xref:System.CodeDom.Compiler.CompilerParameters>-Objekts hinzu, und übermitteln Sie das Objekt an die <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A>-Methode, um die XML-Dokumentationsdatei zu erstellen, wenn der Code kompiliert wird.  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## <a name="example"></a>Beispiel

Das folgende Codebeispiel erstellt ein CodeDOM-Diagramm mit Dokumentationskommentaren, generiert eine Codedatei aus dem Diagramm und kompiliert die Datei und erstellt eine zugeordnete XML-Dokumentationsdatei.  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 Das Codebeispiel erstellt die folgende XML-Dokumentation in der *HelloWorldDoc.xml*-Datei.  
  
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
      </summary>
      <seealso cref="M:Samples.Class1.Main" />
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
  
## <a name="compile-permissions"></a>Kompilierberechtigungen
  
Dieses Codebeispiel benötigt die festgelegte `FullTrust`-Berechtigung, damit es erfolgreich ausgeführt werden kann.
  
## <a name="see-also"></a>Siehe auch

- [Dokumentieren von Code mit XML (Visual Basic)](../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [XML-Dokumentationskommentare](../../csharp/programming-guide/xmldoc/index.md)
- [XML-Dokumentation (Visual C++)](/cpp/ide/xml-documentation-visual-cpp)
