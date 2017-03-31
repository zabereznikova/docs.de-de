---
title: Destruktoren (C#-Programmierhandbuch) Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ~ [C#], in destructors
- C# language, destructors
- destructors [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
caps.latest.revision: 24
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
ms.openlocfilehash: 6940be34b6cc15f006901e6d14d2a38ebb5d012a
ms.lasthandoff: 03/13/2017

---
# <a name="destructors-c-programming-guide"></a>Destruktoren (C#-Programmierhandbuch)
Destruktoren werden zur Zerstörung von Klasseninstanzen verwendet.  
  
## <a name="remarks"></a>Hinweise  
  
-   Destruktoren können nicht in Strukturen definiert werden. Sie werden nur mit Klassen verwendet.  
  
-   Eine Klasse kann nur über einen Destruktor verfügen.  
  
-   Destruktoren können nicht vererbt oder überladen werden.  
  
-   Destruktoren können nicht aufgerufen werden. Sie werden automatisch aufgerufen.  
  
-   Ein Destruktor kann nicht über Modifizierer oder Parameter verfügen.  
  
 Folgendes ist z.B. eine Deklaration eines Destruktors für die Klasse `Car`:  
  
 [!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]  
  
 Der Destruktor ruft implizit <xref:System.Object.Finalize%2A> für die Basisklasse des Objekts auf. Daher wird der vorige Destruktorcode implizit in den folgenden Code übersetzt:  
  
```  
protected override void Finalize()  
{  
    try  
    {  
        // Cleanup statements...  
    }  
    finally  
    {  
        base.Finalize();  
    }  
}  
```  
  
 Dies bedeutet, dass die `Finalize`-Methode für alle Instanzen in der Vererbungskette rekursiv aufgerufen wird, von der am meisten bis zu der am wenigsten abgeleiteten.  
  
> [!NOTE]
>  Leere Destruktoren sollten nicht verwendet werden. Wenn eine Klasse einen Destruktor enthält, wird ein Eintrag in der `Finalize`-Warteschlange erstellt. Wenn der Destruktor aufgerufen wird, wird der Garbage Collector aufgerufen, um die Warteschlange zu verarbeiten. Wenn der Destruktor leer ist, bewirkt dies einen unnötigen Leistungsverlust.  
  
 Der Programmierer hat keine Kontrolle darüber, wann der Destruktor aufgerufen wird, da dies durch den Garbage Collector bestimmt wird. Der Garbage Collector sucht nach Objekten, die von der Anwendung nicht mehr verwendet werden. Wenn er ein Objekt als zerstörbar angesehen wird, ruft er den Destruktor auf (sofern vorhanden) und fordert den Arbeitsspeicher, der zum Speichern des Objekts verwendet wurde, zurück. Destruktoren werden auch aufgerufen, wenn das Programm beendet wird.  
  
 Es ist möglich, die Garbage Collection durch Aufrufen von <xref:System.GC.Collect%2A> zu erzwingen, aber dies sollte meistens vermieden werden, da es Leistungsprobleme hervorrufen kann.  
  
## <a name="using-destructors-to-release-resources"></a>Verwenden von Destruktoren zum Freigeben von Ressourcen  
 Im Allgemeinen erfordert C# nicht so viel Speicherverwaltung wie benötigt wird, wenn Sie mit einer anderen Sprache entwickeln, die nicht auf eine Laufzeit mit der Garbage Collection abzielt. Der Garbage Collector von .NET Framework verwaltet implizit die Belegung und Freigabe von Arbeitsspeicher für Ihre Objekte. Wenn Ihre Anwendung nicht verwaltete Ressourcen wie z.B. Fenster, Dateien und Netzwerkverbindungen kapselt, sollten Sie Destruktoren verwenden, um die Ressourcen freizugeben. Wenn das Objekt zerstört werden kann, führt der Garbage Collector die `Finalize`-Methode des Objekts aus.  
  
## <a name="explicit-release-of-resources"></a>Explizite Freigabe von Ressourcen  
 Wenn Ihre Anwendung eine umfangreiche externe Ressource verwendet, wird außerdem empfohlen, dass Sie eine Möglichkeit bieten, die Ressource explizit freizugeben, bevor der Garbage Collector das Objekt freigibt. Implementieren Sie dazu eine `Dispose`-Methode aus der Schnittstelle <xref:System.IDisposable>, die die erforderliche Bereinigung für das Objekt durchführt. Dies kann die Leistung der Anwendung erheblich verbessern. Trotz dieser expliziten Kontrolle über Ressourcen, wird der Destruktor Ressourcen sicher bereinigen, wenn der Aufruf der `Dispose`-Methode fehlschlägt.  
  
 Weitere Informationen zum Bereinigen von Ressourcen finden Sie unter den folgenden Themen:  
  
-   [Bereinigen von nicht verwalteten Ressourcen](http://msdn.microsoft.com/library/a17b0066-71c2-4ba4-9822-8e19332fc213)  
  
-   [Implementieren einer Dispose-Methode](http://msdn.microsoft.com/library/eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9)  
  
-   [Using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md)  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt drei Klassen, die eine Vererbungskette bilden. Die Klasse `First` ist die Basisklasse, `Second` wird von `First` abgeleitet, und `Third` wird von `Second` abgeleitet. Alle drei verfügen über Destruktoren. In `Main()` wird eine Instanz der am meisten abgeleiteten Klasse erstellt. Wenn das Programm ausgeführt wird, beachten Sie, dass die Destruktoren der drei Klassen automatisch und in Reihenfolge von der am meisten bis zu der am wenigsten abgeleiteten aufgerufen werden.  
  
 [!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IDisposable>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Garbage Collection](../../../standard/garbagecollection/index.md)
