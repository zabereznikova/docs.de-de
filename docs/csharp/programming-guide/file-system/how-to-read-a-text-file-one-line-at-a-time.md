---
title: "Gewusst wie: Zeilenweises Lesen einer Textdatei (Visual C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
caps.latest.revision: 11
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e9327181d82a97559c7be99bb76a2a93118d796b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a>Gewusst wie: Zeilenweises Lesen einer Textdatei (Visual C#)
Dieses Beispiel liest den Inhalt einer Textdatei Zeile pro Zeile in eine Zeichenfolge mithilfe der `ReadLine`-Methode der `StreamReader`-Klasse. Jede Textzeile wird in der Zeichenfolge `line` gespeichert und auf dem Bildschirm angezeigt.  
  
## <a name="example"></a>Beispiel  
  
```  
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine (line);  
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
  
-   Die Datei ist möglicherweise nicht vorhanden.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens. Bei der Datei `myFile.cs` handelt es sich möglicherweise nicht um eine C#-Quelldatei.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO?displayProperty=fullName>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](../../../csharp/programming-guide/file-system/index.md)

