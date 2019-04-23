---
title: Firewall-Anweisungen
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: f1b576b4e413fa3bae70ef1eb8f8ed768e28e309
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773790"
---
# <a name="firewall-instructions"></a>Firewall-Anweisungen
Sie müssen mehrere Ports oder Programme in der Firewall aktivieren, damit die Beispiele für Windows Communication Foundation (WCF) verwendet werden können. In vielen der Beispiele findet die Kommunikation über die Ports im Bereich 8000-8003 und über Port 9000 statt. Die Firewall ist standardmäßig aktiviert und verhindert den Zugriff auf diese Ports. Um die Beispiele mit der Firewall verwenden zu können, haben Sie abhängig von Ihren Anforderungen und Ihrer Sicherheitsumgebung mehrere Möglichkeiten:  
  
-   Option 1: Aktivieren Sie interaktiv die Beispiele während der Ausführung. Ändern Sie die Konfiguration der Firewall nicht, und beginnen Sie mit der Erstellung und Ausführung der Beispiele. Wenn ein Beispiel ausgeführt wird, eine **Windows-Sicherheitshinweis** Dialogfeld wird angezeigt. Hier können Sie das betreffende Beispielprogramm einer Liste mit nicht gesperrten Programmen hinzufügen. Möglicherweise müssen Sie das Beispiel neu starten.  
  
-   Option 2: Aktivieren Sie Beispielprogramme im voraus. Starten Sie den **Windows-Firewall-Systemsteuerung** Applet, und aktivieren Sie die Beispielprogramme, die Sie ausführen möchten. Sie müssen die Programme zunächst erstellen, sodass die ausführbaren Dateien vorhanden sind. Ausführlichere Informationen finden Sie weiter unten.  
  
-   Option 3: Können aktivieren Sie einen Portbereich im voraus. Starten Sie den **Windows-Firewall** **Systemsteuerung** Applet, und aktivieren Sie Ports 80, 443, 8000-8003 und 9000, die von den Beispielen verwendet werden. Ausführlichere Informationen finden Sie weiter unten. Diese Option birgt ein höheres Sicherheitsrisiko als die anderen Optionen, da jedes beliebige Programm auf die Ports zugreifen kann, nicht nur die Beispielprogramme.  
  
 Wenn Sie nicht sicher sind, verwenden Sie die erste Option. Wenn Sie eine Firewall von einem anderen Anbieter ausführen, müssen Sie möglicherweise ähnliche Änderungen vornehmen.  
  
> [!IMPORTANT]
>  Die Änderung der Firewallkonfiguration hat Auswirkungen auf die Sicherheit. Es wird empfohlen, sich die vorgenommenen Änderungen zu notieren, sodass Sie sie wieder rückgängig machen können, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben.  
  
### <a name="to-enable-samples-programs-in-advance"></a>So aktivieren Sie Beispielprogramme im Voraus  
  
1. Erstellen Sie das Beispiel.  
  
2. Klicken Sie auf **starten**, klicken Sie auf **ausführen**, und geben `firewall.cpl`. Daraufhin wird die **Windows-Firewall-Systemsteuerung** Applet.  
  
    > [!NOTE]
    >  Sie müssen über die Berechtigung zum Ändern der Firewalleinstellungen verfügen, um Beispiele auszuführen, für die eine Kommunikation durch die Windows-Firewall erforderlich ist. Wenn einige Firewalleinstellungen nicht verfügbar sind und der Computer eine Verbindung mit einer Domäne hergestellt hat, kann der Systemadministrator diese Einstellungen über Gruppenrichtlinien steuern.  
  
3. Führen Sie eine der folgenden betriebssystemabhängigen Vorgehensweisen aus, um einem Programm den Zugriff durch die Windows-Firewall zu gewähren:  
  
    -   Klicken Sie auf Windows 7 oder Windows Server 2008 r2 auf **können Sie ein Programm oder Feature durch die Windows-Firewall**. Klicken Sie auf **Ändern der Einstellungen**, ermöglichen **ein anderes Programm...** .  
  
    -   Auf [!INCLUDE[wv](../../../../includes/wv-md.md)] oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)], klicken Sie auf **Programm durch die Windows-Firewall lassen**.  
  
4. Auf der **Ausnahmen** auf **Programm hinzufügen**.  
  
5. Klicken Sie auf die **Durchsuchen** Schaltfläche, und wählen Sie die ausführbare Datei des Beispiels, die Sie ausführen möchten.  
  
6. Wiederholen Sie die Schritte 4 und 5, bis Sie die ausführbaren Dateien alle gewünschten Beispiele hinzugefügt haben, die Sie ausführen möchten.  
  
7. Klicken Sie auf **OK** um das Firewall-Applet zu schließen.  
  
### <a name="to-enable-a-port-range-in-advance"></a>So aktivieren Sie einen Portbereich im Voraus  
  
1. Klicken Sie auf **starten**, klicken Sie auf **ausführen**, und geben `firewall.cpl`. Daraufhin wird die **Windows-Firewall-Systemsteuerung** Applet.  
  
2. Führen Sie unter Windows 7 oder bei Windows Server 2008 R2 folgende Schritte aus.  
  
    1.  Klicken Sie auf **Erweiterte Einstellungen** in der linken Spalte des Fensters Windows-Firewall.  
  
    2.  Klicken Sie auf **Eingangsregeln** in der linken Spalte.  
  
    3.  Klicken Sie auf **neue Regeln** in der rechten Spalte.  
  
    4.  Wählen Sie **Port** , und klicken Sie auf **Weiter**.  
  
    5.  Wählen Sie **TCP** , und geben Sie `8000, 8001, 8002, 8003, 9000, 80, 443` in die **bestimmte lokale Ports** Feld.  
  
    6.  Klicken Sie auf **Weiter**.  
  
    7.  Wählen Sie **Verbindung zulassen,**, und klicken Sie auf **Weiter** .  
  
    8.  Wählen Sie **Domäne** und **Private**, und klicken Sie auf **Weiter**.  
  
    9. Nennen Sie die Regel `WCF-WF 4.0 Samples`, und klicken Sie auf **Fertig stellen**.  
  
    10. Klicken Sie auf **Ausgangsregeln** , und wiederholen Sie die Schritte von c bis h.  
  
3. Führen Sie bei [!INCLUDE[wv](../../../../includes/wv-md.md)] oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)] folgende Schritte aus.  
  
    1.  Klicken Sie auf **Programm durch die Windows-Firewall lassen**.  
  
    2.  Auf der **Ausnahmen** auf **Port hinzufügen**.  
  
    3.  Geben Sie einen Namen, geben Sie als Portnummer 8000 ein, und wählen die **TCP** Option.  
  
    4.  Klicken Sie auf die **Änderungsbereich** Klicken die **Mein Netzwerk** unumgänglich (Subnetz), und klicken Sie auf **OK**.  
  
    5.  Wiederholen Sie die Schritte b bis d für die Ports 8001, 8002, 8003, 9000, 80 und 443.  
  
4. Klicken Sie auf **OK** um das Firewall-Applet zu schließen.  
  
> [!NOTE]
>  Machen Sie die konfigurierten Ausnahmen wieder rückgängig, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben. Öffnen Sie hierzu die **Windows-Firewall-Systemsteuerung** Applet und entfernen Sie alle Programme bzw. Ports, die von den vorherigen Prozeduren hinzugefügt wurden.
