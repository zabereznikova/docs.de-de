---
title: 'Vorgehensweise: Ersetzen der WCF URL-Reservierung durch eine eingeschränkte Reservierung'
ms.date: 03/30/2017
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
ms.openlocfilehash: b53596d7ac4e7e7c3748f6a98130492a96c0b48c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111347"
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a>Vorgehensweise: Ersetzen der WCF URL-Reservierung durch eine eingeschränkte Reservierung
Mithilfe einer URL-Reservierung können Sie einschränken, wer Nachrichten von einer URL oder einem Satz von URLs empfangen darf. Eine Reservierung besteht aus einer URL-Vorlage, einer Zugriffssteuerungsliste (ACL) und einer Gruppe von Flags. Die URL-Vorlage definiert, auf welche URLs sich die Reservierung auswirkt. Weitere Informationen zur Verarbeitung von URL-Vorlagen finden Sie unter [Routing eingehender Anfragen](https://go.microsoft.com/fwlink/?LinkId=136764). Die ACL steuert, welche Benutzer oder Benutzergruppen Nachrichten von den angegebenen URLs empfangen dürfen. Die Flags geben an, ob die Reservierung einem Benutzer oder einer Benutzergruppe die Berechtigung erteilt, die URL direkt zu überwachen oder die Überwachungsberechtigung an einen anderen Prozess zu übergeben.  
  
 Als Teil der Standard-Betriebssystemkonfiguration erstellt Windows Communication Foundation (WCF) eine Reservierung mit globalem Zugriff für Anschluss 80, sodass alle Benutzer zum Ausführen von Anwendungen, die eine duale HTTP-Bindung für die Duplexkommunikation verwenden. Da die ACL bei dieser Reservierung allen Benutzern zur Verfügung steht, können Administratoren die Berechtigung, eine URL oder einen Satz von URLs zu überwachen, nicht explizit zulassen oder verweigern. In diesem Thema wird erläutert, wie Sie diese Reservierung löschen und mit einer eingeschränkten ACL neu erstellen.  
  
 Unter [!INCLUDE[wv](../../../../includes/wv-md.md)] oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)] können Sie alle HTTP-URL-Reservierungen von einer Eingabeaufforderung auf höherer Ebene aus anzeigen, indem Sie `netsh http show urlacl` eingeben.  Das folgende Beispiel zeigt, was eine WCF-URL-Reservierung entsprechen soll.  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 Die Reservierung besteht aus einer URL-Vorlage verwendet, wenn eine WCF-Anwendung eine duale HTTP-Bindung für die Duplexkommunikation verwendet wird. Derartige URLs werden für einen WCF-Dienst zum Senden von Nachrichten zurück an den WCF-Client, bei der Kommunikation über eine duale HTTP-Bindung verwendet. Allen Benutzern wird die Berechtigung erteilt, die URL zu überwachen, sie sind jedoch nicht berechtigt, die Überwachung an einen anderen Prozess zu delegieren. Die ACL wird in Security Descriptor Definition Language (SSDL) beschrieben. Weitere Informationen zum SSDL, finden Sie unter [SSDL](https://go.microsoft.com/fwlink/?LinkId=136789)  
  
### <a name="to-delete-the-wcf-url-reservation"></a>So löschen Sie die WCF URL-Reservierung  
  
1.  Klicken Sie auf **starten**, zeigen Sie auf **Programme**, klicken Sie auf **Zubehör**, mit der rechten Maustaste **Eingabeaufforderung** , und klicken Sie auf **Ausführen als Administrator** im Kontextmenü angezeigt wird. Klicken Sie auf **Weiter** auf Fenster (User Account Control, UAC), die Berechtigungen, um den Vorgang fortzusetzen, bitten kann.  
  
2.  Geben Sie in **Netsh http delete Urlacl Url =http://+:80/Temporary_Listen_Addresses/**  im Eingabeaufforderungsfenster Befehl.  
  
3.  Wenn die Reservierung erfolgreich gelöscht wurde, wird die folgende Meldung angezeigt. **URL-Reservierung wurde erfolgreich gelöscht.**  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a>Erstellen einer neuen Sicherheitsgruppe und einer neuer eingeschränkten URL-Reservierung  
 Um die WCF URL-Reservierung durch eine eingeschränkte Reservierung zu ersetzen, müssen Sie zunächst eine neue Sicherheitsgruppe erstellen. Hierzu stehen zwei Methoden zur Auswahl: Verwenden Sie entweder eine Eingabeaufforderung oder die Computerverwaltungskonsole. Sie müssen nur eine Methode ausführen.  
  
#### <a name="to-create-a-new-security-group-from-a-command-prompt"></a>So erstellen Sie eine neue Sicherheitsgruppe an einer Eingabeaufforderung  
  
1.  Klicken Sie auf **starten**, zeigen Sie auf **Programme**, klicken Sie auf **Zubehör**, mit der rechten Maustaste **Eingabeaufforderung** , und klicken Sie auf **Ausführen als Administrator** im Kontextmenü angezeigt wird. Klicken Sie auf **Weiter** auf Fenster (User Account Control, UAC), die Berechtigungen, um den Vorgang fortzusetzen, bitten kann.  
  
2.  Geben Sie in **net Localgroup "\<Name der Sicherheitsgruppe >" / comment: "\<Beschreibung der Sicherheitsgruppe >" / add** an der Eingabeaufforderung. Ersetzen von  **\<Name der Sicherheitsgruppe >** mit dem Namen der zu erstellenden Sicherheitsgruppe und  **\<Beschreibung der Sicherheitsgruppe >** durch eine geeignete Beschreibung für die Sicherheitsgruppe.  
  
3.  Wenn die Sicherheitsgruppe erfolgreich erstellt wurde, wird die folgende Meldung angezeigt. **Der Befehl wurde erfolgreich abgeschlossen.**  
  
#### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a>So erstellen Sie eine neue Sicherheitsgruppe an der Computerverwaltungskonsole  
  
1.  Klicken Sie auf **starten**, klicken Sie auf **Systemsteuerung**, klicken Sie auf **Verwaltung**, und klicken Sie auf **Computerverwaltung** , um den Computer zu öffnen -Verwaltungskonsole. Klicken Sie auf **Weiter** auf Fenster (User Account Control, UAC), die Berechtigungen, um den Vorgang fortzusetzen, bitten kann.  
  
2.  Klicken Sie auf **Systemprogramme**, klicken Sie auf **lokale Benutzer und Gruppen**, mit der rechten Maustaste **Gruppen** Ordner, und klicken Sie auf **neue Gruppe** im Kontextmenü, angezeigt wird. Geben Sie den gewünschten **Gruppenname**, **Beschreibung** und weitere Details dieser neuen Sicherheitsgruppe hinzu, und klicken Sie auf die **erstellen** klicken, um die Sicherheitsgruppe zu erstellen.  
  
#### <a name="to-create-the-restricted-url-reservation"></a>So erstellen Sie die eingeschränkte URL-Reservierung  
  
1.  Klicken Sie auf **starten**, zeigen Sie auf **Programme**, klicken Sie auf **Zubehör**, mit der rechten Maustaste **Eingabeaufforderung** , und klicken Sie auf **Ausführen als Administrator** im Kontextmenü angezeigt wird. Klicken Sie auf **Weiter** auf Fenster (User Account Control, UAC), die Berechtigungen, um den Vorgang fortzusetzen, bitten kann.  
  
2.  Geben Sie in **Netsh http hinzufügen Urlacl Url =http://+:80/Temporary_Listen_Addresses/ Benutzer = "\<Computername >\\< Name der Sicherheitsgruppe\>**  an der Eingabeaufforderung. Ersetzen von  **\<Computername >** mit dem Computernamen, die auf dem die Gruppe erstellt werden und  **\<Name der Sicherheitsgruppe >** durch den Namen der Sicherheitsgruppe, die Sie erstellt haben zuvor.  
  
3.  Wenn die Reservierung erfolgreich erstellt wurde, wird die folgende Meldung angezeigt. **URL-Reservierung wurde erfolgreich hinzugefügt**.
