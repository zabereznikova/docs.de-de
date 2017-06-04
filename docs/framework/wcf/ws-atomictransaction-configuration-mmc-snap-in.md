---
title: "WS-AtomicTransaction-Konfiguration-MMC-Snap-In | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 23592973-1d51-44cc-b887-bf8b0d801e9e
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# WS-AtomicTransaction-Konfiguration-MMC-Snap-In
Das MMC\-Snap\-In für die WS\-AtomicTransaction\-Konfiguration wird zur Konfiguration eines Teils der WS\-AtomicTransaction\-Einstellungen auf lokalen und Remotecomputern eingesetzt.  
  
## Hinweise  
 Wenn Sie [!INCLUDE[wxp](../../../includes/wxp-md.md)] oder [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] ausführen, können Sie auf das MMC\-Snap\-In zugreifen, indem Sie zu **Systemsteuerung\/Verwaltung\/Komponentendienste** navigieren, mit der rechten Maustaste auf **Arbeitsplatz** klicken und **Eigenschaften** auswählen.Dort können Sie auch den MSDTC konfigurieren.Für die Konfiguration verfügbare Optionen sind unter der Registerkarte **WS\-AT** gruppiert.  
  
 Wenn Sie Windows Vista oder [!INCLUDE[lserver](../../../includes/lserver-md.md)] ausführen, finden Sie das MMC\-Snap\-In, indem Sie auf **Start** klicken und `dcomcnfg.exe` in das Feld **Suchen** eingeben.Wenn die MMC geöffnet ist, navigieren Sie zum Knoten **Arbeitsplatz\\Distributed Transaction Coordinator\\Lokaler DTC**, klicken Sie mit der rechten Maustaste, und wählen Sie **Eigenschaften** aus.Für die Konfiguration verfügbare Optionen sind unter der Registerkarte **WS\-AT** gruppiert.  
  
 Die vorherigen Schritte werden verwendet, um das Snap\-In zur Konfiguration eines lokalen Computers zu starten.Wenn Sie einen Remotecomputer konfigurieren möchten, sollte der Name des Remotecomputers unter **Systemsteuerung\/Verwaltung\/Komponentendienste\/** zu finden sein. Führen Sie ähnliche Schritte aus, wenn Sie [!INCLUDE[wxp](../../../includes/wxp-md.md)] oder [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] ausführen.Wenn Sie Windows Vista oder [!INCLUDE[lserver](../../../includes/lserver-md.md)] ausführen, befolgen Sie die vorherigen Schritte für Vista und [!INCLUDE[lserver](../../../includes/lserver-md.md)], aber verwenden Sie den Knoten **Distributed Transaction Coordinator\\Lokaler DTC** unter dem Knoten des Remotecomputers.  
  
 Zum Verwenden der Benutzeroberfläche des Tools müssen Sie zuerst die Datei WsatUI.dll im folgenden Pfad registrieren:  
  
 **%PROGRAMFILES%\\Microsoft SDKs\\Windows\\v6.0 \\Bin\\WsatUI.dll**  
  
 Die Registrierung kann mit folgendem Befehl vorgenommen werden:  
  
```Output  
regasm.exe /codebase WsatUI.dll  
```  
  
 Sie können dieses Tool verwenden, um die grundlegenden WS\-AtomicTransaction\-Einstellungen zu ändern.Sie können beispielsweise die WS\-AtomicTransaction\-Protokollunterstützung aktivieren und deaktivieren, die HTTP\-Ports für WS\-AT konfigurieren, ein SSL\-Zertifikat an den HTTP\-Port binden, Zertifikate durch Angabe von Zertifikatantragstellernamen konfigurieren, den Ablaufverfolgungsmodus aktivieren und Standard\- und Maximaltimeouts festlegen.  
  
 Wenn Sie die WS\-AtomicTransaction\-Unterstützung nur auf dem lokalen Computer konfigurieren müssen, können Sie die Befehlszeilenversion des Tools verwenden.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Befehlszeilentool finden Sie unter dem Thema [WS\-AtomicTransaction\-Konfigurationsdienstprogramm \(wsatConfig.exe\)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md).  
  
 Beachten Sie, dass das MMC\-Snap\-In und das Befehlszeilentool nicht die Konfiguration aller WS\-AT\-Einstellungen unterstützen.Diese Einstellungen können nur durch die Änderung der Registrierung bearbeitet werden.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zu diesen Registrierungseinstellungen finden Sie unter [Konfigurieren der WS\-AtomicTransaction\-Unterstützung](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).  
  
### Benutzeroberflächenbeschreibung  
 **WS\-AtomicTransaction\-Netzwerkunterstützung aktivieren**:  
  
 Mit diesem Kontrollkästchen können die GUI\-Komponenten dieses Snap\-Ins aktiviert oder deaktiviert werden.  
  
 Vor der Aktivierung dieses Kontrollkästchens sollten Sie sicherstellen, dass der DTC\-Netzwerkzugriff mit eingehender oder\/und ausgehender Kommunikation aktiviert ist.Dieser Wert kann auf der Registerkarte **Sicherheit** des MSDTC\-Snap\-Ins überprüft werden.  
  
#### Netzwerkgruppenfeld  
 Sie können den HTTPS\-Anschluss und zusätzliche Sicherheitseinstellungen, wie z. B. SSL\-Verschlüsselung, in der Netzwerkgruppe angeben.Diese Gruppe ist deaktiviert \(abgeblendet\), wenn DTC\-Netzwerktransaktionen nicht aktiviert sind.  
  
 **HTTPS\-Anschluss**  
  
 Dies ist der Wert des für WS\-AT verwendeten HTTPS\-Anschlusses.Der Wert muss eine Zahl im Bereich von 1 bis 65535 sein \(um einen gültigen Anschluss darzustellen\).Durch das Ändern des HTTP\-Anschlusses wird die HTTP\-Dienstkonfiguration geändert, was bedeutet, dass die zuvor verwendete WS\-AT\-Dienstadresse freigegeben wird und eine neue WS\-AT\-Dienstadresse basierend auf dem neuen Anschluss registriert wird.Außerdem wird der neu ausgewählte Anschluss mit dem derzeit ausgewählten Zertifikat für die SSL\-Verschlüsselung verschlüsselt.  
  
> [!NOTE]
>  Wenn Sie die Firewall schon vor dem Ausführen dieses Tools aktiviert haben, wird der Anschluss automatisch in der Ausnahmeliste registriert.Wenn die Firewall vor dem Ausführen dieses Tools deaktiviert wird, werden keine zusätzlichen Konfigurationen in Bezug auf die Firewall vorgenommen.  
  
 Wenn Sie die Firewall nach der Konfiguration von WS\-AT aktivieren, müssen Sie dieses Tool erneut ausführen und die Anschlussnummer mit diesem Parameter angeben.Wenn Sie die Firewall nach der Konfiguration deaktivieren, wird WS\-AT ohne zusätzliche Eingabe ausgeführt.  
  
 **Endpunktzertifikat**  
  
 Durch Klicken auf **Auswählen** wird eine Liste mit den derzeit auf dem lokalen Computer verfügbaren Zertifikaten angezeigt, sodass der Benutzer das für die SSL\-Verschlüsselung zu verwendende Zertifikat auswählen kann.Die Zertifikate müssen einen privaten Schlüssel haben.Andernfalls wird eine Fehlermeldung ausgegeben.  
  
> [!NOTE]
>  Wenn Sie ein SSL\-Zertifikat für einen bestimmten Port festlegen, wird dabei das ursprüngliche SSL\-Zertifikat überschrieben, das diesem Port zugeordnet ist \(sofern vorhanden\).  
  
 **Autorisierte Konten**  
  
 Durch Klicken auf **Auswählen** wird der Zugriffssteuerungslisten\-Editor von Windows aufgerufen, mit dem Sie den Benutzer oder die Gruppe für die WS\-Atomic\-Transaktionen angeben können, indem Sie **Zulassen** oder **Verweigern** in der Berechtigungsgruppe **Teilnehmen** aktivieren.  
  
 **Autorisierte Zertifikate**  
  
 Durch Klicken auf die Schaltfläche **Auswählen** wird eine Liste der derzeit auf dem lokalen Computer verfügbaren Zertifikate angezeigt.Sie können dann auswählen, welchen Zertifikatsidentitäten ermöglicht wird, an WS\-Atomic\-Transaktionen teilzunehmen.  
  
#### Gruppenfeld Timeout  
 Das Gruppenfeld **Timeout** ermöglicht Ihnen, das Standard\- und das Maximaltimeout für eine WS\-Atomic\-Transaktion anzugeben.Ein gültiger Wert für ein ausgehendes Timeout liegt zwischen 1 und 3600.Ein gültiger Wert für ein eingehendes Timeout liegt zwischen 0 und 3600.  
  
#### Gruppenfeld Ablaufverfolgung und Protokollierung  
 Das Gruppenfeld **Ablaufverfolgung und Protokollierung** ermöglicht Ihnen, die gewünschte Ablaufverfolgungs\- und Protokollierungsebene zu konfigurieren.  
  
 Durch Klicken auf die Schaltfläche **Optionen** wird eine Seite aufgerufen, auf der Sie zusätzliche Einstellungen festlegen können.  
  
 Das Kombinationsfeld **Ablaufverfolgungsebene** ermöglicht Ihnen, einen gültigen Wert der <xref:System.Diagnostics.TraceLevel>\-Enumeration auszuwählen.Sie können mit den Kontrollkästchen auch angeben, ob Sie die Ablaufverfolgung oder die Aktivitätspropagierung durchführen oder persönlich identifizierbare Informationen sammeln möchten.  
  
 Sie können auch Protokollierungssitzungen im Gruppenfeld **Protokollierungssitzung** angeben.  
  
> [!NOTE]
>  Wenn ein anderer Benutzer der Ablaufverfolgung den WS\-AT\-Ablaufverfolgungsanbieter verwendet, können Sie keine neue Protokollsitzung für Ablaufverfolgungsereignisse erstellen.Jeder Versuch, die Protokollierung zu diesem Zeitpunkt zu konfigurieren, führt zur Fehlermeldung "Fehler beim Aktivieren des Anbieters.Fehlercode: 1".  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] zu Ablaufverfolgung und Protokollierung finden Sie unter [Verwaltung und Diagnose](../../../docs/framework/wcf/diagnostics/index.md).  
  
## Siehe auch  
 [Konfigurieren der WS\-AtomicTransaction\-Unterstützung](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)   
 [WS\-AtomicTransaction\-Konfigurationsdienstprogramm \(wsatConfig.exe\)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)   
 [Verwaltung und Diagnose](../../../docs/framework/wcf/diagnostics/index.md)