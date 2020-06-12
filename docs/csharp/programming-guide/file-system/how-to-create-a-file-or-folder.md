---
title: 'Vorgehensweise: Erstellen einer Datei oder eines Ordners (C#-Programmierleitfaden)'
ms.date: 07/20/2015
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
ms.openlocfilehash: 5efe3b7dc600645488816d6f931df57fc236efc9
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241642"
---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a>Vorgehensweise: Erstellen einer Datei oder eines Ordners (C#-Programmierleitfaden)
Sie können einen Ordner auf dem Computer programmgesteuert erstellen, einen Unterordner erstellen, eine Datei im Unterordner erstellen und Daten in die Datei schreiben.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csFilesandFolders#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#10)]  
  
 Falls der Ordner bereits vorhanden ist, führt <xref:System.IO.Directory.CreateDirectory%2A> keine Aktion aus, und es wird keine Ausnahme ausgelöst. Allerdings wird mit <xref:System.IO.File.Create%2A?displayProperty=nameWithType> eine vorhandene Datei durch eine neue Datei ersetzt. Im Beispiel wird eine `if`-`else`-Anweisung verwendet, um zu verhindern, dass eine vorhandene Datei ersetzt wird.  
  
 Wenn Sie die folgenden Änderungen im Beispiel vornehmen, können Sie, je nachdem, ob eine Datei mit einem bestimmten Namen bereits vorhanden ist, unterschiedliche Ergebnisse erzeugen. Wenn eine solche Datei nicht vorhanden ist, erstellt der Code sie. Wenn eine solche Datei vorhanden ist, fügt der Code Daten an diese Datei an.  
  
- Geben Sie einen nicht zufälligen Dateinamen an.  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
- Ersetzen Sie im folgenden Code die `if`-`else`-Anweisung durch die `using`-Anweisung.  
  
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
  
- Der Ordnername ist falsch formatiert. Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>-Klasse). Verwenden Sie die <xref:System.IO.Path>-Klasse, um gültige Pfadnamen zu erstellen.  
  
- Der übergeordnete Ordner des zu erstellenden Ordners ist schreibgeschützt (<xref:System.IO.IOException>-Klasse).  
  
- Der Ordnername ist `null` (<xref:System.ArgumentNullException>-Klasse).  
  
- Der Ordnername ist zu lang (<xref:System.IO.PathTooLongException>-Klasse).  
  
- Der Ordnername besteht nur aus einem Doppelpunkt ":" (<xref:System.IO.PathTooLongException>-Klasse).  
  
## <a name="net-security"></a>.NET-Sicherheit  
 Eine Instanz der <xref:System.Security.SecurityException>-Klasse kann in nur teilweise vertrauenswürdigen Umgebungen ausgelöst werden.  
  
 Wenn Sie keine Berechtigung zum Erstellen des Ordners haben, wird in dem Beispiel eine Instanz der <xref:System.UnauthorizedAccessException>-Klasse ausgelöst.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO?displayProperty=nameWithType>
- [C#-Programmierhandbuch](../index.md)
- [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](./index.md)
