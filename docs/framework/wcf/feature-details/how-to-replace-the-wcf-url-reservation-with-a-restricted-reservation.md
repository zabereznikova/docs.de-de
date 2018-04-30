---
title: 'Vorgehensweise: Ersetzen der WCF URL-Reservierung durch eine eingeschränkte Reservierung'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1f17a5c21888a9fc778d9649f62478d43ba0e86
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a>Vorgehensweise: Ersetzen der WCF URL-Reservierung durch eine eingeschränkte Reservierung
Mithilfe einer URL-Reservierung können Sie einschränken, wer Nachrichten von einer URL oder einem Satz von URLs empfangen darf. Eine Reservierung besteht aus einer URL-Vorlage, einer Zugriffssteuerungsliste (ACL) und einer Gruppe von Flags. Die URL-Vorlage definiert, auf welche URLs sich die Reservierung auswirkt. Weitere Informationen zur Verarbeitung von URL-Vorlagen finden Sie unter [Routing eingehender Anfragen](http://go.microsoft.com/fwlink/?LinkId=136764). Die ACL steuert, welche Benutzer oder Benutzergruppen Nachrichten von den angegebenen URLs empfangen dürfen. Die Flags geben an, ob die Reservierung einem Benutzer oder einer Benutzergruppe die Berechtigung erteilt, die URL direkt zu überwachen oder die Überwachungsberechtigung an einen anderen Prozess zu übergeben.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] erstellt im Rahmen der Standardbetriebssystemkonfiguration eine Reservierung mit globalem Zugriff für Anschluss 80, sodass alle Benutzer Anwendungen auszuführen können, die eine duale HTTP-Bindung für die Duplexkommunikation verwenden. Da die ACL bei dieser Reservierung allen Benutzern zur Verfügung steht, können Administratoren die Berechtigung, eine URL oder einen Satz von URLs zu überwachen, nicht explizit zulassen oder verweigern. In diesem Thema wird erläutert, wie Sie diese Reservierung löschen und mit einer eingeschränkten ACL neu erstellen.  
  
 Unter [!INCLUDE[wv](../../../../includes/wv-md.md)] oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)] können Sie alle HTTP-URL-Reservierungen von einer Eingabeaufforderung auf höherer Ebene aus anzeigen, indem Sie `netsh http show urlacl` eingeben.  Das folgende Beispiel zeigt, was eine URL-Reservierung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ungefähr aussehen sollte.  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 Die Reservierung besteht aus einer URL-Vorlage, die verwendet wird, wenn eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendung eine duale HTTP-Bindung für die Duplexkommunikation nutzt. Derartige URLs werden verwendet, damit ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst bei der Kommunikation über eine duale HTTP-Bindung Nachrichten an den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client zurücksenden kann. Allen Benutzern wird die Berechtigung erteilt, die URL zu überwachen, sie sind jedoch nicht berechtigt, die Überwachung an einen anderen Prozess zu delegieren. Die ACL wird in Security Descriptor Definition Language (SSDL) beschrieben. Weitere Informationen zu SSDL, finden Sie unter [SSDL](http://go.microsoft.com/fwlink/?LinkId=136789)  
  
### <a name="to-delete-the-wcf-url-reservation"></a>So löschen Sie die WCF URL-Reservierung  
  
1.  Klicken Sie auf **starten**, zeigen Sie auf **Programme**, klicken Sie auf **Zubehör**, mit der rechten Maustaste **Eingabeaufforderung** , und klicken Sie auf **Ausführen als Administrator** im Kontextmenü wird angezeigt. Klicken Sie auf **Fortfahren** auf Berechtigungen, um den Vorgang fortzusetzen, bitten möglicherweise Zeitfenster für die Benutzerkontensteuerung (UAC).  
  
2.  Geben Sie in **Netsh HTTP-delete Urlacl Url =http://+:80/Temporary_Listen_Addresses/**  in das Eingabeaufforderungsfenster.  
  
3.  Wenn die Reservierung erfolgreich gelöscht wurde, wird die folgende Meldung angezeigt. **URL-Reservierung wurde erfolgreich gelöscht.**  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a>Erstellen einer neuen Sicherheitsgruppe und einer neuer eingeschränkten URL-Reservierung  
 Um die URL-Reservierung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] durch eine eingeschränkte Reservierung zu ersetzen, müssen Sie zunächst eine neue Sicherheitsgruppe erstellen. Hierzu stehen zwei Methoden zur Auswahl: Verwenden Sie entweder eine Eingabeaufforderung oder die Computerverwaltungskonsole. Sie müssen nur eine Methode ausführen.  
  
