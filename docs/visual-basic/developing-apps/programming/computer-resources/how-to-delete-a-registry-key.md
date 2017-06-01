---
title: "Vorgehensweise: Löschen von Registrierungsschlüsseln in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.DeleteSetting
dev_langs:
- VB
helpviewer_keywords:
- GetSetting function
- registry, deleting values
- GetAllSettings function
- registry keys, deleting
- registry, deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
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
ms.openlocfilehash: a50ee5a0853e6209c3bf5d5224d536f4cc6bbe11
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

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
  
-   Der Benutzer ist nicht berechtigt, diese Registrierungsschlüssel zu löschen (<xref:System.Security.SecurityException>).  
  
-   Der Schlüsselname überschreitet die maximale Anzahl von 255 Zeichen (<xref:System.ArgumentException>).  
  
-   Der Registrierungschlüssel ist schreibgeschützt (<xref:System.UnauthorizedAccessException>).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Registrierungsaufrufe schlagen fehl, wenn die notwendigen Laufzeitberechtigungen fehlen (<xref:System.Security.Permissions.RegistryPermission>), oder wenn der Benutzer nicht über den korrekten Zugriff (wie von den ACLs angegeben) für das Erstellen von und Schreiben in Einstellungen verfügt. Beispielsweise besitzt eine lokale Anwendung, die die Sicherheitsberechtigung für den Codezugriff besitzt, möglicherweise keine Betriebssystemberechtigung.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey>   
 [Sicherheit und die Registrierung](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)   
 [Lesen aus der und Schreiben in die Registrierung](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
