---
title: "Gewusst wie: Überprüfen auf Verweisgleichheit (Identität) (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2dbbd7c0e5ebb507ca3dda0f248d9f1c8f9595fe
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a>Gewusst wie: Überprüfen auf Verweisgleichheit (Identität) (C#-Programmierhandbuch)
Sie müssen zur Unterstützung von Verweisgleichheitsprüfungen in Ihren Typen keine benutzerdefinierte Logik implementieren. Diese Funktionalität wird für alle Typen mit der statischen <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>-Methode bereitgestellt.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie zwei Variablen auf *Verweisgleichheit* prüfen, d.h. ob diese auf das gleiche Objekt im Arbeitsspeicher verweisen.  
  
 Das Beispiel veranschaulicht außerdem, warum <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> immer `false` für Wertetypen zurückgibt und warum <xref:System.Object.ReferenceEquals%2A> nicht zur Prüfung der Übereinstimmung von Zeichenfolgen geeignet ist.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideObjects#90](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-test-for-reference-equality-identity_1.cs)]  
  
 Die Implementierung von `Equals` in der universellen Basisklasse <xref:System.Object?displayProperty=nameWithType> führt auch eine Verweisgleichheitsprüfung aus. Diese Methode wird jedoch nicht empfohlen, da es zu unerwarteten Ergebnissen kommen kann, wenn eine Klasse die Methode überschreibt. Dasselbe gilt für den `==`-Operator und den `!=`-Operator. Bei Anwendung auf Verweistypen wird mit == und `!=` standardmäßig eine Verweisgleichheitsprüfung ausgeführt. Der Operator kann aber von abgeleiteten Klassen überladen werden und eine Wertgleichheitsprüfung ausführen. Um Fehler möglichst zu vermeiden, verwenden Sie am besten immer <xref:System.Object.ReferenceEquals%2A> zur Prüfung der Verweisgleichheit zweier Objekte.  
  
 Konstantenzeichenfolgen innerhalb der gleichen Assembly werden durch die Laufzeit immer intern gespeichert. Das heißt, es wird nur eine Instanz jedes eindeutigen Zeichenfolgenliterals beibehalten. Es gibt jedoch keine Garantie dafür, dass zur Laufzeit erstellte Zeichenfolgen oder zwei gleiche Konstantenzeichenfolgen in unterschiedlichen Assemblys intern gespeichert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Übereinstimmungsvergleiche](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)
