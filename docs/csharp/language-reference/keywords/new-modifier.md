---
title: new-Modifizierer (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
caps.latest.revision: 28
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
ms.openlocfilehash: 3c636d50e6c871c529104d5f2985e861f9a652b2
ms.lasthandoff: 03/13/2017

---
# <a name="new-modifier-c-reference"></a>new-Modifizierer (C#-Referenz)
Wenn das Schlüsselwort `new` als Deklarationsmodifizierer verwendet wird, blendet es explizit einen von einer Basisklasse geerbten Member aus. Wenn Sie einen geerbten Member ausblenden, ersetzt die abgeleitete Version des Members die Basisklassenversion. Obwohl Sie Member verdecken können, ohne den `new`-Modifizierer zu verwenden, wird eine Compilerwarnung angezeigt. Wenn Sie `new` verwenden, um einen Member explizit auszublenden, wird diese Warnung unterdrückt.  
  
 Um einen geerbten Member auszublenden, deklarieren Sie ihn mit demselben Membernamen in der abgeleiteten Klasse und ändern ihn mit dem `new`-Schlüsselwort. Beispiel:  
  
 [!code-cs[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]  
  
 In diesem Beispiel wird `BaseC.Invoke` durch `DerivedC.Invoke` ausgeblendet. Der Vorgang wirkt sich nicht auf das Feld `x` aus, da es nicht mit einem ähnlichen Namen ausgeblendet wird.  
  
 Das Ausblenden des Namens durch Vererbung nimmt eine der folgenden Formen an:  
  
-   Im Allgemeinen blendet eine Konstante, ein Feld, eine Eigenschaft oder einen Typ, der in einer Klasse oder Struktur eingegeben wird, alle Basisklassenmember aus, die den gleichen Namen haben.  Es werden bestimmte Fälle unterschieden.  Wenn Sie beispielsweise ein neues Feld mit dem Namen `N` mit einem nicht aufrufbaren Typ deklarieren, und ein Basistyp deklariert `N` als Methode, blendet das neue Feld die Basisdeklaration nicht in der Aufrufsyntax aus.  Weitere Informationen finden Sie unter [C#-Sprachspezifikation](http://go.microsoft.com/fwlink/?LinkId=199552) (siehe Abschnitt „Suche nach Membern“ im Abschnitt „Ausdrücke“).  
  
-   Durch eine Methode, die in eine Klasse oder Struktur eingeführt ist, werden Eigenschaften, Felder und Typen mit dem gleichen Namen in der Basisklasse ausgeblendet. Alle Basisklassenmethoden mit der gleichen Signatur werden ebenfalls ausgeblendet.  
  
-   Durch einen Indexer, der in einer Klasse oder Struktur eingeführt ist, werden alle Basisklassenindexer mit der gleichen Signatur ausgeblendet.  
  
 `new` und [override](../../../csharp/language-reference/keywords/override.md) dürfen nicht gleichzeitig auf denselben Member angewendet werden, da sich die Bedeutungen der beiden Modifizierer gegenseitig ausschließen. Mit dem `new`-Modifizierer wird ein neuer Member mit demselben Namen erstellt, und der ursprüngliche Member wird ausgeblendet. Der `override`-Modifizierer verlängert die Implementierung für einen geerbten Member.  
  
 Wenn der `new`-Modifizierer in einer Deklaration verwendet wird, in der kein geerbter Member ausgeblendet wird, wird eine Warnung generiert.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird von einer Basisklasse, `BaseC`, und einer abgeleiteten Klasse, `DerivedC`, der gleiche Feldname `x` verwendet. Auf diese Weise wird der Wert des geerbten Felds ausgeblendet. Im Beispiel wird die Verwendung des `new`-Modifizierers veranschaulicht. Außerdem wird gezeigt, wie mit den voll qualifizierten Namen auf die ausgeblendeten Member der Basisklasse zugegriffen wird.  
  
 [!code-cs[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel blendet eine geschachtelte Klasse eine Klasse mit dem gleichen Namen in der Basisklasse aus. Das Beispiel veranschaulicht, wie mit dem `new`-Modifizierer die Warnmeldung vermieden wird und wie mit den voll qualifizierten Namen auf die ausgeblendeten Klassenmember zugegriffen wird.  
  
 [!code-cs[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]  
  
 Wenn der `new`-Modifizierer entfernt wird, kann das Programm dennoch kompiliert und ausgeführt werden. Es wird jedoch folgende Warnung angezeigt:  
  
```  
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.  
```  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)   
 [Wann müssen die Schlüsselwörter "override" und "new" verwendet werden?](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
