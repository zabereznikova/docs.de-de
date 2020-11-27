---
title: 'Vorgehensweise: Ersetzen der WCF URL-Reservierung durch eine eingeschränkte Reservierung'
ms.date: 03/30/2017
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
ms.openlocfilehash: 52dc74ea1f8e86d6a92a2894b888b8d150ebf47c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276060"
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a>Vorgehensweise: Ersetzen der WCF URL-Reservierung durch eine eingeschränkte Reservierung

Mithilfe einer URL-Reservierung können Sie einschränken, wer Nachrichten von einer URL oder einem Satz von URLs empfangen darf. Eine Reservierung besteht aus einer URL-Vorlage, einer Zugriffssteuerungsliste (ACL) und einer Gruppe von Flags. Die URL-Vorlage definiert, auf welche URLs sich die Reservierung auswirkt. Weitere Informationen zur Verarbeitung von URL-Vorlagen finden Sie unter [Routing eingehender Anforderungen](/windows/win32/http/routing-incoming-requests). Die ACL steuert, welche Benutzer oder Benutzergruppen Nachrichten von den angegebenen URLs empfangen dürfen. Die Flags geben an, ob die Reservierung einem Benutzer oder einer Benutzergruppe die Berechtigung erteilt, die URL direkt zu überwachen oder die Überwachungsberechtigung an einen anderen Prozess zu übergeben.  
  
 Im Rahmen der Standardkonfiguration des Betriebssystems erstellt Windows Communication Foundation (WCF) eine Global barrierefreie Reservierung für Port 80, um allen Benutzern das Ausführen von Anwendungen zu ermöglichen, die eine duale HTTP-Bindung für die Duplex Kommunikation verwenden. Da die ACL bei dieser Reservierung allen Benutzern zur Verfügung steht, können Administratoren die Berechtigung, eine URL oder einen Satz von URLs zu überwachen, nicht explizit zulassen oder verweigern. In diesem Thema wird erläutert, wie Sie diese Reservierung löschen und mit einer eingeschränkten ACL neu erstellen.  
  
Unter Windows Vista oder Windows Server 2008 können Sie alle HTTP URL-Reservierungen an einer Eingabeaufforderung mit erhöhten Rechten anzeigen, indem Sie eingeben `netsh http show urlacl` . Das folgende Beispiel zeigt, wie eine WCF-URL-Reservierung aussehen sollte:

```output
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```

 Die Reservierung besteht aus einer URL-Vorlage, die verwendet wird, wenn eine WCF-Anwendung eine duale HTTP-Bindung für die Duplex Kommunikation verwendet. URLs dieses Formulars werden für einen WCF-Dienst verwendet, um Nachrichten bei der Kommunikation über eine duale HTTP-Bindung an den WCF-Client zurückzusenden. Allen Benutzern wird die Berechtigung erteilt, die URL zu überwachen, sie sind jedoch nicht berechtigt, die Überwachung an einen anderen Prozess zu delegieren. Die ACL wird in Security Descriptor Definition Language (SSDL) beschrieben. Weitere Informationen zu SSDL finden Sie unter [SSDL](/windows/win32/secauthz/security-descriptor-definition-language) .  
  
## <a name="to-delete-the-wcf-url-reservation"></a>So löschen Sie die WCF URL-Reservierung  
  
1. Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** , und klicken Sie im angezeigten Kontextmenü auf **als Administrator ausführen** . Klicken Sie im Fenster "Benutzerkontensteuerung" auf " **weiter** ", um möglicherweise Berechtigungen zum Fortfahren anzufordern.  
  
2. Geben Sie im Eingabe Aufforderungs `netsh http delete urlacl url=http://+:80/Temporary_Listen_Addresses/` Fenster ein.  
  
3. Wenn die Reservierung erfolgreich gelöscht wurde, wird die folgende Meldung angezeigt. **Die URL-Reservierung wurde erfolgreich gelöscht.**  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a>Erstellen einer neuen Sicherheitsgruppe und einer neuer eingeschränkten URL-Reservierung  

 Um die WCF-URL-Reservierung durch eine eingeschränkte Reservierung zu ersetzen, müssen Sie zuerst eine neue Sicherheitsgruppe erstellen. Hierzu stehen zwei Methoden zur Auswahl: Verwenden Sie entweder eine Eingabeaufforderung oder die Computerverwaltungskonsole. Sie müssen nur eine Methode ausführen.  
  
### <a name="to-create-a-new-security-group-from-a-command-prompt"></a>So erstellen Sie eine neue Sicherheitsgruppe an einer Eingabeaufforderung  
  
1. Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** , und klicken Sie im angezeigten Kontextmenü auf **als Administrator ausführen** . Klicken Sie im Fenster "Benutzerkontensteuerung" auf " **weiter** ", um möglicherweise Berechtigungen zum Fortfahren anzufordern.  
  
2. Geben Sie `net localgroup "<security group name>" /comment:"<security group description>" /add` an der Eingabeaufforderung ein. Ersetzen **\<security group name>** Sie durch den Namen der Sicherheitsgruppe, die Sie erstellen möchten, und **\<security group description>** durch eine geeignete Beschreibung für die Sicherheitsgruppe.  
  
3. Wenn die Sicherheitsgruppe erfolgreich erstellt wurde, wird die folgende Meldung angezeigt. **Der Befehl wurde erfolgreich abgeschlossen.**  
  
### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a>So erstellen Sie eine neue Sicherheitsgruppe an der Computerverwaltungskonsole  
  
1. Klicken Sie auf **Start**, klicken Sie auf **Systemsteuerung**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Computer Verwaltung** , um die Computer Verwaltungskonsole zu öffnen. Klicken Sie im Fenster "Benutzerkontensteuerung" auf " **weiter** ", um möglicherweise Berechtigungen zum Fortfahren anzufordern.  
  
2. Klicken Sie auf **System** Programme, **lokale Benutzer und Gruppen**, klicken Sie mit der rechten Maustaste auf **Gruppen** Ordner, und klicken Sie im angezeigten Kontextmenü auf **neue Gruppe** . Geben Sie den gewünschten **Gruppennamen**, die **Beschreibung** und weitere Details zu dieser neuen Sicherheitsgruppe ein, und klicken Sie auf die Schaltfläche **Erstellen** , um die Sicherheitsgruppe zu erstellen.  
  
### <a name="to-create-the-restricted-url-reservation"></a>So erstellen Sie die eingeschränkte URL-Reservierung  
  
1. Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** , und klicken Sie im angezeigten Kontextmenü auf **als Administrator ausführen** . Klicken Sie im Fenster "Benutzerkontensteuerung" auf " **weiter** ", um möglicherweise Berechtigungen zum Fortfahren anzufordern.  
  
2. Geben Sie `netsh http add urlacl url=http://+:80/Temporary_Listen_Addresses/ user="<machine name>\<security group name>` an der Eingabeaufforderung ein. Ersetzen **\<machine name>** Sie durch den Namen des Computers, auf dem die Gruppe erstellt werden muss, und **\<security group name>** durch den Namen der Sicherheitsgruppe, die Sie zuvor erstellt haben.  
  
3. Wenn die Reservierung erfolgreich erstellt wurde, wird die folgende Meldung angezeigt. **URL-Reservierung wurde erfolgreich hinzugefügt**.
