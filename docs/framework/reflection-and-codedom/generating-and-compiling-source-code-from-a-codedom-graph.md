---
title: "Generieren und Kompilieren von Quellcode aus einem CodeDOM-Diagramm | Microsoft Docs"
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
  - "Assemblys [.NET Framework], CodeDOM"
  - "Codecompiler"
  - "Code Document Object Model (CodeDOM), Generieren von Quellcode"
  - "Code Document Object Model (CodeDOM), Diagramme"
  - "Codegeneratoren"
  - "CodeDOM, Generieren von Quellcode"
  - "CodeDOM, Diagramme"
  - "Kompilieren von Assemblys"
  - "Kompilieren von Quellcode, Mehrere Sprachen"
  - "Dynamische Kompilierung"
  - "Dynamisches Darstellen von Quellcode"
  - "Generieren von CodeDOM-Diagrammen"
  - "Generieren von Quellcode in mehreren Sprachen"
  - "Diagrammerstellung mit CodeDOM"
  - "Ausgabe von Quellcode durch CodeDOM"
  - "Quellcodegenerierung"
  - "Quellcode, Generieren"
  - "Vorlagenbasierte Codegenerierung"
  - "Übersetzen aus einer Sprache in eine andere"
ms.assetid: 6c864c8e-6dd3-4a65-ace0-36879d9a9c42
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Generieren und Kompilieren von Quellcode aus einem CodeDOM-Diagramm
Der <xref:System.CodeDom.Compiler>\-Namespace stellt Schnittstellen zum Generieren von Quellcode aus CodeDOM\-Objektdiagrammen und zum Verwalten der Kompilierung mit unterstützten Compilern bereit.   Ein Codeanbieter kann Quellcode in einer bestimmten Programmiersprache entsprechend einem CodeDOM\-Diagramm erstellen.  Eine von <xref:System.CodeDom.Compiler.CodeDomProvider> abgeleitete Klasse kann normalerweise Methoden bereitstellen, durch die Code für die vom Anbieter unterstützte Sprache generiert und kompiliert wird.  
  
