---
title: Generieren und Kompilieren von Quellcode aus einem CodeDOM-Diagramm
description: Generieren und kompilieren Sie Quellcode aus einem CodeDOM-Graphen in .NET. Verwenden Sie einen CodeDOM-Codeanbieter zum Erstellen von Quellcode und kompilieren Sie Assemblys.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- CodeDOM, generating source code
- Code Document Object Model, graphs
- templated code generation
- source code, generating
- dynamically representing source code
- generating CodeDOM graphs
- Code Document Object Model, generating source code
- translating language to language
- compiling assemblies
- generating source code in multiple languages
- graphing with CodeDOM
- dynamic compilation
- assemblies [.NET Framework], CodeDOM
- source code generation
- outputting source code by CodeDOM
- code generators
- compiling source code, multiple languages
- CodeDOM, graphs
ms.assetid: 6c864c8e-6dd3-4a65-ace0-36879d9a9c42
ms.openlocfilehash: 85654fe961f01ad7b8fb886d59a3de9ab0efe7aa
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474045"
---
# <a name="generating-and-compiling-source-code-from-a-codedom-graph"></a>Generieren und Kompilieren von Quellcode aus einem CodeDOM-Diagramm
Der <xref:System.CodeDom.Compiler>-Namespace stellt Schnittstellen zum Generieren von Sourcecode aus CodeDOM-Objektdiagrammen und zum Verwalten der Kompilierung mit unterstützten Compilern bereit. Ein Codeanbieter kann Quellcode in einer bestimmten Programmiersprache anhand eines CodeDOM-Diagramms erstellen. Eine Klasse, die von <xref:System.CodeDom.Compiler.CodeDomProvider> abgeleitet wurde, kann in der Regel Methoden zum Generieren und Kompilieren von Code für die Sprache bereitstellen, die der Anbieter unterstützt.  
  
