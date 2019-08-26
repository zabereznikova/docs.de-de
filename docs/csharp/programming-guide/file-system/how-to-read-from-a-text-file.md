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
ms.openlocfilehash: 2b98f24da7f13ae752f248eb8f26c75c1d47a824
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923953"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a>Vorgehensweise: Lesen aus einer Textdatei (C#-Programmierhandbuch)
In diesem Beispiel wird der Inhalt von Textdateien gelesen, indem die statische Methoden <xref:System.IO.File.ReadAllText%2A> und <xref:System.IO.File.ReadAllLines%2A> aus der <xref:System.IO.File?displayProperty=nameWithType>-Klasse verwendet werden.  
  
 Ein Beispiel, in dem <xref:System.IO.StreamReader> verwendet wird, finden Sie unter [Vorgehensweise: Zeilenweises Lesen einer Textdatei](./how-to-read-a-text-file-one-line-at-a-time.md).  
  
> [!NOTE]
> Die in diesem Beispiel verwendeten Dateien werden in diesem Thema beschrieben: [Vorgehensweise: Schreiben in eine Textdatei](./how-to-write-to-a-text-file.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Code, und fügen Sie ihn in eine C#-Konsolenanwendung ein.  
  
 Wenn Sie nicht die Textdateien aus [Vorgehensweise: Schreiben in eine Textdatei](./how-to-write-to-a-text-file.md) verwenden, ersetzen Sie das Argument für `ReadAllText` und `ReadAllLines` durch die entsprechenden Pfad- und Dateinamen auf Ihrem Computer.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Die Datei ist nicht oder nicht am angegebenen Speicherort vorhanden. Überprüfen Sie die Schreibweise des Dateinamens und -pfads.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Schließen Sie nicht vom Namen einer Datei auf deren Inhalt. Bei der Datei `myFile.cs` handelt es sich zum Beispiel nicht unbedingt um eine C#-Quelldatei.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO?displayProperty=nameWithType>
- [C#-Programmierhandbuch](../index.md)
- [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](./index.md)
