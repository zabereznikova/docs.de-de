---
title: "How to: Create a Registry Key and Set Its Value in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "RegistryKey.CreateSubKey"
  - "RegistryKey.SetValue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "registry keys, creating"
  - "registry, adding values"
  - "registry, adding keys"
  - "registry keys, setting values"
  - "examples [Visual Basic], registry"
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# How to: Create a Registry Key and Set Its Value in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Die `CreateSubKey`\-Methode des `My.Computer.Registry`\-Objekts kann zum Erstellen eines Registrierungsschlüssels verwendet werden.  
  
## Verfahren  
  
#### So erstellen Sie einen Registrierungsschlüssel  
  
-   Verwenden Sie die `CreateSubKey`\-Methode, und geben Sie dort den Hive, in den der Schlüssel eingefügt werden soll, sowie den Namen des Schlüssels an.  Beim Parameter  `Subkey`  wird nicht zwischen Groß\-\/Kleinschreibung unterschieden.  In diesem Beispiel wird der Registrierungsschlüssel `MyTestKey` unter HKEY\_CURRENT\_USER erstellt.  
  
     [!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-create-a-registry_1.vb)]  
  
#### So erstellen Sie einen Registrierungsschlüssel und legen einen Wert dafür fest  
  
1.  Verwenden Sie die `CreateSubkey`\-Methode, und geben Sie dort den Hive, in den der Schlüssel eingefügt werden soll, sowie den Namen des Schlüssels an.  In diesem Beispiel wird der Registrierungsschlüssel `MyTestKey` unter HKEY\_CURRENT\_USER erstellt.  
  
     [!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-create-a-registry_1.vb)]  
  
2.  Legen Sie den Wert mit der `SetValue`\-Methode fest.  In diesem Beispiel wird der Zeichenfolgenwert festgelegt. "  "MyTestKeyValue" wird "This is a test value" zugewiesen.  
  
     [!code-vb[VbResourceTasks#14](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-create-a-registry_2.vb)]  
  
## Beispiel  
 In diesem Beispiel wird der Registrierungsschlüssel `MyTestKey` unter HKEY\_CURRENT\_USER erstellt und anschließend dem Zeichenfolgenwert `MyTestKeyValue` die Zeichenfolge `This is a test value` zugewiesen.  
  
 [!code-vb[VbResourceTasks#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-create-a-registry_3.vb)]  
  
## Robuste Programmierung  
 Untersuchen Sie die Registrierungsstruktur, um eine adäquate Position für den Schlüssel zu ermitteln.  Beispielsweise können Sie den Schlüssel HKEY\_CURRENT\_USER\\Software für den aktuellen Benutzer öffnen und einen Schlüssel mit dem Namen Ihrer Firma erstellen.  Anschließend fügen Sie die Registrierungswerte dem Schlüssel für das Unternehmen hinzu.  
  
 Wenn Sie die Registrierung von einer Webanwendung aus lesen, hängt der aktuelle Benutzer von der Authentifizierung und dem Identitätswechsel ab, die in der Webanwendung implementiert wurden.  
  
 Es ist sicherer, die Daten in den Benutzerordner \(<xref:Microsoft.Win32.Registry.CurrentUser>\) anstatt in den lokalen Computer \(<xref:Microsoft.Win32.Registry.LocalMachine>\) zu schreiben.  
  
 Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist.  Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann.  Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen.  Um dies zu verhindern, verwenden Sie die <xref:Microsoft.Win32.RegistryKey.GetValue%2A>\-Methode.  Die Methode gibt `Nothing` zurück, wenn der Schlüssel noch nicht vorhanden ist.  
  
 Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als reinen Text zu speichern. Dies gilt auch, wenn die Registrierung durch Zugriffssteuerungslisten \(ACLs\) geschützt ist.  
  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Name des Schlüssels lautet `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Der Benutzer ist nicht zum Erstellen von Registrierungsschlüsseln berechtigt \(<xref:System.Security.SecurityException>\).  
  
-   Der Name des Schlüssels ist länger als 255 Zeichen \(<xref:System.ArgumentException>\).  
  
-   Der Schlüssel ist geschlossen \(<xref:System.IO.IOException>\).  
  
-   Der Registrierungsschlüssel ist schreibgeschützt \(<xref:System.UnauthorizedAccessException>\).  
  
## .NET Framework-Sicherheit  
 Um diesen Prozess auszuführen, benötigt die Assembly eine Berechtigungsebene, die von der <xref:System.Security.Permissions.RegistryPermission>\-Klasse gewährt wird.  Bei Ausführung in einer teilweise vertrauenswürdigen Umgebung kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen.  Dementsprechend muss der Benutzer die richtigen Zugriffssteuerungslisten haben, um Einstellungen erstellen oder bearbeiten zu können.  Eine lokale Anwendung, die über die Berechtigung zum Zugriff auf Code verfügt, ist nicht automatisch zum Zugriff auf das Betriebssystem berechtigt.  Weitere Informationen finden Sie unter [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>   
 <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>   
 [Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)   
 [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md)