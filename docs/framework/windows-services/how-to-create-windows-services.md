---
title: 'Vorgehensweise: Erstellen von Windows-Diensten'
description: Verwenden Sie die Projektvorlage „Windows-Dienst“, um einen Dienst zu erstellen. Legen Sie die Eigenschaft ServiceName fest, erstellen Sie Installationsprogramme, und setzen Sie die Methoden OnStart und OnStop außer Kraft.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
author: ghogen
ms.openlocfilehash: 6918225e39c15a52710fd0d56342aae869b42325
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925773"
---
# <a name="how-to-create-windows-services"></a>Vorgehensweise: Erstellen von Windows-Diensten
Wenn Sie einen Dienst erstellen möchten, können Sie die Visual Studio-Projektvorlage **Windows-Dienst** verwenden. Von dieser Vorlage wird ein großer Teil der Arbeit übernommen, indem auf die entsprechenden Klassen und Namespaces verwiesen wird, die Vererbung von den Basisklassen für Dienste eingerichtet wird und eine Reihe von Methoden überschrieben werden, die voraussichtlich überschrieben werden sollen.  
  
> [!WARNING]
> Die Projektvorlage Windows Service ist nicht in der Express Edition von Visual Studio verfügbar.  
  
 Das Erstellen eines funktionierenden Diensts erfordert mindestens:  
  
- Legen Sie die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft fest.  
  
- Das Erstellen der für die Dienstanwendung erforderlichen Installationsprogramme.  
  
- Durch das Überschreiben der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode und der <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Methode und die Eingabe von Code wird das Verhalten des Diensts angepasst.  
  
### <a name="to-create-a-windows-service-application"></a>So erstellen Sie eine Windows-Dienstanwendung  
  
1. Erstellen Sie ein **Windows-Dienstprojekt**.  
  
    > [!NOTE]
    > Anweisungen zum Schreiben von Diensten ohne die Vorlage finden Sie unter [Vorgehensweise: Programmgesteuertes Schreiben von Diensten](how-to-write-services-programmatically.md).  
  
2. Legen Sie im Fenster **Eigenschaften** die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft für den Dienst fest.  
  
     ![Legen Sie die Eigenschaft ServiceName fest.](./media/windowsservice-servicename.PNG "WindowsService_ServiceName")  
  
    > [!NOTE]
    > Der Wert der <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft muss immer mit dem Namen übereinstimmen, der in den Installationsprogrammklassen aufgezeichnet wurde. Wenn Sie diese Eigenschaft ändern, muss auch die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft der Installationsprogrammklassen aktualisiert werden.  
  
3. Legen Sie eine oder mehrere der folgenden Eigenschaften fest, um zu bestimmen, wie der Dienst funktionieren soll.  
  
    |Eigenschaft|Einstellung|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|Mit `True` wird angezeigt, dass vom Dienst Anforderungen zum Beenden angenommen werden. Mit `false` wird verhindert, dass der Dienst beendet werden kann.|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|Mit `True` wird angegeben, dass der Dienst benachrichtigt werden soll, wenn der ausführende Computer heruntergefahren wird. Dadurch wird ermöglicht, dass die <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>-Prozedur aufgerufen werden kann.|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|Mit `True` wird angegeben, dass vom Dienst Anforderungen zum Anhalten und Fortsetzen angenommen werden. Mit `false` wird verhindert, dass der Dienst angehalten oder fortgesetzt werden kann.|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|Mit `True` wird angegeben, dass der Dienst Benachrichtigungen zu Änderungen des Leistungsstatus eines Computers verarbeiten kann. `false` gibt an, dass der Dienst nicht über diese Änderungen informiert wird.|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|Mit `True` werden informative Einträge in das Anwendungsereignisprotokoll geschrieben, sobald vom Dienst eine Aktion durchgeführt wird. Mit `false` wird diese Funktion deaktiviert. Weitere Informationen finden Sie unter [Vorgehensweise: Protokollinformationen über Dienste](how-to-log-information-about-services.md). **Hinweis**:  <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> ist standardmäßig auf `true` festgelegt.|  
  
    > [!NOTE]
    > Wenn <xref:System.ServiceProcess.ServiceBase.CanStop%2A> oder <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> auf `false` festgelegt sind, werden vom **Dienststeuerungs-Manager** die entsprechenden Menüoptionen zum Beenden, Anhalten oder Fortsetzen des Diensts deaktiviert.  
  
4. Greifen Sie auf den Code-Editor zu, und geben Sie die gewünschte Verarbeitung für die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Prozedur und die <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Prozedur ein.  
  
5. Überschreiben Sie alle anderen Methoden, für die Sie Funktionen definieren möchten.  
  
6. Fügen Sie die für die Dienstanwendung erforderlichen Installationsprogramme hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](how-to-add-installers-to-your-service-application.md).  
  
7. Erstellen Sie das Projekt, indem Sie im Menü **Erstellen** den Befehl **Projektmappe erstellen** auswählen.  
  
    > [!NOTE]
    > Drücken Sie nicht F5, um das Projekt auszuführen. Dienstprojekte können auf diese Weise nicht ausgeführt werden.  
  
8. Installieren Sie den Dienst. Weitere Informationen finden Sie unter [Vorgehensweise: Installieren und Deinstallieren von Diensten](how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Windows-Dienstanwendungen](introduction-to-windows-service-applications.md)
- [How to: Programmgesteuertes Schreiben von Diensten](how-to-write-services-programmatically.md)
- [How to: Hinzufügen von Installern zur Dienstanwendung](how-to-add-installers-to-your-service-application.md)
- [How to: Protokollinformationen über Dienste](how-to-log-information-about-services.md)
- [How to: Starten von Diensten](how-to-start-services.md)
- [How to: Angeben des Sicherheitskontexts für Dienste](how-to-specify-the-security-context-for-services.md)
- [How to: Installieren und Deinstallieren von Diensten](how-to-install-and-uninstall-services.md)
- [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
