---
title: Erstellen und Auslösen von Ausnahmen – C#-Programmierhandbuch
description: Erfahren Sie mehr über das Erstellen und Auslösen von Ausnahmen. Ausnahmen werden verwendet, um anzugeben, dass während der Ausführung eines Programms ein Fehler aufgetreten ist.
ms.date: 12/09/2020
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
ms.openlocfilehash: a6998c5b274736b290460808ad4c7cb22be7ebf6
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110207"
---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a>Erstellen und Auslösen von Ausnahmen (C#-Programmierhandbuch)

Ausnahmen werden verwendet, um anzugeben, dass während der Ausführung des Programms ein Fehler aufgetreten ist. Ausnahmeobjekte, die einen Fehler beschreiben, werden erstellt und dann mit dem Schlüsselwort [throw](../../language-reference/keywords/throw.md) (auslösen) *ausgelöst*. Die Laufzeit sucht dann nach dem kompatibelsten Ausnahmehandler.

Programmierer sollten Ausnahmen auslösen, wenn eine oder mehrere der folgenden Bedingungen wahr sind:

- Die Methode kann ihre definierte Funktionalität nicht abschließen. Wenn beispielsweise ein Parameter einer Methode einen ungültigen Wert hat:
  :::code language="csharp" source="snippets/exceptions/Program.cs" ID="CantComplete":::
- Ein unpassender Aufruf eines Objekts erfolgt, basierend auf dem Objektzustand. Ein Beispiel wäre ein Versuch, in eine schreibgeschützte Datei zu schreiben. Lösen Sie in Fällen, in denen ein Objektzustand keinen Vorgang erlaubt, eine Instanz von <xref:System.InvalidOperationException> oder ein Objekt aus, das auf einer Ableitung dieser Klasse basiert. Der folgende Code ist ein Beispiel für eine Methode, die ein <xref:System.InvalidOperationException>-Objekt auslöst:
  :::code language="csharp" source="snippets/exceptions/ProgramLog.cs" ID="ProgramLog":::
- Wenn ein Argument an eine Methode eine Ausnahme auslöst. In diesem Fall muss die ursprüngliche Ausnahme abgefangen und eine <xref:System.ArgumentException>-Instanz erstellt werden. Die ursprüngliche Ausnahme sollte an den Konstruktor der <xref:System.ArgumentException> als <xref:System.Exception.InnerException%2A>-Parameter übergeben werden:
  :::code language="csharp" source="snippets/exceptions/Program.cs" ID="InvalidArg":::

Ausnahmen enthalten eine Eigenschaft mit dem Namen <xref:System.Exception.StackTrace%2A>. Diese Zeichenfolge enthält den Namen der Methoden für die aktuelle Aufrufliste, zusammen mit dem Dateinamen und der Zeilennummer, in der die Ausnahme für jede Methode ausgelöst wurde. Ein <xref:System.Exception.StackTrace%2A>-Objekt wird automatisch von der Common Language Runtime (CLR) ab der `throw`-Anweisung erstellt, sodass Ausnahmen ab dem Punkt ausgelöst werden müssen, an dem die Stapelüberwachung beginnen soll.

Alle Ausnahmen enthalten eine Eigenschaft mit dem Namen <xref:System.Exception.Message%2A>. Diese Zeichenfolge sollte festgelegt werden, um die Gründe für die Ausnahme zu erklären. Vertrauliche Informationen dürfen aus Sicherheitsgründen nicht in den Nachrichtentext eingefügt werden. Zusätzlich zu <xref:System.Exception.Message%2A> enthält <xref:System.ArgumentException> eine Eigenschaft mit dem Namen <xref:System.ArgumentException.ParamName%2A>, die auf den Namen des Arguments festgelegt werden sollte, das die Ausnahme ausgelöst hat. Bei einem Eigenschaftensetter sollte <xref:System.ArgumentException.ParamName%2A> auf `value` festgelegt werden.

Öffentliche und geschützte Methoden lösen Ausnahmen aus, wenn sie ihre Funktionen nicht durchführen können. Die ausgelöste Ausnahmeklasse ist die verfügbare Ausnahme, die am besten zu den vorliegenden Fehlerbedingungen passt. Diese Ausnahmen sollten als Teil der Klassenfunktionalität dokumentiert werden, und abgeleitete Klassen oder Updates an der ursprünglichen Klasse müssen das gleiche Verhalten für die Abwärtskompatibilität beibehalten.

## <a name="things-to-avoid-when-throwing-exceptions"></a>Was Sie beim Auslösen von Ausnahmen vermeiden sollten

Die folgende Liste enthält Vorgehensweisen, die beim Auslösen von Ausnahmen zu vermeiden sind:

- Verwenden Sie Ausnahmen nicht, um den Ablauf eines Programms als Teil der normalen Ausführung zu ändern. Verwenden Sie Ausnahmen, um Fehlerbedingungen zu melden und zu behandeln.
- Ausnahmen sollten nicht als Rückgabewert oder Parameter zurückgegeben werden, sie sollten ausgelöst werden.
- Lösen Sie <xref:System.Exception?displayProperty=nameWithType>, <xref:System.SystemException?displayProperty=nameWithType>, <xref:System.NullReferenceException?displayProperty=nameWithType> oder <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> nicht absichtlich über Ihren eigenen Quellcode aus.
- Erstellen Sie keine Ausnahmen, die im Debugmodus, aber nicht im Releasemodus ausgelöst werden können. Um Laufzeitfehler während der Entwicklungsphase zu identifizieren, verwenden Sie stattdessen die Debugassertion.

## <a name="defining-exception-classes"></a>Definieren von Ausnahmeklassen

Programme können eine zuvor definierte Ausnahmeklasse im <xref:System>-Namespace auslösen (mit Ausnahme der eben beschriebenen Fälle) oder ihre eigenen Ausnahmeklassen durch Ableitung von <xref:System.Exception> erstellen. Die abgeleiteten Klassen müssen zumindest vier Konstruktoren definieren: einen parameterlosen Konstruktor, einen, der die message-Eigenschaft festlegt, und einen, der sowohl die <xref:System.Exception.Message%2A>- als auch <xref:System.Exception.InnerException%2A>-Eigenschaft festlegt. Der vierte Konstruktor wird verwendet, um die Ausnahme zu serialisieren. Neue Ausnahmeklassen sollten serialisierbar sein. Zum Beispiel:

:::code language="csharp" source="snippets/exceptions/InvalidDepartmentException.cs" id="DefineExceptionClass":::

Fügen Sie neue Eigenschaften zur Ausnahmeklasse hinzu, wenn diese Daten bereitstellen, die zum Auflösen der Ausnahme nützlich sind. Wenn der abgeleiteten Ausnahmeklasse neue Eigenschaften hinzugefügt werden, muss `ToString()` überschrieben werden, um die hinzugefügten Informationen zurückzugeben.

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

Weitere Informationen finden Sie unter [Ausnahmen](~/_csharplang/spec/exceptions.md) und [Die throw-Anweisung](~/_csharplang/spec/statements.md#the-throw-statement) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Siehe auch

- [Ausnahmenhierarchie](../../../standard/exceptions/index.md)
