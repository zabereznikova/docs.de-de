---
title: 'Vorgehensweise: Lesen aus einer Textdatei – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: f7ddfbec13fad073272c75c3e68a4f5c9c3eef9e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672239"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a>Vorgehensweise: Lesen aus einer Textdatei (C#-Programmierhandbuch)
In diesem Beispiel wird der Inhalt von Textdateien gelesen, indem die statische Methoden <xref:System.IO.File.ReadAllText%2A> und <xref:System.IO.File.ReadAllLines%2A> aus der <xref:System.IO.File?displayProperty=nameWithType>-Klasse verwendet werden.  
  
 Ein Beispiel, in dem <xref:System.IO.StreamReader> verwendet wird, finden Sie unter [Vorgehensweise: Zeilenweises Lesen einer Textdatei](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).  
  
> [!NOTE]
>  Die in diesem Beispiel verwendeten Dateien werden in diesem Thema beschrieben: [Vorgehensweise: Schreiben in eine Textdatei](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Code, und fügen Sie ihn in eine C#-Konsolenanwendung ein.  
  
 Wenn Sie nicht die Textdateien aus [Vorgehensweise: Schreiben in eine Textdatei](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) verwenden, ersetzen Sie das Argument für `ReadAllText` und `ReadAllLines` durch die entsprechenden Pfad- und Dateinamen auf Ihrem Computer.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Die Datei ist nicht oder nicht am angegebenen Speicherort vorhanden. Überprüfen Sie die Schreibweise des Dateinamens und -pfads.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Schließen Sie nicht vom Namen einer Datei auf deren Inhalt. Bei der Datei `myFile.cs` handelt es sich zum Beispiel nicht unbedingt um eine C#-Quelldatei.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO?displayProperty=nameWithType>
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](../../../csharp/programming-guide/file-system/index.md)
