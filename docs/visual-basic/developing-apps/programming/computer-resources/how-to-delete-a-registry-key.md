---
title: "Gewusst wie: Löschen von Registrierungsschlüsseln in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.DeleteSetting
helpviewer_keywords:
- GetSetting function [Visual Basic]
- registry [Visual Basic], deleting values
- GetAllSettings function
- registry keys [Visual Basic], deleting
- registry [Visual Basic], deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0cb98c02531bac133b9dc37a92f75d5c0418dc7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a>Gewusst wie: Löschen von Registrierungsschlüsseln in Visual Basic
Die Methoden <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> und <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> können zum Löschen von Registrierungsschlüsseln verwendet werden.  
  
## <a name="procedure"></a>Prozedur  
  
#### <a name="to-delete-a-registry-key"></a>Löschen von Registrierungsschlüsseln  
  
-   Verwenden Sie die `DeleteSubKey`-Methode zum Löschen von Registrierungsschlüsseln. In diesem Beispiel wird der Schlüssel „Software/TestApp“ aus der Struktur „CurrentUser“ gelöscht. Dies können Sie im Code in die entsprechende Zeichenfolge ändern, oder Sie können es von vom Benutzer zur Verfügung gestellten Informationen abhängig machen.  
  
     [!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die `DeleteSubKey`-Methode gibt eine leere Zeichenfolge zurück, wenn das Schlüssel-Wert-Paar nicht vorhanden ist.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Name des Schlüssels lautet `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Der Benutzer ist nicht zum Löschen von Registrierungsschlüsseln berechtigt (<xref:System.Security.SecurityException>).  
  
-   Der Name des Schlüssels überschreitet das Limit von 255 Zeichen (<xref:System.ArgumentException>).  
  
-   Der Registrierungsschlüssel ist schreibgeschützt (<xref:System.UnauthorizedAccessException>).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Registrierungsaufrufe schlagen fehl, wenn die notwendigen Laufzeitberechtigungen fehlen (<xref:System.Security.Permissions.RegistryPermission>), oder wenn der Benutzer nicht über den korrekten Zugriff (wie von den ACLs angegeben) für das Erstellen von und Schreiben in Einstellungen verfügt. Beispielsweise besitzt eine lokale Anwendung, die die Sicherheitsberechtigung für den Codezugriff besitzt, möglicherweise keine Betriebssystemberechtigung.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>  
 <xref:Microsoft.Win32.RegistryKey>  
 [Sicherheit und die Registrierung](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 [Lesen aus der und Schreiben in die Registrierung](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
