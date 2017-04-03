---
title: using-Anweisung (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
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
ms.openlocfilehash: 587e50d5c81c19d75e9d8bf4779064947a373b71
ms.lasthandoff: 03/13/2017

---
# <a name="using-statement-c-reference"></a>using-Anweisung (C#-Referenz)
Bietet eine praktische Syntax, die die korrekte Verwendung von <xref:System.IDisposable>-Objekten gewährleistet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der using-Anweisung gezeigt.  
  
 [!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a>Hinweise  
 <xref:System.IO.File> und <xref:System.Drawing.Font> sind Beispiele für verwaltete Typen, die auf nicht verwaltete Ressourcen zugreifen (in diesem Fall Dateihandles und Gerätekontexte). Es gibt viele andere Arten von nicht verwalteten Ressourcen und Klassenbibliothekstypen, die sie einschließen. Alle diese Typen müssen die Schnittstelle <xref:System.IDisposable> implementieren.  
  
 In der Regel sollten Sie bei der Verwendung eines `IDisposable`-Objekts das Objekt in einer `using`-Anweisung deklarieren und instanziieren. Die `using`-Anweisung ruft die Methode <xref:System.IDisposable.Dispose%2A> ordnungsgemäß für das Objekt auf. Wenn Sie sie, wie vorher gezeigt, verwenden, führt dies auch dazu, dass das Objekt den gültigen Bereich verlässt, sobald <xref:System.IDisposable.Dispose%2A> aufgerufen wird. Innerhalb des `using`-Blocks ist das Objekt schreibgeschützt und kann nicht geändert oder neu zugewiesen werden.  
  
 Die `using`-Anweisung stellt sicher, dass <xref:System.IDisposable.Dispose%2A> aufgerufen wird, auch wenn eine Ausnahme ausgelöst wird, während Sie die Methode für das Objekt aufrufen. Sie können das gleiche Ergebnis erzielen, indem Sie das Objekt in einen Try-Block einfügen und dann <xref:System.IDisposable.Dispose%2A> in einem Finally-Block aufrufen; so wird die `using`-Anweisung vom Compiler übersetzt. Das vorherige Codebeispiel wird zur Kompilierzeit auf den folgenden Code erweitert (beachten Sie die zusätzlichen geschweiften Klammern zum Erstellen des eingeschränkten Gültigkeitsbereichs für das Objekt):  
  
 [!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 Wie im folgenden Beispiel gezeigt, können mehrere Instanzen eines Typs in einer `using`-Anweisung deklariert werden.  
  
 [!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 Sie können das Ressourcenobjekt instanziieren und die Variable an die `using`-Anweisung übergeben; dies wird jedoch nicht empfohlen. In diesem Fall verbleibt das Objekt im Gültigkeitsbereich, nachdem das `using`-Steuerelement den Block verlassen hat, obwohl es wahrscheinlich keinen Zugriff auf dessen nicht verwaltete Ressourcen mehr hat. Das heißt, es wird nicht mehr vollständig initialisiert. Wenn Sie versuchen, das Objekt außerhalb des `using`-Blocks zu verwenden, riskieren Sie, dass eine Ausnahme ausgelöst wird. Aus diesem Grund ist es im Allgemeinen besser, das Objekt in der `using`-Anweisung zu instanziieren und dessen Bereich auf den `using`-Block zu begrenzen.  
  
 [!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [using-Direktive](../../../csharp/language-reference/keywords/using-directive.md)   
 [Garbage Collection](../../../standard/garbagecollection/index.md)   
 [Implementieren einer Dispose-Methode](http://msdn.microsoft.com/library/eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9)
