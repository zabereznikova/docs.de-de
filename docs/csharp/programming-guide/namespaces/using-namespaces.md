---
title: Verwenden von Namespaces – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 5193fc7aaae83cbc0c75e81835244eaaaece69a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75700197"
---
# <a name="using-namespaces-c-programming-guide"></a>Verwenden von Namespaces (C#-Programmierhandbuch)

Namespaces werden häufig in C# -Programmen auf zwei verschiedene Arten verwendet. Erstens: Die .NET Framework-Klassen verwenden Namespaces, um ihre zahlreichen Klassen zu organisieren. Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern.  
  
## <a name="accessing-namespaces"></a>Zugriff auf Namespaces

 Die meisten C#-Anwendungen beginnen mit einem Abschnitt von `using`-Anweisungen. Dieser Abschnitt enthält die von der Anwendung häufig verwendeten Namespaces und erspart dem Programmierer die Angabe eines vollqualifizierten Namens bei jedem Verwenden einer enthaltenen Methode.  
  
 Z.B. durch das Einfügen der Zeile  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 Bei Programmstart kann der Programmierer folgenden Code verwenden:  
  
 [!code-csharp[csProgGuide#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#31)]  
  
 anstelle von:  
  
 [!code-csharp[csProgGuide#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#30)]  
  
## <a name="namespace-aliases"></a>Namespacealiase

 Sie können auch die [`using`-Anweisung](../../language-reference/keywords/using-directive.md) verwenden, um einen Alias für einen Namespace zu erstellen. Verwenden Sie [den Namespacealias-Qualifizierer`::`](../../language-reference/operators/namespace-alias-qualifier.md), um auf die Member des Namespace mit Alias zuzugreifen. Im folgenden Beispiel wird gezeigt, wie ein Namespacealias erstellt und verwendet wird:
  
[!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]
  
## <a name="using-namespaces-to-control-scope"></a>Verwenden von Namespaces zur Steuerung des Gültigkeitsbereichs

 Mit dem Schlüsselwort `namespace` wird ein Bereich deklariert. Die Möglichkeit zum Erstellen von Bereichen innerhalb des Projekts, hilft Ihnen den Code zu organisieren und ermöglicht Ihnen die Erstellung von global eindeutigen Typen. Im folgenden Beispiel, wird eine Klasse mit dem Titel `SampleClass` in zwei ineinander geschachtelten Namespaces definiert. Der [Operator `.` für den Memberzugriff](../../language-reference/operators/member-access-operators.md#member-access-operator-) wird verwendet, um zu unterscheiden, welche Methode aufgerufen wird.  
  
 [!code-csharp[csProgGuideNamespaces#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#8)]  
  
## <a name="fully-qualified-names"></a>Vollqualifizierte Namen

 Namespaces und Typen verfügen über eindeutige durch den vollqualifizierten Namen, die eine logische Hierarchie an. Beispielsweise impliziert die Anweisung `A.B`, dass `A` der Name des Namespaces oder des Typs ist und, dass `B` darin geschachtelt ist.  
  
 Im folgenden Beispiel gibt es geschachtelte Klassen und Namespaces. Der vollqualifizierte Name ist als Kommentar angegeben, der auf jede Entität folgt.  
  
 [!code-csharp[csProgGuideNamespaces#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#9)]  
  
 Das vorherige Codesegment weist Folgendes auf:  
  
- Der Namespace `N1` ist ein Mitglied des globalen Namespaces. Sein vollqualifizierter Name lautet `N1`.  
  
- Der Namespace `N2` ist ein Mitglied von `N1`. Sein vollqualifizierter Name lautet `N1.N2`.  
  
- Die Klasse `C1` ist ein Mitglied von `N1`. Sein vollqualifizierter Name lautet `N1.C1`.  
  
- Der Klassenname `C2` wird zweimal in diesem Code verwendet. Die vollqualifizierten Namen sind jedoch eindeutig. Die erste Instanz von `C2` wird in `C1` deklariert; daher lautet der vollqualifizierte Name: `N1.C1.C2`. Die zweite Instanz von `C2` wird in einem Namespace `N2` deklariert; daher lautet der vollqualifizierte Name: `N1.N2.C2`.  
  
 Mithilfe des vorhergehenden Codesegments können Sie dem Namespace `C3` ein neues Klassenmitglied `N1.N2` wie folgt hinzufügen:  
  
 [!code-csharp[csProgGuideNamespaces#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#10)]  
  
 Im Allgemeinen verwenden Sie den [Namespacealias-Qualifizierer `::`](../../language-reference/operators/namespace-alias-qualifier.md), um auf einen Namespacealias, oder `global::`, um auf den globalen Namespace zu verweisen, und `.`, um Typen oder Mitglieder zu qualifizieren.  
  
 Die Verwendung von `::` mit einem Alias, der auf einen Typ statt auf einen Namespace verweist ist ein Fehler. Beispiel:  
  
 [!code-csharp[csProgGuideNamespaces#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#11)]  
  
 [!code-csharp[csProgGuideNamespaces#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#12)]  
  
 Beachten Sie, dass das Wort `global` kein vorderfinierter Alias ist; deshalb hat `global.X` keine spezielle Bedeutung. Er erhält erst dann eine besondere Bedeutung, wenn er mit `::` verwendet wird.  
  
 Compilerwarnung CS0440 wird generiert, wenn Sie einen Alias mit dem Namen global definieren, da `global::` immer ein Verweis auf den globalen Namespace und nicht auf einen Alias ist. Beispielsweise generiert die folgende Zeile die folgende Warnung:  
  
 [!code-csharp[csProgGuideNamespaces#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#13)]  
  
 Die Verwendung von `::` mit Aliasen ist ratsam, und verhindert die unbeabsichtigte Einführung von zusätzlichen Typen. Betrachten Sie beispielsweise das folgende Beispiel:  
  
 [!code-csharp[csProgGuideNamespaces#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#14)]  
  
 [!code-csharp[csProgGuideNamespaces#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#15)]  
  
 Dies funktioniert, aber wenn anschließend ein Typ mit dem Namen `Alias` eingeführt werden würde, würde `Alias.` an diesen Typ gebunden. Mit `Alias::Exception` wird sichergestellt, dass `Alias` als ein Namespacealias behandelt und nicht für einen Typ gehalten wird.  

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Namespaces](./index.md)
- [.-Operator](../../language-reference/operators/member-access-operators.md#member-access-operator-)
- [::-Operator](../../language-reference/operators/namespace-alias-qualifier.md)
- [extern alias](../../language-reference/keywords/extern-alias.md)
