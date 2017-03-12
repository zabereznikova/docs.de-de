---
title: "Security and the Registry (Visual Basic) | Microsoft Docs"
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
  - "security [Visual Basic], registry"
  - "registry, security issues"
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Security and the Registry (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Auf dieser Seite wird erläutert, welche Sicherheitsauswirkungen das Speichern von Daten in der Registrierung hat.  
  
## Berechtigungen  
 Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Volltext zu speichern. Dies gilt auch, wenn die Registrierung durch Zugriffssteuerungslisten \(ACLs \- Access Control Lists\) geschützt ist.  
  
 Die Verwendung der Registrierung kann eine Beeinträchtigung der Sicherheit zur Folge haben, da hierdurch ungewollter Zugriff auf Systemressourcen oder geschützte Informationen möglich wird.  Um diese Eigenschaften verwenden zu können, muss die <xref:System.Security.Permissions.RegistryPermissionAccess>\-Enumeration, die den Zugriff auf Registrierungsvariablen steuert, die entsprechenden Lese\- und Schreibberechtigungen gewähren.  Jeder Code, der als voll vertrauenswürdig ausgeführt wird \(gemäß der Standardsicherheitsrichtlinie ist dies jeder Code, der auf der lokalen Festplatte des Benutzers installiert ist\), hat die erforderlichen Berechtigungen für den Zugriff auf die Registrierung.  Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Security.Permissions.RegistryPermission>\-Klasse.  
  
 Registrierungsvariablen sollten nicht in Speicherbereichen gespeichert werden, in denen Code ohne <xref:System.Security.Permissions.RegistryPermission> auf sie zugreifen kann.  Ebenso gilt, dass Sie beim Erteilen von Berechtigungen jeweils nur die Rechte gewähren sollten, die zur Ausführung einer Aufgabe unbedingt erforderlich sind.  
  
 Die Zugriffswerte der Registrierungsberechtigung werden durch die <xref:System.Security.Permissions.RegistryPermissionAccess>\-Enumeration definiert.  In der folgenden Tabelle sind deren Member aufgeführt.  
  
|Wert|Zugriff auf Registrierungsvariablen|  
|----------|-----------------------------------------|  
|`AllAccess`|Erstellen, Lesen und Schreiben|  
|`Create`|Create|  
|`NoAccess`|Kein Zugriff|  
|`Read`|Thema|  
|`Write`|Write|  
  
## Überprüfen von Werten in Registrierungsschlüsseln  
 Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist.  Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann.  Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen.  Um dies zu verhindern, verwenden Sie die `GetValue`\-Methode.  Die Methode gibt `Nothing` zurück, wenn der Schlüssel noch nicht vorhanden ist.  
  
> [!IMPORTANT]
>  Wenn Sie die Registrierung von einer Webanwendung aus lesen, hängt die Identität des aktuellen Benutzers von der Authentifizierung und dem Identitätswechsel ab, die in der Webanwendung implementiert wurden.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 [Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)