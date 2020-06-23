---
title: Firewall-Anweisungen
description: Erfahren Sie, wie Sie Ports oder Programme in der Firewall für WCF-Beispiele aktivieren. Verwenden Sie je nach Ihren Anforderungen und der Sicherheitsumgebung eines dieser Prozeduren.
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: de55d067960b8f2096c129f6feaf037219e06a96
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246140"
---
# <a name="firewall-instructions"></a>Firewallanweisungen

Sie müssen mehrere Ports oder Programme in der Firewall aktivieren, damit die Windows Communication Foundation (WCF)-Beispiele funktionieren können. In vielen der Beispiele findet die Kommunikation über die Ports im Bereich 8000-8003 und über Port 9000 statt. Die Firewall ist standardmäßig aktiviert und verhindert den Zugriff auf diese Ports. Um die Beispiele mit der Firewall verwenden zu können, haben Sie abhängig von Ihren Anforderungen und Ihrer Sicherheitsumgebung mehrere Möglichkeiten:

- Option 1: Sie können die Beispiele während der Ausführung aktivieren. Ändern Sie die Konfiguration der Firewall nicht, und beginnen Sie mit der Erstellung und Ausführung der Beispiele. Wenn ein Beispiel ausgeführt wird, wird das Dialogfeld **Windows-Sicherheitswarnung** angezeigt. Hier können Sie das betreffende Beispielprogramm einer Liste mit nicht gesperrten Programmen hinzufügen. Möglicherweise müssen Sie das Beispiel neu starten.

- Option 2: Sie können Beispielprogramme im Voraus aktivieren. Starten Sie das Applet **Windows-Firewall-Systemsteuerung** , und aktivieren Sie die Beispiel Programme, die Sie ausführen möchten. Sie müssen die Programme zunächst erstellen, sodass die ausführbaren Dateien vorhanden sind. Ausführlichere Informationen finden Sie weiter unten.

- Option 3: Sie können ein Portbereich im Voraus aktivieren. Starten Sie das Applet **Windows-Firewall-Systemsteuerung** , und aktivieren Sie die Ports 80, 443, 8000-8003 und 9000, die von den Beispielen verwendet werden. Ausführlichere Informationen finden Sie weiter unten. Diese Option birgt ein höheres Sicherheitsrisiko als die anderen Optionen, da jedes beliebige Programm auf die Ports zugreifen kann, nicht nur die Beispielprogramme.

Wenn Sie nicht sicher sind, verwenden Sie die erste Option. Wenn Sie eine Firewall von einem anderen Anbieter ausführen, müssen Sie möglicherweise ähnliche Änderungen vornehmen.

> [!IMPORTANT]
> Die Änderung der Firewallkonfiguration hat Auswirkungen auf die Sicherheit. Es wird empfohlen, sich die vorgenommenen Änderungen zu notieren, sodass Sie sie wieder rückgängig machen können, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben.

## <a name="enable-samples-programs-in-advance"></a>Beispiel Programme im Voraus aktivieren

1. Erstellen Sie das Beispiel.

2. Wählen Sie **Start**  >  **Run**aus, und geben Sie ein `firewall.cpl` . Dadurch wird das Applet **Windows-Firewall-Systemsteuerung** geöffnet.

    > [!NOTE]
    > Sie müssen über die Berechtigung zum Ändern der Firewalleinstellungen verfügen, um Beispiele auszuführen, für die eine Kommunikation durch die Windows-Firewall erforderlich ist. Wenn einige Firewalleinstellungen nicht verfügbar sind und der Computer eine Verbindung mit einer Domäne hergestellt hat, kann der Systemadministrator diese Einstellungen über Gruppenrichtlinien steuern.

3. Führen Sie einen der folgenden betriebsspezifischen Schritte aus, um ein Programm durch die Windows-Firewall zuzulassen:

    - Klicken Sie unter Windows 7 oder Windows Server 2008 R2 auf **Programm oder Feature durch Windows-Firewall zulassen**. Klicken Sie auf **Einstellungen ändern**, um  >  **ein anderes Programm zuzulassen**.

    - Klicken Sie unter Windows Vista oder Windows Server 2008 auf **Programm durch die Windows-Firewall zulassen**.

4. Klicken Sie auf der Registerkarte **Ausnahmen** auf **Programm hinzufügen**.

5. Klicken Sie auf die Schaltfläche **Durchsuchen** , und wählen Sie die ausführbare Datei des Beispiels, das Sie ausführen möchten.

6. Wiederholen Sie die Schritte 4 und 5, bis Sie die ausführbaren Dateien aller Beispiele hinzugefügt haben, die Sie ausführen möchten.

7. Klicken Sie auf **OK** , um das Applet Firewall zu schließen.

## <a name="enable-a-port-range-in-advance"></a>Aktivieren Sie einen Port Bereich im voraus.

1. Wählen Sie **Start**  >  **Run**aus, und geben Sie ein `firewall.cpl` . Dadurch wird das Applet **Windows-Firewall-Systemsteuerung** geöffnet.

2. Führen Sie unter Windows 7 oder bei Windows Server 2008 R2 folgende Schritte aus.

    1. Klicken Sie in der linken Spalte des Fensters Windows-Firewall auf **Erweiterte Einstellungen** .

    2. Klicken Sie in der linken Spalte auf **Eingehende Regeln** .

    3. Klicken Sie in der rechten Spalte auf **neue Regeln** .

    4. Wählen Sie **Port** , und klicken Sie auf **weiter**.

    5. Wählen Sie **TCP** aus, und geben Sie `8000, 8001, 8002, 8003, 9000, 80, 443` im Feld **bestimmte lokale Ports** ein.

    6. Klicken Sie auf **Weiter**.

    7. Wählen Sie **Verbindung zulassen**aus, und klicken Sie auf **weiter** .

    8. Wählen Sie **Domäne** und **Privat**aus, und klicken Sie auf **weiter**.

    9. Benennen Sie diese Regel `WCF-WF 4.0 Samples` , und klicken Sie auf **Fertig**stellen.

    10. Klicken Sie auf **ausgehende Regeln** und wiederholen Sie die Schritte c bis h.

3. Führen Sie unter Windows Vista oder Windows Server 2008 die folgenden Schritte aus.

    1. Klicken Sie auf **Programm durch die Windows-Firewall kommunizieren lassen**.

    2. Klicken Sie auf der Registerkarte **Ausnahmen** auf **Port hinzufügen**.

    3. Geben Sie einen Namen ein, geben Sie 8000 als Portnummer ein, und wählen Sie die Option **TCP** aus.

    4. Klicken Sie auf die Schaltfläche **Bereich ändern** , wählen Sie die Option **mein Netzwerk** (Subnetz) nur aus, und klicken Sie auf **OK**.

    5. Wiederholen Sie die Schritte b bis d für die Ports 8001, 8002, 8003, 9000, 80 und 443.

4. Klicken Sie auf **OK** , um das Applet Firewall zu schließen.

> [!NOTE]
> Machen Sie die konfigurierten Ausnahmen wieder rückgängig, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben. Öffnen Sie hierzu das Applet **Windows-Firewall-Systemsteuerung** , und entfernen Sie alle Programme oder Port Einträge, die von den vorherigen Prozeduren hinzugefügt wurden.
