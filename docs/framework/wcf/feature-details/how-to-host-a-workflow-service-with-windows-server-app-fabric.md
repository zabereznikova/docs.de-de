---
title: 'Vorgehensweise: Hosten eines Workflowdiensts mit Windows Server AppFabric'
ms.date: 03/30/2017
ms.assetid: 83b62cce-5fc2-4c6d-b27c-5742ba3bac73
ms.openlocfilehash: 287067391f47a0b4bcbe11bd4bfab971954cd706
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465125"
---
# <a name="how-to-host-a-workflow-service-with-windows-server-app-fabric"></a>Vorgehensweise: Hosten eines Workflowdiensts mit Windows Server AppFabric
Das Hosten von Workflowdiensten in AppFabric ähnelt dem Hosten unter IIS/WAS. Der einzige Unterschied besteht in den Tools von AppFabric zum Bereitstellen, Überwachen und Verwalten von Workflowdiensten. In diesem Thema wird den Workflowdienst der [zum Erstellen eines Workflowdiensts langer](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md). Sie werden Schritt für Schritt durch das Erstellen eines Workflowdiensts geführt. In diesem Thema wird erläutert, wie der Workflowdienst mit AppFabric gehostet wird. Weitere Informationen zu Windows Server AppFabric, finden Sie unter [Dokumentation zu Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409). Vergewissern Sie sich, dass Windows Server AppFabric installiert ist, bevor Sie die nachfolgenden Schritte ausführen.  Dazu öffnen Sie Internet Information Services (inetmgr.exe) dazu klicken Sie auf den Servernamen in der **Verbindungen** anzuzeigen, klicken Sie auf Standorte, und klicken Sie auf **Default Web Site**. Auf der rechten Seite des Bildschirms sehen Sie sich der Unterabschnitt **AppFabric**. Wenn dieser Bereich nicht (oben rechts) angezeigt wird, ist AppFabric nicht installiert. Weitere Informationen zum Installieren von Windows Server AppFabric finden Sie unter [Installieren von Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=193136).  
  
### <a name="creating-a-simple-workflow-service"></a>Erstellen eines einfachen Workflowdiensts  
  
1.  Öffnen Sie Visual Studio 2012, und Laden Sie die OrderProcessing-Projektmappe, die Sie erstellt, in haben der [zum Erstellen eines Workflowdiensts langer](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md) Thema.  
  
2.  Klicken Sie mit der rechten Maustaste auf die **OrderService** Projekt, und wählen **Eigenschaften** , und wählen Sie die **Web** Registerkarte.  
  
3.  In der **Startaktion** wählen Sie im Abschnitt der Eigenschaftenseite **bestimmte Seite** , und geben Sie im Eingabefeld Service1.xamlx.  
  
4.  In der **Server** wählen Sie im Abschnitt der Eigenschaftenseite **lokalen IIS-Webserver verwenden** und geben Sie die folgende URL: `http://localhost/OrderService`.  
  
5.  Klicken Sie auf die **virtuelles Verzeichnis erstellen** Schaltfläche. Dadurch wird ein neues virtuelles Verzeichnis erstellt, und das Projekt wird eingerichtet, damit die erforderlichen Dateien beim Erstellen des Projekts in das virtuelle Verzeichnis kopiert werden.  Sie können die XAMLX-, die web.config- sowie alle erforderlichen DLL-Dateien auch manuell in das virtuelle Verzeichnis kopieren.  
  
### <a name="configuring-a-workflow-service-hosted-in-windows-server-app-fabric"></a>Konfigurieren eines Workflowdiensts zum Hosten in Windows Server AppFabric  
  
1.  Öffnen Sie den Internetinformationsdienste-Manager (inetmgr.exe).  
  
2.  Navigieren Sie zum virtuellen Verzeichnis OrderService in die **Verbindungen** Bereich.  
  
3.  Klicken Sie mit der rechten Maustaste auf OrderService, und wählen Sie **WCF- und WF-Dienste verwalten**, **konfigurieren...** . Die **Konfiguration von WCF und WF für die Anwendung** Dialogfeld wird angezeigt.  
  
4.  Wählen Sie die **allgemeine** Registerkarte, um allgemeine Informationen zur Anwendung anzuzeigen, wie im folgenden Screenshot gezeigt.  
  
     ![Registerkarte "Allgemein" im AppFabric-Dialogfeld](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-general.gif "AppFabricConfiguration – Allgemein")  
  
