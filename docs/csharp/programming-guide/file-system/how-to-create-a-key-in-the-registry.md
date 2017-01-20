---
title: "Gewusst wie: Erstellen eines Schl&#252;ssels in der Registrierung (Visual&#160;C#) | Microsoft Docs"
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
  - "Schlüssel, Erstellen in Registrierung"
  - "Registrierungsschlüssel, Erstellen [C#]"
  - "Registrierung, Hinzufügen von Schlüsseln und Werten [C#]"
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Erstellen eines Schl&#252;ssels in der Registrierung (Visual&#160;C#)
Dieses Beispiel fügt der Registrierung des aktuellen Benutzers unter dem Schlüssel "Names" das Wertepaar "Name" und "Isabella" hinzu.  
  
## Beispiel  
  
```  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## Kompilieren des Codes  
  
-   Kopieren Sie den Code, und fügen Sie ihn in die `Main`\-Methode einer Konsolenanwendung ein.  
  
-   Ersetzen Sie den `Names`\-Parameter durch den Namen eines Schlüssels, der sich in der Registrierung direkt unter dem HKEY\_CURRENT\_USER\-Knoten befindet.  
  
-   Ersetzen Sie den `Nam`e\-Parameter durch den Namen eines Werts, der sich direkt unterhalb des Names\-Knotens befindet.  
  
## Robuste Programmierung  
 Untersuchen Sie die Registrierungsstruktur, um eine adäquate Position für den Schlüssel zu ermitteln.  Sie können beispielsweise den Schlüssel Software des aktuellen Benutzers öffnen und einen Schlüssel mit dem Namen Ihres Unternehmens erstellen.  Anschließend fügen Sie die Registrierungswerte dem Schlüssel für das Unternehmen hinzu.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Name des Schlüssels ist NULL.  
  
-   Der Benutzer ist nicht zum Erstellen von Registrierungsschlüsseln berechtigt.  
  
-   Der Name des Schlüssels ist länger als 255 Zeichen.  
  
-   Der Schlüssel ist geschlossen.  
  
-   Der Registrierungsschlüssel ist schreibgeschützt.  
  
## .NET Framework-Sicherheit  
 Es ist sicherer, die Daten in den Benutzerordner \(`Microsoft.Win32.Registry.CurrentUser`\) anstatt auf den lokalen Computer \(`Microsoft.Win32.Registry.LocalMachine`\) zu schreiben.  
  
 Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist.  Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann.  Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen.  Um dies zu verhindern, verwenden Sie die `Overload:Microsoft.Win32.RegistryKey.GetValue`\-Methode.  Die Methode gibt NULL zurück, wenn der Schlüssel noch nicht vorhanden ist.  
  
 Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Klartext zu speichern. Dies gilt auch, wenn der Registrierungsschlüssel durch Zugriffssteuerungslisten \(ACLs\) geschützt ist.  
  
## Siehe auch  
 <xref:System.IO?displayProperty=fullName>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Das Dateisystem und die Registrierung](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)   
 [Ausführen von Aktionen in der Registrierung mit C\#: Lesen, Schreiben und Löschen](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)