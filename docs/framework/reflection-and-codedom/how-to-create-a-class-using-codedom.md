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
ms.openlocfilehash: 7c2cda2bb7cbdb93c27aef91c08f7c7227da7eed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235700"
---
# <a name="how-to-create-a-class-using-codedom"></a>Vorgehensweise: Erstellen einer Klasse mit CodeDOM

Die folgenden Verfahren stellen dar, wie ein CodeDOM-Diagramm erstellt und kompiliert, das eine Klasse erstellt, die zwei Felder, drei Eigenschaften, eine Methode, einen Konstruktor und einen Einstiegspunkt enthält.  
  
1. Erstellen Sie eine Konsolenanwendung, die den CodeDOM-Code zum Generieren des Quellcodes für eine Klasse verwendet.  
  
     In diesem Beispiel heißt die generierende Klasse `Sample`, und der generierte Code ist eine Klasse namens `CodeDOMCreatedClass` in einer Datei namens „SampleCode“.  
  
2. Initialisieren Sie in der generierenden Klasse das CodeDOM-Diagramm, und verwenden Sie CodeDOM-Methoden, um die Member, den Konstruktor und den Einstiegspunkt (`Main`-Methode) der generierten Klasse zu definieren.  
  
     In diesem Beispiel verfügt die generierte Klasse über zwei Felder, drei Eigenschaften, einen Konstruktor, eine Methode und eine `Main`-Methode.  
  
3. Erstellen Sie in der generierenden Klasse einen sprachspezifischen Codeanbieter, und rufen Sie dessen <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>-Methode auf, um den Code aus dem Diagramm zu erstellen.  
  
4. Kompilieren Sie die Anwendung, und führen Sie sie aus, um den Code zu generieren.  
  
     In diesem Beispiel befindet sich der generierte Code in einer Datei namens „SampleCode“. Kompilieren Sie diesen Code, und führen Sie ihn aus, um die Beispielausgabe zu sehen.  
  
### <a name="to-create-the-application-that-will-execute-the-codedom-code"></a>So erstellen Sie die Anwendung, die den CodeDOM-Code ausführen wird  
  
- Erstellen Sie eine Konsolenanwendungsklasse, die den CodeDOM-Code enthalten soll. Definieren Sie die globalen Felder, die in der Klasse verwendet werden sollen, um die Assembly (<xref:System.CodeDom.CodeCompileUnit>) und die Klasse (<xref:System.CodeDom.CodeTypeDeclaration>) zu verweisen, den Namen der generierten Quelldatei anzugeben und die `Main`-Methode zu deklarieren.  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### <a name="to-initialize-the-codedom-graph"></a>So initialisieren Sie das CodeDOM-Diagramm  
  
- Initialisieren Sie im Konstruktor für die Konsolenanwendungsklasse die Assembly und Klasse, und fügen Sie dem CodeDOM-Diagramm die passenden Deklarationen hinzu.  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### <a name="to-add-members-to-the-codedom-graph"></a>So fügen Sie dem CodeDOM-Diagramm Member hinzu  
  
- Fügen Sie dem CodeDOM-Diagramm Felder hinzu, indem Sie der <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>-Eigenschaft der Klasse <xref:System.CodeDom.CodeMemberField>-Objekte hinzufügen.  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
- Fügen Sie dem CodeDOM-Diagramm Eigenschaften hinzu, indem Sie der <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>-Eigenschaft der Klasse <xref:System.CodeDom.CodeMemberProperty>-Objekte hinzufügen.  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
- Fügen Sie dem CodeDOM-Diagramm eine Methode hinzu, indem Sie der <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>-Eigenschaft der Klasse <xref:System.CodeDom.CodeMemberMethod>-Objekte hinzufügen.  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
- Fügen Sie dem CodeDOM-Diagramm einen Konstruktor hinzu, indem Sie der <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>-Eigenschaft der Klasse <xref:System.CodeDom.CodeConstructor>-Objekte hinzufügen.  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
- Fügen Sie dem CodeDOM-Diagramm einen Einstiegspunkt hinzu, indem Sie der <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>-Eigenschaft der Klasse <xref:System.CodeDom.CodeEntryPointMethod>-Objekte hinzufügen.  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### <a name="to-generate-the-code-from-the-codedom-graph"></a>So generieren Sie den Code aus dem CodeDOM-Diagramm  
  
- Generieren Sie Quellcode aus dem CodeDOM-Diagramm, indem Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>-Methode aufrufen.  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### <a name="to-create-the-graph-and-generate-the-code"></a>So erstellen Sie das Diagramm und generieren den Code  
  
1. Fügen Sie die in den vorherigen Schritten erstellten Methoden der `Main`-Methode, die im ersten Schritt definiert ist, hinzu.  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2. Kompilieren Sie die generierende Klasse, und führen Sie sie aus.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Codebeispiel wird der Code aus den vorherigen Schritten gezeigt.  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 Wenn das vorherige Beispiel kompiliert und ausgeführt wird, wird der folgende Quellcode erstellt.  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 Der generierte Quellcode erstellt die folgende Ausgabe, wenn er kompiliert und ausgeführt wird.  
  
```output
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- Dieses Codebeispiel benötigt die festgelegte `FullTrust`-Berechtigung, damit es erfolgreich ausgeführt werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von CodeDOM](using-the-codedom.md)
- [Generieren und Kompilieren von Quellcode aus einem CodeDOM-Diagramm](generating-and-compiling-source-code-from-a-codedom-graph.md)