## <a name="using-a-codedom-code-provider-to-generate-source-code"></a>Verwenden eines CodeDOM-Codeanbieters zum Generieren von Quellcode  
 Zum Generieren von Quellcode in einer bestimmten Sprache benötigen Sie ein CodeDOM-Diagramm, das die Struktur des zu generierenden Quellcode darstellt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine Instanz einer <xref:Microsoft.CSharp.CSharpCodeProvider> erstellt wird:  
  
 [!code-cpp[CodeDomExample#21](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#21)]
 [!code-csharp[CodeDomExample#21](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#21)]
 [!code-vb[CodeDomExample#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#21)]  
  
 Das Diagramm für die Generierung von Code ist in der Regel Bestandteil einer <xref:System.CodeDom.CodeCompileUnit>. Zum Generieren von Code für eine **CodeCompileUnit**, die ein CodeDOM-Diagramm enthält, rufen Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>-Methode des Codeanbieters auf. Diese Methode verfügt einen Parameter für eine <xref:System.IO.TextWriter>, die zum Generieren des Quellcodes verwendet wird. Deshalb ist es manchmal erforderlich, zuerst eine **TextWriter**-Klasse zu erstellen, in die geschrieben werden kann. Das folgende Beispiel veranschaulicht die Erstellung von Code aus einer **CodeCompileUnit** und das Schreiben des generierten Quellcodes in eine Datei mit der Bezeichnung „HelloWorld.cs“.  
  
 [!code-cpp[CodeDomExample#22](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#22)]
 [!code-csharp[CodeDomExample#22](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#22)]
 [!code-vb[CodeDomExample#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#22)]  
  
## <a name="using-a-codedom-code-provider-to-compile-assemblies"></a>Verwenden eines CodeDOM-Codeanbieters zum Kompilieren von Assemblys  
 **Aufrufen der Kompilierung**  
  
 Um eine Assembly mit einem CodeDom-Anbieter zu kompilieren, müssen Sie entweder Quellcode besitzen, um in eine Sprache zu kompilieren, für die Sie einen Compiler oder ein CodeDOM-Diagramm besitzen, von dem der zu kompilierende Quellcode generiert werden kann.  
  
 Wenn Sie aus einem CodeDOM-Diagramm kompilieren, übergeben Sie die <xref:System.CodeDom.CodeCompileUnit> mit dem Diagramm an die <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A>-Methode des Codeanbieters. Wenn Sie über eine Quellcodedatei in einer Sprache verfügen, die der Compiler versteht, übergeben Sie den Namen der Datei, die den Quellcode enthält, an die <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A>-Methode des CodeDom-Anbieters. Sie können auch eine Zeichenfolge an die <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A>-Methode des CodeDom-Anbieters übergeben, die den Quellcode in einer Sprache enthält, die der Compiler versteht.  
  
 **Konfigurieren von Kompilierungsparametern**  
  
 Alle Standardmethoden zum Kompilierungsaufruf eines CodeDom-Anbieters besitzen einen Parameter vom Typ <xref:System.CodeDom.Compiler.CompilerParameters>, der die erforderlichen Optionen für die Kompilierung anzeigt.  
  
 Sie können den Dateinamen für die Ausgabeassembly in der <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A>-Eigenschaft der **CompilerParameters** angeben. Andererseits wird ein Standardname für die Ausgabedatei verwendet.  
  
 Standardmäßig wird eine **CompilerParameters**-Klasse initialisiert, und deren Eigenschaft <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> ist auf **FALSE** festgelegt. Wenn Sie ein ausführbares Programm kompilieren, müssen Sie die Eigenschaft **GenerateExecutable** auf **TRUE** festlegen. Wenn die **GenerateExecutable** auf **FALSE** festgelegt ist, generiert der Compiler eine Klassenbibliothek.  
  
 Wenn Sie eine ausführbare Datei aus einem CodeDOM-Diagramm kompilieren, muss eine <xref:System.CodeDom.CodeEntryPointMethod> im Diagramm definiert werden. Wenn es mehrere Codeeinstiegspunkte gibt, kann es womöglich erforderlich sein, die <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A>-Eigenschaft der **CompilerParameters** auf den Namen der Klasse festzulegen, die den zu verwendenden Einstiegspunkt definiert.  
  
 Um die Debuginformation in eine generierte ausführbare Datei einzuschließen, legen Sie die <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A>-Eigenschaft auf **TRUE** fest.  
  
 Wenn Ihr Projekt auf Assemblys verweist, müssen Sie die Assemblynamen als Elemente in einer <xref:System.Collections.Specialized.StringCollection> als <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A>-Eigenschaft der **CompilerParameters** angeben, die Sie beim Aufruf der Kompilierung verwenden.  
  
 Sie können eine Assembly kompilieren, die zum Speicher und nicht auf den Datenträger geschrieben wurde, indem Sie die <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A>-Eigenschaft auf **TRUE** festlegen. Wenn eine Assembly im Speicher generiert wird, kann Ihr Code einen Verweis aus einer <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A>-Eigenschaft einer <xref:System.CodeDom.Compiler.CompilerResults> für die generierte Assembly abrufen. Wenn eine Assembly auf den Datenträger geschrieben wird, können Sie den Pfad zur generierten Assembly aus einer <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A>-Eigenschaft einer **CompilerResults** abrufen.  
  
 Um einen benutzerdefinierte Argumentzeichenfolge auf Befehlszeilenebene anzugeben, die Sie beim Aufruf des Kompilierungsprozesses verwenden, legen Sie die Zeichenfolge in der <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A>-Eigenschaft fest.  
  
 Wenn ein Win32-Sicherheitstoken erforderlich ist, um den Compilerprozess auszurufen, geben Sie das Token in der <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A>-Eigenschaft an.  
  
 Um eine Win32-Ressourcendatei in der kompilierten Assembly zu verknüpfen, geben Sie den Namen der Win32-Ressourcendatei in der <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A>-Eigenschaft an.  
  
 Wenn Sie eine Warnstufe angeben möchten, an der Sie die Kompilierung anhalten möchten, legen Sie die <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A>-Eigenschaft auf einen Integer fest, der die Warnstufe darstellt, an der die Kompilierung angehalten werden soll. Sie können auch den Compiler konfigurieren, um die Kompilierung anzuhalten, wenn Warnungen aufgetreten sind, indem Sie die <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A>-Eigenschaft auf **TRUE** festlegen.  
  
 Das folgende Codebeispiel stellt die Kompilierung einer Quelldatei mithilfe des CodeDom-Anbieters dar, der aus der <xref:System.CodeDom.Compiler.CodeDomProvider>-Klasse abgeleitet wurde.  
  
 [!code-cpp[CodeDomExample#23](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#23)]
 [!code-csharp[CodeDomExample#23](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#23)]
 [!code-vb[CodeDomExample#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#23)]  
  
## <a name="languages-with-initial-support"></a>Sprachen mit erweiterter Unterstützung  
 Das .NET Framework bietet Codecompiler für Codegeneratoren für die folgenden Sprachen: C#, Visual Basic, C++ und JScript. Die CodeDOM-Unterstützung kann auf andere Sprachen durch Implementierung sprachspezifischer Codegeneratoren und Codecompiler erweitert werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.CodeDom>
- <xref:System.CodeDom.Compiler>
- [Generieren und Kompilieren von dynamischem Quellcode](dynamic-source-code-generation-and-compilation.md)
- [Kurzreferenz zum CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100))
