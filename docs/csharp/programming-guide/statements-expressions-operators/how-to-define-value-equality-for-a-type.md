---
title: "Gewusst wie: Definieren von Wertgleichheit f&#252;r einen Typ (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Equals-Methode [C#], Überschreiben"
  - "Äquivalenz [C#]"
  - "Objektäquivalenz [C#]"
  - "Überschreiben der Equals-Methode [C#]"
  - "Wertgleichheit [C#]"
ms.assetid: 4084581e-b931-498b-9534-cf7ef5b68690
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Definieren von Wertgleichheit f&#252;r einen Typ (C#-Programmierhandbuch)
Wenn Sie eine Klasse oder eine Struktur definieren, entscheiden Sie, ob es Sinn macht, eine benutzerdefinierte Definition der Wertgleichheit \(oder Äquivalenz\) für den Typ zu erstellen.  In der Regel implementieren Sie Wertgleichheit, wenn Objekte eines Typs in irgendeiner Weise einer Auflistung hinzugefügt werden sollen, oder wenn ihr primärer Zweck darin besteht, eine Reihe von Feldern oder Eigenschaften zu speichern.  Für die Definition der Wertgleichheit können Sie einen Vergleich aller Felder und Eigenschaften im Typ oder aber eine Teilmenge zugrunde legen.  Aber in jedem Fall sollte Ihre Implementierung sich sowohl bei Klassen als auch bei Strukturen nach den folgenden Grundsätzen richten:  
  
1.  x.`Equals`\(x\) gibt `true.` zurück. Dies wird als reflexive Eigenschaft bezeichnet.  
  
2.  x.`Equals`\(y\) gibt den gleichen Wert zurück wie y.`Equals`\(x\).  Dies wird als symmetrische Eigenschaft bezeichnet.  
  
3.  Wenn \(x.`Equals`\(y\) && y.`Equals`\(z\)\) `true` zurückgibt, dann gibt x.`Equals`\(z\) auch `true` zurück.  Dies wird als transitive Eigenschaft bezeichnet.  
  
4.  Aufeinanderfolgende Aufrufe von x.`Equals`\(y\) geben den gleichen Wert zurück, vorausgesetzt, die Objekte, auf die x und y verweisen, werden nicht geändert.  
  
5.  x.`Equals`\(null\) gibt `false` zurück.  null.Equals\(null\) löst jedoch eine Ausnahme aus, die zweite oben stehende Regel gilt hier nicht.  
  
 Jede Struktur, die Sie definieren, verfügt bereits über eine Standardimplementierung der Wertgleichheit, die von der <xref:System.ValueType?displayProperty=fullName>\-Überschreibung der <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>\-Methode geerbt wird.  Diese Implementierung prüft mithilfe von Reflektion alle öffentlichen und nicht öffentlichen Felder und Eigenschaften im Typ.  Diese Implementierung führt zwar zu richtigen Ergebnissen, ist jedoch im Vergleich zu einer benutzerdefinierten Implementierung, die Sie speziell für den Typ schreiben, relativ langsam.  
  
 Die Implementierungsdetails der Wertgleichheit sind für Klassen und Strukturen unterschiedlich.  Die grundlegenden Schritte zur Implementierung der Gleichheit sind jedoch für Klassen und Strukturen dieselben:  
  
1.  Überschreiben Sie die [virtual](../../../csharp/language-reference/keywords/virtual.md) <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>\-Methode.  In den meisten Fällen sollte die Implementierung von `bool Equals( object obj )` nur die typspezifische `Equals`\-Methode aufrufen, bei der es sich um die Implementierung der <xref:System.IEquatable%601?displayProperty=fullName>\-Schnittstelle handelt.  \(Siehe Schritt 2.\)  
  
2.  Implementieren Sie die <xref:System.IEquatable%601?displayProperty=fullName>\-Schnittstelle, indem Sie eine typspezifische `Equals`\-Methode angeben.  An diesem Punkt findet der tatsächliche Äquivalenzvergleich statt.  Sie können z. B. entscheiden, zur Definition der Gleichheit den Vergleich von lediglich einem oder zwei Feldern in Ihrem Typ zu wählen.  Lösen Sie keine Ausnahmen von `Equals` aus.  Nur für Klassen: Diese Methode darf nur Felder prüfen, die in der Klasse deklariert werden.  Zur Prüfung von Feldern in der Basisklasse muss `base.Equals` aufgerufen werden.  \(Lassen Sie dies weg, wenn der Typ direkt von <xref:System.Object> erbt, da die <xref:System.Object>\-Implementierung von <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> eine Verweisgleichheitsprüfung ausführt.\)  
  
3.  Optional, aber empfohlen: Überladen des [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md)\-Operators und des [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md)\-Operators.  
  
4.  Überschreiben Sie <xref:System.Object.GetHashCode%2A?displayProperty=fullName>, damit zwei Objekte mit Wertgleichheit den gleichen Hash erzeugen.  
  
5.  Optional: Zur Unterstützung von Definitionen für "größer als" oder "kleiner als" implementieren Sie die <xref:System.IComparable%601>\-Schnittstelle für Ihren Typ, und überladen Sie den [\<\=](../../../csharp/language-reference/operators/less-than-equal-operator.md)\-Operator und den [\>\=](../../../csharp/language-reference/operators/greater-than-equal-operator.md)\-Operator.  
  
 Das erste folgende Beispiel zeigt eine Klassenimplementierung.  Das zweite folgende Beispiel zeigt eine Strukturimplementierung.  
  
## Beispiel  
 Im folgenden Beispiel wird die Implementierung der Gleichheitsprüfung in einer Klasse \(Verweistyp\) veranschaulicht.  
  
 [!code-cs[csProgGuideStatements#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equalit_1.cs)]  
  
 Für Klassen \(Verweistypen\) führt die Standardimplementierung beider <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>\-Methoden eine Verweisgleichheitsprüfung aus, keine Wertgleichheitsprüfung.  Wenn ein Ausführender die virtuelle Methode überschreibt, ist der Zweck die Zuweisung von Wertgleichheitssemantik.  
  
 Der `==`\-Operator und der `!=`\-Operator können mit Klassen verwendet werden, auch wenn die Klasse diese nicht überlädt.  Das Standardverhalten ist jedoch die Ausführung einer Verweisgleichheitsprüfung.  Wenn Sie in einer Klasse die `Equals`\-Methode überladen, wird empfohlen, die Operatoren `==` und `!=` zu überladen. Dies ist jedoch nicht zwingend erforderlich.  
  
## Beispiel  
 Im folgenden Beispiel wird die Implementierung der Wertgleichheit in einer Struktur \(Werttyp\) veranschaulicht:  
  
 [!code-cs[csProgGuideStatements#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equalit_2.cs)]  
  
 Für Strukturen führt die Standardimplementierung von <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> \(die überschriebene Version in <xref:System.ValueType?displayProperty=fullName>\) eine Wertgleichheitsprüfung durch, wobei die Werte jedes Feldes im Typ mithilfe von Reflektion verglichen werden.  Wenn ein Ausführender die virtuelle `Equals`\-Methode in einer Struktur überschreibt, dient dies zur Bereitstellung einer effizienteren Methode zur Ausführung der Wertgleichheitsprüfung und zur Verwendung einer Teilmenge der Felder und Eigenschaften der Struktur für den Vergleich \(optional\).  
  
 Die Operatoren [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) und [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md) müssen zur Verwendung für eine Struktur explizit überladen werden.  
  
## Siehe auch  
 [Übereinstimmungsvergleiche](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)