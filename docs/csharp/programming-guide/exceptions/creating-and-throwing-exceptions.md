---
title: "Erstellen und Auslösen von Ausnahmen (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
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
ms.translationtype: HT
ms.sourcegitcommit: 81117b1419c2a9c3babd6a7429052e2b23e08a70
ms.openlocfilehash: ea3104b1850fd2014ef0d4b8fcd31098d2c4b9d4
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a>Erstellen und Auslösen von Ausnahmen (C#-Programmierhandbuch)
Ausnahmen werden verwendet, um anzugeben, dass während der Ausführung des Programms ein Fehler aufgetreten ist. Ausnahmeobjekte, die einen Fehler beschreiben, werden erstellt und dann mit dem Schlüsselwort [throw](../../../csharp/language-reference/keywords/throw.md) (auslösen) *ausgelöst*. Die Laufzeit sucht dann nach dem kompatibelsten Ausnahmehandler.  
  
 Programmierer sollten Ausnahmen auslösen, wenn eine oder mehrere der folgenden Bedingungen wahr sind:  
  
-   Die Methode kann deren definierte Funktionalität nicht abschließen.  
  
     Wenn beispielsweise ein Parameter einer Methode einen ungültigen Wert hat:  
  
     [!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]  
  
-   Ein unpassender Aufruf eines Objekts erfolgt, basierend auf dem Objektzustand.  
  
     Ein Beispiel wäre ein Versuch, in eine schreibgeschützte Datei zu schreiben. Lösen Sie in Fällen, in denen ein Objektzustand keinen Vorgang erlaubt, eine Instanz von <xref:System.InvalidOperationException> oder ein Objekt aus, das auf einer Ableitung dieser Klasse basiert. Dies ist ein Beispiel für eine Methode, die eine <xref:System.InvalidOperationException> auslöst:  
  
     [!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]  
  
-   Wenn ein Argument an eine Methode eine Ausnahme auslöst.  
  
     In diesem Fall muss die ursprüngliche Ausnahme abgefangen und eine <xref:System.ArgumentException>-Instanz erstellt werden. Die ursprüngliche Ausnahme sollte an den Konstruktor der <xref:System.ArgumentException> als <xref:System.Exception.InnerException%2A>-Parameter übergeben werden:  
  
     [!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]  
  
 Ausnahmen enthalten eine Eigenschaft mit dem Namen <xref:System.Exception.StackTrace%2A>. Diese Zeichenfolge enthält den Namen der Methoden für die aktuelle Aufrufliste, zusammen mit dem Dateinamen und der Zeilennummer, in der die Ausnahme für jede Methode ausgelöst wurde. Ein <xref:System.Exception.StackTrace%2A>-Objekt wird automatisch von der Common Language Runtime (CLR) ab der `throw`-Anweisung erstellt, sodass Ausnahmen ab dem Punkt ausgelöst werden müssen, an dem die Stapelüberwachung beginnen soll.  
  
 Alle Ausnahmen enthalten eine Eigenschaft mit dem Namen <xref:System.Exception.Message%2A>. Diese Zeichenfolge sollte festgelegt werden, um die Gründe für die Ausnahme zu erklären. Beachten Sie, dass vertrauliche Informationen aus Sicherheitsgründen nicht im E-Mail-Text eingefügt werden dürfen. Zusätzlich zu <xref:System.Exception.Message%2A> enthält <xref:System.ArgumentException> eine Eigenschaft mit dem Namen <xref:System.ArgumentException.ParamName%2A>, die auf den Namen des Arguments festgelegt werden sollte, das die Ausnahme ausgelöst hat. Im Falle eines Eigenschaftensetters sollte <xref:System.ArgumentException.ParamName%2A> auf `value` festgelegt werden.  
  
 Öffentliche und geschützte Methodenmember sollten Ausnahmen auslösen, wann immer sie ihre beabsichtigten Funktionen nicht auslösen können. Die Ausnahmeklasse, die ausgelöst wird, muss die möglichst genaueste verfügbare Ausnahme sein, die zu den Fehlerbedingungen passt. Diese Ausnahmen sollten als Teil der Klassenfunktionalität dokumentiert werden, und abgeleitete Klassen oder Updates an der ursprünglichen Klasse müssen das gleiche Verhalten für die Abwärtskompatibilität beibehalten.  
  
## <a name="things-to-avoid-when-throwing-exceptions"></a>Was Sie beim Auslösen von Ausnahmen vermeiden sollten  
 Die folgende Liste enthält Vorgehensweisen, die beim Auslösen von Ausnahmen zu vermeiden sind:  
  
-   Ausnahmen dürfen nicht zum Ändern des Flusses eines Programms als Teil der normalen Ausführung verwendet werden. Ausnahmen dürfen nur zum Melden und Behandeln von Fehlerzuständen verwendet werden.  
  
-   Ausnahmen dürfen nicht als Rückgabewert oder Parameter zurückgegeben werden, anstatt ausgelöst zu werden.  
  
-   Lösen Sie <xref:System.Exception?displayProperty=nameWithType>, <xref:System.SystemException?displayProperty=nameWithType>, <xref:System.NullReferenceException?displayProperty=nameWithType> oder <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> nicht mit Absicht über Ihren eigenen Quellcode aus.  
  
-   Erstellen Sie keine Ausnahmen, die im Debugmodus, aber nicht im Releasemodus ausgelöst werden können. Um Laufzeitfehler während der Entwicklungsphase zu identifizieren, verwenden Sie stattdessen die Debugassertion.  
  
## <a name="defining-exception-classes"></a>Definieren von Ausnahmeklassen  
 Programme können eine zuvor definierte Ausnahmeklasse im <xref:System>-Namespace auslösen (mit Ausnahme der eben beschriebenen Fälle) oder ihre eigenen Ausnahmeklassen durch Ableitung von <xref:System.Exception> erstellen. Die abgeleiteten Klassen müssen zumindest vier Konstruktoren definieren: einen Standardkonstruktor, einen, der die message-Eigenschaft festlegt, und einen, der jeweils die Eigenschaften <xref:System.Exception.Message%2A> und <xref:System.Exception.InnerException%2A> festlegt. Der vierte Konstruktor wird verwendet, um die Ausnahme zu serialisieren. Neue Ausnahmeklassen sollten serialisierbar sein. Zum Beispiel:  
  
 [!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]  
  
 Neue Eigenschaften sollten nur zur Ausnahmeklasse hinzugefügt werden, wenn die Daten, die sie bereitstellen, zur Auflösung der Ausnahme nützlich sind. Wenn der abgeleiteten Ausnahmeklasse neue Eigenschaften hinzugefügt werden, muss `ToString()` überschrieben werden, um die hinzugefügten Informationen zurückzugeben.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/index.md)   
 [Ausnahmenhierarchie](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b)   
 [Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exception-handling.md)

