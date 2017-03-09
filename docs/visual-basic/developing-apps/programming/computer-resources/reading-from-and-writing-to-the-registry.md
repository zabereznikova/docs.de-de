---
title: "Reading from and Writing to the Registry (Visual Basic) | Microsoft Docs"
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
  - "My.Computer.Registry object, tasks"
  - "registry, writing to"
  - "registry, reading"
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Reading from and Writing to the Registry (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Dieses Thema beschreibt Aufgabe und konzeptionelle Themen, die mit der Registrierung zugeordnet sind.  
  
 Beim Programmieren in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] können Sie entweder mit den in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] bereitgestellten Funktionen oder mit den Registrierungsklassen von .NET Framework auf die Registrierung zugreifen.  Die Registrierung stellt Informationen aus dem Betriebssystem sowie aus Anwendungen bereit, die auf dem Computer verwendet werden.  Die Verwendung der Registrierung kann eine Beeinträchtigung der Sicherheit zur Folge haben, da hierdurch ungewollter Zugriff auf Systemressourcen oder geschützte Informationen möglich wird.  
  
## In diesem Abschnitt  
 [How to: Create a Registry Key and Set Its Value](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 Beschreibt, wie die `CreateSubKey``SetValue` und Methoden des `My.Computer.Registry`\-Objekts verwendet, um einen Registrierungsschlüssel zu erstellen und den Wert festzulegen.  
  
 [How to: Read a Value from a Registry Key](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 Beschreibt, wie die `GetValue`\-Methode des `My.Computer.Registry`\-Objekts verwendet, um einen Wert aus einem Registrierungsschlüssel zu lesen.  
  
 [How to: Delete a Registry Key](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 Beschreibt, wie die `DeleteSubKey`\-Methode der `My.Computer.Registry.CurrentUser`\-Eigenschaft verwendet, um einen Registrierungsschlüssel zu löschen.  
  
 [Lesen von der und Schreiben in die Registrierung mithilfe des Microsoft.Win32\-Namespaces](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 Beschreibt, wie die `Registry` und `RegistryKey`\-Klassen [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] verwendet, um die Registrierung zuzugreifen.  
  
 [Security and the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 Behandelt Sicherheitsprobleme im Zusammenhang mit der Registrierung.  
  
## Verwandte Abschnitte  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 Führt die Member des `My.Computer.Registry`\-Objekts auf und erläutert diese.  
  
 <xref:Microsoft.Win32.Registry>  
 Bietet eine Übersicht über die `Registry`\-Klasse sowie Links zu einzelnen Schlüsseln und Membern.