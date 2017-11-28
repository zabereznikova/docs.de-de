---
title: 'Gewusst wie: Schreiben in eine Textdatei (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c576536947cdb4984d6e5ce67c8377fe23b354c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Gewusst wie: Schreiben in eine Textdatei (C#-Programmierhandbuch)
In diesen Beispielen werden verschiedene Möglichkeiten veranschaulicht, Text in eine Datei zu schreiben.  In den ersten beiden Beispielen werden statische Hilfsmethoden für die <xref:System.IO.File?displayProperty=nameWithType>-Klasse verwendet, um jedes Element von „IEnumerable\<string>“ und um eine Zeichenfolge in eine Textdatei zu schreiben.  In Beispiel 3 wird dargestellt, wie Text einer Datei hinzugefügt wird, wenn jede Zeile beim Schreiben in die Datei einzeln verarbeitet werden muss.  Die Beispiele 1–3 überschreiben alle vorhandenen Inhalte in der Datei. In Beispiel 4 wird jedoch gezeigt, wie einer vorhandenen Datei Text angefügt wird.  
  
 In allen diesen Beispielen werden Zeichenfolgenliterale in Dateien geschrieben. Sie sollten jedoch eher die <xref:System.String.Format%2A>-Methode verwenden, die viele Steuerelemente enthält, mit denen verschiedene Wertetypen rechts- oder linksbündig mit oder ohne Abstand in ein Feld geschrieben werden können.  Sie können auch die Funktion für die C#-[Zeichenfolgeninterpolierung](../../../csharp/language-reference/keywords/interpolated-strings.md) verwenden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
 In allen diesen Beispielen werden Zeichenfolgenliterale in Dateien geschrieben. Sie sollten jedoch eher die <xref:System.String.Format%2A>-Methode verwenden, die viele Steuerelemente enthält, mit denen verschiedene Wertetypen rechts- oder linksbündig mit oder ohne Abstand in ein Feld geschrieben werden können.  Sie können auch die Funktion für die C#-[Zeichenfolgeninterpolierung](../../../csharp/language-reference/keywords/interpolated-strings.md) verwenden.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Die Datei ist bereits vorhanden und ist schreibgeschützt.  
  
-   Der Pfadname ist möglicherweise zu lang.  
  
-   Der Datenträger ist möglicherweise voll.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](../../../csharp/programming-guide/file-system/index.md)  
 [Beispiel: Speichern einer Auflistung im Anwendungsspeicher](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
