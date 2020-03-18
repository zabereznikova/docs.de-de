---
title: Sicherheit und die Registrierung
ms.date: 07/20/2015
helpviewer_keywords:
- security [Visual Basic], registry
- registry [Visual Basic], security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
ms.openlocfilehash: 454180207d6432e80d87941d1f329f2a4ea7a801
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345483"
---
# <a name="security-and-the-registry-visual-basic"></a>Sicherheit und die Registrierung (Visual Basic)

Diese Seite beschreibt die Sicherheitsauswirkungen bei der Speicherung von Daten in der Registrierung.  
  
## <a name="permissions"></a>Berechtigungen  

 Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Klartext zu speichern. Dies gilt auch, wenn der Registrierungsschlüssel durch Zugriffssteuerungslisten (ACLs) geschützt ist.  
  
 Das Arbeiten mit der Registrierung schränkt möglicherweise die Sicherheit ein, da nicht ordnungsgemäßer Zugriff auf Systemressourcen oder geschützte Informationen zugelassen wird. Um diese Eigenschaften verwenden zu können, benötigen Sie Lese- und Schreibberechtigungen aus der Enumeration <xref:System.Security.Permissions.RegistryPermissionAccess>, die den Zugriff auf Registrierungsvariablen steuert. Jeder Code, der mit voller Vertrauenswürdigkeit ausgeführt wird (gemäß der Standardsicherheitsrichtlinie ist dies jeder Code, der auf der lokalen Festplatte des Benutzers installiert ist) verfügt über die erforderlichen Berechtigungen zum Zugriff auf die Registrierung. Weitere Informationen finden Sie in der <xref:System.Security.Permissions.RegistryPermission>-Klasse.  
  
 Registrierungsvariablen sollten nicht an Speicherorten gespeichert werden, in denen Code ohne <xref:System.Security.Permissions.RegistryPermission> darauf zugreifen kann. Gewähren Sie auf ähnliche Weise die zur Erledigung der Aufgabe erforderlichen Mindestberechtigungen, wenn Sie Berechtigungen erteilen.  
  
 Zugriffswerte für Registrierungsberechtigungen werden von der Enumeration <xref:System.Security.Permissions.RegistryPermissionAccess> definiert. In der folgenden Tabelle werden die Member aufgeführt.  
  
|Wert|Zugriff auf Registrierungsvariablen|  
|-----------|----------------------------------|  
|`AllAccess`|Erstellen, Lesen und Schreiben|  
|`Create`|Erstellen|  
|`NoAccess`|Kein Zugriff|  
|`Read`|Lesen|  
|`Write`|Write|  
  
## <a name="checking-values-in-registry-keys"></a>Überprüfen von Werten in Registrierungsschlüsseln  

 Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist. Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann. Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen. Um dies zu verhindern, verwenden Sie die `GetValue`-Methode. Die Methode gibt `Nothing` zurück, wenn der Schlüssel noch nicht vorhanden ist.  
  
> [!IMPORTANT]
> Wenn Sie die Registrierung von einer Webanwendung lesen, hängt die Identität aktueller Benutzer von der Authentifizierung und dem Identitätswechsel ab, die in der Webanwendung implementiert sind.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [Lesen aus der und Schreiben in die Registrierung](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
