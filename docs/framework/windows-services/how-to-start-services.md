---
title: 'Gewusst wie: Starten von Diensten'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
manager: douge
ms.openlocfilehash: 3c8382d2e425d11dc8aa8b22e361b3cc5637744f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-start-services"></a>Gewusst wie: Starten von Diensten
Nachdem ein Dienst installiert wurde, muss er gestartet werden. Beim Starten wird die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode für die Dienstklasse aufgerufen. In der Regel werden die Vorgänge, die vom Dienst durchgeführt werden, von der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode definiert. Nachdem ein Dienst gestartet worden ist, bleibt er aktiv, solange er nicht manuell angehalten oder beendet wird.  
  
 Für Dienste kann festgelegt werden, ob sie automatisch oder manuell gestartet werden. Ein automatisch startender Dienst wird gestartet, wenn der Computer, auf dem er installiert ist, neu gestartet oder zum ersten Mal eingeschaltet wird. Ein Dienst, der manuell gestartet wird, muss von Benutzern gestartet werden.  
  
> [!NOTE]
>  Standardmäßig sind Dienste, die mit Visual Studio erstellten auf Manuelles Starten festgelegt.  
  
 Es gibt mehrere Möglichkeiten, die Sie manuell einen Dienst zu starten – aus **Server-Explorer**, aus der **Dienststeuerungs-Manager**, oder von Code mithilfe einer Komponente namens der <xref:System.ServiceProcess.ServiceController>.  
  
 Die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft für die <xref:System.ServiceProcess.ServiceInstaller>-Klasse wird festgelegt, um zu bestimmen, ob ein Dienst manuell oder automatisch gestartet werden soll.  
  
### <a name="to-specify-how-a-service-should-start"></a>So geben Sie an, wie ein Dienst gestartet werden soll  
  
1.  Nachdem Sie den Dienst erstellt haben, fügen Sie die erforderlichen Installationsprogramme hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  Klicken Sie im Designer auf das Dienstinstallationsprogramm für den Dienst, mit dem Sie arbeiten.  
  
3.  In der **Eigenschaften** legen die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> -Eigenschaft auf einen der folgenden:  
  
    |Installationszeitpunkt|Festzulegender Wert|  
    |----------------------------------|--------------------|  
    |Sobald der Computer neu gestartet wird|**Automatisch**|  
    |Sobald der Dienst von einer expliziten Benutzeraktion gestartet wird|**Manuell**|  
  
    > [!TIP]
    >  Um zu verhindern, dass den Dienst gestartet wird, legen Sie die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> Eigenschaft **deaktiviert**. Wenn ein Server mehrmals neu gestartet wird, kann damit Zeit gespart werden, indem das Starten von Diensten verhindert wird, die in der Regel gestartet würden.  
  
    > [!NOTE]
    >  Diese und weitere Eigenschaften können geändert werden, nachdem der Dienst installiert wurde.  
  
     Es gibt mehrere Möglichkeiten, Sie können starten ein Diensts, dessen <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> Prozess festgelegt werden, um **manuell** – aus **Server-Explorer**, aus der **Windows-Dienstkontroll-Manager**, oder von Code. Es ist wichtig zu beachten, dass nicht alle diese Methoden tatsächlich den Dienst im Kontext der start der **Dienststeuerungs-Manager**; **Server-Explorer** und programmgesteuerte Methoden für das Starten des Diensts Startmethoden geändert, den Controller.  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a>So starten Sie einen Dienst manuell mit dem Server-Explorer  
  
1.  In **Server-Explorer**, fügen Sie den Server soll, wenn er noch nicht aufgelistet ist. Weitere Informationen finden Sie unter Vorgehensweise: Zugriff und Server-Explorer-Datenbank-Explorer zu initialisieren.  
  
2.  Erweitern Sie die **Services** Knoten, und suchen Sie den Dienst, die Sie starten möchten.  
  
3.  Maustaste auf den Namen des Diensts, und klicken Sie auf **starten**.  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a>So starten Sie einen Dienst manuell mit dem Dienststeuerungs-Manager  
  
1.  Öffnen der **Dienststeuerungs-Manager** durch eine der folgenden Aktionen ausführen:  
  
    -   Windows XP und 2000 Professional, mit der Maustaste **Arbeitsplatz** auf den Desktop, und klicken Sie dann auf **verwalten**. Erweitern Sie im angezeigten Dialogfeld die **Dienste und Anwendungen** Knoten.  
  
         \- oder –  
  
    -   Klicken Sie in Windows Server 2003 und Windows 2000 Server **starten**, zeigen Sie auf **Programme**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Services**.  
  
        > [!NOTE]
        >  In Windows NT, Version 4.0, können Sie öffnen das Dialogfeld über **Systemsteuerung**.  
  
     Daraufhin sollte jetzt der Dienst die **Services** Bereich des Fensters.  
  
2.  Wählen Sie den Dienst in der Liste der rechten Maustaste darauf, und klicken Sie dann auf **starten**.  
  
### <a name="to-manually-start-a-service-from-code"></a>So starten Sie einen Dienst programmgesteuert  
  
1.  Erstellen Sie eine Instanz der <xref:System.ServiceProcess.ServiceController>-Klasse, und konfigurieren Sie sie so, dass Daten mit dem Dienst ausgetauscht werden können.  
  
2.  Starten Sie den Dienst, indem Sie die <xref:System.ServiceProcess.ServiceController.Start%2A>-Methode aufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Vorgehensweise: Erstellen von Windows-Diensten](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
