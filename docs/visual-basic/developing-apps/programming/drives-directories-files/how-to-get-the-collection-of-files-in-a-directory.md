---
title: 'Vorgehensweise: Abrufen einer Auflistung der Dateien in einem Verzeichnis in Visual Basic | Microsoft-Dokumentation'
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
- folders, working with
- files, accessing
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
caps.latest.revision: 23
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: d5b36baee302db0214844e0553473a05603090f1
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-get-the-collection-of-files-in-a-directory-in-visual-basic"></a>Gewusst wie: Abrufen einer Auflistung der Dateien in einem Verzeichnis in Visual Basic
Die Überladungen der Methode <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> gibt eine schreibgeschützte Auflistung von Zeichenfolgen zurück, die die Namen der Dateien in einem Verzeichnis darstellt:  
  
-   Verwenden Sie die Überladung <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29>, um bei einer einfachen Dateisuche in einem angegebenen Verzeichnis die Unterverzeichnisse auszuschließen.  
  
-   Verwenden Sie die Überladung <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])>, um zusätzliche Optionen für die Suche anzugeben. Sie können die `wildCards`-Parameter verwenden, um ein Suchmuster anzugeben. Um Unterverzeichnisse in die Suche einzubeziehen, legen Sie den Parameter `searchType` auf <xref:Microsoft.VisualBasic.FileIO.SearchOption?displayProperty=fullName> fest.  
  
 Es wird eine leere Sammlung zurückgegeben, wenn keine Dateien dem angegebenen Muster entsprechen.  
  
### <a name="to-list-files-in-a-directory"></a>So listen Sie Dateien in einem Verzeichnis auf  
  
-   Verwenden Sie eine der <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName>-Methodenüberladungen, und geben Sie dabei den Namen und den Pfad des im `directory`-Parameter zu durchsuchenden Verzeichnisses an. Im folgenden Beispiel werden alle Dateien im Verzeichnis zurückgegeben und `ListBox1` hinzugefügt.  
  
     [!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-get-the-collection-of-files-in-a-directory_1.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0 (null), er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Der Pfad ist ungültig, da er `Nothing` entspricht (<xref:System.ArgumentNullException>).  
  
-   `directory` ist nicht vorhanden (<xref:System.IO.DirectoryNotFoundException>).  
  
-   `directory` verweist auf eine vorhandene Datei (<xref:System.IO.IOException>).  
  
-   Der Pfad überschreitet die vom System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
-   Der Pfad eines Datei- oder Verzeichnisnamens im Pfad enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>   
 [Gewusst wie: Suchen nach Dateien mit einem bestimmten Muster](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)   
 [Gewusst wie: Suchen nach Unterverzeichnissen mit einem bestimmten Muster](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)

