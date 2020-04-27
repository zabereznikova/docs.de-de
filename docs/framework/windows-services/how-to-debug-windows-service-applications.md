---
title: 'Vorgehensweise: Debuggen von Windows-Dienstanwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- Windows NT services, debugging
- Windows Service applications, debugging
- services, debugging
ms.assetid: 63ab0800-0f05-4f1e-88e6-94c73fd920a2
author: ghogen
ms.openlocfilehash: 860f2ae22eb6510dc1f1a454ae3e51ccb366078b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053622"
---
# <a name="how-to-debug-windows-service-applications"></a>Vorgehensweise: Debuggen von Windows-Dienstanwendungen
Ein Dienst muss im Kontext des Dienststeuerelement-Managers und nicht innerhalb von Visual Studio ausgeführt werden. Aus diesem Grund ist das Debuggen eines Dienstes nicht so einfach wie das Debuggen anderer Anwendungstypen in Visual Studio. Damit ein Dienst gedebuggt werden kann, muss er gestartet werden. Danach muss ein Debugger an den Prozess angehängt werden, in dem er ausgeführt wird. Anschließend kann die Anwendung mit allen Standarddebugfunktionen von Visual Studio gedebuggt werden.  
  
> [!CAUTION]
> Das Anhängen darf nur bei bekannten Prozessen durchgeführt werden. Außerdem müssen die Konsequenzen bekannt sein, wenn an den Prozess angehängt wird und dieser u. U. abgebrochen wird. Wenn z. B. an den WinLogon-Prozess angehängt und anschließend das Debuggen beendet wird, hält das System an, weil es ohne WinLogon nicht lauffähig ist.  
  
 Ein Debugger kann nur an einen Dienst angehängt werden, der ausgeführt wird. Durch den Vorgang des Anhängens wird die aktuelle Funktion des Diensts unterbrochen. Die Verarbeitung des Diensts wird nicht tatsächlich beendet oder angehalten. Das bedeutet: Wenn mit dem Debuggen eines Diensts begonnen wird, während er ausgeführt wird, befindet er sich während des Debuggens technisch gesehen weiterhin im Status Gestartet. Die Verarbeitung ist jedoch unterbrochen worden.  
  
 Nach dem Anhängen an den Prozess können Sie Haltepunkte einrichten und diese zum Debuggen des Codes verwenden. Sobald Sie das zum Anhängen des Prozesses verwendete Dialogfeld verlassen haben, befinden Sie sich im Debugmodus. Dann kann der Dienst mit dem Dienststeuerungs-Manager gestartet, beendet, angehalten und fortgesetzt werden, sodass die festgelegten Haltepunkte angesteuert werden. Nach erfolgreichem Debuggen kann der Dummydienst entfernt werden.  
  
 Dieser Artikel umfasst das Debuggen eines Dienstes, der auf dem lokalen Computer ausgeführt wird, aber Sie können auch Windows-Dienste debuggen, die auf einem Remotecomputer ausgeführt werden. Weitere Informationen finden Sie unter [Remotedebuggen](/visualstudio/debugger/debug-installed-app-package).  
  
> [!NOTE]
> Das Debuggen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode kann Schwierigkeiten bereiten, da vom Dienststeuerungs-Manager ein Limit von 30 Sekunden für alle Versuche erzwungen wird, einen Dienst zu starten. Weitere Informationen finden Sie unter [Problembehandlung: Debuggen von Windows-Diensten](troubleshooting-debugging-windows-services.md).  
  
> [!WARNING]
> Um aussagekräftige Informationen für das Debuggen zu erhalten, muss der Visual Studio-Debugger Symboldateien für die Binärdateien finden, die gerade gedebuggt werden. Wenn Sie einen Dienst debuggen, den Sie in Visual Studio erstellt haben, befinden sich die Symboldateien (PDB-Dateien) in demselben Ordner wie die ausführbare Datei oder Bibliothek, und der Debugger lädt diese automatisch. Wenn Sie einen Dienst debuggen, den Sie erstellt haben, sollten Sie zuerst die Symbole für den Dienst suchen und sicherstellen, dass sie vom Debugger gefunden werden können. Weitere Informationen finden Sie unter [Angeben von Symbol- und Quelldateien (PDB) im Visual Studio Debugger](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger). Wenn Sie einen Systemprozess debuggen oder Symbole für Systemaufrufe in Ihren Diensten haben möchten, sollten Sie die Microsoft-Symbolserver hinzufügen. Weitere Informationen finden Sie unter [Debugging with Symbols(Debuggen mit Symbolen)](/windows/desktop/DxTechArts/debugging-with-symbols).  
  
### <a name="to-debug-a-service"></a>So debuggen Sie einen Dienst  
  
1. Erstellen Sie Ihren Dienst in der Debugkonfiguration.  
  
2. Installieren Sie den Dienst. Weitere Informationen finden Sie unter [Vorgehensweise: Installieren und Deinstallieren von Diensten](how-to-install-and-uninstall-services.md).  
  
3. Starten Sie den Dienst entweder mit dem **Dienststeuerungs-Manager**, mit dem **Server-Explorer** oder aus dem Code. Weitere Informationen finden Sie unter [Vorgehensweise: Starten von Diensten](how-to-start-services.md).  
  
4. Starten Sie Visual Studio mit Administratorrechten, damit Sie die Systemprozesse zuordnen können.  
  
