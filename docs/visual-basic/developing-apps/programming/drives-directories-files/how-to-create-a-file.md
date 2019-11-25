---
title: 'Vorgehensweise: Erstellen einer Datei'
ms.date: 07/20/2015
helpviewer_keywords:
- text files [Visual Basic], creating
- files [Visual Basic], creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
ms.openlocfilehash: 20533ec01d3198d499312ed0c15ec8cca2ff70bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348801"
---
# <a name="how-to-create-a-file-in-visual-basic"></a>Vorgehensweise: Erstellen einer Datei in Visual Basic

Dieses Beispiel erstellt mithilfe der <xref:System.IO.File.Create%2A>-Methode in der <xref:System.IO.File>-Klasse eine leere Textdatei auf dem bestimmten Pfad.  
  
## <a name="example"></a>Beispiel  

 [!code-vb[VbFileIOMisc#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/class2.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

 Verwenden Sie die Varible `file`, um in die Datei zu schreiben.  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Wenn die Datei bereits vorhanden ist, wird sie ignoriert.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Der Pfadname ist falsch formatiert. Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>).  
  
- Der Pfad ist schreibgeschützt (<xref:System.IO.IOException>).  
  
- Der Pfadname ist `Nothing` (<xref:System.ArgumentNullException>).  
  
- Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>).  
  
- Der Pfad ist ungültig (<xref:System.IO.DirectoryNotFoundException>).  
  
- Der Pfad besteht nur aus einem Doppelpunkt „:“ (<xref:System.NotSupportedException>).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  

 Eine <xref:System.Security.SecurityException> wir möglicherweise in teilweise vertrauenswürdigen Umgebungen ausgelöst.  
  
 Der Aufruf auf die <xref:System.IO.File.Create%2A>-Methode erfordert <xref:System.Security.Permissions.FileIOPermission>.  
  
 Eine <xref:System.UnauthorizedAccessException> wird ausgelöst, wenn der Benutzer keine Berechtigungen zum Erstellen der Datei besitzt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO>
- <xref:System.IO.File.Create%2A>
- [Verwenden von Bibliotheken aus teilweise vertrauenswürdigem Code](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)
- [Grundlagen der Codezugriffssicherheit](../../../../framework/misc/code-access-security-basics.md)
