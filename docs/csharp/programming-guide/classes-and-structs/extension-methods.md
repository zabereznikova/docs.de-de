---
title: Erweiterungsmethoden – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], adding to existing types
- extension methods [C#]
- methods [C#], extension
ms.assetid: 175ce3ff-9bbf-4e64-8421-faeb81a0bb51
ms.openlocfilehash: ce35ef4d4286310aa6c8b6e40c3a448b0d91ea7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937522"
---
# <a name="extension-methods-c-programming-guide"></a>Erweiterungsmethoden (C#-Programmierhandbuch)
Mit Erweiterungsmethoden können Sie vorhandenen Typen Methoden hinzufügen, ohne einen neuen abgeleiteten Typ zu erstellen und ohne den ursprünglichen Typ neu kompilieren oder auf andere Weise bearbeiten zu müssen. Erweiterungsmethoden sind eine besondere Art von statischen Methoden, die Sie jedoch wie Instanzmethoden für den erweiterten Typ aufrufen können. Für in C#, F# und Visual Basic geschriebenen Clientcode gibt es keinen sichtbaren Unterschied zwischen dem Aufrufen einer Erweiterungsmethode und den Methoden, die in einem Typ tatsächlich definiert sind.  
  
 Die häufigsten Erweiterungsmethoden sind die LINQ-Standardabfrageoperatoren, die vorhandenen <xref:System.Collections.IEnumerable?displayProperty=nameWithType>- und <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>-Typen Funktionalität hinzufügen. Um die Standardabfrageoperatoren zu verwenden, müssen Sie sie zuerst mit einer `using System.Linq`-Direktive einbinden. Jeder Typ, der <xref:System.Collections.Generic.IEnumerable%601> implementiert, scheint Instanzmethoden zu haben, wie z. B. <xref:System.Linq.Enumerable.GroupBy%2A>, <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Average%2A>. Sie können diese zusätzlichen Methoden in der IntelliSense-Anweisungsvervollständigung sehen, wenn Sie nach einer Instanz eines <xref:System.Collections.Generic.IEnumerable%601>-Typs, z.B. <xref:System.Collections.Generic.List%601> oder <xref:System.Array>, "dot" eingeben.  
  
 Das folgende Beispiel zeigt, wie Sie die Standardabfrageoperator-Methode `OrderBy` für ein Ganzzahlarray aufrufen können. Der Ausdruck in Klammern ist ein Lambda-Ausdruck. Viele Standardabfrageoperatoren verwenden Lambda-Ausdrücke als Parameter, dies ist jedoch keine Voraussetzung für Erweiterungsmethoden. Weitere Informationen finden Sie unter [Lambdaausdrücke](../statements-expressions-operators/lambda-expressions.md).  
  
 [!code-csharp[csProgGuideExtensionMethods#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#3)]  
  
 Erweiterungsmethoden werden als statische Methoden definiert, jedoch mithilfe einer Instanzmethodensyntax aufgerufen. Der erste Parameter bestimmt, für welchen Typ die Methode gilt, und vor dem Parameter steht der [this](../../language-reference/keywords/this.md)-Modifizierer. Erweiterungsmethoden befinden sich nur dann im Bereich, wenn Sie den Namespace explizit mit einer `using`-Direktive in Ihren Quellcode importieren.  
  
 Im folgenden Beispiel wird eine für die <xref:System.String?displayProperty=nameWithType>-Klasse definierte Erweiterungsmethode veranschaulicht. Beachten Sie, dass sie in einer nicht geschachtelten, nicht generischen statischen Klasse definiert wird:  
  
 [!code-csharp[csProgGuideExtensionMethods#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#4)]  
  
 Die `WordCount`-Erweiterungsmethode kann mit dieser `using`-Direktive eingebunden werden:  
  
```csharp  
using ExtensionMethods;  
```  
  
 Sie kann darüber hinaus mit dieser Syntax von einer Anwendung aufgerufen werden:  
  
```csharp  
string s = "Hello Extension Methods";  
int i = s.WordCount();  
```  
  
 Im Code rufen Sie die Erweiterungsmethode mit Instanzmethodensyntax auf. Die vom Compiler erstellte Intermediate Language (IL) übersetzt jedoch Ihren Code in einen Aufruf der statischen Methode. Daher wird nicht wirklich gegen das Prinzip der Kapselung verstoßen. Erweiterungsmethoden können vielmehr nicht auf private Variablen im Typ zugreifen, den sie erweitern.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode](./how-to-implement-and-call-a-custom-extension-method.md).
  
 Im Allgemeinen werden Sie vermutlich viel häufiger Erweiterungsmethoden aufrufen, anstatt Ihre eigenen zu implementieren. Da Erweiterungsmethoden mit der Instanzmethodensyntax aufgerufen werden, sind für ihren Einsatz aus dem Clientcode keine besonderen Kenntnisse erforderlich. Um Erweiterungsmethoden für einen bestimmten Typ zu aktivieren, fügen Sie eine `using`-Direktive für den Namespace, in dem die Methoden definiert werden, hinzu. Um beispielsweise die Standardabfrageoperatoren zu verwenden, fügen Sie diese `using`-Direktive dem Code hinzu:  
  
```csharp  
using System.Linq;  
```  
  
 (Möglicherweise müssen Sie auch einen Verweis auf System.Core.dll hinzufügen.) Wie Sie sehen, werden die Standardabfrageoperatoren jetzt in IntelliSense als zusätzliche Methoden, die für die meisten <xref:System.Collections.Generic.IEnumerable%601>-Typen verfügbar sind, angezeigt.  
  
## <a name="binding-extension-methods-at-compile-time"></a>Binden von Erweiterungsmethoden während der Kompilierung  
 Sie können Erweiterungsmethoden verwenden, um eine Klasse oder eine Schnittstelle zu erweitern, jedoch nicht, um sie zu überschreiben. Eine Erweiterungsmethode mit dem gleichen Namen und der gleichen Signatur wie eine Schnittstellen- oder Klassenmethode wird nie aufgerufen. Bei der Kompilierung verfügen Erweiterungsmethoden immer über niedrigere Priorität als im Typ selbst definierte Instanzmethoden. Das heißt, wenn ein Typ eine Methode mit dem Namen `Process(int i)` hat und Sie über eine Erweiterungsmethode mit der gleichen Signatur verfügen, stellt der Compiler immer eine Bindung mit der Instanzmethode her. Wenn der Compiler einen Methodenaufruf erkennt, sucht er zuerst nach einer Entsprechung in den Instanzmethoden des Typs. Wenn keine Entsprechung gefunden wird, sucht er nach Erweiterungsmethoden, die für den Typ definiert wurden, und stellt eine Bindung mit der ersten gefundenen Erweiterungsmethode her. Im folgenden Beispiel wird veranschaulicht, wie der Compiler bestimmt, mit welcher Erweiterungsmethode oder Instanzmethode die Bindung erfolgen soll.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Regeln, denen der C#-Compiler folgt, um zu bestimmen, ob ein Methodenaufruf an eine Instanzmethode für den Typ oder an eine Erweiterungsmethode gebunden werden soll. Die statische Klasse `Extensions` enthält Erweiterungsmethoden, die für jeden Typ definiert wurden, der `IMyInterface` implementiert. Die Klassen `A`, `B` und `C` implementieren alle die Schnittstelle.  
  
 Die `MethodB`-Erweiterungsmethode wird nie aufgerufen, da ihr Name und die Signatur genau mit Methoden übereinstimmen, die bereits von den Klassen implementiert wurden.  
  
 Wenn der Compiler keine Instanzmethode mit einer entsprechenden Signatur findet, stellt er ggf. eine Bindung mit einer entsprechenden Erweiterungsmethode her.  
  
 [!code-csharp[csProgGuideExtensionMethods#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#5)]  
  
## <a name="general-guidelines"></a>Allgemeine Richtlinien  
 Im Allgemeinen wird empfohlen, dass Sie Erweiterungsmethoden sparsam und nur wenn unbedingt notwendig implementieren. Wenn möglich sollte der Clientcode, der einen vorhandenen Typ erweitern muss, dies durch die Erstellung eines neuen, vom vorhandenen Typ abgeleiteten Typs durchführen. Weitere Informationen finden Sie unter [Vererbung](./inheritance.md).  
  
 Wenn Sie eine Erweiterungsmethode zum Erweitern eines Typs, dessen Quellcode Sie nicht ändern können, verwenden, laufen Sie Gefahr, dass eine Änderung an der Implementierung des Typs eine Beschädigung der Erweiterungsmethode bewirkt.  
  
 Wenn Sie Erweiterungsmethoden für einen gegebenen Typ implementieren, beachten Sie die folgenden Punkte:  
  
- Eine Erweiterungsmethode wird nie aufgerufen, wenn sie die gleiche Signatur wie eine im Typ definierte Methode hat.  
  
- Erweiterungsmethoden werden auf Namespace-Ebene eingebunden. Wenn Sie z. B. mehrere statische Klassen haben, die Erweiterungsmethoden in einem einzelnen Namespace mit dem Namen `Extensions` enthalten, werden sie alle mit der `using Extensions;`-Direktive eingebunden.  
  
 Für eine Klassenbibliothek, die Sie implementiert haben, sollten Sie keine Erweiterungsmethoden verwenden, um zu vermeiden, dass die Versionsnummer einer Assembly erhöht wird. Wenn Sie einer Bibliothek, von deren Quellcode Sie der Besitzer oder die Besitzerin sind, wichtige Funktionen hinzufügen möchten, sollten Sie die standardmäßigen .NET Framework-Richtlinien für die Assemblyversionsverwaltung befolgen. Weitere Informationen dazu finden Sie unter [Assemblyversionen](../../../standard/assembly/versioning.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Parallel Programming Samples (Beispiele für parallele Programmierung (dazu gehören viele Beispielerweiterungsmethoden))](https://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)
- [Lambda-Ausdrücke](../statements-expressions-operators/lambda-expressions.md)
- [Übersicht über Standardabfrageoperatoren](../concepts/linq/standard-query-operators-overview.md)
- [Conversion rules for Instance parameters and their impact (Konvertierungsregeln für Instanzenparameter und ihre Auswirkungen)](https://docs.microsoft.com/archive/blogs/sreekarc/conversion-rules-for-instance-parameters-and-their-impact)
- [Extension methods Interoperability between languages (Erweiterungsmethoden-Interoperabilität zwischen Sprachen)](https://docs.microsoft.com/archive/blogs/sreekarc/extension-methods-interoperability-between-languages)
- [Extension methods and Curried Delegates (Erweiterungsmethoden und Curry-Delegaten)](https://docs.microsoft.com/archive/blogs/sreekarc/extension-methods-and-curried-delegates)
- [Extension method Binding and Error reporting (Binden von Erweiterungsmethoden und Problemberichten)](https://docs.microsoft.com/archive/blogs/sreekarc/extension-method-binding-and-error-reporting)