5. (Optional) Klicken Sie in Visual Studio auf der Menüleiste auf **Extras** und **Optionen**. Wählen Sie im Dialogfeld **Optionen** die Optionen **Debuggen** und **Symbole** aus. Aktivieren Sie das Kontrollkästchen **Microsoft-Symbolserver**, und klicken Sie anschließend auf die Schaltfläche **OK**.  
  
6. Wählen Sie auf der Menüleiste aus dem Menü **Debuggen** oder **Extras** die Option **An den Prozess anhängen** aus. (Tastatur: STRG+ALT+P)  
  
     Das Dialogfeld **Prozesse** wird angezeigt.  
  
7. Aktivieren Sie das Kontrollkästchen **Prozesse aller Benutzer anzeigen**.  
  
8. Wählen Sie im Abschnitt **Verfügbare Prozesse** den Prozess für den Dienst aus, und klicken Sie anschließend auf **Anfügen**.  
  
    > [!TIP]
    > Der Prozess weist den gleichen Namen wie die ausführbare Datei für den Dienst auf.  
  
     Das Dialogfeld **An den Prozess anhängen** wird angezeigt.  
  
9. Wählen Sie die entsprechenden Optionen aus, und klicken Sie anschließend auf **OK**, um das Dialogfeld zu schließen.  
  
    > [!NOTE]
    > Sie befinden sich jetzt im Debugmodus.  
  
10. Legen Sie die Haltepunkte fest, die im Code verwendet werden sollen.  
  
11. Öffnen Sie den Dienststeuerungs-Manager und bearbeiten Sie den Dienst, indem Sie Befehle zum Beenden, Anhalten und Fortsetzen ausgeben, um die festgelegten Haltepunkte anzusteuern. Weitere Informationen zum Ausführen des Dienststeuerungs-Managers finden Sie unter [Vorgehensweise: Starten von Diensten](how-to-start-services.md). Zudem finden Sie Informationen unter [Problembehandlung: Debuggen von Windows-Diensten](troubleshooting-debugging-windows-services.md).  
  
## <a name="debugging-tips-for-windows-services"></a>Tipps zum Debuggen für Windows-Dienste  
 Durch das Anfügen an den Prozess des Dienstes können Sie die meisten, aber nicht alle, Codes für diesen Dienst debuggen. Z. B. weil der Dienst bereits gestartet wurde, können Sie den Code in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode des Dienstes oder den Code in der `Main`-Methode nicht debuggen, die verwendet wird, um den Dienst auf diese Weise zu lassen. Dies kann dadurch umgangen werden, dass ein zweiter temporärer Dienst in der Dienstanweisung erstellt wird, der lediglich als Hilfsmittel für das Debuggen verwendet wird. Beide Dienste können installiert werden. Anschließend wird der Dienstprozess geladen, indem der "Dummydienst" gestartet wird. Sobald der Prozess vom temporären Dienst gestartet wurde, können Sie mit dem Anhängen an den Dienstprozess über das Menü **Debuggen** in Visual Studio beginnen.  
  
 Versuchen Sie, Aufrufe an die <xref:System.Threading.Thread.Sleep%2A>-Methode zur Verzögerung der Aktion hinzuzufügen, bis Sie sie an den Prozess anfügen können.  
  
 Versuchen Sie, das Programm in eine reguläre Konsolenanwendung umzuwandeln. Dazu schreiben Sie die `Main`-Methode wie folgt um, damit sie sowohl als Windows-Dienst als auch als Konsolenanwendung ausgeführt werden kann, je nachdem, wie sie gestartet wird.  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a>Vorgehensweise: Ausführen eines Windows-Dienstes als Konsolenanwendung  
  
1. Fügen Sie eine Methode zu Ihrem Dienst hinzu, die die Methoden <xref:System.ServiceProcess.ServiceBase.OnStart%2A> und <xref:System.ServiceProcess.ServiceBase.OnStop%2A> ausführt:  
  
    ```csharp  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2. Schreiben Sie die `Main`-Methode wie folgt um:  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        if (Environment.UserInteractive)  
        {  
            MyNewService service1 = new MyNewService(args);  
            service1.TestStartupAndStop(args);  
        }  
        else  
        {  
            // Put the body of your old Main method here.  
        }  
    }
    ```  
  
3. Legen Sie in der Registerkarte **Anwendung** der Projekteigenschaften den **Ausgabetyp** auf **Konsolenanwendung** fest.  
  
4. Wählen Sie **Debugging starten** (F5) aus.  
  
5. Wenn Sie das Programm als Windows-Dienst ausführen, installieren Sie es, und starten Sie sie wie gewohnt für einen Windows-Dienst. Es ist nicht notwendig, diese Änderungen rückgängig zu machen.  
  
 In einigen Fällen, z. B. beim Debuggen eines Problems, das nur beim Systemstart auftritt, müssen Sie den Windows-Debugger verwenden. [Laden Sie das Windows Driver Kit (WDK) herunter](/windows-hardware/drivers/download-the-wdk), und informieren Sie sich über die [Fehlerbehebung (Debugging) bei Windows-Diensten](https://support.microsoft.com/kb/824344).  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Windows-Dienstanwendungen](introduction-to-windows-service-applications.md)
- [How to: Installieren und Deinstallieren von Diensten](how-to-install-and-uninstall-services.md)
- [How to: Starten von Diensten](how-to-start-services.md)
- [Debugging a Service (Debuggen eines Diensts)](/windows/desktop/Services/debugging-a-service)
