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
ms.openlocfilehash: 7a730a828488fd3ca04419588b3f32703dfda1c9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541733"
---
# <a name="using-the-codedom"></a>Verwenden von CodeDOM
CodeDOM stellt Typen bereit, die zahlreiche häufig verwendete Quellcodeelemente darstellen. Ein Programm kann entworfen werden, das ein Quellcodemodell mithilfe von CodeDOM-Elementen erstellt, um ein Objektdiagramm zusammenzustellen. Dieses Objektdiagramm kann mit einem CodeDOM-Code-Generator für eine unterstützte Programmiersprache als Quellcode gerendert werden. CodeDOM kann auch verwendet werden, um Quellcode in eine binäre Assembly zu kompilieren.  
  
 Im Folgenden werden einige häufige Verwendungsmöglichkeiten von CodeDOM aufgeführt:  
  
- Generieren von Code mit Vorlagen: Generieren von Code für ASP.NET, XML-Clientproxys für Webdienste, Code-Assistenten, Designer oder Mechanismen zur Ausgabe von Code.  
  
- Dynamische Kompilierung: Unterstützen der Codekompilierung in einer oder in mehreren Sprachen.  
  
## <a name="building-a-codedom-graph"></a>Erstellen eines CodeDOM-Diagramms  
 Der <xref:System.CodeDom>-Namespace stellt Klassen zur Verfügung, die die logische Struktur von Quellcode unabhängig von der Syntax der Sprache darstellen können.  
  
### <a name="the-structure-of-a-codedom-graph"></a>Die Struktur eines CodeDOM-Diagramms  
 Die Struktur eines CodeDOM-Diagramms ist mit der Struktur von Containern vergleichbar. Der oberste Container bzw. Stammcontainer der einzelnen kompilierbaren CodeDOM-Diagramme ist eine <xref:System.CodeDom.CodeCompileUnit>. Jedes Element des Quellcodemodells muss durch eine <xref:System.CodeDom.CodeObject>-Eigenschaft mit dem Diagramm verknüpft sein.  
  
### <a name="building-a-source-code-model-for-a-sample-hello-world-program"></a>Erstellen eines Quellcodemodells für ein Hello World-Beispielprogramm  
 Die folgende exemplarische Vorgehensweise bietet ein Beispiel für das Erstellen eines CodeDOM-Objektdiagramms, das den Code einer einfachen Hello World-Anwendung wiedergibt. Den vollständigen Quellcode für dieses Codebeispiel finden Sie im Thema <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.  
  
