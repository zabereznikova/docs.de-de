---
title: Finalizer – C#-Programmierhandbuch
ms.date: 10/08/2018
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
ms.openlocfilehash: c8ad738baa3ff76cf9ae8367f2fd2a1fb44a79d6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170298"
---
# <a name="finalizers-c-programming-guide"></a>Finalizer (C#-Programmierhandbuch)
Mit Finalizern (die auch als **Destruktoren** bezeichnet werden) werden alle erforderlichen endgültigen Bereinigungen durchgeführt, wenn eine Klasseninstanz vom Garbage Collector gesammelt wird.  
  
## <a name="remarks"></a>Hinweise  
  
- Finalizer können nicht in Strukturen definiert werden. Sie werden nur mit Klassen verwendet.  
  
- Eine Klasse kann nur über einen Finalizer verfügen.  
  
- Finalizer können nicht vererbt oder überladen werden.  
  
- Finalizer können nicht aufgerufen werden. Sie werden automatisch aufgerufen.  
  
- Ein Finalizer kann nicht über Modifizierer oder Parameter verfügen.  
  
 Folgendes ist z.B. eine Deklaration eines Finalizers für die Klasse `Car`:
  
 [!code-csharp[csProgGuideObjects#86](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#86)]  

Ein Finalizer kann auch als Ausdruckstextdefinition implementiert werden, wie im folgenden Beispiel gezeigt.

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  
  
 Der Finalizer ruft <xref:System.Object.Finalize%2A> implizit auf der Basisklasse des Objekts auf. Daher wird der Aufruf eines Finalizers implizit in den folgenden Code übersetzt:  
  
```csharp  
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
> Leere Finalizer sollten nicht verwendet werden. Wenn eine Klasse einen Finalizer enthält, wird ein Eintrag in der `Finalize`-Warteschlange erstellt. Wenn der Finalizer aufgerufen wird, wird der Garbage Collector aufgerufen, um die Warteschlange zu verarbeiten. Ein leerer Finalizer führt nur zu einem unnötigen Leistungsverlust.  
  
 Der Programmierer hat keine Kontrolle darüber, wann der Finalizer aufgerufen wird, da dies durch den Garbage Collector bestimmt wird. Der Garbage Collector sucht nach Objekten, die von der Anwendung nicht mehr verwendet werden. Wenn er ein Objekt als abschließbar angesehen wird, ruft er den Finalizer auf (sofern vorhanden) und fordert den Arbeitsspeicher, der zum Speichern des Objekts verwendet wurde, zurück.

 In .NET Framework-Anwendungen (aber nicht in .NET Core-Anwendungen) werden auch Finalizer aufgerufen, wenn das Programm beendet wird.
  
 Es ist möglich, die Garbage Collection durch Aufrufen von <xref:System.GC.Collect%2A> zu erzwingen, aber dies sollte meistens vermieden werden, da es Leistungsprobleme hervorrufen kann.  
  
## <a name="using-finalizers-to-release-resources"></a>Verwenden von Finalizern zum Freigeben von Ressourcen  
 Im Allgemeinen erfordert C# nicht so viel Speicherverwaltung wie benötigt wird, wenn Sie mit einer anderen Sprache entwickeln, die nicht auf eine Laufzeit mit der Garbage Collection abzielt. Der Garbage Collector von .NET Framework verwaltet implizit die Belegung und Freigabe von Arbeitsspeicher für Ihre Objekte. Wenn Ihre Anwendung nicht verwaltete Ressourcen wie z.B. Fenster, Dateien und Netzwerkverbindungen kapselt, sollten Sie Finalizer verwenden, um die Ressourcen freizugeben. Wenn das Objekt abgeschlossen werden kann, führt der Garbage Collector die `Finalize`-Methode des Objekts aus.  
  
## <a name="explicit-release-of-resources"></a>Explizite Freigabe von Ressourcen  
 Wenn Ihre Anwendung eine umfangreiche externe Ressource verwendet, wird außerdem empfohlen, dass Sie eine Möglichkeit bieten, die Ressource explizit freizugeben, bevor der Garbage Collector das Objekt freigibt. Implementieren Sie dazu eine `Dispose`-Methode aus der Schnittstelle <xref:System.IDisposable>, die die erforderliche Bereinigung für das Objekt durchführt. Dies kann die Leistung der Anwendung erheblich verbessern. Trotz dieser expliziten Kontrolle über Ressourcen, wird der Finalizer Ressourcen sicher bereinigen, wenn der Aufruf der `Dispose`-Methode fehlschlägt.  
  
 Weitere Informationen zum Bereinigen von Ressourcen finden Sie unter den folgenden Themen:  
  
- [Bereinigen von nicht verwalteten Ressourcen](../../../standard/garbage-collection/unmanaged.md)  
  
- [Implementieren einer Dispose-Methode](../../../standard/garbage-collection/implementing-dispose.md)  
  
- [Using-Anweisung](../../language-reference/keywords/using-statement.md)  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt drei Klassen, die eine Vererbungskette bilden. Die Klasse `First` ist die Basisklasse, `Second` wird von `First` abgeleitet, und `Third` wird von `Second` abgeleitet. Alle drei verfügen über Finalizer. In `Main` wird eine Instanz der am meisten abgeleiteten Klasse erstellt. Wenn das Programm ausgeführt wird, beachten Sie, dass die Finalizer der drei Klassen automatisch und in Reihenfolge von der am meisten bis zu der am wenigsten abgeleiteten aufgerufen werden.  
  
 [!code-csharp[csProgGuideObjects#85](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#85)]  
  
## <a name="c-language-specification"></a>C#-Sprachspezifikation  

Weitere Informationen finden Sie im Abschnitt [Destruktoren](~/_csharplang/spec/classes.md#destructors) der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IDisposable>
- [C#-Programmierhandbuch](../index.md)
- [Konstruktoren](./constructors.md)
- [Garbage Collection](../../../standard/garbage-collection/index.md)
