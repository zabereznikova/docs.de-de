---
title: Verwenden von Namespaces (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.names
dev_langs:
- CSharp
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 61b5d78f1c4924e3858c14876d36e52d4ee46ceb
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="using-namespaces-c-programming-guide"></a>Verwenden von Namespaces (C#-Programmierhandbuch)
Namespaces werden häufig in C# -Programmen auf zwei verschiedene Arten verwendet. Erstens: Die .NET Framework-Klassen verwenden Namespaces, um ihre zahlreichen Klassen zu organisieren. Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern.  
  
## <a name="accessing-namespaces"></a>Zugriff auf Namespaces  
 Die meisten C#-Anwendungen beginnen mit einem Abschnitt von `using`-Anweisungen. Dieser Abschnitt enthält die von der Anwendung häufig verwendeten Namespaces und erspart dem Programmierer die Angabe eines vollqualifizierten Namens bei jedem Verwenden einer enthaltenen Methode.  
  
 Z.B. durch das Einfügen der Zeile  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]  
  
 Bei Programmstart kann der Programmierer folgenden Code verwenden:  
  
 [!code-cs[CsProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]  
  
 anstelle von:  
  
 [!code-cs[CsProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]  
  
## <a name="namespace-aliases"></a>Namespacealiase  
 Die [using-Anweisungen](../../../csharp/language-reference/keywords/using-directive.md) kann auch zum Erstellen eines Alias für einen [Namespace](../../../csharp/language-reference/keywords/namespace.md) verwendet werden. Wenn Sie einen bereits vorhandenen Namespace verwenden, der geschachtelte Namespaces enthält, können Sie einen Alias deklarieren, als schnelle Möglichkeit um auf einen bestimmten geschachtelten Namespace zu verweisen, wie im folgenden Beispiel gezeigt:  
  
 [!code-cs[CsProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]  
  
## <a name="using-namespaces-to-control-scope"></a>Verwenden von Namespaces zur Steuerung des Gültigkeitsbereichs  
 Mit dem Schlüsselwort `namespace` wird ein Bereich deklariert. Die Möglichkeit zum Erstellen von Bereichen innerhalb des Projekts, hilft Ihnen den Code zu organisieren und ermöglicht Ihnen die Erstellung von global eindeutigen Typen. Im folgenden Beispiel, wird eine Klasse mit dem Titel `SampleClass` in zwei ineinander geschachtelten Namespaces definiert. Die [. Operator](../../../csharp/language-reference/operators/member-access-operator.md) wird verwendet, um zu unterscheiden, welche Methode aufgerufen wird.  
  
 [!code-cs[CsProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]  
  
## <a name="fully-qualified-names"></a>Vollqualifizierte Namen  
 Namespaces und Typen verfügen über eindeutige durch den vollqualifizierten Namen, die eine logische Hierarchie an. Beispielsweise impliziert die Anweisung `A.B`, dass `A` der Name des Namespaces oder des Typs ist und, dass `B` darin geschachtelt ist.  
  
 Im folgenden Beispiel gibt es geschachtelte Klassen und Namespaces. Der vollqualifizierte Name ist als Kommentar angegeben, der auf jede Entität folgt.  
  
 [!code-cs[CsProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]  
  
 Das vorherige Codesegment weist Folgendes auf:  
  
-   Der Namespace `N1` ist ein Mitglied des globalen Namespaces. Sein vollqualifizierter Name lautet `N1`.  
  
-   Der Namespace `N2` ist ein Mitglied von `N1`. Sein vollqualifizierter Name lautet `N1.N2`.  
  
-   Die Klasse `C1` ist ein Mitglied von `N1`. Sein vollqualifizierter Name lautet `N1.C1`.  
  
-   Der Klassenname `C2` wird zweimal in diesem Code verwendet. Die vollqualifizierten Namen sind jedoch eindeutig. Die erste Instanz von `C2` wird in `C1` deklariert; daher lautet der vollqualifizierte Name: `N1.C1.C2`. Die zweite Instanz von `C2` wird in einem Namespace `N2` deklariert; daher lautet der vollqualifizierte Name: `N1.N2.C2`.  
  
 Mithilfe des vorhergehenden Codesegments können Sie dem Namespace `N1.N2` ein neues Klassenmitglied `C3` wie folgt hinzufügen:  
  
 [!code-cs[CsProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]  
  
 Im Allgemeinen verwenden Sie `::`, um auf einen Namespacealias, oder `global::`, um auf den globalen Namespace zu verweisen, und `.`, um Typen oder Mitglieder zu qualifizieren.  
  
 Die Verwendung von `::` mit einem Alias, der auf einen Typ statt auf einen Namespace verweist ist ein Fehler. Zum Beispiel:  
  
 [!code-cs[CsProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]  
  
 [!code-cs[CsProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]  
  
 Beachten Sie, dass das Wort `global` kein vorderfinierter Alias ist; deshalb hat `global.X` keine spezielle Bedeutung. Er erhält erst dann eine besondere Bedeutung, wenn er mit `::` verwendet wird.  
  
 Compilerwarnung CS0440 wird generiert, wenn Sie einen Alias mit dem Namen global definieren, da `global::` immer ein Verweis auf den globalen Namespace und nicht auf einen Alias ist. Beispielsweise generiert die folgende Zeile die folgende Warnung:  
  
 [!code-cs[CsProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]  
  
 Die Verwendung von `::` mit Aliasen ist ratsam, und verhindert die unbeabsichtigte Einführung von zusätzlichen Typen. Betrachten Sie beispielsweise das folgende Beispiel:  
  
 [!code-cs[CsProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]  
  
 [!code-cs[CsProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]  
  
 Dies funktioniert, aber wenn anschließend ein Typ mit dem Namen `Alias` eingeführt werden würde, würde `Alias.` an diesen Typ gebunden. Mit `Alias::Exception` wird sichergestellt, dass `Alias` als ein Namespacealias behandelt und nicht für einen Typ gehalten wird.  
  
 Finden Sie im Thema [Vorgehensweise: Verwenden des globalen Namespacealias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) Informationen zum `global` Alias.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Namespaces](../../../csharp/programming-guide/namespaces/index.md)   
 [Namespace Keywords (Schlüsselwörter des Namespace)](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [. Operator](../../../csharp/language-reference/operators/member-access-operator.md)   
 [Operator ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)