#### <a name="creating-a-compile-unit"></a>Erstellen einer Kompilierungseinheit  
 CodeDOM definiert ein als <xref:System.CodeDom.CodeCompileUnit> bezeichnetes Objekt, das auf ein CodeDOM-Objektdiagramm verweisen kann, das ein Modell des zu kompilierenden Quellcodes darstellt. Eine **CodeCompileUnit** verfügt über Eigenschaften zum Speichern von Verweisen auf Attribute, Namespaces und Assemblys.  
  
 Die von der <xref:System.CodeDom.Compiler.CodeDomProvider>-Klasse abgeleiteten CodeDom-Anbieter enthalten Methoden zum Verarbeiten des Objektdiagramms, auf das von einer **CodeCompileUnit** verwiesen wird.  
  
 Um ein Objektdiagramm für eine einfache Anwendung zu erstellen, müssen Sie das Quellcodemodell zusammenstellen und von einer **CodeCompileUnit** aus darauf verweisen.  
  
 Mit der in diesem Beispiel gezeigten Syntax können Sie eine neue Kompilierungseinheit erstellen:  
  
 [!code-cpp[CodeDomExample#12](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#12)]
 [!code-csharp[CodeDomExample#12](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#12)]
 [!code-vb[CodeDomExample#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#12)]  
  
 Eine <xref:System.CodeDom.CodeSnippetCompileUnit> kann einen Ausschnitt des Quellcodes enthalten, der sich bereits in der Zielsprache befindet, aber nicht in einer anderen Sprache gerendert werden kann.  
  
#### <a name="defining-a-namespace"></a>Definieren eines Namespaces  
 Zum Definieren eines Namespaces erstellen Sie einen <xref:System.CodeDom.CodeNamespace> und weisen ihm mit dem entsprechenden Konstruktor oder durch Festlegen der **Name**-Eigenschaft einen Namen zu.  
  
 [!code-cpp[CodeDomExample#13](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#13)]
 [!code-csharp[CodeDomExample#13](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#13)]
 [!code-vb[CodeDomExample#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#13)]  
  
#### <a name="importing-a-namespace"></a>Importieren eines Namespaces  
 Um dem Namespace eine Anweisung für den Namespaceimport hinzuzufügen, fügen Sie einen <xref:System.CodeDom.CodeNamespaceImport> hinzu, der den in die **CodeNamespace.Imports**-Auflistung zu importierenden Namespace angibt.  
  
 Der folgende Code fügt der **Imports**-Auflistung von **CodeNamespace** mit der Bezeichnung `samples` einen Import für den **System**-Namespace hinzu:  
  
 [!code-cpp[CodeDomExample#14](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#14)]
 [!code-csharp[CodeDomExample#14](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#14)]
 [!code-vb[CodeDomExample#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#14)]  
  
#### <a name="linking-code-elements-into-the-object-graph"></a>Verknüpfen von Codeelementen mit dem Objektdiagramm  
 Alle Codeelemente eines CodeDOM-Diagramms müssen durch eine Reihe von Verweisen zwischen Elementen, auf die von den Eigenschaften des Stammobjekts des Diagramms direkt verwiesen wird, mit der <xref:System.CodeDom.CodeCompileUnit> verknüpft werden, bei der es sich um das Stammelement der Struktur handelt. Legen Sie ein Objekt auf eine Eigenschaft eines Containerobjekts fest, um einen Verweis vom Containerobjekt zu erstellen.  
  
 Die folgende Anweisung fügt der **Namespaces**-Auflistungseigenschaft der Stamm-**CodeCompileUnit** den `samples`-**CodeNamespace** hinzu.  
  
 [!code-cpp[CodeDomExample#15](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#15)]
 [!code-csharp[CodeDomExample#15](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#15)]
 [!code-vb[CodeDomExample#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#15)]  
  
#### <a name="defining-a-type"></a>Definieren eines Typs  
 Um mit CodeDOM eine Klasse, Struktur, Schnittstelle oder Enumeration zu deklarieren, erstellen Sie eine neue <xref:System.CodeDom.CodeTypeDeclaration> und weisen ihr einen Namen zu. Das folgende Beispiel veranschaulicht dies. Die **Name**-Eigenschaft wird mithilfe einer Überladung des Konstruktors festgelegt:  
  
 [!code-cpp[CodeDomExample#16](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#16)]
 [!code-csharp[CodeDomExample#16](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#16)]
 [!code-vb[CodeDomExample#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#16)]  
  
 Zum Hinzufügen eines Typs zu einem Namespace fügen Sie der **Types**-Auflistung von **CodeNamespace** eine <xref:System.CodeDom.CodeTypeDeclaration> hinzu, die den dem Namespace hinzuzufügenden Typ darstellt.  
  
 Das folgende Beispiel veranschaulicht das Hinzufügen der Klasse `class1` zum **CodeNamespace** mit dem Namen `samples`:  
  
 [!code-cpp[CodeDomExample#17](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#17)]
 [!code-csharp[CodeDomExample#17](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#17)]
 [!code-vb[CodeDomExample#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#17)]  
  
#### <a name="adding-class-members-to-a-class"></a>Hinzufügen von Klassenmembern zu einer Klasse  
 Der <xref:System.CodeDom>-Namespace stellt eine Vielzahl von Elementen bereit, mit denen Klassenmember dargestellt werden können. Jeder Klassenmember kann der **Members**-Auflistung einer <xref:System.CodeDom.CodeTypeDeclaration> hinzugefügt werden.  
  
#### <a name="defining-a-code-entry-point-method-for-an-executable"></a>Definieren einer Code-Einstiegspunktmethode für eine ausführbare Datei  
 Wenn Sie den Code für ein ausführbares Programm erstellen, müssen Sie den Einstiegspunkt eines Programms angeben, indem Sie eine <xref:System.CodeDom.CodeEntryPointMethod> für die Darstellung der Methode erstellen, bei der die Programmausführung beginnen soll.  
  
 Im folgenden Beispiel wird das Definieren einer Einstiegspunktmethode veranschaulicht, die einen <xref:System.CodeDom.CodeMethodInvokeExpression> enthält, der **System.Console.WriteLine** aufruft, um „Hello World!“ auszugeben:  
  
 [!code-cpp[CodeDomExample#18](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#18)]
 [!code-csharp[CodeDomExample#18](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#18)]
 [!code-vb[CodeDomExample#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#18)]  
  
 Die folgende Anweisung fügt der **Members**-Auflistung von `class1` die Einstiegspunktmethode mit dem Namen `Start` hinzu:  
  
 [!code-cpp[CodeDomExample#19](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#19)]
 [!code-csharp[CodeDomExample#19](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#19)]
 [!code-vb[CodeDomExample#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#19)]  
  
 Die <xref:System.CodeDom.CodeCompileUnit> mit der Bezeichnung `compileUnit` enthält nun das CodeDOM-Diagramm für ein einfaches Hello World-Programm. Weitere Informationen über das Generieren und Kompilieren von Code aus einem CodeDOM-Diagramm finden Sie unter [Generating Source Code and Compiling a Program from a CodeDOM Graph (Generieren von Quellcode und Kompilieren eines Programms aus einem CodeDOM-Diagramm)](generating-and-compiling-source-code-from-a-codedom-graph.md).  
  
### <a name="more-information-on-building-a-codedom-graph"></a>Weitere Informationen zum Erstellen eines CodeDOM-Diagramms  
 Von CodeDOM werden viele häufig verwendete Typen von Codeelementen in den Programmiersprachen unterstützt, die die Common Language Runtime unterstützen. CodeDOM zielt nicht darauf ab, für die Darstellung aller denkbaren Programmiersprachenfeatures Elemente bereitzustellen. Code, der nicht einfach mit CodeDOM-Elementen dargestellt werden kann, kann in <xref:System.CodeDom.CodeSnippetExpression>, <xref:System.CodeDom.CodeSnippetStatement>, <xref:System.CodeDom.CodeSnippetTypeMember> oder <xref:System.CodeDom.CodeSnippetCompileUnit> gekapselt werden. Allerdings kann CodeDOM die Codeausschnitte nicht automatisch in andere Sprachen übersetzen.  
  
 Eine Dokumentation aller CodeDOM-Typen finden Sie in der Referenzdokumentation zum <xref:System.CodeDom>-Namespace.  
  
 Ein Übersichtsdiagramm, in dem das jeweils zum Darstellen eines bestimmten Codeelementtyps zu verwendende CodeDOM-Element gesucht werden kann, finden Sie in der [Kurzreferenz zu CodeDOM](/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)).
