---
title: "Vorgehensweise: Ersetzen der WCF URL-Reservierung durch eine eingeschr&#228;nkte Reservierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Vorgehensweise: Ersetzen der WCF URL-Reservierung durch eine eingeschr&#228;nkte Reservierung
Mithilfe einer URL\-Reservierung können Sie einschränken, wer Nachrichten von einer URL oder einem Satz von URLs empfangen darf.Eine Reservierung besteht aus einer URL\-Vorlage, einer Zugriffssteuerungsliste \(ACL\) und einer Gruppe von Flags.Die URL\-Vorlage definiert, auf welche URLs sich die Reservierung auswirkt.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] über die Verarbeitung von URL\-Vorlagen finden Sie unter [Routing eingehender Anfragen](http://go.microsoft.com/fwlink/?LinkId=136764).Die ACL steuert, welche Benutzer oder Benutzergruppen Nachrichten von den angegebenen URLs empfangen dürfen.Die Flags geben an, ob die Reservierung einem Benutzer oder einer Benutzergruppe die Berechtigung erteilt, die URL direkt zu überwachen oder die Überwachungsberechtigung an einen anderen Prozess zu übergeben.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] erstellt im Rahmen der Standardbetriebssystemkonfiguration eine Reservierung mit globalem Zugriff für Anschluss 80, sodass alle Benutzer Anwendungen auszuführen können, die eine duale HTTP\-Bindung für die Duplexkommunikation verwenden.Da die ACL bei dieser Reservierung allen Benutzern zur Verfügung steht, können Administratoren die Berechtigung, eine URL oder einen Satz von URLs zu überwachen, nicht explizit zulassen oder verweigern.In diesem Thema wird erläutert, wie Sie diese Reservierung löschen und mit einer eingeschränkten ACL neu erstellen.  
  
 Unter [!INCLUDE[wv](../../../../includes/wv-md.md)] oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)] können Sie alle HTTP\-URL\-Reservierungen von einer Eingabeaufforderung auf höherer Ebene aus anzeigen, indem Sie `netsh http show urlacl` eingeben.Das folgende Beispiel zeigt, was eine URL\-Reservierung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ungefähr aussehen sollte.  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 Die Reservierung besteht aus einer URL\-Vorlage, die verwendet wird, wenn eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendung eine duale HTTP\-Bindung für die Duplexkommunikation nutzt.Derartige URLs werden verwendet, damit ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst bei der Kommunikation über eine duale HTTP\-Bindung Nachrichten an den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Client zurücksenden kann.Allen Benutzern wird die Berechtigung erteilt, die URL zu überwachen, sie sind jedoch nicht berechtigt, die Überwachung an einen anderen Prozess zu delegieren.Die ACL wird in Security Descriptor Definition Language \(SSDL\) beschrieben.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] über SSDL finden Sie unter [SSDL](http://go.microsoft.com/fwlink/?LinkId=136789)  
  
### So löschen Sie die WCF URL\-Reservierung  
  
1.  Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie im eingeblendeten Kontextmenü **Als Administrator ausführen** aus.Klicken Sie im Fenster "Benutzerkontensteuerung", in dem ggf. Berechtigungen für die Fortsetzung des Vorgangs angefordert werden, auf **Weiter**.  
  
2.  Geben Sie **netsh http delete urlacl url\=http:\/\/\+:80\/Temporary\_Listen\_Addresses\/** im Eingabeaufforderungsfenster ein.  
  
3.  Wenn die Reservierung erfolgreich gelöscht wurde, wird die folgende Meldung angezeigt.**URL reservation successfully deleted**  
  
## Erstellen einer neuen Sicherheitsgruppe und einer neuer eingeschränkten URL\-Reservierung  
 Um die URL\-Reservierung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] durch eine eingeschränkte Reservierung zu ersetzen, müssen Sie zunächst eine neue Sicherheitsgruppe erstellen.Hierzu stehen zwei Methoden zur Auswahl: Verwenden Sie entweder eine Eingabeaufforderung oder die Computerverwaltungskonsole.Sie müssen nur eine Methode ausführen.  
  
#### So erstellen Sie eine neue Sicherheitsgruppe an einer Eingabeaufforderung  
  
1.  Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie im eingeblendeten Kontextmenü **Als Administrator ausführen** aus.Klicken Sie im Fenster "Benutzerkontensteuerung", in dem ggf. Berechtigungen für die Fortsetzung des Vorgangs angefordert werden, auf **Weiter**.  
  
2.  Geben Sie **net localgroup "\<security group name\>" \/comment:"\<security group description\>" \/add** an der Eingabeaufforderung ein.Ersetzen Sie dabei **\<security group name\>** durch den Namen der zu erstellenden Sicherheitsgruppe und **\<security group description\>** durch eine geeignete Beschreibung für die Sicherheitsgruppe.  
  
3.  Wenn die Sicherheitsgruppe erfolgreich erstellt wurde, wird die folgende Meldung angezeigt.**The command completed successfully.**  
  
#### So erstellen Sie eine neue Sicherheitsgruppe an der Computerverwaltungskonsole  
  
1.  Klicken Sie auf **Start**, **Systemsteuerung**, **Verwaltung** und **Computerverwaltung**, um die Computerverwaltungskonsole zu öffnen.Klicken Sie im Fenster "Benutzerkontensteuerung", in dem ggf. Berechtigungen für die Fortsetzung des Vorgangs angefordert werden, auf **Weiter**.  
  
2.  Klicken Sie auf **System** und auf **Lokale Benutzer und Gruppen**, klicken Sie dann mit der rechten Maustaste auf den Ordner **Gruppen**, und wählen Sie in dem eingeblendeten Kontextmenü **Neue Gruppe** aus.Geben Sie in die Felder **Gruppenname** und **Beschreibung** die gewünschten Werte sowie weitere Details zu dieser neuen Sicherheitsgruppe ein, und klicken Sie auf die Schaltfläche **Erstellen**, um die Sicherheitsgruppe zu erstellen.  
  
#### So erstellen Sie die eingeschränkte URL\-Reservierung  
  
1.  Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie im eingeblendeten Kontextmenü **Als Administrator ausführen** aus.Klicken Sie im Fenster "Benutzerkontensteuerung", in dem ggf. Berechtigungen für die Fortsetzung des Vorgangs angefordert werden, auf **Weiter**.  
  
2.  Geben Sie **netsh http add urlacl url\=http:\/\/\+:80\/Temporary\_Listen\_Addresses\/ user\="\<machine name\>\\\<security group name\>** an der Eingabeaufforderung ein.Ersetzen Sie **\<machine name\>** durch den Namen des Computers, auf dem die Gruppe erstellt werden soll, und **\<security group name\>** durch den Namen der zuvor erstellten Sicherheitsgruppe.  
  
3.  Wenn die Reservierung erfolgreich erstellt wurde, wird die folgende Meldung angezeigt.**URL reservation successfully added**.