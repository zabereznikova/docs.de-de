---
title: 'Gewusst wie: Debuggen von Windows-Dienstanwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- Windows NT services, debugging
- Windows Service applications, debugging
- services, debugging
ms.assetid: 63ab0800-0f05-4f1e-88e6-94c73fd920a2
author: ghogen
manager: douge
ms.openlocfilehash: 2c73ccd75bdbd1298371921bababa87ba4520495
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-debug-windows-service-applications"></a>Gewusst wie: Debuggen von Windows-Dienstanwendungen
Ein Dienst muss im Kontext des Dienststeuerelement-Managers und nicht innerhalb von Visual Studio ausgeführt werden. Aus diesem Grund ist das Debuggen eines Dienstes nicht so einfach wie das Debuggen anderer Anwendungstypen in Visual Studio. Damit ein Dienst gedebuggt werden kann, muss er gestartet werden. Danach muss ein Debugger an den Prozess angehängt werden, in dem er ausgeführt wird. Anschließend kann die Anwendung mit allen Standarddebugfunktionen von Visual Studio gedebuggt werden.  
  
> [!CAUTION]
>  Das Anhängen darf nur bei bekannten Prozessen durchgeführt werden. Außerdem müssen die Konsequenzen bekannt sein, wenn an den Prozess angehängt wird und dieser u. U. abgebrochen wird. Wenn z. B. an den WinLogon-Prozess angehängt und anschließend das Debuggen beendet wird, hält das System an, weil es ohne WinLogon nicht lauffähig ist.  
  
 Ein Debugger kann nur an einen Dienst angehängt werden, der ausgeführt wird. Durch den Vorgang des Anhängens wird die aktuelle Funktion des Diensts unterbrochen. Die Verarbeitung des Diensts wird nicht tatsächlich beendet oder angehalten. Das bedeutet: Wenn mit dem Debuggen eines Diensts begonnen wird, während er ausgeführt wird, befindet er sich während des Debuggens technisch gesehen weiterhin im Status Gestartet. Die Verarbeitung ist jedoch unterbrochen worden.  
  
 Nach dem Anhängen an den Prozess können Sie Haltepunkte einrichten und diese zum Debuggen des Codes verwenden. Sobald Sie das zum Anhängen des Prozesses verwendete Dialogfeld verlassen haben, befinden Sie sich im Debugmodus. Dann kann der Dienst mit dem Dienststeuerungs-Manager gestartet, beendet, angehalten und fortgesetzt werden, sodass die festgelegten Haltepunkte angesteuert werden. Nach erfolgreichem Debuggen kann der Dummydienst entfernt werden.  
  
 Dieser Artikel umfasst das Debuggen eines Dienstes, der auf dem lokalen Computer ausgeführt wird, aber Sie können auch Windows-Dienste debuggen, die auf einem Remotecomputer ausgeführt werden. Finden Sie unter [Remotedebuggen](/visualstudio/debugger/debug-installed-app-package).  
  
> [!NOTE]
>  Das Debuggen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode kann Schwierigkeiten bereiten, da vom Dienststeuerungs-Manager ein Limit von 30 Sekunden für alle Versuche erzwungen wird, einen Dienst zu starten. Weitere Informationen finden Sie unter [Problembehandlung: Debuggen von Windows-Diensten](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).  
  
