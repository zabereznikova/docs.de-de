---
title: "Konfigurieren von HTTP und HTTPS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Konfigurieren von HTTP [WCF]"
ms.assetid: b0c29a86-bc0c-41b3-bc1e-4eb5bb5714d4
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Konfigurieren von HTTP und HTTPS
WCF\-Dienste und \-Clients können über HTTP und HTTPS kommunizieren.  Die HTTP\/HTTPS\-Einstellungen werden mit Internetinformationsdienste \(IIS\) oder mit einem Befehlszeilentool konfiguriert.  Wenn ein WCF\-Dienst unter IIS gehostet wird, können die HTTP\- oder HTTPS\-Einstellungen in IIS konfiguriert werden \(mit dem Tool "inetmgr.exe"\).  Bei einem selbst gehosteten WCF\-Dienst werden die HTTP\- oder HTTPS\-Einstellungen mit einem Befehlszeilentool konfiguriert.  
  
 Sie konfigurieren mindestens eine URL\-Registrierung und fügen eine Firewallausnahme für die vom Dienst verwendete URL hinzu.  
  
 Welches Tool zum Konfigurieren der HTTP\-Einstellungen verwendet wird, hängt vom Betriebssystem des Computers ab.  
  
 Verwenden Sie unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)] das Tool "HttpCfg.exe".  Dieses Tool wird von [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] automatisch installiert.  Bei Verwendung von [!INCLUDE[wxp](../../../../includes/wxp-md.md)] können Sie das Tool unter [Windows XP Service Pack 2\-Supporttools](http://go.microsoft.com/fwlink/?LinkId=88606) herunterladen.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Httpcfg\-Übersicht](http://go.microsoft.com/fwlink/?LinkId=88605).  
  
 Unter [!INCLUDE[wv](../../../../includes/wv-md.md)] oder Windows 7 werden diese Einstellungen mithilfe des Tools "Netsh.exe" konfiguriert.  
  
## Konfigurieren von Namespacereservierungen  
 Eine Namespacereservierung weist die Rechte für einen Teil des HTTP\-URL\-Namespace einer bestimmten Gruppe von Benutzern zu.  Eine Reservierung gibt diesen Benutzern das Recht, Dienste zu erstellen, die bei diesem Teil des Namespaces lauschen.  Reservierungen sind URL\-Präfixe, was bedeutet, dass die Reservierung dem Reservierungspfad untergeordnete Pfade abdeckt.  Namespacereservierungen eröffnen zwei Möglichkeiten, Platzhalter zu verwenden.  In der HTTP\-Server\-API\-Dokumentation findet sich eine Beschreibung der [Auflösungsreihenfolge von Namespaceansprüchen, die Platzhalter verwenden](http://go.microsoft.com/fwlink/?LinkId=94841).  
  
 Eine laufende Anwendung kann eine ähnliche Anforderung stellen, um Namespaceregistrierungen hinzuzufügen.  Registrierungen und Reservierungen konkurrieren um Teile des Namespaces.  Eine Reservierung kann entsprechend der Auflösungsreihenfolge Vorrang vor einer Registrierung haben. Weitere Informationen hierzu finden Sie unter [Auflösungsreihenfolge von Namespaceansprüchen, die Platzhalter verwenden](http://go.microsoft.com/fwlink/?LinkId=94841).  In diesem Fall blockiert die Reservierung in der laufenden Anwendung den Empfang von Anforderungen.  
  
### Unter Windows&\#160;XP oder Windows Server&\#160;2003  
 Verwenden Sie den Befehl `httpcfg.exe set urlacl`, um Namespacereservierungen zu ändern.  Die Syntax des Tools "Httpcfg.exe" wird in der [Dokumentation der Windows\-Supporttools](http://go.microsoft.com/fwlink/?LinkId=94840) erläutert.  Zur Änderung der Reservierungsrechte für einen Teil des Namespaces sind entweder Administratorrechte oder der Besitz dieses Teils des Namespaces erforderlich.  Anfänglich gehört der gesamte HTTP\-Namespace dem lokalen Administrator.  
  
 Hier die Syntax des Befehls Httpcfg mit der `set urlacl`\-Option  
  
```  
httpcfg set urlacl /u {http://URL:Port/ | https://URL:Port/} /aACL  
  
```  
  
 Der `/u`\-Parameter ist für die Verwendung von `set urlacl` erforderlich.  Der Parameter akzeptiert eine Zeichenfolge, die eine vollqualifizierte URL enthält, der als Datensatzschlüssel für die vorzunehmende Reservierung dient.  
  
 Der `/a`\-Parameter ist auch für die Verwendung von `set urlacl` erforderlich.  Der Parameter akzeptiert eine Zeichenfolge, die eine Zugriffssteuerungsliste in Form einer SDDL\-Zeichenfolge \(Security Descriptor Definition Language\) enthält.  
  
 Das folgende Beispiel zeigt, wie dieser Befehl verwendet wird.  
  
```  
httpcfg.exe set urlacl /u http://myhost:8000/ /a "O:AOG:DAD:(A;;RPWPCCDCLCSWRCWDWOGA;;;S-1-0-0)"  
  
```  
  
### Unter Windows Vista, Windows Server 2008 R2 oder Windows 7  
 Verwenden Sie bei der Ausführung unter [!INCLUDE[wv](../../../../includes/wv-md.md)], Windows Server 2008 R2 oder Windows 7 das Tool "Netsh.exe".  Das folgende Beispiel zeigt, wie dieser Befehl verwendet wird.  
  
```  
netsh http add urlacl url=http://+:80/MyUri user=DOMAIN\user  
  
```  
  
 Durch diesen Befehl wird eine URL\-Reservierung für den angegebenen URL\-Namespace für das Konto "DOMAIN\\user" hinzugefügt.  Wenn Sie weitere Informationen zur Verwendung des netsh\-Befehls wünschen, geben Sie in einer Eingabeaufforderung "netsh http add urlacl" ein, und drücken Sie die EINGABETASTE.  
  
## Konfigurieren einer Firewallausnahme  
 Beim Selbsthosting eines WCF\-Diensts, der über HTTP kommuniziert, muss der Firewallkonfiguration eine Ausnahme hinzugefügt werden, die eingehende Verbindungen über eine bestimmte URL zulässt.  Weitere Informationen finden Sie unter [Öffnen eines Ports in der Windows\-Firewall \(Windows 7\)](http://go.microsoft.com/fwlink/?LinkId=239961)  
  
## Konfigurieren eines SSL\-Zertifikats  
 Das Secure Sockets Layer \(SSL\)\-Protokoll verwendet Zertifikate auf Client und Server, um Verschlüsselungsschlüssel zu speichern.  Der Server muss ein SSL\-Zertifikat bereitstellen, wenn eine Verbindung hergestellt wird, damit der Client die Identität des Servers überprüfen kann.  Der Server kann ebenfalls ein Zertifikat vom Client anfordern, so dass eine wechselseitige Authentifizierung auf beiden Seiten der Verbindung möglich wird.  
  
 Zertifikate sind in einem zentralen Speicher entsprechend der IP\-Adresse und der Anschlussnummer der Verbindung gespeichert.  Die spezielle IP\-Adresse 0.0.0.0 stimmt mit jeder IP\-Adresse für den lokalen Computer überein.  Beachten Sie, dass der Zertifikatspeicher URLs nicht anhand der Pfade unterscheidet.  Dienste mit der gleichen Kombination von IP\-Adresse und Anschlussnummer müssen die gleichen Zertifikate verwenden, auch wenn sich der Pfad in der URL dieser Dienste unterscheidet.  
  
 Schritt\-für\-Schritt\-Anleitungen finden Sie unter [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL\-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
## Konfigurieren der IP\-Lauschliste  
 Die HTTP\-Server\-API stellt erst dann eine Bindung mit einer IP\-Adresse und einem Port her, wenn ein Benutzer eine URL registriert.  Standardmäßig verbindet die HTTP\-Server\-API mit dem Anschluss in der URL für alle IP\-Adressen des Computers.  Ein Konflikt tritt auf, wenn eine Anwendung, die die HTTP\-Server\-API nicht verwendet, sich vorher mit dieser Kombination von IP\-Adresse und \-Anschluss verbunden hat.  Die IP\-Lauschliste ermöglicht [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensten, mit Anwendungen zu koexistieren, die einen Anschluss für einige der IP\-Adressen des Computers verwenden.  Enthält die IP\-Lauschliste irgendwelche Einträge, verbindet die HTTP\-Server\-API nur mit den IP\-Adressen, die in der Liste angegeben sind.  Die Änderung der IP\-Lauschliste erfordert Administratorrechte.  
  
### Unter Windows&\#160;XP oder Windows Server&\#160;2003  
 Verwenden Sie das httpcfg\-Tool, um die IP\-Lauschliste zu ändern, wie im folgenden Beispiel gezeigt.  Die Syntax des Tools "Httpcfg.exe" wird in der [Dokumentation der Windows\-Supporttools](http://go.microsoft.com/fwlink/?LinkId=94840) erläutert.  
  
```  
httpcfg.exe set iplisten -i 0.0.0.0:8000  
```  
  
### Unter Windows Vista oder Windows 7  
 Verwenden Sie das netsh\-Tool wie im folgenden Beispiel gezeigt, um die IP\-Lauschliste zu ändern:  
  
```  
netsh http add iplisten ipaddress=0.0.0.0:8000  
```  
  
## Andere Konfigurationseinstellungen  
 Bei Verwendung der <xref:System.ServiceModel.WsDualHttpBinding> verwendet die Clientverbindung Standardwerte, die mit Namespacereservierungen und der Windows\-Firewall kompatibel sind.  Wenn Sie sich dafür entscheiden, die Clientbasisadresse einer dualen Verbindung anzupassen, müssen Sie diese HTTP\-Einstellungen auch auf dem Client mit der neuen Adresse konfigurieren.  
  
 Die HTTP\-Server\-API bietet einige erweiterte Konfigurationseinstellungen, die über HttpCfg nicht verfügbar sind.  Diese Einstellungen sind in der Registrierung gespeichert und gelten für alle Anwendungen, die auf Systemen laufen, die HTTP\-Server\-APIs verwenden.  Informationen zu diesen Einstellungen finden Sie unter [Http.sys\-Registrierungseinstellungen für IIS](http://go.microsoft.com/fwlink/?LinkId=94843).  Die meisten Benutzer sollten diese Einstellungen nicht ändern müssen.  
  
## Probleme bezüglich Windows XP  
 IIS unterstützt keine Anschlussfreigabe unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  Wird IIS ausgeführt, und ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst versucht, einen Namespace mit dem gleichen Anschluss zu verwenden, schlägt der Start des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts fehl.  Sowohl IIS als auch [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwenden standardmäßig Anschluss 80.  Ändern Sie entweder die Anschlusszuweisung für einen der Dienste, oder verwenden Sie die IP\-Abhörliste, um den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst einer Netzwerkkarte zuzuweisen, die nicht von IIS verwendet wird.  IIS&\#160;6.0 und höher wurde für die Verwendung der HTTP\-Server\-APIs neu konzipiert.  
  
## Siehe auch  
 <xref:System.ServiceModel.WsDualHttpBinding>   
 [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL\-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)