---
title: Erstellen von Konsolenanwendungen in .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework, building console applications
- application development [.NET Framework], console
- console applications
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
ms.openlocfilehash: 1ec65795a7f3d706b2878dd8a8397ae42b61ce7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132867"
---
# <a name="building-console-applications-in-the-net-framework"></a>Erstellen von Konsolenanwendungen in .NET Framework
Anwendungen in .NET Framework können die <xref:System.Console?displayProperty=nameWithType>-Klasse verwenden, um Zeichen aus der Konsole zu lesen und in ihr zu schreiben. Daten aus der Konsole werden aus dem Standardeingabestream gelesen, in die Konsole eingehende Daten werden in den Standardausgabestream geschrieben. In die Konsole eingehende Fehlerdaten werden in den Standard-Fehlerausgabestream geschrieben. Diese Streams werden automatisch mit der Konsole verknüpft, wenn die Anwendung gestartet wird, und werden entsprechend als Eigenschaften <xref:System.Console.In%2A>, <xref:System.Console.Out%2A> und <xref:System.Console.Error%2A> dargestellt.  
  
 Der Wert der <xref:System.Console.In%2A?displayProperty=nameWithType>-Eigenschaft ist ein <xref:System.IO.TextReader?displayProperty=nameWithType>-Objekt. Die Werte der Eigenschaften <xref:System.Console.Out%2A?displayProperty=nameWithType> und <xref:System.Console.Error%2A?displayProperty=nameWithType> hingegen sind <xref:System.IO.TextWriter?displayProperty=nameWithType>-Objekte. Sie können diese Eigenschaften mit Streams verknüpfen, die nicht für die Konsole stehen. So können Sie den Stream auf einen anderen Ort für eingehende oder ausgehende Daten lenken. Sie können die Ausgabe zum Beispiel zu einer Datei umlenken, indem Sie die <xref:System.Console.Out%2A?displayProperty=nameWithType>-Eigenschaft auf <xref:System.IO.StreamWriter?displayProperty=nameWithType> einstellen. Dadurch wird ein <xref:System.IO.FileStream?displayProperty=nameWithType> mit der <xref:System.Console.SetOut%2A?displayProperty=nameWithType>-Methode gekapselt. Die Eigenschaften <xref:System.Console.In%2A?displayProperty=nameWithType> und <xref:System.Console.Out%2A?displayProperty=nameWithType> müssen sich nicht auf denselben Stream beziehen.  
  
> [!NOTE]
> Weitere Informationen zum Erstellen von Konsolenanwendungen, einschließlich Beispielen in C#, Visual Basic und C++, finden Sie in der Dokumentation zur <xref:System.Console>-Klasse.  
  
 Wenn keine Konsole vorhanden ist, wie beispielsweise in einer Windows-basierten Anwendung, ist die Ausgabe, die in den Standardausgabestream geschrieben wird, nicht sichtbar. Dies liegt daran, dass keine Konsole vorhanden ist, in die die Information geschrieben werden kann. Werden Informationen in eine Konsole geschrieben, auf die nicht zugegriffen werden kann, wird keine Ausnahme ausgelöst.  
  
 Alternativ können Sie die Konsole für Lese- und Schreibzugriff in einer Windows-basierten Anwendung aktivieren, die mit Visual Studio entwickelt wurde. Öffnen Sie hierzu im Projekt das Dialogfenster **Eigenschaften**, klicken Sie auf die Registerkarte **Anwendung**, und stellen Sie den **Anwendungstyp** auf **Konsolenanwendung** ein.  
  
 Konsolenanwendungen verfügen nicht über eine Meldungsverteilschleife, die standardmäßig gestartet wird. Daher können Konsolenaufrufe von Microsoft Win32-Timern möglicherweise fehlschlagen.  
  
 Die **System.Console**-Klasse verfügt über Methoden, die individuelle Zeichen oder ganze Zeilen aus der Konsole lesen können. Andere Methoden konvertieren Daten und formatieren Zeichenfolgen. Dann schreiben sie die formatierten Zeichenfolgen in die Konsole. Weitere Informationen zum Formatieren von Zeichenfolgen finden Sie unter [Formatierungstypen](../../docs/standard/base-types/formatting-types.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Console?displayProperty=nameWithType>
- [Formatierung von Typen](../../docs/standard/base-types/formatting-types.md)