> [!WARNING]
>  Um aussagekräftige Informationen für das Debuggen zu erhalten, muss der Visual Studio-Debugger Symboldateien für die Binärdateien finden, die gerade gedebuggt werden. Wenn Sie einen Dienst debuggen, den Sie in Visual Studio erstellt haben, befinden sich die Symboldateien (PDB-Dateien) in demselben Ordner wie die ausführbare Datei oder Bibliothek, und der Debugger lädt diese automatisch. Wenn Sie einen Dienst debuggen, den Sie erstellt haben, sollten Sie zuerst die Symbole für den Dienst suchen und sicherstellen, dass sie vom Debugger gefunden werden können. Finden Sie unter [angeben von Symbol(PDB)- und Quelldateien](http://msdn.microsoft.com/library/1105e169-5272-4e7c-b3e7-cda1b7798a6b). Wenn Sie einen Systemprozess debuggen oder Symbole für Systemaufrufe in Ihren Diensten haben möchten, sollten Sie die Microsoft-Symbolserver hinzufügen. Finden Sie unter [Debugsymbole](http://msdn.microsoft.com/windows/desktop/ee416588.aspx).  
  
### <a name="to-debug-a-service"></a>So debuggen Sie einen Dienst  
  
1.  Erstellen Sie Ihren Dienst in der Debugkonfiguration.  
  
2.  Installieren Sie den Dienst. Weitere Informationen finden Sie unter [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
3.  Starten Sie den Dienst aus **Dienststeuerungs-Manager**, **Server-Explorer**, oder von Code. Weitere Informationen finden Sie unter [Vorgehensweise: Starten von Diensten](../../../docs/framework/windows-services/how-to-start-services.md).  
  
4.  Starten Sie Visual Studio mit Administratorrechten, damit Sie die Systemprozesse zuordnen können.  
  
5.  (Optional) Wählen Sie in der Visual Studio-Menüleiste **Tools**, **Optionen**. In der **Optionen** Dialogfeld Wählen Sie **Debuggen**, **Symbole**, wählen die **Microsoft-Symbolserver** Kontrollkästchen, und wählen Sie dann die **OK** Schaltfläche.  
  
6.  Wählen Sie in der Menüleiste **an den Prozess anhängen** aus der **Debuggen** oder **Tools** Menü. (Tastatur: Strg + Alt + P)  
  
     Die **Prozesse** Dialogfeld wird angezeigt.  
  
7.  Wählen Sie die **Prozesse aller Benutzer anzeigen** Kontrollkästchen.  
  
8.  In der **verfügbare Prozesse** Abschnitt, wählen Sie den Prozess für den Dienst, und wählen Sie dann **Anfügen**.  
  
    > [!TIP]
    >  Der Prozess weist den gleichen Namen wie die ausführbare Datei für den Dienst auf.  
  
     Das Dialogfeld **An den Prozess anhängen** wird angezeigt.  
  
9. Wählen Sie die gewünschten Optionen aus, und wählen Sie dann **OK** um das Dialogfeld zu schließen.  
  
    > [!NOTE]
    >  Sie befinden sich jetzt im Debugmodus.  
  
10. Legen Sie die Haltepunkte fest, die im Code verwendet werden sollen.  
  
11. Öffnen Sie den Dienststeuerungs-Manager und bearbeiten Sie den Dienst, indem Sie Befehle zum Beenden, Anhalten und Fortsetzen ausgeben, um die festgelegten Haltepunkte anzusteuern. Weitere Informationen zum Ausführen des Dienststeuerungs-Managers finden Sie unter [Vorgehensweise: Starten von Diensten](../../../docs/framework/windows-services/how-to-start-services.md). Siehe auch [Problembehandlung: Debuggen von Windows-Diensten](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).  
  
## <a name="debugging-tips-for-windows-services"></a>Tipps zum Debuggen für Windows-Dienste  
 Durch das Anfügen an den Prozess des Dienstes können Sie die meisten, aber nicht alle, Codes für diesen Dienst debuggen. Z. B. weil der Dienst bereits gestartet wurde, können Sie den Code in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode des Dienstes oder den Code in der `Main`-Methode nicht debuggen, die verwendet wird, um den Dienst auf diese Weise zu lassen. Dies kann dadurch umgangen werden, dass ein zweiter temporärer Dienst in der Dienstanweisung erstellt wird, der lediglich als Hilfsmittel für das Debuggen verwendet wird. Beide Dienste können installiert werden. Anschließend wird der Dienstprozess geladen, indem der "Dummydienst" gestartet wird. Nachdem vom temporäre Dienst den Prozess gestartet wurde, können Sie die **Debuggen** Menü in Visual Studio an den Dienstprozess anfügen.  
  
 Versuchen Sie, Aufrufe an die <xref:System.Threading.Thread.Sleep%2A>-Methode zur Verzögerung der Aktion hinzuzufügen, bis Sie sie an den Prozess anfügen können.  
  
 Versuchen Sie, das Programm in eine reguläre Konsolenanwendung umzuwandeln. Dazu schreiben Sie die `Main`-Methode wie folgt um, damit sie sowohl als Windows-Dienst als auch als Konsolenanwendung ausgeführt werden kann, je nachdem, wie sie gestartet wird.  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a>Vorgehensweise: Ausführen eines Windows-Dienstes als Konsolenanwendung  
  
1.  Fügen Sie eine Methode zu Ihrem Dienst hinzu, die die Methoden <xref:System.ServiceProcess.ServiceBase.OnStart%2A> und <xref:System.ServiceProcess.ServiceBase.OnStop%2A> ausführt:  
  
    ```  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2.  Schreiben Sie die `Main`-Methode wie folgt um:  
  
    ```  
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
    ```  
  
3.  In der **Anwendung** der Projekteigenschaften auf der Registerkarte legen Sie die **Ausgabetyp** auf **Konsolenanwendung**.  
  
4.  Wählen Sie **Starten des Debuggens** (F5).  
  
5.  Wenn Sie das Programm als Windows-Dienst ausführen, installieren Sie es, und starten Sie sie wie gewohnt für einen Windows-Dienst. Es ist nicht notwendig, diese Änderungen rückgängig zu machen.  
  
 In einigen Fällen, z. B. beim Debuggen eines Problems, das nur beim Systemstart auftritt, müssen Sie den Windows-Debugger verwenden. Installieren Sie [Debugtools für Windows](http://msdn.microsoft.com/windows/hardware/hh852365) und finden Sie unter [zum Debuggen von Windows-Dienste](http://support.microsoft.com/kb/824344).  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Vorgehensweise: Installieren und Deinstallieren von Diensten](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [Vorgehensweise: Starten von Diensten](../../../docs/framework/windows-services/how-to-start-services.md)  
 [Debuggen eines Diensts](http://msdn.microsoft.com/library/windows/desktop/ms682546.aspx)
