---
title: "Verwenden von Namespaces (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.names"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Vollqualifizierte Namen [C#]"
  - "Namespaces [C#], Verwendung"
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# Verwenden von Namespaces (C#-Programmierhandbuch)
In C\#\-Programmen wird ausgiebig Gebrauch von Namespaces gemacht, wobei zwei Anwendungsfälle zu unterscheiden sind.  Zum einen verwenden die Klassen von .NET Framework Namespaces, um die große Anzahl von Klassen zu organisieren.  Zum anderen können Sie durch die Definition eines eigenen Namespaces die Steuerung des Gültigkeitsbereichs von Klassen\- und Methodennamen in größeren Programmierprojekten unterstützen.  
  
## Zugriff auf Namespaces  
 Die meisten C\#\-Anwendungen beginnen mit einem Abschnitt von `using`\-Direktiven.  In diesem Abschnitt werden die Namespaces aufgelistet, die in der Anwendung häufig verwendet werden. So muss der Programmierer nicht bei jeder Verwendung einer Methode aus einem dieser Namespaces den vollqualifizierten Namen angeben.  
  
 So kann der Programmierer zum Beispiel durch das Einfügen der Zeile  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]  
  
 an den Anfang eines Programms in der Folge den Code  
  
 [!code-cs[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]  
  
 anstelle dieses Codes verwenden:  
  
 [!code-cs[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]  
  
## Namespacealiase  
 Die [using\-Direktive](../../../csharp/language-reference/keywords/using-directive.md) kann auch verwendet werden, um einen Alias für einen [Namespace](../../../csharp/language-reference/keywords/namespace.md) zu erstellen.  Wenn Sie zum Beispiel einen bereits vorhandenen Namespace verwenden, der geschachtelte Namespaces enthält, können Sie einen Alias erzeugen, um den Schnellzugriff auf einen bestimmten geschachtelten Namespace zu ermöglichen. Beispiel:  
  
 [!code-cs[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]  
  
## Verwenden von Namespaces zur Steuerung des Gültigkeitsbereichs  
 Das `namespace`\-Schlüsselwort wird verwendet, um einen Gültigkeitsbereich zu deklarieren.  Durch die Möglichkeit, Gültigkeitsbereiche innerhalb eines Projekts zu definieren, wird die Organisation des Codes unterstützt. Zusätzlich lassen sich auf diese Art und Weise global eindeutige Typen erstellen.  Im folgenden Beispiel wird eine Klasse mit dem Namen `SampleClass` in zwei Namespaces definiert, von denen einer in den anderen geschachtelt ist.  Mit dem [. Operator](../../../csharp/language-reference/operators/member-access-operator.md) wird unterschieden, welche Methode aufgerufen wird.  
  
 [!code-cs[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]  
  
## Vollgekennzeichnete Namen  
 Namespaces und Typen verfügen über eindeutige Namen. Sie sind durch vollqualifizierte Namen beschrieben, die eine logische Hierarchie festlegen.  So impliziert zum Beispiel die Anweisung `A.B`, dass `A` der Name des Namespaces oder Typs ist und dass `B` darin enthalten ist.  
  
 Das folgende Beispiel enthält geschachtelte Klassen und Namespaces.  Der vollqualifizierte Name ist als Kommentar angegeben, der auf die einzelnen Entitäten folgt.  
  
 [!code-cs[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]  
  
 Das oben angegebene Codesegment weist Folgendes auf:  
  
-   Der Namespace `N1` ist ein Member des globalen Namespaces.  Sein vollqualifizierter Name lautet `N1`.  
  
-   Der Namespace `N2` ist ein Member von `N1`.  Sein vollqualifizierter Name lautet `N1.N2`.  
  
-   Die Klasse `C1` ist ein Member von `N1`.  Ihr vollqualifizierter Name lautet `N1.C1`.  
  
-   Der Klassenname `C2` wird in diesem Code zweimal verwendet.  Die vollqualifizierten Namen sind jedoch eindeutig.  Die erste Instanz von `C2` wird in `C1` deklariert, daher lautet der vollqualifizierte Name `N1.C1.C2`.  Die zweite Instanz von `C2` wird in einem Namespace `N2` deklariert, daher lautet der vollqualifizierte Name `N1.N2.C2`.  
  
 Im oben angegebenen Codesegment können Sie dem Namespace `N1.N2` auf folgende Weise den neuen Klassenmember `C3` hinzufügen:  
  
 [!code-cs[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]  
  
 Im Allgemeinen verweisen Sie mithilfe von `::` auf einen Namespacealias und mithilfe von `global::` auf den globalen Namespace, während Sie mit `.` Typen oder Member qualifizieren.  
  
 Die Verwendung von `::` mit einem Alias, der auf einen Typ statt auf einen Namespace verweist, stellt einen Fehler dar.  Beispiele:  
  
 [!code-cs[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]  
  
 [!code-cs[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]  
  
 Beachten Sie, dass das Wort `global` kein vordefinierter Alias ist und `global.X` daher keine besondere Bedeutung hat.  Eine besondere Bedeutung erhält der Ausdruck nur dann, wenn er mit `::` verwendet wird.  
  
 Wenn Sie einen Alias mit dem Namen global erstellen, wird die Compilerwarnung CS0440 generiert, da `global::` immer auf den globalen Namespace verweist, nicht jedoch auf einen Alias.  Zum Beispiel wird bei folgender Zeile eine Warnung generiert:  
  
 [!code-cs[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]  
  
 Die Verwendung von `::` mit Aliasen ist grundsätzlich sehr empfehlenswert. Auf diese Weise wird die unbeabsichtigte Einführung zusätzlicher Typen verhindert.  Betrachten Sie z. B. das folgende Beispiel:  
  
 [!code-cs[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]  
  
 [!code-cs[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]  
  
 Dies funktioniert, aber wenn anschließend ein Typ mit dem Namen `Alias` eingeführt würde, würde `Alias.` an diesen Typ gebunden.  Die Verwendung von `Alias::Exception` stellt sicher, dass `Alias` als Namespacealias behandelt und nicht mit einem Typ verwechselt wird.  
  
 Unter [Gewusst wie: Verwenden des globalen Namespacealias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) finden Sie ausführlichere Informationen zum `global`\-Alias.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Namespaces](../../../csharp/programming-guide/namespaces/index.md)   
 [Namespaceschlüsselwörter](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [. Operator](../../../csharp/language-reference/operators/member-access-operator.md)   
 [Operator ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)