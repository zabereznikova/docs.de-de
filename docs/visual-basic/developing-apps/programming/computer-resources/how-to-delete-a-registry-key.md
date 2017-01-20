---
title: "How to: Delete a Registry Key in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.DeleteSetting"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "GetSetting function"
  - "registry, deleting values"
  - "GetAllSettings function"
  - "registry keys, deleting"
  - "registry, deleting keys"
  - "examples [Visual Basic], registry"
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Delete a Registry Key in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29>\-Methode und die <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29>\-Methode können zum Löschen von Registrierungsschlüsseln verwendet werden.  
  
## Verfahren  
  
#### So löschen Sie einen Registrierungsschlüssel  
  
-   Verwenden Sie die `DeleteSubKey`\-Methode, um einen Registrierungsschlüssel zu löschen.  In diesem Beispiel wird der Schlüssel Software\/TestApp im CurrentUser\-Hive gelöscht.  Sie können im Code die entsprechende Zeichenfolge ändern oder die entsprechenden Informationen vom Benutzer eingeben lassen.  
  
     [!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-ke_1.vb)]  
  
## Robuste Programmierung  
 Die `DeleteSubKey`\-Methode gibt eine leere Zeichenfolge zurück, wenn das Schlüssel\/Wert\-Paar nicht vorhanden ist.  
  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Name des Schlüssels lautet `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Der Benutzer ist nicht berechtigt, Registrierungsschlüssel zu löschen \(<xref:System.Security.SecurityException>\).  
  
-   Der Name des Schlüssels ist länger als 255 Zeichen \(<xref:System.ArgumentException>\).  
  
-   Der Registrierungsschlüssel ist schreibgeschützt \(<xref:System.UnauthorizedAccessException>\).  
  
## .NET Framework-Sicherheit  
 Registrierungsaufrufe schlagen fehl, wenn nicht genügend Laufzeitberechtigungen erteilt wurden \(<xref:System.Security.Permissions.RegistryPermission>\) oder wenn der Benutzer nicht über die entsprechenden Zugriffsrechte \(die durch die ACLs festgelegt werden\) zum Erstellen oder Schreiben von Einstellungen verfügt.  Eine lokale Anwendung, die über die Berechtigung zum Zugriff auf Code verfügt, ist nicht automatisch zum Zugriff auf das Betriebssystem berechtigt.  
  
## Siehe auch  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey>   
 [Security and the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)   
 [Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)