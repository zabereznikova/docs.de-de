---
title: 'Vorgehensweise: Lesen aus Textdateien mit mehreren Formaten in Visual Basic | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- TextFieldParser object, reading from a file
- TextFieldType enumeration
- My.Computer.FileSystem.WriteAllText method, parsing structured text files
- WriteAllText method, parsing structured text files
- PeekChars method, determining format of text
- reading text files, multiple formats
- I/O [Visual Basic], reading text files
- text files, reading
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6df284f7204b0731063db10cf026aed863f99fa9
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-read-from-text-files-with-multiple-formats-in-visual-basic"></a>Gewusst wie: Lesen aus Textdateien mit mehreren Formaten in Visual Basic
Das <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>-Objekt bietet die Möglichkeit, strukturierte Textdateien (z.B. Protokolle) einfach und effizient zu analysieren. Sie können eine Datei mit mehreren Formaten verarbeiten, indem Sie die `PeekChars`-Methode verwenden, um das Format jeder Zeile zu bestimmen, während Sie eine Datei analysieren.  
  
### <a name="to-parse-a-text-file-with-multiple-formats"></a>Analysieren einen Textdatei mit mehreren Formaten  
  
1.  Fügen Sie eine Textdatei mit dem Namen „textfile.txt“ in Ihrem Projekt hinzu. Fügen Sie folgenden Inhalt in der Textdatei ein.  
  
    ```  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2.  Definieren Sie das erwartete Format und das Format, das verwendet werden soll, wenn ein Fehler gemeldet wird. Der letzte Eintrag in jedem Array ist -1. Deshalb wird davon ausgegangen, dass das letzte Feld von variabler Breite ist. Dies tritt auf, wenn der letzte Eintrag des Arrays weniger oder gleich 0 (null) ist.  
  
     [!code-vb[VbFileIORead#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_1.vb)]  
  
3.  Erstellen Sie ein neues <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>-Objekt, und definieren Sie die Breite und das Format.  
  
     [!code-vb[VbFileIORead#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_2.vb)]  
  
4.  Gehen Sie durch die Reihen, und prüfen Sie vor dem Lesen das Format.  
  
     [!code-vb[VbFileIORead#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_3.vb)]  
  
5.  Schreiben Sie Fehler in die Konsole.  
  
     [!code-vb[VbFileIORead#7](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_4.vb)]  
  
## <a name="example"></a>Beispiel  
 Unten stehend finden Sie das vollständige Beispiel, das aus der `testfile.txt`-Datei liest.  
  
 [!code-vb[VbFileIORead#8](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_5.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Eine Zeile kann nicht mit dem angegebenen Format analysiert werden (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). Die Ausnahmemeldung gibt die Zeile an, die die Ausnahme verursacht, während der in der Zeile enthaltene Text der <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>-Eigenschaft zugewiesen wird.  
  
-   Die angegebene Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).  
  
-   Eine teilweise vertrauenswürdige Situation, in der der Benutzer nicht über ausreichende Berechtigungen für den Dateizugriff verfügt. (<xref:System.Security.SecurityException>).  
  
-   Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).  
  
-   Der Benutzer verfügt nicht über ausreichende Berechtigungen für den Dateizugriff (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 [Gewusst wie: Lesen aus durch Kommas getrennten Textdateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [Gewusst wie: Lesen aus einer Textdatei mit fester Breite](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [Analysieren von Textdateien mit dem TextFieldParser-Objekt](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
