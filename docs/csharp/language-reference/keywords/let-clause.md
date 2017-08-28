---
title: let-Klausel (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- let_CSharpKeyword
- let
dev_langs:
- CSharp
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
caps.latest.revision: 15
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
ms.openlocfilehash: 37ec0cb0c8c374a0b5250d82e880c96696b5584a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="let-clause-c-reference"></a>let-Klausel (C#-Referenz)
Bei einem Abfrageausdruck kann es manchmal nützlich sein, das Ergebnis eines Unterausdrucks zur Verwendung in nachfolgenden Klauseln zu speichern. Sie können hierzu das Schlüsselwort `let` verwenden, das eine neue Bereichsvariable erstellt und sie mit dem von Ihnen bereitgestellten Ergebnis des Ausdrucks initialisiert. Sobald die Bereichsvariable mit einem Wert initialisiert wurde, kann sie nicht mehr zum Speichern eines anderen Werts verwendet werden. Enthält die Bereichsvariable jedoch einen abfragbaren Typ, kann sie abgefragt werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird `let` auf zweierlei Weise verwendet:  
  
1.  Um einen aufzählbaren Typ zu erstellen, der selbst abgefragt werden kann.  
  
2.  Um es der Abfrage zu ermöglichen, `ToLower` nur ein Mal für die Bereichsvariable `word` aufzurufen. Ohne `let` müssten Sie `ToLower` in jedem Prädikat der `where`-Klausel aufrufen.  
  
 [!code-cs[cscsrefAbfrageSchlüsselwörter#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [Abfrageschlüsselwörter (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Erste Schritte mit LINQ in C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Gewusst wie: Behandeln von Ausnahmen in Abfrageausdrücken](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)

