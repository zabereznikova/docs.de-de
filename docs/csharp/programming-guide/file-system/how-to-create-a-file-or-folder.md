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
ms.translationtype: HT
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 95b35941e18d22e2d484017262d9adbe8a081a8a
ms.contentlocale: de-de
ms.lasthandoff: 07/26/2017

---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a>Gewusst wie: Erstellen einer Datei oder eines Ordners (C#-Programmierhandbuch)
Sie können einen Ordner auf dem Computer programmgesteuert erstellen, einen Unterordner erstellen, eine Datei im Unterordner erstellen und Daten in die Datei schreiben.  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]  
  
 Falls der Ordner bereits vorhanden ist, führt <xref:System.IO.Directory.CreateDirectory%2A> keine Aktion aus, und es wird keine Ausnahme ausgelöst. Allerdings wird mit <xref:System.IO.File.Create%2A?displayProperty=fullName> eine vorhandene Datei durch eine neue Datei ersetzt. Im Beispiel wird eine `if`-`else`-Anweisung verwendet, um zu verhindern, dass eine vorhandene Datei ersetzt wird.  
  
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
  
-   Der Ordnername ist `null` (<xref:System.ArgumentNullException>-Klasse).  
  
-   Der Ordnername ist zu lang (<xref:System.IO.PathTooLongException>-Klasse).  
  
-   Der Ordnername besteht nur aus einem Doppelpunkt ":" (<xref:System.IO.PathTooLongException>-Klasse).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Eine Instanz der <xref:System.Security.SecurityException>-Klasse kann in nur teilweise vertrauenswürdigen Umgebungen ausgelöst werden.  
  
 Wenn Sie keine Berechtigung zum Erstellen des Ordners haben, wird in dem Beispiel eine Instanz der <xref:System.UnauthorizedAccessException>-Klasse ausgelöst.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO?displayProperty=fullName>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](../../../csharp/programming-guide/file-system/index.md)