## Verwenden eines CodeDOM\-Codeanbieters zum Generieren von Quellcode  
 Zum Generieren von Quellcode in einer bestimmten Sprache benötigen Sie ein CodeDOM\-Diagramm, das die Struktur des zu generierenden Quellcodes darstellt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine Instanz von <xref:Microsoft.CSharp.CSharpCodeProvider> erstellt wird:  
  
 [!code-cpp[CodeDomExample#21](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#21)]
 [!code-csharp[CodeDomExample#21](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#21)]
 [!code-vb[CodeDomExample#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#21)]  
  
 Das Diagramm für die Codegenerierung befindet sich normalerweise in einer <xref:System.CodeDom.CodeCompileUnit>.  Zum Generieren von Code für eine **CodeCompileUnit**, die ein CodeDOM\-Diagramm enthält, rufen Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>\-Methode des Codeanbieters auf.  Diese Methode enthält einen Parameter für einen <xref:System.IO.TextWriter>, der zum Generieren des Quellcodes verwendet wird, sodass in einigen Fällen zunächst ein **TextWriter** erstellt werden muss, in den geschrieben werden kann.   Das folgende Beispiel veranschaulicht das Generieren von Code aus einer **CodeCompileUnit** und das Schreiben des generierten Quellcodes in eine Datei mit der Bezeichnung HelloWorld.cs.  
  
 [!code-cpp[CodeDomExample#22](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#22)]
 [!code-csharp[CodeDomExample#22](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#22)]
 [!code-vb[CodeDomExample#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#22)]  
  
## Verwenden eines CodeDOM\-Codeanbieters zum Kompilieren von Assemblys  
 **Aufrufen der Kompilierung**  
  
 Zum Kompilieren einer Assembly mithilfe eines CodeDom\-Anbieters benötigen Sie entweder in einer Sprache zu kompilierenden Quellcode, für die ein Compiler vorhanden ist, oder ein CodeDOM\-Diagramm, aus dem der zu kompilierende Quellcode generiert werden kann.  
  
 Wenn Sie aus einem CodeDOM\-Diagramm kompilieren, übergeben Sie die <xref:System.CodeDom.CodeCompileUnit> mit dem Diagramm an die <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A>\-Methode des Codeanbieters.   Bei einer Quellcodedatei in einer vom Compiler unterstützten Sprache übergeben Sie der <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A>\-Methode des CodeDom\-Anbieters den Namen der Datei, die den Quellcode enthält.  Sie können der <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A>\-Methode des CodeDom\-Anbieters auch eine Zeichenfolge übergeben, die den Quellcode in einer vom Compiler unterstützten Sprache enthält.  
  
 **Konfigurieren von Kompilierungsparametern**  
  
 Alle Standardmethoden zum Kompilierungsaufruf eines CodeDom\-Anbieters enthalten einen Parameter vom Typ <xref:System.CodeDom.Compiler.CompilerParameters>, der die Optionen angibt, die zum Kompilieren verwendet werden.  
  
 In der <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A>\-Eigenschaft von **CompilerParameters** können Sie einen Dateinamen für die Ausgabeassembly angeben.   Andernfalls wird ein Standardname für die Ausgabedatei verwendet.  
  
 Beim Initialisieren einer neuen Instanz von **CompilerParameters** wird die <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A>\-Eigenschaft standardmäßig auf **false** festgelegt.   Wenn Sie ein ausführbares Programm kompilieren, müssen Sie die **GenerateExecutable**\-Eigenschaft auf **true** festlegen.  Wenn **GenerateExecutable** auf **false** festgelegt ist, generiert der Compiler eine Klassenbibliothek.  
  
 Wenn Sie eine ausführbare Datei aus einem CodeDOM\-Diagramm kompilieren, muss im Diagramm eine <xref:System.CodeDom.CodeEntryPointMethod> definiert sein.  Wenn mehrere Codeeinstiegspunkte vorhanden sind, muss die <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A>\-Eigenschaft von **CompilerParameters** möglicherweise auf den Namen der Klasse festgelegt werden, die den zu verwendenden Einstiegspunkt definiert.  
  
 Um Debuginformationen in eine generierte ausführbare Datei einzufügen, legen Sie die <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A>\-Eigenschaft auf **true** fest.  
  
 Wenn das Projekt Verweise auf Assemblys enthält, müssen Sie für die <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A>\-Eigenschaft der beim Aufruf der Kompilierung verwendeten **CompilerParameters** die Assemblynamen als Elemente in einer <xref:System.Collections.Specialized.StringCollection> angeben.  
  
 Sie können eine Assembly kompilieren, die nicht auf den Datenträger, sondern in den Speicher geschrieben wird, indem Sie die <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A>\-Eigenschaft auf **true** festlegen.  Wenn eine Assembly im Speicher generiert wird, kann der Code aus der <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A>\-Eigenschaft von <xref:System.CodeDom.Compiler.CompilerResults> einen Verweis auf die generierte Assembly abrufen.  Wenn eine Assembly auf einen Datenträger geschrieben wird, können Sie aus der <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A>\-Eigenschaft von **CompilerResults** den Pfad zur generierten Assembly abrufen.  
  
 Um eine benutzerdefinierte Zeichenfolge für Befehlszeilenargumente anzugeben, die beim Aufrufen der Kompilierung verwendet werden soll, legen Sie die Zeichenfolge in der <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A>\-Eigenschaft fest.  
  
 Wenn für den Aufruf des Compilerprozesses ein Win32\-Sicherheitstoken erforderlich ist, geben Sie das Token in der <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A>\-Eigenschaft an.  
  
 Um mit der kompilierten Assembly eine Win32\-Ressourcendatei zu verknüpfen, geben Sie den Namen der Win32\-Ressourcendatei in der <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A>\-Eigenschaft an.  
  
 Wenn Sie eine Warnstufe angeben möchten, bei der die Kompilierung unterbrochen werden soll, legen Sie die <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A>\-Eigenschaft auf eine ganze Zahl fest, die die Warnstufe zum Unterbrechen der Kompilierung darstellt.  Sie können den Compiler auch für die Unterbrechung der Kompilierung beim Auftreten von Warnungen konfigurieren, indem Sie die <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A>\-Eigenschaft auf **true** festlegen.  
  
 Das folgende Codebeispiel veranschaulicht die Kompilierung einer Quelldatei mithilfe eines CodeDom\-Anbieters, der von der <xref:System.CodeDom.Compiler.CodeDomProvider>\-Klasse abgeleitet wurde.  
  
 [!code-cpp[CodeDomExample#23](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#23)]
 [!code-csharp[CodeDomExample#23](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#23)]
 [!code-vb[CodeDomExample#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#23)]  
  
## Von Beginn an unterstützte Sprachen  
 .NET Framework bietet Codecompiler und Codegeneratoren für folgende Sprachen: C\#, Visual Basic, C\+\+ und JScript.  Die CodeDOM\-Unterstützung kann auf andere Sprachen erweitert werden, indem sprachspezifische Code\-Generatoren und Codecompiler implementiert werden.  
  
## Siehe auch  
 <xref:System.CodeDom>   
 <xref:System.CodeDom.Compiler>   
 [Generieren und Kompilieren von dynamischem Quellcode](../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)   
 [CodeDOM Quick Reference](http://msdn.microsoft.com/de-de/c77b8bfd-0a32-4e36-b59a-4f687f32c524)