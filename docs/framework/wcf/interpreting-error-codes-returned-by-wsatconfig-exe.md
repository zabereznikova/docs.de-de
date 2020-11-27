---
title: Interpretieren von Fehlercodes, die von wsatConfig.exe zurückgegeben werden
ms.date: 03/30/2017
ms.assetid: ab65f22b-0d69-4c21-9aaf-74acef0ca102
ms.openlocfilehash: c5f423f5054a3a80bc0c730444ca9e90c203e288
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262748"
---
# <a name="interpreting-error-codes-returned-by-wsatconfigexe"></a>Interpretieren von Fehlercodes, die von wsatConfig.exe zurückgegeben werden

In diesem Thema werden alle vom WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe) generierten Fehlercodes und die empfohlenen Maßnahmen aufgelistet.  
  
## <a name="list-of-error-codes"></a>Liste der Fehlercodes  
  
|Fehlercode|BESCHREIBUNG|Empfohlene Aktion|  
|----------------|-----------------|------------------------------------|  
|0|Vorgang erfolgreich|Keine|  
|1|Unerwarteter Fehler|Microsoft kontaktieren|  
|2|Ein unerwarteter Fehler ist aufgetreten, als versucht wurde, Sicherheitseinstellungen von MSDTC abzurufen.|Stellen Sie sicher, dass der MSDTC-Dienst nicht deaktiviert ist, und beheben Sie alle Probleme, die in der zurückgegebenen Ausnahmemeldung aufgelistet sind.|  
|3|Das Konto, unter dem WsatConfig.exe ausgeführt wurde, hat keine ausreichenden Berechtigungen zum Lesen der Netzwerksicherheitseinstellungen.|Führen Sie WsatConfig.exe über ein Administratorbenutzerkonto aus.|  
|4|Aktivieren Sie den "DTC-Netzwerkzugriff" für MSDTC, bevor Sie versuchen, die WS-AT-Unterstützung zu aktivieren.|Aktivieren Sie den "DTC-Netzwerkzugriff" für MSDTC, und führen Sie das Hilfsprogramm erneut aus.|  
|5|Der eingegebene Anschluss lag außerhalb des Bereichs. Der Wert muss im Bereich zwischen 1 und 65535 liegen.|Korrigieren Sie die `-port:<portNum>`-<br /><br /> Befehlszeilenoption wie in der Fehlermeldung angegeben.|  
|6|Ein ungültiges Endpunktzertifikat wurde in der Befehlszeile angegeben.  Das Zertifikat konnte nicht gefunden werden, oder es hat die Überprüfung nicht bestanden.|Korrigieren Sie die `-endpointCert`-Befehlszeilenoption. Stellen Sie sicher, dass das Zertifikat einen privaten Schlüssel aufweist, für die Clientauthentifizierung und Serverauthentifizierung verwendet werden kann, im Zertifikatspeicher LocalMachine\MY installiert ist und vollständig vertrauenswürdig ist.|  
|7|Ein ungültiges Kontozertifikat wurde in der Befehlszeile angegeben.|Korrigieren Sie die `-accountsCerts`-Befehlszeilenoption. Das Zertifikat wurde entweder nicht korrekt angegeben oder wurde nicht gefunden.|  
|8|Ein Standardtimeout wurde außerhalb des Bereichs von 1 bis 3600 Sekunden angegeben.|Geben Sie einen zulässigen Standardtimeoutwert ein.|  
|10|Ein unerwarteter Fehler ist aufgetreten, während versucht wurde, auf die Registrierung zuzugreifen.|Überprüfen Sie die Fehlermeldung und den Fehlercode auf Elemente, die Aktionen erfordern.|  
|11|Schreiben in die Registrierung nicht möglich.|Stellen Sie sicher, dass der in der Fehlermeldung aufgeführte Schlüssel den Registrierungszugriff von dem Konto unterstützt, unter dem WsatConfig.exe ausgeführt wurde.|  
|12|Ein unerwarteter Fehler ist aufgetreten, während versucht wurde, auf den Zertifikatspeicher zuzugreifen.|Verwenden Sie den zurückgegebenen Fehlercode zum Zuweisen des entsprechenden Systemfehlers.|  
|13|Die Konfiguration von http.sys ist fehlgeschlagen. Es kann keine neue HTTPS-Anschlussreservierung für MSDTC erstellt werden.|Verwenden Sie den zurückgegebenen Fehlercode zum Zuweisen des entsprechenden Systemfehlers.|  
|14|Die Konfiguration von http.sys ist fehlgeschlagen. Die vorherige HTTPS-Anschlussreservierung für MSDTC kann nicht entfernt werden.|Verwenden Sie den zurückgegebenen Fehlercode zum Zuweisen des entsprechenden Systemfehlers.|  
|15|Die Konfiguration von http.sys ist fehlgeschlagen. Eine vorherige HTTPS-Anschlussreservierung ist bereits für den angegebenen Anschluss vorhanden.|Eine andere Anwendung ist bereits im Besitz des bestimmten Anschlusses. Ändern Sie den Anschluss, deinstallieren Sie die aktuelle Anwendung, oder konfigurieren Sie sie neu.|  
|16|Die Konfiguration von http.sys ist fehlgeschlagen. Das Zertifikat kann nicht an den Anschluss gebunden werden.|Verwenden Sie den zurückgegebenen Fehlercode in der Fehlermeldung zum Zuweisen des entsprechenden Systemfehlers.|  
|17|Die Konfiguration von http.sys ist fehlgeschlagen. Die Bindung des SSL-Zertifikats an den vorherigen Anschluss kann nicht aufgehoben werden.|Verwenden Sie den zurückgegebenen Fehlercode in der Fehlermeldung zum Zuweisen des entsprechenden Systemfehlers. Falls notwendig können Sie httpcfg.exe oder netsh.exe verwenden, um die falschen Anschlussreservierungen zu entfernen.|  
|18|Die Konfiguration von http.sys ist fehlgeschlagen. Das angegebene Zertifikat kann nicht an den Anschluss gebunden werden, da eine vorherige SSL-Bindung bereits vorhanden ist.|Eine andere Anwendung ist bereits im Besitz des bestimmten Anschlusses. Ändern Sie den Anschluss, deinstallieren Sie die aktuelle Anwendung, oder konfigurieren Sie sie neu.|  
|19|Das Neustarten von MSDTC ist fehlgeschlagen.|Starten Sie MSDTC manuell neu, falls notwendig. Wenden Sie sich an Microsoft, wenn das Problem weiterhin auftritt.|  
|20|WinFX ist nicht auf dem Remote Computer installiert oder nicht ordnungsgemäß installiert.|Installieren Sie WinFX auf dem Computer.|  
|21|Die Remotekonfiguration ist aufgrund eines Vorgangstimeouts fehlgeschlagen.|Der Aufruf zur Konfiguration von WS-AT auf dem Remotecomputer sollte nicht länger als 90 Sekunden dauern.|  
|22|WinFX ist nicht auf dem Remote Computer installiert oder nicht ordnungsgemäß installiert.|Installieren Sie WinFX auf dem Computer.|  
|23|Die Remotekonfiguration ist aufgrund einer Ausnahme auf dem Remotecomputer fehlgeschlagen.|Überprüfen Sie die Fehlermeldung auf Elemente, die Aktionen erfordern.|  
|26|Ein ungültiges Argument wurde an WsatConfig.exe übergeben.|Überprüfen Sie die Befehlszeile auf Fehler.|  
|27|Die `-accounts`-Befehlszeilenoption war ungültig.|Korrigieren Sie die `accounts`-Befehlszeilenoption, um ein Benutzerkonto ordnungsgemäß anzugeben.|  
|28|Die `-network`-Befehlszeilenoption war ungültig.|Korrigieren Sie die `-network`-Befehlszeilenoption, um "enable" oder "disable" ordnungsgemäß anzugeben.|  
|29|Die `-maxTimeout`-Befehlszeilenoption war ungültig.|Korrigieren Sie die `-maxTimeout`-Befehlszeilenoption wie angegeben.|  
|30|Die `-timeout`-Befehlszeilenoption war ungültig.|Korrigieren Sie die `-timeout`-Befehlszeilenoption wie angegeben.|  
|31|Die `-traceLevel`-Befehlszeilenoption war ungültig.|Korrigieren Sie die `-traceLevel`-Befehlszeilenoption, um einen der folgenden gültigen Werte anzugeben:<br /><br /> -Aus<br />– Fehler<br />- Kritisch<br />– Warnung<br />-Informationen<br />-Verbose<br />-Alle|  
|32|Die `-traceActivity`-Befehlszeilenoption war ungültig.|Korrigieren Sie die `-traceActivity`-Befehlszeilenoption, um "enable" oder "disable" anzugeben.|  
|33|Die `-traceProp`-Befehlszeilenoption war ungültig.|Korrigieren Sie die `-traceProp`-Befehlszeilenoption, um "enable" oder "disable" anzugeben.|  
|34|Die `-tracePII`-Befehlszeilenoption war ungültig.|Korrigieren Sie die `-tracePII`-Befehlszeilenoption, um "enable" oder "disable" anzugeben.|  
|37|WsatConfig.exe konnte nicht das exakte Computerzertifikat ermitteln. Dies kann auftreten, wenn es mehr als einen oder keinen Kandidaten gibt.|Geben Sie einen Zertifikatfingerabdruck oder ein Issuer\SubjectName-Paar an, um das zu konfigurierende Zertifikat ordnungsgemäß zu identifizieren.|  
|38|Der Prozess oder der Benutzer hat keine ausreichenden Berechtigungen, die Firewallkonfiguration zu ändern.|Führen Sie WsatConfig.exe über ein Administratorbenutzerkonto aus.|  
|39|In WsatConfig.exe ist ein Fehler während der Aktualisierung der Firewallkonfiguration aufgetreten.|Überprüfen Sie die Fehlermeldung auf Elemente, die Aktionen erfordern.|  
|40|WsatConfig.exe kann MSDTC keinen Lesezugriff auf die Privatschlüsseldatei des Zertifikats bieten.|Führen Sie WsatConfig.exe über ein Administratorbenutzerkonto aus.|  
|41|Entweder konnte keine WinFX-Installation gefunden werden, oder die gefundene Version entspricht nicht den Anforderungen, die das Tool konfigurieren kann.|Stellen Sie sicher, dass WinFX ordnungsgemäß installiert ist, und verwenden Sie nur das WsatConfig.exe Tool, das in dieser Version von WinFX zur Konfiguration von WS-AT kam.|  
|42|Ein Argument wurde mehr als einmal in der Befehlszeile angegeben.|Geben Sie jedes Argument nur einmal an, wenn Sie WsatConfig.exe ausführen.|  
|43|WsatConfig.exe kann keine WS-AT-Einstellungen aktualisieren, wenn WS-AT nicht aktiviert ist.|Geben Sie `-network:enable` als zusätzliches Befehlszeilenargument an.|  
|44|Ein erforderlicher Hotfix fehlt, und WS-AT kann erst konfiguriert werden, wenn der Hotfix installiert ist.|Anweisungen zum Installieren des erforderlichen Hotfixes finden Sie in den Anmerkungen zu dieser Version von WinFX.|  
|45|Die `-virtualServer`-Befehlszeilenoption war ungültig.|Korrigieren Sie die `-virtualServer`-Befehlszeilenoption durch Angabe des Netzwerknamens der Clusterressource, in der die Konfiguration vorgenommen werden soll.|  
|46|Ein unerwarteter Fehler ist aufgetreten, als versucht wurde, die ETW-Ablaufverfolgungssitzung zu starten.|Verwenden Sie den zurückgegebenen Fehlercode zum Zuweisen des entsprechenden Systemfehlers.|  
|47|Der Prozess oder der Benutzer hat keine ausreichenden Berechtigungen zum Aktivieren der ETW-Ablaufverfolgungssitzung.|Führen Sie WsatConfig.exe über ein Administratorbenutzerkonto aus.|  
|48|Ein unerwarteter Fehler ist aufgetreten, als versucht wurde, die ETW-Ablaufverfolgungssitzung zu starten.|Wenden Sie sich an Microsoft.|  
|49|Es kann keine neue Protokolldatei auf %systemdrive% aufgrund ungenügenden Speicherplatzes erstellt werden.|Stellen Sie sicher, dass das %systemdrive% ausreichenden Platz für die Protokolldatei aufweist.|  
|51|Ein unerwarteter Fehler ist aufgetreten, als versucht wurde, die ETW-Ablaufverfolgungssitzung zu starten.|Wenden Sie sich an Microsoft.|  
|52|Ein unerwarteter Fehler ist aufgetreten, als versucht wurde, die ETW-Ablaufverfolgungssitzung zu starten.|Wenden Sie sich an Microsoft.|  
|53|Die Sicherung der vorherigen ETW-Sitzungsprotokolldatei ist fehlgeschlagen.|Stellen Sie sicher, dass %systemdrive% über ausreichenden Speicherplatz für die Protokolldatei und die Sicherung der vorherigen Protokolldatei (sofern vorhanden) verfügt. Entfernen Sie die vorherige Protokolldatei manuell, falls notwendig.|  
|55|Ein unerwarteter Fehler ist aufgetreten, als versucht wurde, die ETW-Ablaufverfolgungssitzung zu starten.|Wenden Sie sich an Microsoft.|  
|56|Ein unerwarteter Fehler ist aufgetreten, als versucht wurde, die ETW-Ablaufverfolgungssitzung zu starten.|Wenden Sie sich an Microsoft.|  
  
## <a name="see-also"></a>Weitere Informationen

- [WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe)](ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
