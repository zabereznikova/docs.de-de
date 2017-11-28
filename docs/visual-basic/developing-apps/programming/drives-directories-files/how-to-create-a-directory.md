---
title: 'Gewusst wie: Erstellen eines Verzeichnisses in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2e4cd94113d77b2f4ff8127c80174107966ef360
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-directory-in-visual-basic"></a>Gewusst wie: Erstellen eines Verzeichnisses in Visual Basic
Verwenden Sie die `CreateDirectory`-Methode des `My.Computer.FileSystem`-Objekts, um Verzeichnisse zu erstellen.  
  
 Wenn das Verzeichnis bereits vorhanden ist, werden keine Ausnahmen ausgelöst.  
  
### <a name="to-create-a-directory"></a>So erstellen Sie ein Verzeichnis  
  
-   Verwenden Sie die `CreateDirectory`-Methode, indem Sie den vollständigen Pfad des Speicherorts angeben, an dem das Verzeichnis erstellt werden soll. Dieses Beispiel erstellt das Verzeichnis `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.  
  
     [!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Name des Verzeichnisses ist falsch formatiert. Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>).  
  
-   Das übergeordnete Verzeichnis des zu erstellenden Verzeichnisses ist schreibgeschützt (<xref:System.IO.IOException>).  
  
-   Der Name des Verzeichnisses ist `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Der Name des Verzeichnisses ist zu lang (<xref:System.IO.PathTooLongException>).  
  
-   Der Name des Verzeichnisses ist ein Doppelpunkt „:“ (<xref:System.NotSupportedException>).  
  
-   Der Benutzer verfügt über keine Berechtigungen zum Erstellen des Verzeichnisses (<xref:System.UnauthorizedAccessException>).  
  
-   Der Benutzer verfügt über keine Berechtigung in einem teilweise vertrauenswürdigen Kontext (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>  
 [Erstellen, Löschen und Verschieben von Dateien und Verzeichnissen](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
