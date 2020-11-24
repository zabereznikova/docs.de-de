---
title: Erstellen von Konsolenanwendungen in .NET
ms.date: 03/30/2017
helpviewer_keywords:
- .NET, creating console applications
- application development [.NET], console
- console applications
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
ms.openlocfilehash: 8046b1b8cb50476860fee53654de93c924d23346
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823971"
---
# <a name="console-apps-in-net"></a>Konsolen-Apps in .NET

.NET-Anwendungen können die <xref:System.Console?displayProperty=nameWithType>-Klasse verwenden, um Zeichen aus der Konsole zu lesen und in ihr zu schreiben. Daten aus der Konsole werden aus dem Standardeingabestream gelesen, in die Konsole eingehende Daten werden in den Standardausgabestream geschrieben. In die Konsole eingehende Fehlerdaten werden in den Standard-Fehlerausgabestream geschrieben. Diese Streams werden automatisch mit der Konsole verknüpft, wenn die Anwendung gestartet wird, und werden entsprechend als Eigenschaften <xref:System.Console.In%2A>, <xref:System.Console.Out%2A> und <xref:System.Console.Error%2A> dargestellt.

Der Wert der <xref:System.Console.In%2A?displayProperty=nameWithType>-Eigenschaft ist ein <xref:System.IO.TextReader?displayProperty=nameWithType>-Objekt. Die Werte der Eigenschaften <xref:System.Console.Out%2A?displayProperty=nameWithType> und <xref:System.Console.Error%2A?displayProperty=nameWithType> hingegen sind <xref:System.IO.TextWriter?displayProperty=nameWithType>-Objekte. Sie können diese Eigenschaften mit Streams verknüpfen, die nicht für die Konsole stehen. So können Sie den Stream auf einen anderen Ort für eingehende oder ausgehende Daten lenken. Sie können die Ausgabe zum Beispiel zu einer Datei umlenken, indem Sie die <xref:System.Console.Out%2A?displayProperty=nameWithType>-Eigenschaft auf <xref:System.IO.StreamWriter?displayProperty=nameWithType> einstellen. Dadurch wird ein <xref:System.IO.FileStream?displayProperty=nameWithType> mit der <xref:System.Console.SetOut%2A?displayProperty=nameWithType>-Methode gekapselt. Die Eigenschaften <xref:System.Console.In%2A?displayProperty=nameWithType> und <xref:System.Console.Out%2A?displayProperty=nameWithType> müssen sich nicht auf denselben Stream beziehen.

> [!NOTE]
> Weitere Informationen zum Erstellen von Konsolenanwendungen, einschließlich Beispielen in C#, Visual Basic und C++, finden Sie in der Dokumentation zur <xref:System.Console>-Klasse.

Wenn keine Konsole vorhanden ist, beispielsweise bei einer Windows Forms-Anwendung, ist die Ausgabe, die in den Standardausgabestream geschrieben wird, nicht sichtbar. Dies liegt daran, dass keine Konsole vorhanden ist, in die die Information geschrieben werden kann. Werden Informationen in eine Konsole geschrieben, auf die nicht zugegriffen werden kann, wird keine Ausnahme ausgelöst. (Sie können den Anwendungstyp jederzeit in **Konsolenanwendung** ändern, z. B. auf den Projekteigenschaftenseiten in Visual Studio).

Die **System.Console**-Klasse verfügt über Methoden, die individuelle Zeichen oder ganze Zeilen aus der Konsole lesen können. Andere Methoden konvertieren Daten und formatieren Zeichenfolgen. Dann schreiben sie die formatierten Zeichenfolgen in die Konsole. Weitere Informationen zum Formatieren von Zeichenfolgen finden Sie unter [Formatieren von Typen in .NET](base-types/formatting-types.md).

> [!TIP]
> Konsolenanwendungen verfügen nicht über eine Meldungsverteilschleife, die standardmäßig gestartet wird. Daher können Konsolenaufrufe von Microsoft Win32-Timern möglicherweise fehlschlagen.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Console?displayProperty=nameWithType>
- [Formatierung von Typen](base-types/formatting-types.md)
