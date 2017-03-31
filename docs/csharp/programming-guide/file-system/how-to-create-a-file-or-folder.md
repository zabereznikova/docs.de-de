---
title: 'Vorgehensweise: Erstellen einer Datei oder eines Ordners (C#-Programmierhandbuch) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bba53c8d175d95aa3b89ba458517d439a8d2bb11
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a>Gewusst wie: Erstellen einer Datei oder eines Ordners (C#-Programmierhandbuch)
Sie können einen Ordner auf dem Computer programmgesteuert erstellen, einen Unterordner erstellen, eine Datei im Unterordner erstellen und Daten in die Datei schreiben.  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]  
  
 Wenn der Ordner bereits existiert, macht <xref:System.IO.Directory.CreateDirectory%2A> nichts, und es wird keine Ausnahme ausgelöst. Allerdings ersetzt <xref:System.IO.File.Create%2A?displayProperty=fullName> eine vorhandene Datei durch eine neue. Im Beispiel wird eine `if`-`else`-Anweisung verwendet, um zu verhindern, dass eine vorhandene Datei ersetzt wird.  
  
 Wenn Sie die folgenden Änderungen im Beispiel vornehmen, können Sie, je nachdem, ob eine Datei mit einem bestimmten Namen bereits vorhanden ist, unterschiedliche Ergebnisse erzeugen. Wenn eine solche Datei nicht vorhanden ist, erstellt der Code sie. Wenn eine solche Datei vorhanden ist, fügt der Code Daten an diese Datei an.  
  
-   Geben Sie einen nicht zufälligen Dateinamen an.  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
  
    ```  
  
-   Ersetzen Sie im folgenden Code die `if`-`else`-Anweisung durch die `using`-Anweisung.  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
  
    ```  
  
 Führen Sie das Beispiel mehrmals aus, um zu überprüfen, dass der Datei jedes Mal Daten hinzugefügt werden.  
  
 Weitere `FileMode`-Werte, die Sie ausprobieren können, finden Sie unter <xref:System.IO.FileMode>.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Ordnername ist falsch formatiert. Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>-Klasse). Verwenden Sie die <xref:System.IO.Path>-Klasse, um gültige Pfadnamen zu erstellen.  
  
-   Der übergeordnete Ordner des zu erstellenden Ordners ist schreibgeschützt (<xref:System.IO.IOException>-Klasse).  
  
-   Der Name des Ordners lautet `null` (<xref:System.ArgumentNullException>-Klasse).  
  
-   Der Name des Ordners ist zu lang (<xref:System.IO.PathTooLongException>-Klasse).  
  
-   Der Name des Ordners ist nur ein Doppelpunkt, „:“ (<xref:System.IO.PathTooLongException>-Klasse).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Eine Instanz der <xref:System.Security.SecurityException>-Klasse kann in teilweise vertrauenswürdigen Umgebungen ausgelöst werden.  
  
 Wenn Sie keine Berechtigung zum Erstellen des Ordners haben, wird in dem Beispiel eine Instanz der <xref:System.UnauthorizedAccessException>-Klasse ausgelöst.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO?displayProperty=fullName>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](../../../csharp/programming-guide/file-system/index.md)
