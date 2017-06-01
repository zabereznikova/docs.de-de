---
title: "Firewall-Anweisungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
caps.latest.revision: 32
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 32
---
# Firewall-Anweisungen
Sie müssen mehrere Ports oder Programme in der Firewall aktivieren, damit die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Beispiele ausgeführt werden können.In vielen der Beispiele findet die Kommunikation über die Ports im Bereich 8000\-8003 und über Port 9000 statt.Die Firewall ist standardmäßig aktiviert und verhindert den Zugriff auf diese Ports.Um die Beispiele mit der Firewall verwenden zu können, haben Sie abhängig von Ihren Anforderungen und Ihrer Sicherheitsumgebung mehrere Möglichkeiten:  
  
-   Option 1: Sie können die Beispiele während der Ausführung aktivieren.Ändern Sie die Konfiguration der Firewall nicht, und beginnen Sie mit der Erstellung und Ausführung der Beispiele.Wenn Sie ein Beispiel ausführen, wird ein Dialogfeld mit dem Namen **Windows\-Sicherheitshinweis** geöffnet.Hier können Sie das betreffende Beispielprogramm einer Liste mit nicht gesperrten Programmen hinzufügen.Möglicherweise müssen Sie das Beispiel neu starten.  
  
-   Option 2: Sie können Beispielprogramme im Voraus aktivieren.Starten Sie das Applet **Windows\-Firewall\-Systemsteuerung**, und aktivieren Sie die Beispielprogramme, die Sie ausführen möchten.Sie müssen die Programme zunächst erstellen, sodass die ausführbaren Dateien vorhanden sind.Ausführlichere Informationen finden Sie weiter unten.  
  
-   Option 3: Sie können ein Portbereich im Voraus aktivieren.Starten Sie das Applet **Windows\-Firewall\-Systemsteuerung**, und aktivieren Sie die Ports 80, 443, 8000 \- 8003 und 9000.Ausführlichere Informationen finden Sie weiter unten.Diese Option birgt ein höheres Sicherheitsrisiko als die anderen Optionen, da jedes beliebige Programm auf die Ports zugreifen kann, nicht nur die Beispielprogramme.  
  
 Wenn Sie nicht sicher sind, verwenden Sie die erste Option.Wenn Sie eine Firewall von einem anderen Anbieter ausführen, müssen Sie möglicherweise ähnliche Änderungen vornehmen.  
  
> [!IMPORTANT]
>  Die Änderung der Firewallkonfiguration hat Auswirkungen auf die Sicherheit.Es wird empfohlen, sich die vorgenommenen Änderungen zu notieren, sodass Sie sie wieder rückgängig machen können, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben.  
  
### So aktivieren Sie Beispielprogramme im Voraus  
  
1.  Erstellen Sie das Beispiel.  
  
2.  Klicken Sie auf **Start** und dann auf **Ausführen**. Geben Sie `firewall.cpl` ein.Hierdurch wird das Applet **Windows\-Firewall\-Systemsteuerung** geöffnet.  
  
    > [!NOTE]
    >  Sie müssen über die Berechtigung zum Ändern der Firewalleinstellungen verfügen, um Beispiele auszuführen, für die eine Kommunikation durch die Windows\-Firewall erforderlich ist.Wenn einige Firewalleinstellungen nicht verfügbar sind und der Computer eine Verbindung mit einer Domäne hergestellt hat, kann der Systemadministrator diese Einstellungen über Gruppenrichtlinien steuern.  
  
3.  Führen Sie eine der folgenden betriebssystemabhängigen Vorgehensweisen aus, um einem Programm den Zugriff durch die Windows\-Firewall zu gewähren:  
  
    -   Klicken Sie bei Windows 7 oder Windows Server 2008 R2 auf **Ein Programm oder Feature durch die Windows\-Firewall zulassen**.Klicken Sie auf **Einstellungen ändern** und dann auf **Anderes Programm zulassen**.  
  
    -   Klicken Sie bei [!INCLUDE[wv](../../../../includes/wv-md.md)] oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)] auf **Programm durch die Windows\-Firewall kommunizieren lassen**.  
  
4.  Klicken Sie auf der Registerkarte **Ausnahmen** auf **Programm hinzufügen**.  
  
5.  Klicken Sie auf die Schaltfläche **Durchsuchen**, und wählen Sie die EXE\-Datei des Beispielprogramms aus, das Sie ausführen möchten.  
  
6.  Wiederholen Sie die Schritte 4 und 5, bis Sie alle gewünschten Beispiele hinzugefügt haben.  
  
7.  Klicken Sie auf **OK**, um das Firewall\-Applet zu schließen.  
  
### So aktivieren Sie einen Portbereich im Voraus  
  
1.  Klicken Sie auf **Start** und dann auf **Ausführen**. Geben Sie `firewall.cpl` ein.Hierdurch wird das Applet **Windows\-Firewall\-Systemsteuerung** geöffnet.  
  
2.  Führen Sie unter Windows 7 oder bei Windows Server 2008 R2 folgende Schritte aus.  
  
    1.  Klicken Sie im Fenster der Windows\-Firewall in der linken Spalte auf **Erweiterte Einstellungen**.  
  
    2.  Klicken Sie in der linken Spalte auf **Eingehende Regeln**.  
  
    3.  Klicken Sie in der rechten Spalte auf **Neue Regeln**.  
  
    4.  Wählen Sie **Port** aus, und klicken Sie auf **Weiter**.  
  
    5.  Wählen Sie **TCP** aus, und geben Sie im Feld **Bestimmte lokale Ports** die Ports `8000, 8001, 8002, 8003, 9000, 80, 443` ein.  
  
    6.  Klicken Sie auf **Weiter**.  
  
    7.  Wählen Sie **Verbindung zulassen** aus, und klicken Sie auf **Weiter**.  
  
    8.  Wählen Sie **Domäne** und **Privat** aus, und klicken Sie auf **Weiter**.  
  
    9. Nennen Sie die Regel `WCF-WF 4.0 Samples`, und klicken Sie auf **Fertig stellen**.  
  
    10. Klicken Sie auf **Ausgehende Regeln**, und wiederholen Sie die Schritte von c bis h.  
  
3.  Führen Sie bei [!INCLUDE[wv](../../../../includes/wv-md.md)] oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)] folgende Schritte aus.  
  
    1.  Klicken Sie auf **Programm durch die Windows\-Firewall kommunizieren lassen**.  
  
    2.  Klicken Sie auf der Registerkarte **Ausnahmen** auf **Port hinzufügen**.  
  
    3.  Geben Sie einen Namen und als Portnummer 8000 ein, und wählen Sie die Option **TCP** aus.  
  
    4.  Klicken Sie auf die Schaltfläche **Bereich ändern**, wählen Sie **Nur für eigenes Netzwerk \(Subnetz\)**, und klicken Sie auf **OK**.  
  
    5.  Wiederholen Sie die Schritte b bis d für die Ports 8001, 8002, 8003, 9000, 80 und 443.  
  
4.  Klicken Sie auf **OK**, um das Firewall\-Applet zu schließen.  
  
> [!NOTE]
>  Machen Sie die konfigurierten Ausnahmen wieder rückgängig, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben.Öffnen Sie hierzu das Applet **Windows\-Firewall\-Systemsteuerung**, und entfernen Sie alle Programme bzw. Ports, die Sie zuvor hinzugefügt haben.