#### <a name="to-create-a-new-security-group-from-a-command-prompt"></a>So erstellen Sie eine neue Sicherheitsgruppe an einer Eingabeaufforderung  
  
1.  Klicken Sie auf **starten**, zeigen Sie auf **Programme**, klicken Sie auf **Zubehör**, mit der rechten Maustaste **Eingabeaufforderung** , und klicken Sie auf **Ausführen als Administrator** im Kontextmenü wird angezeigt. Klicken Sie auf **Fortfahren** auf Berechtigungen, um den Vorgang fortzusetzen, bitten möglicherweise Zeitfenster für die Benutzerkontensteuerung (UAC).  
  
2.  Geben Sie in **net Localgroup "\<Security Group Name >" / Kommentar: "\<sicherheitsgruppenbeschreibung >" / add** an der Eingabeaufforderung. Ersetzen von  **\<Sicherheitsgruppenname >** mit dem Namen der zu erstellenden Sicherheitsgruppe und  **\<sicherheitsgruppenbeschreibung >** durch eine geeignete Beschreibung für die Sicherheitsgruppe "-".  
  
3.  Wenn die Sicherheitsgruppe erfolgreich erstellt wurde, wird die folgende Meldung angezeigt. **Der Befehl wurde erfolgreich abgeschlossen.**  
  
#### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a>So erstellen Sie eine neue Sicherheitsgruppe an der Computerverwaltungskonsole  
  
1.  Klicken Sie auf **starten**, klicken Sie auf **Systemsteuerung**, klicken Sie auf **Verwaltung**, und klicken Sie auf **Computerverwaltung** auf dem Computer zu öffnen -Verwaltungskonsole. Klicken Sie auf **Fortfahren** auf Berechtigungen, um den Vorgang fortzusetzen, bitten möglicherweise Zeitfenster für die Benutzerkontensteuerung (UAC).  
  
2.  Klicken Sie auf **Systemprogramme**, klicken Sie auf **lokale Benutzer und Gruppen**, mit der rechten Maustaste **Gruppen** Ordner, und klicken Sie auf **neue Gruppe** in dem eingeblendeten Kontextmenü, hochgefahren. Geben Sie den gewünschten **Gruppenname**, **Beschreibung** und weitere Details zu dieser neuen Sicherheitsgruppe hinzu und klicken Sie auf die **erstellen** Schaltfläche, um die Sicherheitsgruppe zu erstellen.  
  
#### <a name="to-create-the-restricted-url-reservation"></a>So erstellen Sie die eingeschränkte URL-Reservierung  
  
1.  Klicken Sie auf **starten**, zeigen Sie auf **Programme**, klicken Sie auf **Zubehör**, mit der rechten Maustaste **Eingabeaufforderung** , und klicken Sie auf **Ausführen als Administrator** im Kontextmenü wird angezeigt. Klicken Sie auf **Fortfahren** auf Berechtigungen, um den Vorgang fortzusetzen, bitten möglicherweise Zeitfenster für die Benutzerkontensteuerung (UAC).  
  
2.  Geben Sie in **Netsh http Urlacl Url hinzufügen =http://+:80/Temporary_Listen_Addresses/ Benutzer = "\<Computername >\\< Name der Sicherheitsgruppe\>**  an der Eingabeaufforderung. Ersetzen von  **\<Computername >** mit den Namen des Computers, auf dem die Gruppe erstellt werden muss, und  **\<Sicherheitsgruppenname >** mit dem Namen der Sicherheitsgruppe, die Sie erstellt haben zuvor.  
  
3.  Wenn die Reservierung erfolgreich erstellt wurde, wird die folgende Meldung angezeigt. **URL-Reservierung, die erfolgreich hinzugefügt**.
