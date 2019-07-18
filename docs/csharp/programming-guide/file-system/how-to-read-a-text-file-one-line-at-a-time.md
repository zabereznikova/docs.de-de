---
title: 'Vorgehensweise: Zeilenweises Lesen einer Textdatei (Visual C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: 4e6c4cfce1b5e97f70040b318eb68ee78ee4a953
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595390"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a>Vorgehensweise: Zeilenweises Lesen einer Textdatei (Visual C#)
Dieses Beispiel liest den Inhalt einer Textdatei Zeile pro Zeile in eine Zeichenfolge mithilfe der `ReadLine`-Methode der `StreamReader`-Klasse. Jede Textzeile wird in der Zeichenfolge `line` gespeichert und auf dem Bildschirm angezeigt.  
  
## <a name="example"></a>Beispiel  
  
```csharp
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine(line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Code, und fügen Sie ihn in die `Main`-Methode einer Konsolenanwendung ein.  
  
 Ersetzen Sie `"c:\test.txt"` durch den tatsächlichen Dateinamen.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Die Datei ist möglicherweise nicht vorhanden.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens. Bei der Datei `myFile.cs` handelt es sich möglicherweise nicht um eine C#-Quelldatei.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO?displayProperty=nameWithType>
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](../../../csharp/programming-guide/file-system/index.md)
