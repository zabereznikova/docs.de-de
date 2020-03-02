---
title: Schreiben eines einfachen parallelen Programms mit Parallel.ForEach
ms.date: 02/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
ms.openlocfilehash: 02b94b673dc4468e68a1dadd83aab0e3bfcfaa16
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160299"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Vorgehensweise: Schreiben einer einfachen Parallel.ForEach-Schleife

Dieses Beispiel zeigt die Verwendung einer <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Schleife, um alle <xref:System.Collections.IEnumerable?displayProperty=nameWithType>- oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>-Datenquellen übergreifende Datenparallelität zu ermöglichen.

> [!NOTE]
> In dieser Dokumentation werden Delegaten in PLINQ mithilfe von Lambdaausdrücken definiert. Falls Sie mit Lambdaausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambdaausdrücke in PLINQ und TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Beispiel

In diesem Beispiel wird davon ausgegangen, dass mehrere JPG-Dateien im Ordner *C:\Users\Public\Pictures\Sample Pictures* (C:\Benutzer\Öffentlich\Bilder\Beispielbilder) vorhanden sind, und es wird ein neuer Unterordner namens *Modified* (Geändert) erstellt. Wenn Sie das Beispiel ausführen, wird jedes JPG-Bild in *Sample Pictures* (Beispielbilder) gedreht und unter *Modified* (Geändert) gespeichert. Sie können die beiden Pfade nach Bedarf anpassen.

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

Eine <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Schleife funktioniert wie eine <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Schleife. Die Schleife partitioniert die Quellsammlung und plant die Arbeit basierend auf der Systemumgebung in mehrere Threads ein. Je mehr Prozessoren das System aufweist, desto schneller wird die parallele Methode ausgeführt. Bei manchen Quellsammlungen ist eine sequenzielle Schleife je nach Größe der Quelle und Art der Arbeit, die die Schleife ausführt, möglicherweise schneller. Weitere Informationen zur Leistung finden Sie unter [Potenzielle Fehler bei Daten- und Aufgabenparallelität](potential-pitfalls-in-data-and-task-parallelism.md).

Weitere Informationen zu parallelen Schleifen finden Sie unter [Vorgehensweise: Schreiben einer einfachen Parallel.For-Schleife](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).

Um <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> mit einer nicht generischen Sammlung zu verwenden, können Sie die Sammlung mithilfe der <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType>-Erweiterungsmethode in eine generische Sammlung umwandeln, wie im folgenden Beispiel gezeigt:

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

Sie können auch Parallel LINQ (PLINQ) verwenden, um die Verarbeitung von <xref:System.Collections.Generic.IEnumerable%601>-Datenquellen zu parallelisieren. Mit PLINQ können Sie deklarative Abfragesyntax verwenden, um das Schleifenverhalten auszudrücken. Weitere Informationen finden Sie unter [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).

## <a name="compile-and-run-the-code"></a>Kompilieren und Ausführen des Codes

Sie können den Code als Konsolenanwendung für das .NET Framework oder als Konsolenanwendung für .NET Core kompilieren.

In Visual Studio gibt es Visual Basic- und C#-Konsolenanwendungsvorlagen für Windows Desktop und .NET Core.

Sie können über die Befehlszeile entweder die Befehle der .NET Core-CLI (z. B. `dotnet new console` oder `dotnet new console -lang vb`) verwenden oder die Datei erstellen und den Befehlszeilencompiler für eine .NET Framework-Anwendung nutzen.

Bei einem .NET Core-Projekt müssen Sie auf das NuGet-Paket **System.Drawing.Common** verweisen. Verwenden Sie in Visual Studio den NuGet-Paket-Manager zum Installieren des Pakets. Alternativ können Sie in Ihrer \*.CSPROJ oder \*.VBPROJ-Datei auf das Paket verweisen:

```xml
<ItemGroup>
     <PackageReference Include="System.Drawing.Common" Version="4.5.1" />
</ItemGroup>
```

Verwenden Sie zum Ausführen einer .NET Core-Konsolenanwendung über die Befehlszeile `dotnet run` aus dem Ordner, der Ihre Anwendung enthält.

Drücken Sie zum Ausführen Ihrer Konsolenanwendung aus Visual Studio **F5**.

## <a name="see-also"></a>Siehe auch

- [Datenparallelität](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
