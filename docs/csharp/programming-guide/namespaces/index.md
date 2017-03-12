---
title: "Namespaces (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Namespaces"
  - "Namespaces [C#]"
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# Namespaces (C#-Programmierhandbuch)
Bei der C\#\-Programmierung wird ausgiebig Gebrauch von Namespaces gemacht, wobei zwei Anwendungsfälle zu unterscheiden sind.  Zum einen werden Namespaces von .NET Framework zur Organisation seiner vielen Klassen verwendet. Beispiel:  
  
 [!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#22)]  
  
 `System` ist ein Namespace und `Console` ist eine in diesem Namespace enthaltene Klasse.  Das `using`\-Schlüsselwort kann verwendet werden, um nicht den ganzen Namen angeben zu müssen. Beispiel:  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/using.cs#1)]  
  
 [!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#25)]  
  
 Weitere Informationen finden Sie unter [using\-Direktive](../../../csharp/language-reference/keywords/using-directive.md).  
  
 Zum anderen können Sie durch die Definition eines eigenen Namespaces die Steuerung des Gültigkeitsbereiches von Klassen\- und Methodennamen in größeren Programmierprojekten unterstützen.  Verwenden Sie das [namespace](../../../csharp/language-reference/keywords/namespace.md)\-Schlüsselwort, um einen Namespace wie in folgendem Beispiel zu deklarieren:  
  
 [!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#6)]  
  
## Übersicht über Namespaces  
 Namespaces verfügen über folgende Eigenschaften:  
  
-   Sie organisieren große Codeprojekte.  
  
-   Sie werden mit dem Operator `.` begrenzt.  
  
-   Die `using directive` macht es überflüssig, den Namen des Namespace für jede Klasse anzugeben.  
  
-   Der `global`\-Namespace ist der "Stamm"\-Namespace: `global::System` verweist immer auf den .NET Framework\-Namespace `System`.  
  
## Verwandte Abschnitte  
 Weitere Informationen zur Verwendung von Namespaces finden Sie in den folgenden Themen:  
  
-   [Verwenden von Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [Gewusst wie: Verwenden des globalen Namespacealias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [Gewusst wie: Verwenden des My\-Namespaces](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Namespaceschlüsselwörter](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [using\-Direktive](../../../csharp/language-reference/keywords/using-directive.md)   
 [Operator ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [. Operator](../../../csharp/language-reference/operators/member-access-operator.md)