---
title: "How to: Read a Value from a Registry Key in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "registry keys, determining if a value exists in"
  - "My.Computer.Registry object, examples"
  - "registry, determining if values exist"
  - "registry keys, reading from"
  - "registry, reading"
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: 31
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 31
---
# How to: Read a Value from a Registry Key in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Mit der `GetValue`\-Methode des `My.Computer.Registry`\-Objekts können Werte in der Windows\-Registrierung gelesen werden.  
  
 Wenn der Schlüssel, „Software \\ MyApp“ im folgenden Beispiel nicht vorhanden ist, wird eine Ausnahme ausgelöst.  Wenn `ValueName`, „Name“ im folgenden Beispiel nicht vorhanden ist, wird `Nothing` zurückgegeben.  
  
 Die `GetValue`\-Methode kann auch verwendet werden, um zu bestimmen, ob ein angegebener Wert in einem bestimmten Registrierungsschlüssel vorhanden ist.  
  
 Wenn Code die Registrierung von einer Webanwendung aus lesen, wird der aktuelle Benutzer von der Authentifizierung und dem Identitätswechsel bestimmt, die in der Webanwendung implementiert wird.  
  
### So lesen Sie einen Wert aus einem Registrierungsschlüssel  
  
-   Verwenden Sie die `GetValue`\-Methode, und geben Sie den Pfad und Namen an, um einen Wert aus einem Registrierungsschlüssel zu lesen.  Mit dem folgenden Beispielcode wird der Wert `Name` aus `HKEY_CURRENT_USER\Software\MyApp` gelesen und in einem Meldungsfeld angezeigt.  
  
     [!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-read-a-value-from_1.vb)]  
  
 Dieses Codebeispiel ist auch als IntelliSense\-Codeausschnitt verfügbar.  Sie finden das Element in der Codeausschnittauswahl unter **Windows\-Betriebssystem \> Registrierung**.  Weitere Informationen finden Sie unter [Codeausschnitte](/visual-studio/ide/code-snippets).  
  
### So ermitteln Sie, ob ein Wert in einem Registrierungsschlüssel vorhanden ist  
  
-   Verwenden Sie die `GetValue`\-Methode, um den Wert abzurufen.  Die folgenden Code überprüft, ob der Wert einer Nachricht vorhanden und zurückgibt, wenn dies nicht der Fall ist.  
  
     [!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-read-a-value-from_2.vb)]  
  
## Robuste Programmierung  
 Die Registrierung enthält Schlüssel der obersten Ebene \(auch: Stammschlüssel\), die zum Speichern von Daten verwendet werden.  Der Stammschlüssel HKEY\_LOCAL\_MACHINE dient z. B. zum Speichern von Einstellungen auf Computerebene, die für alle Benutzer gelten, während unter HKEY\_CURRENT\_USER  Daten gespeichert werden, die für einen einzelnen Benutzer gelten.  
  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Name des Schlüssels lautet `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Der Benutzer ist nicht berechtigt, Registrierungsschlüssel zu lesen \(<xref:System.Security.SecurityException>\).  
  
-   Der Name des Schlüssels ist länger als 255 Zeichen \(<xref:System.ArgumentException>\).  
  
## .NET Framework-Sicherheit  
 Um diesen Prozess auszuführen, benötigt die Assembly eine Berechtigungsebene, die von der <xref:System.Security.Permissions.RegistryPermission>\-Klasse gewährt wird.  Bei Ausführung in einer teilweise vertrauenswürdigen Umgebung kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen.  Dementsprechend muss der Benutzer die richtigen Zugriffssteuerungslisten haben, um Einstellungen erstellen oder bearbeiten zu können.  Eine lokale Anwendung, die über die Berechtigung zum Zugriff auf Code verfügt, ist nicht automatisch zum Zugriff auf das Betriebssystem berechtigt.  Weitere Informationen finden Sie unter [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.Win32.RegistryHive>   
 [Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)