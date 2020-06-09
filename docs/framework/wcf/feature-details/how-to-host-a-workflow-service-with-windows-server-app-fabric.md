---
title: 'Vorgehensweise: Hosten eines Workflowdiensts mit Windows Server AppFabric'
ms.date: 03/30/2017
ms.assetid: 83b62cce-5fc2-4c6d-b27c-5742ba3bac73
ms.openlocfilehash: 519c76e3e46e01b5e8c696234e39fefbb9f8ad06
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593307"
---
# <a name="how-to-host-a-workflow-service-with-windows-server-app-fabric"></a>Vorgehensweise: Hosten eines Workflowdiensts mit Windows Server AppFabric

Das Hosten von Workflowdiensten in AppFabric ähnelt dem Hosten unter IIS/WAS. Der einzige Unterschied besteht in den Tools von AppFabric zum Bereitstellen, Überwachen und Verwalten von Workflowdiensten. In diesem Thema wird der Workflow Dienst verwendet, der im [Erstellen eines Workflow Dienstanbieter mit langer Laufzeit](creating-a-long-running-workflow-service.md)erstellt wurde. Sie werden Schritt für Schritt durch das Erstellen eines Workflowdiensts geführt. In diesem Thema wird erläutert, wie der Workflowdienst mit AppFabric gehostet wird. Weitere Informationen zu Windows Server App Fabric finden Sie in der [Dokumentation zu Windows Server](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10))AppFabric. Vergewissern Sie sich, dass Windows Server AppFabric installiert ist, bevor Sie die nachfolgenden Schritte ausführen.  Öffnen Sie hierzu Internetinformationsdienste (inetmgr. exe), klicken Sie in der Ansicht **Verbindungen** auf den Servernamen, klicken Sie auf Sites, und klicken Sie auf **Standard Website**. Auf der rechten Seite des Bildschirms sollte ein Abschnitt mit dem Namen **App Fabric**angezeigt werden. Wenn dieser Bereich nicht (oben rechts) angezeigt wird, ist AppFabric nicht installiert. Weitere Informationen zum Installieren von Windows Server App Fabric finden Sie unter [Installieren von Windows Server](https://docs.microsoft.com/previous-versions/appfabric/ee790960(v=azure.10))AppFabric.  
  
### <a name="creating-a-simple-workflow-service"></a>Erstellen eines einfachen Workflowdiensts  
  
1. Öffnen Sie Visual Studio 2012, und laden Sie die Projekt Mappe Order Processing, die Sie im Thema [Erstellen eines Workflow Dienstanbieter mit langer Laufzeit](creating-a-long-running-workflow-service.md) erstellt haben.  
  
2. Klicken Sie mit der rechten Maustaste auf das Projekt **OrderService** , und wählen Sie **Eigenschaften** und dann die Registerkarte **Web**  
  
3. Wählen Sie im Abschnitt **Start Aktion** der Eigenschaften Seite **bestimmte Seite** aus, und geben Sie Service1. xamlx in das Bearbeitungsfeld ein.  
  
4. Wählen Sie auf der Eigenschaften Seite im Abschnitt **Server** die Option **lokalen IIS-Webserver verwenden** aus, und geben Sie die folgende URL ein: `http://localhost/OrderService` .  
  
5. Klicken Sie auf die Schaltfläche **virtuelles Verzeichnis erstellen** . Dadurch wird ein neues virtuelles Verzeichnis erstellt, und das Projekt wird eingerichtet, damit die erforderlichen Dateien beim Erstellen des Projekts in das virtuelle Verzeichnis kopiert werden.  Sie können die XAMLX-, die web.config- sowie alle erforderlichen DLL-Dateien auch manuell in das virtuelle Verzeichnis kopieren.  
  
### <a name="configuring-a-workflow-service-hosted-in-windows-server-app-fabric"></a>Konfigurieren eines Workflowdiensts zum Hosten in Windows Server AppFabric  
  
1. Öffnen Sie den Internetinformationsdienste-Manager (inetmgr.exe).  
  
2. Navigieren Sie im Bereich **Verbindungen** zum virtuellen Verzeichnis OrderService.  
  
3. Klicken Sie mit der rechten Maustaste auf OrderService, und wählen Sie **WCF-und WF-Dienste verwalten**, **Konfigurieren**aus. Das Dialogfeld **WCF und WF für die Anwendung konfigurieren** wird angezeigt.  
  
4. Wählen Sie die Registerkarte **Allgemein** aus, um allgemeine Informationen zur Anwendung anzuzeigen, wie im folgenden Screenshot zu sehen.  
  
     ![Registerkarte "Allgemein" im AppFabric-Konfigurationsdialogfeld](media/appfabricconfiguration-general.gif "Appfabricconfiguration-allgemein")  
  
5. Wählen Sie die Registerkarte **Überwachung** aus. Dies zeigt verschiedene Überwachungs Einstellungen, wie im folgenden Screenshot gezeigt.  
  
     ![AppFabric-Konfiguration – Registerkarte "Überwachung"](media/appfabricconfiguration-monitoring.gif "Appfabricconfiguration-Überwachung")  
  
     Weitere Informationen zum Konfigurieren der Workflow Dienst Überwachung in App Fabric finden Sie unter [Konfigurieren der Überwachung mit App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677384(v=azure.10)).  
  
6. Wählen Sie die Registerkarte **Workflow Persistenz** aus. Dies ermöglicht es Ihnen, Ihre Anwendung so zu konfigurieren, dass Sie den Standard Dauerhaftigkeits Anbieter von App Fabric verwendet, wie im folgenden Screenshot gezeigt.  
  
     ![App Fabric-Konfiguration &#45; Persistenz](media/appfabricconfiguration-persistence.gif "Appfabricconfiguration-Persistenz")  
  
     Weitere Informationen zum Konfigurieren der Workflow Persistenz in Windows Server App Fabric finden Sie [unter Konfigurieren der Workflow Persistenz in der APP-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677353(v=azure.10)).  
  
7. Wählen Sie die Registerkarte **Workflow Host Verwaltung** aus. Dadurch können Sie angeben, wann Workflow Dienst Instanzen im Leerlauf entladen und beibehalten werden sollen, wie im folgenden Screenshot gezeigt.  
  
     ![App Fabric-Konfigurations Workflow-Host Verwaltung](media/appfabricconfiguration-management.gif "Appfabricconfiguration-Verwaltung")  
  
     Weitere Informationen zur Konfiguration der Workflow Host Verwaltung finden Sie [unter Konfigurieren der Workflow Host Verwaltung in App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ff383424(v=azure.10)).  
  
8. Wählen Sie die Registerkarte **automatisch starten** aus. Auf diese Weise können Sie Einstellungen für den automatischen Start für die Workflow Dienste in der Anwendung angeben, wie im folgenden Screenshot gezeigt.  
  
     ![Screenshot, der APP Fabric Auto&#45;Startkonfiguration anzeigt](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-auto-start-configuration.gif)  
  
     Weitere Informationen zum Konfigurieren des automatischen Starts finden Sie [unter Konfigurieren des automatischen Starts mit App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677261(v=azure.10)).  
  
9. Wählen Sie die Registerkarte **Drosselung** aus. Dies ermöglicht es Ihnen, einschränerungs Einstellungen für den Workflow Dienst zu konfigurieren, wie im folgenden Screenshot zu sehen.  
  
     ![Screenshot, der die Konfiguration der APP Fabric-Drosselung anzeigt](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-throttling-configuration.gif)  
  
     Weitere Informationen zum Konfigurieren der Drosselung finden Sie [unter Konfigurieren der Drosselung mit App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677261(v=azure.10)).  
  
10. Wählen Sie die Registerkarte **Sicherheit** aus. Auf diese Weise können Sie die Sicherheitseinstellungen für die Anwendung konfigurieren, wie im folgenden Screenshot zu sehen.  
  
     ![AppFabric-Sicherheitskonfiguration](media/appfabricconfiguration-security.gif "Appfabricconfiguration-Sicherheit")  
  
     Weitere Informationen zum Konfigurieren der Sicherheit mit Windows Server AppFabric finden Sie unter [Konfigurieren der Sicherheit mit App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677278(v=azure.10)).  
  
### <a name="using-windows-server-app-fabric"></a>Verwenden von Windows Server AppFabric  
  
1. Erstellen Sie die Projektmappe, um die benötigten Dateien in das virtuelle Verzeichnis zu kopieren.  
  
2. Klicken Sie mit der rechten Maustaste auf das Projekt Order Client, und wählen Sie **Debuggen**, **neue Instanz starten** , um die Client Anwendung  
  
3. Der Client wird ausgeführt, und Visual Studio zeigt das Dialogfeld **Sicherheitswarnung anfügen** an, und klicken Sie auf die Schaltfläche **nicht anfügen** . Damit wird Visual Studio angewiesen, den IIS-Prozess nicht zum Debuggen anzufügen.  
  
4. Der Workflowdienst wird unmittelbar von der Clientanwendung aufgerufen; anschließend wartet die Anwendung. Der Workflowdienst wird in den Leerlauf versetzt und beibehalten. Sie können dies überprüfen, indem Sie Internetinformationsdienste (inetmgr.exe) starten, im Bereich Verbindungen zu OrderService navigieren und die Instanz auswählen. Klicken Sie dann im rechten Bereich auf das Symbol für das AppFabric-Dashboard. Unter persistente WF-Instanzen sehen Sie, dass eine beibehaltene Workflow Dienst Instanz vorhanden ist, wie im folgenden Screenshot gezeigt.  
  
     ![Screenshot, der das App Fabric-Dashboard anzeigt.](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-dashboard.gif)  
  
     Der **WF-Instanzverlauf** listet Informationen zum Workflow Dienst auf, z. b. die Anzahl der Workflow Dienst Aktivierungen, die Anzahl der Vervollständigungen von Workflow Dienst Instanzen und die Anzahl der Workflow Instanzen mit Fehlern. Unter "aktive" oder "Leerlauf"-Instanzen wird ein Link angezeigt. Wenn Sie auf den Link klicken, werden weitere Informationen zu den Workflow Instanzen im Leerlauf angezeigt, wie im folgenden Screenshot zu sehen.  
  
     ![Screenshot, der persistente Workflow-Instanzdetails anzeigt.](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/persisted-workflow-instance-detail.gif)  
  
     Weitere Informationen zu Windows Server App Fabric-Features und deren Verwendung finden Sie unter [Windows Server App Fabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10)) .  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen eines Workflowdiensts mit langer Ausführungszeit](creating-a-long-running-workflow-service.md)
- [Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
- [Installieren von Windows Server-App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee790960(v=azure.10))
- [Dokumentation zu Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10))
