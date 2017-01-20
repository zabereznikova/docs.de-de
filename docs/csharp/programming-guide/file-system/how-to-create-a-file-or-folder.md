---
title: "Gewusst wie: Erstellen einer Datei oder eines Ordners (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Erstellen von Dateien [C#]"
  - "Erstellen von Ordnern [C#]"
  - "Dateien [C#]"
  - "Ordner [C#]"
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Erstellen einer Datei oder eines Ordners (C#-Programmierhandbuch)
Sie können einen Ordner auf dem Computer programmgesteuert erstellen, einen Unterordner erstellen, eine Datei im Unterordner erstellen und Daten in die Datei schreiben.  
  
## Beispiel  
 [!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/csFilesFolders/FileIteration.cs#10)]  
  
 Falls der Ordner bereits vorhanden ist, führt <xref:System.IO.Directory.CreateDirectory%2A> keine Aktion aus, und es wird keine Ausnahme ausgelöst.  Allerdings wird mit <xref:System.IO.File.Create%2A?displayProperty=fullName> eine vorhandene Datei durch eine neue Datei ersetzt.  Im Beispiel wird eine `if`\-`else`\-Anweisung verwendet, um zu verhindern, dass eine vorhandene Datei ersetzt wird.  
  
 Wenn Sie die folgenden Änderungen im Beispiel vornehmen, können Sie, je nachdem, ob eine Datei mit einem bestimmten Namen bereits vorhanden ist, unterschiedliche Ergebnisse erzeugen.  Wenn eine solche Datei nicht vorhanden ist, erstellt der Code sie.  Wenn eine solche Datei vorhanden ist, fügt der Code Daten an diese Datei an.  
  
-   Geben Sie einen nicht zufälligen Dateinamen an.  
  
    ```c#  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
  
    ```  
  
-   Ersetzen Sie im folgenden Code die `if`\-`else`\-Anweisung durch die `using`\-Anweisung.  
  
    ```c#  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
  
    ```  
  
 Führen Sie das Beispiel mehrmals aus, um zu überprüfen, dass der Datei jedes Mal Daten hinzugefügt werden.  
  
 Weitere `FileMode`\-Werte, die Sie ausprobieren können, finden Sie unter <xref:System.IO.FileMode>.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Ordnername ist falsch formatiert.  Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen \(<xref:System.ArgumentException>\-Klasse\).  Verwenden Sie die <xref:System.IO.Path>\-Klasse, um gültige Pfadnamen zu erstellen.  
  
-   Der übergeordnete Ordner des zu erstellenden Ordners ist schreibgeschützt \(<xref:System.IO.IOException>\-Klasse\).  
  
-   Der Ordnername ist `null` \(<xref:System.ArgumentNullException>\-Klasse\).  
  
-   Der Ordnername ist zu lang \(<xref:System.IO.PathTooLongException>\-Klasse\).  
  
-   Der Ordnername besteht nur aus einem Doppelpunkt ":" \(<xref:System.IO.PathTooLongException>\-Klasse\).  
  
## .NET Framework-Sicherheit  
 Eine Instanz der <xref:System.Security.SecurityException>\-Klasse kann in nur teilweise vertrauenswürdigen Umgebungen ausgelöst werden.  
  
 Wenn Sie keine Berechtigung zum Erstellen des Ordners haben, wird in dem Beispiel eine Instanz der <xref:System.UnauthorizedAccessException>\-Klasse ausgelöst.  
  
## Siehe auch  
 <xref:System.IO?displayProperty=fullName>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Das Dateisystem und die Registrierung](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)