---
title: "Gewusst wie: Erstellen einer Klasse mit CodeDOM | Microsoft Docs"
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
  - "Code Document Object Model (CodeDOM), Erstellen von Klassen"
  - "Code Document Object Model (CodeDOM), Diagramme"
  - "CodeDOM, Erstellen von Klassen"
  - "CodeDOM, Diagramme"
  - "Diagrammerstellung mit CodeDOM"
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Erstellen einer Klasse mit CodeDOM
Die folgenden Verfahren zeigen, wie ein CodeDOM\-Diagramm erstellt und kompiliert wird, das eine Klasse mit zwei Feldern, drei Eigenschaften, einer Methode, einem Konstruktor und einem Einstiegspunkt generiert.  
  
1.  Erstellen Sie eine Konsolenanwendung, die CodeDOM\-Code verwendet, um den Quellcode für eine Klasse zu generieren.  
  
     In diesem Beispiel wird die generierende Klasse als `Sample` bezeichnet, und der generierte Code ist eine Klasse mit dem Namen `CodeDOMCreatedClass` in der Datei SampleCode.  
  
2.  Initialisieren Sie in der generierenden Klasse das CodeDOM\-Diagramm, und verwenden Sie CodeDOM\-Methoden, um die Member, den Konstruktor und den Einstiegspunkt \(`Main`\-Methode\) der generierten Klasse zu definieren.  
  
     In diesem Beispiel besitzt die generierte Klasse zwei Felder, drei Eigenschaften, einen Konstruktor, eine Methode und eine `Main`\-Methode.  
  
3.  Erstellen Sie in der generierenden Klasse einen sprachspezifischen Codeanbieter, und rufen Sie dessen <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>\-Methode auf, um den Code aus dem Diagramm zu generieren.  
  
4.  Kompilieren und führen Sie die Anwendung aus, um den Code zu generieren.  
  
     In diesem Beispiel ist der generierte Code in einer Datei mit dem Namen SampleCode.  Kompilieren und führen Sie diesen Code aus, um die Beispielausgabe zu sehen.  
  
### So erstellen Sie die Anwendung, die den CodeDOM\-Code ausführt  
  
-   Erstellen Sie eine Konsolenanwendungsklasse für den CodeDOM\-Code.  Definieren Sie die in der Klasse zu verwendenden globalen Felder, um auf die Assembly \(<xref:System.CodeDom.CodeCompileUnit>\) und die Klasse \(<xref:System.CodeDom.CodeTypeDeclaration>\) zu verweisen, geben Sie den Namen der generierten Quelldatei an, und deklarieren Sie die `Main`\-Methode.  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### So initialisieren Sie das CodeDOM\-Diagramm  
  
-   Initialisieren Sie im Konstruktor für die Konsolenanwendungsklasse die Assembly und die Klasse, und fügen Sie dem CodeDOM\-Diagramm die geeigneten Deklarationen hinzu.  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### So fügen Sie dem CodeDOM\-Diagramm Member hinzu  
  
-   Fügen Sie dem CodeDOM\-Diagramm Felder hinzu, indem Sie <xref:System.CodeDom.CodeMemberField>\-Objekte zur <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>\-Eigenschaft der Klasse hinzufügen.  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
-   Fügen Sie dem CodeDOM\-Diagramm Eigenschaften hinzu, indem Sie <xref:System.CodeDom.CodeMemberProperty>\-Objekte zur <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>\-Eigenschaft der Klasse hinzufügen.  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
-   Fügen Sie dem CodeDOM\-Diagramm eine Methode hinzu, indem Sie ein <xref:System.CodeDom.CodeMemberMethod>\-Objekt zur <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>\-Eigenschaft der Klasse hinzufügen.  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
-   Fügen Sie dem CodeDOM\-Diagramm einen Konstruktor hinzu, indem Sie ein <xref:System.CodeDom.CodeConstructor>\-Objekt zur <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>\-Eigenschaft der Klasse hinzufügen.  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
-   Fügen Sie dem CodeDOM\-Diagramm einen Einstiegspunkt hinzu, indem Sie ein <xref:System.CodeDom.CodeEntryPointMethod>\-Objekt zur <xref:System.CodeDom.CodeTypeDeclaration.Members%2A>\-Eigenschaft der Klasse hinzufügen.  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### So generieren Sie den Code aus dem CodeDOM\-Diagramm  
  
-   Generieren Sie Quellcode aus dem CodeDOM\-Diagramm, indem Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>\-Methode aufrufen.  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### So erstellen Sie das Diagramm und generieren den Code  
  
1.  Fügen Sie der im ersten Schritt definierten `Main`\-Methode die in den vorhergehenden Schritten erstellten Methoden hinzu.  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2.  Kompilieren und führen Sie die generierende Klasse aus.  
  
## Beispiel  
 Im folgenden Codebeispiel wird der Code der vorangehenden Schritte veranschaulicht.  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 Wenn das vorangehende Beispiel kompiliert und ausgeführt wird, erzeugt es den folgenden Quellcode.  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 Der generierte Quellcode erzeugt die folgende Ausgabe, wenn er kompiliert und ausgeführt wird.  
  
```  
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## Kompilieren des Codes  
  
-   Dieses Codebeispiel erfordert den `FullTrust`\-Berechtigungssatz, um erfolgreich ausgeführt werden zu können.  
  
## Siehe auch  
 [Verwenden von CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)   
 [Generieren und Kompilieren von Quellcode aus einem CodeDOM\-Diagramm](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)