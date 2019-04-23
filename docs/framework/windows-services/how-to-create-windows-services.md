---
title: 'Vorgehensweise: Erstellen von Windows-Diensten'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
author: ghogen
ms.openlocfilehash: 469074336c8aa49fee1acf871360f8dbc1363247
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313267"
---
# <a name="how-to-create-windows-services"></a>Vorgehensweise: Erstellen von Windows-Diensten
Wenn Sie einen Dienst erstellen möchten, können Sie die Visual Studio-Projektvorlage **Windows-Dienst** verwenden. Von dieser Vorlage wird ein großer Teil der Arbeit übernommen, indem auf die entsprechenden Klassen und Namespaces verwiesen wird, die Vererbung von den Basisklassen für Dienste eingerichtet wird und eine Reihe von Methoden überschrieben werden, die voraussichtlich überschrieben werden sollen.  
  
> [!WARNING]
>  Die Projektvorlage Windows Service ist nicht in der Express Edition von Visual Studio verfügbar.  
  
 Das Erstellen eines funktionierenden Diensts erfordert mindestens:  
  
-   Legen Sie die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft fest.  
  
-   Das Erstellen der für die Dienstanwendung erforderlichen Installationsprogramme.  
  
-   Durch das Überschreiben der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode und der <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Methode und die Eingabe von Code wird das Verhalten des Diensts angepasst.  
  
### <a name="to-create-a-windows-service-application"></a>So erstellen Sie eine Windows-Dienstanwendung  
  
1. Erstellen Sie ein **Windows-Dienstprojekt**.  
  
    > [!NOTE]
    >  Anweisungen zum Schreiben von Diensten ohne die Vorlage finden Sie unter [Vorgehensweise: Programmgesteuertes Schreiben von Diensten](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
2. Legen Sie im Fenster **Eigenschaften** die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft für den Dienst fest.  
  
     ![Legen Sie die ServiceName-Eigenschaft fest.](../../../docs/framework/windows-services/media/windowsservice-servicename.PNG "Windows_Dienstname")  
  
    > [!NOTE]
    >  Der Wert der <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft muss immer mit dem Namen übereinstimmen, der in den Installationsprogrammklassen aufgezeichnet wurde. Wenn Sie diese Eigenschaft ändern, muss auch die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft der Installationsprogrammklassen aktualisiert werden.  
  
3. Legen Sie eine oder mehrere der folgenden Eigenschaften fest, um zu bestimmen, wie der Dienst funktionieren soll.  
  
    |Eigenschaft|Einstellung|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|`True` dient zum Anzeigen, dass vom Dienst Anforderungen zum Beenden angenommen werden. Mit `false` wird verhindert, dass der Dienst beendet werden kann.|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|`True` dient zum Angeben, dass der Dienst benachrichtigt werden soll, wenn der ausführende Computer heruntergefahren wird. Dadurch wird ermöglicht, dass die <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>-Prozedur aufgerufen werden kann.|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|`True` dient zum Angeben, dass vom Dienst Anforderungen zum Anhalten und Fortsetzen angenommen werden. Mit `false` wird verhindert, dass der Dienst angehalten oder fortgesetzt werden kann.|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|`True` dient zum Angeben, dass der Dienst Benachrichtigungen zu Änderungen des Leistungsstatus eines Computers verarbeiten kann. `false` gibt an, dass der Dienst nicht über diese Änderungen informiert wird.|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|`True` dient zum Schreiben informativer Einträge in das Anwendungsereignisprotokoll, sobald vom Dienst eine Aktion durchgeführt wird. Mit `false` wird diese Funktion deaktiviert. Weitere Informationen finden Sie unter [Vorgehensweise: Protokollinformationen über Dienste](../../../docs/framework/windows-services/how-to-log-information-about-services.md). **Hinweis**:  <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> ist standardmäßig auf `true` festgelegt.|  
  
    > [!NOTE]
    >  Wenn <xref:System.ServiceProcess.ServiceBase.CanStop%2A> oder <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> auf `false` festgelegt sind, werden vom **Dienststeuerungs-Manager** die entsprechenden Menüoptionen zum Beenden, Anhalten oder Fortsetzen des Diensts deaktiviert.  
  
4. Greifen Sie auf den Code-Editor zu, und geben Sie die gewünschte Verarbeitung für die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Prozedur und die <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Prozedur ein.  
  
5. Überschreiben Sie alle anderen Methoden, für die Sie Funktionen definieren möchten.  
  
6. Fügen Sie die für die Dienstanwendung erforderlichen Installationsprogramme hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
7. Erstellen Sie das Projekt, indem Sie im Menü **Erstellen** den Befehl **Projektmappe erstellen** auswählen.  
  
    > [!NOTE]
    >  Drücken Sie nicht F5, um das Projekt auszuführen. Dienstprojekte können auf diese Weise nicht ausgeführt werden.  
  
8. Installieren Sie den Dienst. Weitere Informationen finden Sie unter [Vorgehensweise: Installieren und Deinstallieren von Diensten](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [Vorgehensweise: Programmgesteuertes Schreiben von Diensten](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)
- [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
- [Vorgehensweise: Protokollinformationen über Dienste](../../../docs/framework/windows-services/how-to-log-information-about-services.md)
- [Vorgehensweise: Starten von Diensten](../../../docs/framework/windows-services/how-to-start-services.md)
- [Vorgehensweise: Angeben des Sicherheitskontexts für Dienste](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
- [Vorgehensweise: Installieren und Deinstallieren von Diensten](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)
- [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
