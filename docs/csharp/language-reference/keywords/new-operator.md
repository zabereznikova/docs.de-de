---
title: new-Operator (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 22
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f0831bbbaf68c8c9e1e0e2d77ccf18e7c8b42e4a
ms.lasthandoff: 03/13/2017

---
# <a name="new-operator-c-reference"></a>new-Operator (C#-Referenz)
Wird zum Erstellen von Objekten und zum Aufrufen von Konstruktoren verwendet. Zum Beispiel:  
  
```  
Class1 obj  = new Class1();  
```  
  
 Er wird auch verwendet, um Instanzen von anonymen Typen zu erstellen:  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 Der `new`-Operator wird auch verwendet, um den Standardkonstruktor für Werttypen aufzurufen. Zum Beispiel:  
  
```  
int i = new int();  
```  
  
 In der vorherigen Anweisung wird `i` auf `0` initialisiert, dem Standardwert für den `int`-Typ. Die Anweisung hat den gleichen Effekt wie die Folgende:  
  
```  
int i = 0;  
```  
  
 Eine vollständige Liste der Standardwerte finden Sie in der [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Beachten Sie, dass das Deklarieren eines Standardkonstruktors für eine [Struktur](../../../csharp/language-reference/keywords/struct.md) ein Fehler ist, da jeder Werttyp implizit einen öffentlichen Standardkonstruktor besitzt. Es ist möglich, parametrisierte Konstruktoren auf einem Strukturtyp zu deklarieren, um seine Standardwerte festzulegen. Dies ist aber nur notwendig, wenn andere Werte als der Standardwert erforderlich sind.  
  
 Werttypobjekte wie Strukturen werden auf einem Stapel erstellt, während Verweistypobjekte auf einem Heap erstellt werden. Beide Objekttypen werden automatisch zerstört. Allerdings werden auf Werttypen basierende Objekte zerstört, wenn sie den gültigen Bereich verlassen. Auf Verweistypen basierende Objekte hingegen werden zu einem unbestimmten Zeitpunkt zerstört, nachdem der letzte Verweis auf sie entfernt wurde. Für Verweistypen, die feste Ressourcen wie große Mengen an Speicher, Dateihandles oder Netzwerkverbindungen verbrauchen, ist es manchmal wünschenswert, einen deterministischen Abschluss zu nutzen, um sicherzustellen, dass das Objekt sobald wie möglich zerstört wird. Weitere Informationen finden Sie unter [using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md).  
  
 Der Operator `new` kann nicht überladen werden.  
  
 Wenn der `new`-Operator bei der Zuweisung von Arbeitsspeicher scheitert, löst er die Ausnahme <xref:System.OutOfMemoryException> aus.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden ein `struct`-Objekt und ein Klassenobjekt mithilfe des `new`-Operators erstellt und initialisiert. Anschließend werden ihnen Werte zugewiesen. Die Standardwerte und die zugewiesenen Werte werden angezeigt.  
  
 [!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
 Beachten Sie im Beispiel, dass der Standardwert einer Zeichenfolge `null` ist. Daher wird er nicht angezeigt.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
