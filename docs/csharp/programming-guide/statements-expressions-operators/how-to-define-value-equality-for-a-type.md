---
title: 'Gewusst wie: Definieren von Wertgleichheit für einen Typ (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- overriding Equals method [C#]
- object equivalence [C#]
- Equals method [C#] , overriding
- value equality [C#]
- equivalence [C#]
ms.assetid: 4084581e-b931-498b-9534-cf7ef5b68690
ms.openlocfilehash: 365aa5a71eb3d07a79920f565a66fcac67de0b42
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042620"
---
# <a name="how-to-define-value-equality-for-a-type-c-programming-guide"></a>Gewusst wie: Definieren von Wertgleichheit für einen Typ (C#-Programmierhandbuch)
Wenn Sie eine Klasse oder Struktur definieren, entscheiden Sie, ob es sinnvoll ist, eine benutzerdefinierte Definition der Wertgleichheit (oder Äquivalenz) für den Typ zu erstellen. In der Regel implementieren Sie Wertgleichheit, wenn Objekte des Typs zu einer Auflistung hinzugefügt werden sollen oder wenn ihr Hauptzweck im Speichern einer Reihe von Feldern oder Eigenschaften besteht. Sie können die Definition der Wertgleichheit auf einem Vergleich aller Felder und Eigenschaften im Typ oder auf einer Teilmenge aufbauen. Ihre Implementierung in Klassen und Strukturen sollte in beiden Fällen die fünf Äquivalenzgarantien befolgen:  
  
1.  `x.Equals(x)` gibt `true` zurück. Dies wird als reflexive Eigenschaft bezeichnet.  
  
2.  `x.Equals(y)` gibt denselben Wert zurück wie `y.Equals(x)`. Die wird als symmetrische Eigenschaft bezeichnet.  
  
3.  Wenn `true` von `(x.Equals(y) && y.Equals(z))` zurückgegeben wird, wird `true` von `x.Equals(z)` zurückgegeben. Dies wird als transitive Eigenschaft bezeichnet.  
  
4.  Aufeinander folgende Aufrufe von `x.Equals(y)` geben immer denselben Wert zurück, es sei denn, die Objekte, auf die x und y verweisen, werden geändert.  
  
5.  `x.Equals(null)` gibt `false` zurück. `null.Equals(null)` löst allerdings eine Ausnahme aus, da die obige Regel Nummer 2 nicht befolgt wird.  
  
 Jede Struktur, die Sie definieren, besitzt bereits eine Standardimplementierung der Wertgleichheit, die von der <xref:System.ValueType?displayProperty=nameWithType>-Außerkraftsetzung der <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>-Methode geerbt wurde. Diese Implementierung verwendet Reflektion, um alle Felder und Eigenschaften im Typ zu untersuchen. Obwohl diese Implementierung richtige Ergebnisse produziert, ist sie relativ langsam im Vergleich zu einer benutzerdefinierten Implementierung, die Sie speziell für den Typ schreiben.  
  
 Die Implementierungsdetails für Wertgleichheit unterscheiden sich für Klassen und Strukturen. Sowohl Klassen als auch Strukturen erfordern dieselben grundlegenden Schritte zur Implementierung der Gleichheit:  
  
1.  Überschreiben Sie die [virtuelle](../../../csharp/language-reference/keywords/virtual.md) Methode <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>. In den meisten Fällen sollte Ihre Implementierung von `bool Equals( object obj )` nur die typspezifische `Equals`-Methode aufrufen, die die Implementierung der Schnittstelle <xref:System.IEquatable%601?displayProperty=nameWithType> darstellt. (Siehe Schritt 2)  
  
2.  Implementieren Sie die Schnittstelle <xref:System.IEquatable%601?displayProperty=nameWithType>, indem Sie eine typspezifische `Equals`-Methode bereitstellen. An dieser Stelle wird der eigentliche Äquivalenzvergleich ausgeführt. Sie könnten Gleichheit z.B. nur über den Vergleich von ein oder zwei Feldern in Ihrem Typ definieren. Lösen Sie keine Ausnahmen aus `Equals` aus. Nur für Klassen: Diese Methode sollte nur Felder prüfen, die in der Klasse deklariert sind. Sie sollte `base.Equals` aufrufen, um Felder in der Basisklasse zu prüfen. (Tun Sie dies nicht, wenn der Typ direkt von <xref:System.Object> erbt, da die <xref:System.Object>-Implementierung von <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> eine Überprüfung der Verweisgleichheit durchführt.)  
  
3.  Optional, aber empfohlen: Überladen Sie die Operatoren [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) und [!=](../../../csharp/language-reference/operators/not-equal-operator.md).  
  
4.  Überschreiben Sie <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>, damit zwei Objekte, die Wertgleichheit besitzen, den gleichen Hashcode erzeugen.  
  
5.  Optional: Implementieren Sie zur Unterstützung von Definitionen für „größer als“ oder „kleiner als“ die Schnittstelle <xref:System.IComparable%601> für Ihren Typ, und überladen Sie die Operatoren [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) und [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md).  
  
 Das erste nachfolgende Beispiel zeigt die Implementierung einer Klasse. Das zweite nachfolgende Beispiel zeigt die Implementierung einer Struktur.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie Wertgleichheit in einer Klasse (Referenztyp) implementieren.  
  
 [!code-csharp[csProgGuideStatements#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_1.cs)]  
  
 Die standardmäßige Implementierung beider <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>-Methoden führt bei Klassen (Referenztypen) einen Verweisgleichheitsvergleich, keine Wertgleichheitsprüfung aus. Wenn eine Implementierer die virtuelle Methode überschreibt, dient dies dazu, ihr Wertgleichheitssemantik zu verleihen.  
  
 Die Operatoren `==` und `!=` können mit Klassen verwendet werden, selbst wenn die Klasse sie nicht überlädt. Allerdings ist das Standardverhalten eine Ausführung einer Verweisgleichheitsprüfung. Wenn Sie die `Equals`-Methode in einer Klasse überladen, sollten Sie die Operatoren `==` und `!=` überladen, obwohl dies nicht erforderlich ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie Wertgleichheit in einer Struktur (Werttyp) implementieren:  
  
 [!code-csharp[csProgGuideStatements#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_2.cs)]  
  
 Für Strukturen führt die Standardimplementierung von <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> (was die außer Kraft gesetzte Version in <xref:System.ValueType?displayProperty=nameWithType> ist) eine Überprüfung der Wertgleichheit durch, indem sie Reflektion zum Vergleichen der Werte jedes Felds im Typ verwendet. Wenn ein Implementierer die virtuelle `Equals`-Methode in einer Struktur überschreibt, dient dies der Bereitstellung effizienterer Mittel für die Ausführung der Wertgleichheitsprüfung und optional dazu, den Vergleich auf einer Teilmenge des Felds oder der Eigenschaften der Struktur zu basieren.  
  
 Die Operatoren [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) und [!=](../../../csharp/language-reference/operators/not-equal-operator.md) können nicht auf Strukturen operieren, es sei denn, die Struktur überlädt sie explizit.  
  
## <a name="see-also"></a>Siehe auch

- [Übereinstimmungsvergleiche](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
