---
title: "Gewusst wie: &#220;berpr&#252;fen auf Verweisgleichheit (Identit&#228;t) (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Objektidentität [C#]"
  - "Verweisgleichheit [C#]"
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# Gewusst wie: &#220;berpr&#252;fen auf Verweisgleichheit (Identit&#228;t) (C#-Programmierhandbuch)
Sie müssen zur Unterstützung von Verweisgleichheitsprüfungen in Ihren Typen keine benutzerdefinierte Logik implementieren.  Diese Funktionalität wird für alle Typen mit der statischen <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName>\-Methode bereitgestellt.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie zwei Variablen auf *Verweisgleichheit* prüfen, d. h. ob diese auf das gleiche Objekt im Arbeitsspeicher verweisen.  
  
 Das Beispiel veranschaulicht außerdem, warum <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName> immer `false` für Wertetypen zurückgibt und warum <xref:System.Object.ReferenceEquals%2A> nicht zur Prüfung der Übereinstimmung von Zeichenfolgen geeignet ist.  
  
## Beispiel  
 [!code-cs[csProgGuideObjects#90](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-test-for-referenc_1.cs)]  
  
 Die Implementierung von `Equals` in der universellen Basisklasse <xref:System.Object?displayProperty=fullName> führt auch eine Verweisgleichheitsprüfung aus. Diese Methode wird jedoch nicht empfohlen, da es zu unerwarteten Ergebnissen kommen kann, wenn eine Klasse die Methode überschreibt.  Dasselbe gilt für den `==`\-Operator und den `!=`\-Operator.  Bei Anwendung auf Verweistypen wird mit \=\= und `!=` standardmäßig eine Verweisgleichheitsprüfung ausgeführt.  Der Operator kann aber von abgeleiteten Klassen überladen werden und eine Wertgleichheitsprüfung ausführen.  Um Fehler möglichst zu vermeiden, verwenden Sie am besten immer <xref:System.Object.ReferenceEquals%2A> zur Prüfung der Verweisgleichheit zweier Objekte.  
  
 Konstantenzeichenfolgen innerhalb der gleichen Assembly werden durch die Laufzeit immer intern gespeichert.  Das heißt, es wird nur eine Instanz jedes eindeutigen Zeichenfolgenliterals beibehalten.  Es gibt jedoch keine Garantie dafür, dass zur Laufzeit erstellte Zeichenfolgen oder zwei gleiche Konstantenzeichenfolgen in unterschiedlichen Assemblys intern gespeichert werden.  
  
## Siehe auch  
 [Übereinstimmungsvergleiche](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)