5.  Wählen Sie die **Überwachung** Registerkarte. Es werden verschiedene Überwachungseinstellungen angezeigt, wie in der folgenden Bildschirmabbildung veranschaulicht.  
  
     ![App-Fabric Konfigurationsüberwachung Registerkarte](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-monitoring.gif "AppFabricConfiguration-Überwachung")  
  
     Weitere Informationen zum Konfigurieren der Workflowdienst in AppFabric finden Sie unter [Konfigurieren der Überwachung mit AppFabric](https://go.microsoft.com/fwlink/?LinkId=193153).  
  
6.  Wählen Sie die **Workflowpersistenz** Registerkarte. Dort können Sie Ihre Anwendung für die Verwendung des Standardpersistenzanbieters von AppFabric konfigurieren, wie in der folgenden Bildschirmabbildung veranschaulicht.  
  
     ![AppFabric-Konfiguration &#45; Persistenz](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-persistence.gif "AppFabricConfiguration-Persistenz")  
  
     Weitere Informationen zum Konfigurieren von Workflowpersistenz in Windows Server AppFabric finden Sie unter [Konfigurieren von Workflowpersistenz in AppFabric](https://go.microsoft.com/fwlink/?LinkId=193148).  
  
7.  Wählen Sie die **Workflowhostverwaltung** Registerkarte. Dort können Sie angeben, wann Workflowdienstinstanzen im Leerlauf entladen und beibehalten werden sollen, wie in der folgenden Bildschirmabbildung veranschaulicht.  
  
     ![AppFabric-Konfiguration – Workflowhostverwaltung](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-management.gif "AppFabricConfiguration-Verwaltung")  
  
     Weitere Informationen zur Workflow-Host-Management-Konfiguration finden Sie unter [Konfiguration – Workflowhostverwaltung in AppFabric](https://go.microsoft.com/fwlink/?LinkId=193151).  
  
8.  Wählen Sie die **Autostart-** Registerkarte. Dort können Sie Autostarteinstellungen für die Workflowdienste in der Anwendung angeben, wie in der folgenden Bildschirmabbildung veranschaulicht.  
  
     ![Screenshot mit App-Fabric automatisch&#45;Konfiguration starten.](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-auto-start-configuration.gif)  
  
     Weitere Informationen zum Konfigurieren von Autostart finden Sie unter [Konfigurieren von Autostart-mit App-Fabric](https://go.microsoft.com/fwlink/?LinkId=193150).  
  
9. Wählen Sie die **Drosselung** Registerkarte. Dort können Sie Einschränkungseinstellungen für den Workflowdienst konfigurieren, wie in der folgenden Bildschirmabbildung veranschaulicht.  
  
     ![Screenshot mit AppFabric-Einschränkung.](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-throttling-configuration.gif)  
  
     Weitere Informationen zum Konfigurieren von Einschränkungen finden Sie unter [Konfigurieren der Drosselung mit AppFabric](https://go.microsoft.com/fwlink/?LinkId=193149).  
  
10. Wählen Sie die **Sicherheit** Registerkarte. Dort können Sie Sicherheitseinstellungen für die Anwendung konfigurieren, wie in der folgenden Bildschirmabbildung veranschaulicht.  
  
     ![AppFabric-Sicherheitskonfiguration](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-security.gif "AppFabricConfiguration-Sicherheit")  
  
     Weitere Informationen zum Konfigurieren der Sicherheit mit Windows Server AppFabric finden Sie unter [Konfigurieren der Sicherheit mit AppFabric](https://go.microsoft.com/fwlink/?LinkId=193152).  
  
### <a name="using-windows-server-app-fabric"></a>Verwenden von Windows Server AppFabric  
  
1.  Erstellen Sie die Projektmappe, um die benötigten Dateien in das virtuelle Verzeichnis zu kopieren.  
  
2.  Klicken Sie mit der rechten Maustaste auf das Projekt OrderClient, und wählen Sie **Debuggen**, **neue Instanz starten** um die Client-Anwendung zu starten.  
  
3.  Der Client wird ausgeführt, und Visual Studio zeigt eine **Sicherheitswarnung Anfügen** Dialogfeld klicken Sie auf die **nicht Anfügen** Schaltfläche. Damit wird Visual Studio angewiesen, den IIS-Prozess nicht zum Debuggen anzufügen.  
  
4.  Der Workflowdienst wird unmittelbar von der Clientanwendung aufgerufen; anschließend wartet die Anwendung. Der Workflowdienst wird in den Leerlauf versetzt und beibehalten. Sie können dies überprüfen, indem Sie Internetinformationsdienste (inetmgr.exe) starten, im Bereich Verbindungen zu OrderService navigieren und die Instanz auswählen. Klicken Sie dann im rechten Bereich auf das Symbol für das AppFabric-Dashboard. Unter Persistente WF-Instanzen wird eine beibehaltene Workflowdienstinstanz angezeigt, wie in der folgenden Bildschirmabbildung veranschaulicht.  
  
     ![Screenshot mit der AppFabric-Dashboard.](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-dashboard.gif)  
  
     Die **WF Instanz Verlauf** listet Informationen zu den Workflowdienst, z. B. die Anzahl der Workflowdienst aktiviert, die Anzahl der instanzverlauf und die Anzahl der Workflowinstanzen Fehler aufwiesen. Unter Aktive Instanzen (einschließlich Leerlauf) wird ein Link angezeigt. Wenn Sie darauf klicken, werden weitere Informationen über Workflowinstanzen im Leerlauf angezeigt, wie in der folgenden Bildschirmabbildung veranschaulicht.  
  
     ![Screenshot mit Details für einen Workflow Instanzen beibehalten.](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/persisted-workflow-instance-detail.gif)  
  
     Weitere Informationen zu Windows Server AppFabric-Funktionen und deren Verwendung finden Sie unter [Windows Server AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkID=193143&clcid=0x409)  
  
## <a name="see-also"></a>Siehe auch
- [Erstellen eines Workflowdiensts mit langer Ausführungszeit](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)
- [Windows Server AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=193143)
- [Installieren von Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=193136)
- [Windows Server AppFabric-Dokumentation](https://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409)
