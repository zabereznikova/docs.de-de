---
title: Konfigurieren von HTTP und HTTPS
ms.date: 03/30/2017
helpviewer_keywords:
- configuring HTTP [WCF]
ms.assetid: b0c29a86-bc0c-41b3-bc1e-4eb5bb5714d4
ms.openlocfilehash: 36dbf725dfcd6fefe6482f7de69daea9356d3d07
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087698"
---
# <a name="configuring-http-and-https"></a>Konfigurieren von HTTP und HTTPS
WCF-Dienste und -Clients können über HTTP und HTTPS kommunizieren. Die HTTP/HTTPS-Einstellungen werden mit Internetinformationsdienste (IIS) oder mit einem Befehlszeilentool konfiguriert. Wenn ein WCF-Dienst unter IIS gehostet wird, können die HTTP- oder HTTPS-Einstellungen in IIS konfiguriert werden (mit dem Tool "inetmgr.exe"). Bei einem selbst gehosteten WCF-Dienst werden die HTTP- oder HTTPS-Einstellungen mit einem Befehlszeilentool konfiguriert.  
  
 Sie konfigurieren mindestens eine URL-Registrierung und fügen eine Firewallausnahme für die vom Dienst verwendete URL hinzu.  
  
 Welches Tool zum Konfigurieren der HTTP-Einstellungen verwendet wird, hängt vom Betriebssystem des Computers ab.  
  
 Bei der Ausführung [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)], verwenden Sie das HttpCfg.exe-Tool. Dieses Tool wird von [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] automatisch installiert. Bei der Ausführung [!INCLUDE[wxp](../../../../includes/wxp-md.md)], Sie können das Tool unter [Windows XP Service Pack 2-Supporttools](https://go.microsoft.com/fwlink/?LinkId=88606). Weitere Informationen finden Sie unter [Httpcfg-Übersicht](https://go.microsoft.com/fwlink/?LinkId=88605).  
  
 Bei der Ausführung [!INCLUDE[wv](../../../../includes/wv-md.md)] oder Windows 7, konfigurieren Sie diese Einstellungen, mit dem Netsh.exe-Tool.  
  
## <a name="configuring-namespace-reservations"></a>Konfigurieren von Namespacereservierungen  
 Eine Namespacereservierung weist die Rechte für einen Teil des HTTP-URL-Namespace einer bestimmten Gruppe von Benutzern zu. Eine Reservierung gibt diesen Benutzern das Recht, Dienste zu erstellen, die bei diesem Teil des Namespaces lauschen. Reservierungen sind URL-Präfixe, was bedeutet, dass die Reservierung dem Reservierungspfad untergeordnete Pfade abdeckt. Namespacereservierungen eröffnen zwei Möglichkeiten, Platzhalter zu verwenden. Die HTTP-Server-API-Dokumentation beschreibt die [Auflösungsreihenfolge von Namespace-Ansprüche, die Platzhalter verwenden](https://go.microsoft.com/fwlink/?LinkId=94841).  
  
 Eine laufende Anwendung kann eine ähnliche Anforderung stellen, um Namespaceregistrierungen hinzuzufügen. Registrierungen und Reservierungen konkurrieren um Teile des Namespaces. Eine Reservierung kann haben Vorrang vor einer Registrierung entsprechend der Auflösungsreihenfolge die [Auflösungsreihenfolge von Namespace-Ansprüche, die Platzhalter verwenden](https://go.microsoft.com/fwlink/?LinkId=94841). In diesem Fall blockiert die Reservierung in der laufenden Anwendung den Empfang von Anforderungen.  
  
### <a name="running-windows-xp-or-server-2003"></a>Unter Windows&#160;XP oder Windows Server&#160;2003  
 Verwenden der `httpcfg.exe set urlacl` Befehl aus, um Namespacereservierungen zu ändern. Die [Dokumentation der Windows-Supporttools](https://go.microsoft.com/fwlink/?LinkId=94840) erklärt die Syntax für das Httpcfg.exe-Tool. Zur Änderung der Reservierungsrechte für einen Teil des Namespaces sind entweder Administratorrechte oder der Besitz dieses Teils des Namespaces erforderlich. Anfänglich gehört der gesamte HTTP-Namespace dem lokalen Administrator.  
  
 Hier die Syntax des Befehls Httpcfg mit der `set urlacl`-Option  
  
```  
httpcfg set urlacl /u {http://URL:Port/ | https://URL:Port/} /aACL  
```  
  
 Der `/u`-Parameter ist für die Verwendung von `set urlacl` erforderlich. Der Parameter akzeptiert eine Zeichenfolge, die eine vollqualifizierte URL enthält, der als Datensatzschlüssel für die vorzunehmende Reservierung dient.  
  
 Der `/a`-Parameter ist auch für die Verwendung von `set urlacl` erforderlich. Der Parameter akzeptiert eine Zeichenfolge, die eine Zugriffssteuerungsliste in Form einer SDDL-Zeichenfolge (Security Descriptor Definition Language) enthält.  
  
 Das folgende Beispiel zeigt, wie dieser Befehl verwendet wird.  
  
```  
httpcfg.exe set urlacl /u http://myhost:8000/ /a "O:AOG:DAD:(A;;RPWPCCDCLCSWRCWDWOGA;;;S-1-0-0)"  
```  
  
### <a name="running-windows-vista-windows-server-2008-r2-or-windows-7"></a>Unter Windows Vista, Windows Server 2008 R2 oder Windows 7  
 Verwenden Sie bei der Ausführung unter [!INCLUDE[wv](../../../../includes/wv-md.md)], Windows Server 2008 R2 oder Windows 7 das Tool "Netsh.exe". Das folgende Beispiel zeigt, wie dieser Befehl verwendet wird.  
  
```  
netsh http add urlacl url=http://+:80/MyUri user=DOMAIN\user  
```  
  
 Durch diesen Befehl wird eine URL-Reservierung für den angegebenen URL-Namespace für das Konto "DOMAIN\user" hinzugefügt.  Weitere Informationen zur Verwendung des Typs des Netsh-Befehl "Netsh http add Urlacl" in eine Eingabeaufforderung, und drücken Sie eingeben.  
  
## <a name="configuring-a-firewall-exception"></a>Konfigurieren einer Firewallausnahme  
 Beim Selbsthosting eines WCF-Diensts, der über HTTP kommuniziert, muss der Firewallkonfiguration eine Ausnahme hinzugefügt werden, die eingehende Verbindungen über eine bestimmte URL zulässt. Weitere Informationen finden Sie unter [Öffnen eines Ports in der Windows-Firewall (Windows 7)](https://go.microsoft.com/fwlink/?LinkId=239961)  
  
## <a name="configuring-ssl-certificates"></a>Konfigurieren eines SSL-Zertifikats  
 Das Secure Sockets Layer (SSL)-Protokoll verwendet Zertifikate auf Client und Server, um Verschlüsselungsschlüssel zu speichern. Der Server muss ein SSL-Zertifikat bereitstellen, wenn eine Verbindung hergestellt wird, damit der Client die Identität des Servers überprüfen kann. Der Server kann ebenfalls ein Zertifikat vom Client anfordern, so dass eine wechselseitige Authentifizierung auf beiden Seiten der Verbindung möglich wird.  
  
 Zertifikate sind in einem zentralen Speicher entsprechend der IP-Adresse und der Anschlussnummer der Verbindung gespeichert. Die spezielle IP-Adresse 0.0.0.0 stimmt mit jeder IP-Adresse für den lokalen Computer überein. Beachten Sie, dass der Zertifikatspeicher URLs nicht anhand der Pfade unterscheidet. Dienste mit der gleichen Kombination von IP-Adresse und Anschlussnummer müssen die gleichen Zertifikate verwenden, auch wenn sich der Pfad in der URL dieser Dienste unterscheidet.  
  
 Schrittweise Anweisungen finden Sie unter [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
## <a name="configuring-the-ip-listen-list"></a>Konfigurieren der IP-Lauschliste  
 Die HTTP-Server-API stellt erst dann eine Bindung mit einer IP-Adresse und einem Port her, wenn ein Benutzer eine URL registriert. Standardmäßig verbindet die HTTP-Server-API mit dem Anschluss in der URL für alle IP-Adressen des Computers. Ein Konflikt tritt auf, wenn eine Anwendung, die die HTTP-Server-API nicht verwendet, sich vorher mit dieser Kombination von IP-Adresse und -Anschluss verbunden hat. Die IP-Lauschliste ermöglicht WCF-Dienste mit Anwendungen zu koexistieren, die einen Port für einige der IP-Adressen des Computers zu verwenden. Enthält die IP-Lauschliste irgendwelche Einträge, verbindet die HTTP-Server-API nur mit den IP-Adressen, die in der Liste angegeben sind. Die Änderung der IP-Lauschliste erfordert Administratorrechte.  
  
### <a name="running-windows-xp-or-server-2003"></a>Unter Windows&#160;XP oder Windows Server&#160;2003  
 Verwenden Sie das httpcfg-Tool, um die IP-Lauschliste zu ändern, wie im folgenden Beispiel gezeigt. Die [Dokumentation der Windows-Supporttools](https://go.microsoft.com/fwlink/?LinkId=94840) erklärt die Syntax für das httpcfg.exe-Tool.  
  
```  
httpcfg.exe set iplisten -i 0.0.0.0:8000  
```  
  
### <a name="running-windows-vista-or-windows-7"></a>Unter Windows Vista oder Windows 7  
 Verwenden Sie das netsh-Tool wie im folgenden Beispiel gezeigt, um die IP-Lauschliste zu ändern:  
  
```  
netsh http add iplisten ipaddress=0.0.0.0:8000  
```  
  
## <a name="other-configuration-settings"></a>Andere Konfigurationseinstellungen  
 Bei Verwendung der <xref:System.ServiceModel.WSDualHttpBinding> verwendet die Clientverbindung Standardwerte, die mit Namespacereservierungen und der Windows-Firewall kompatibel sind. Wenn Sie sich dafür entscheiden, die Clientbasisadresse einer dualen Verbindung anzupassen, müssen Sie diese HTTP-Einstellungen auch auf dem Client mit der neuen Adresse konfigurieren.  
  
 Die HTTP-Server-API bietet einige erweiterte Konfigurationseinstellungen, die über HttpCfg nicht verfügbar sind. Diese Einstellungen sind in der Registrierung gespeichert und gelten für alle Anwendungen, die auf Systemen laufen, die HTTP-Server-APIs verwenden. Weitere Informationen zu diesen Einstellungen finden Sie unter [Http.sys-registrierungseinstellungen für IIS](https://go.microsoft.com/fwlink/?LinkId=94843). Die meisten Benutzer sollten diese Einstellungen nicht ändern müssen.  
  
## <a name="issues-specific-to-windows-xp"></a>Probleme bezüglich Windows XP  
 IIS unterstützt keine Anschlussfreigabe unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)]. Wenn IIS ausgeführt wird, und ein WCF-Dienst versucht, einen Namespace mit dem gleichen Anschluss zu verwenden, kann der WCF-Dienst gestartet. IIS und WCF, die standardmäßig auf Port 80 verwenden. Ändern Sie die anschlusszuweisung für einen der Dienste oder verwenden Sie die IP-Lauschliste, um einen Netzwerkadapter, die nicht von IIS verwendet den WCF-Dienst zuweisen. IIS&#160;6.0 und höher wurde für die Verwendung der HTTP-Server-APIs neu konzipiert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.WSDualHttpBinding>  
 [Vorgehensweise: Konfigurieren eines Ports mit einem SSL-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
