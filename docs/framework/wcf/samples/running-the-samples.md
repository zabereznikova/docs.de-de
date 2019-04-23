---
title: Durchführen der Windows Communication Foundation-Beispiele
ms.date: 03/30/2017
ms.assetid: db8a83da-95c1-4a21-a9d2-48caeb6398ea
ms.openlocfilehash: b7a719aeeba2c14e79d790dfa5cbb4090d50009a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333144"
---
# <a name="running-the-windows-communication-foundation-samples"></a>Durchführen der Windows Communication Foundation-Beispiele
Die Windows Communication Foundation (WCF)-Beispiele können in einer Konfiguration mit einem einzelnen Computer oder computerübergreifend ausgeführt werden. Wie angegeben, können die Beispiele auf einem einzelnen Computer ausgeführt werden. In einer computerübergreifenden Konfiguration ist es notwendig, die Konfigurationsdateieinstellungen des Beispiels zu ändern. Die folgenden Prozeduren erklären, wie ein Beispiel in einer Konfiguration mit einem einzelnen Computer und computerübergreifend ausgeführt wird. Beachten Sie, dass es Abweichungen in den Schritten für Dienste, die in Internetinformationsdiensten (IIS) gehostet werden, und den selbst gehosteten Diensten gibt. Die meisten Beispiele werden in IIS gehostet. Der Infodatei eines Beispiels können Sie entnehmen, wie das Beispiel gehostet wird.  
  
 Bei [!INCLUDE[wv](../../../../includes/wv-md.md)] erfordern Beispiele, die nicht in IIS gehostet werden, erweiterte Berechtigungen, um einen Listener mit "Http.sys" zu registrieren. Verwenden Sie Httpcfg.exe, um die Überwachungsadressen des Diensts mit dem Konto, unter dem der Dienst ausgeführt wird, zu registrieren, oder starten Sie den Dienst an einer Eingabeaufforderung, die mit Administratorrechten ausgeführt wird.  
  
> [!NOTE]
>  Vor dem Erstellen, oder der WCF-Beispiele ausführen, achten Sie darauf durchgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-machine"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1. Wenn der Dienst von IIS gehostet wird, stellen Sie sicher, dass Sie den Dienst, der über einen Browser unter Eingabe der folgenden Adresse zugreifen können: `http://localhost/servicemodelsamples/service.svc`. Als Antwort sollte eine Bestätigungsseite angezeigt werden. Wenn die Seite "Bestätigung" nicht angezeigt wird, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
2. Wenn der Dienst selbst gehostet ist, führen Sie "Service.exe" aus "\service\bin" im sprachspezifischen Ordner aus. Im Dienstkonsolenfenster wird die Dienstaktivität angezeigt.  
  
3. Führen Sie Client.exe aus \client\bin\\, unter dem sprachspezifischen Ordner. Im Clientkonsolenfenster wird die Clientaktivität angezeigt.  
  
4. Wenn der Client und Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-machines"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1. Wenn der Dienst in IIS gehostet wird:  
  
    1.  Erstellen Sie auf dem Dienstcomputer ein virtuelles Verzeichnis namens "ServiceModelSamples". Die Batchdatei Setupvroot.bat in enthaltenen [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) kann zum Erstellen des festplattenverzeichnisses und des virtuellen Verzeichnisses verwendet werden.  
  
    2.  Kopieren Sie die Dienstprogrammdateien aus %SystemDrive%\Inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis "ServiceModelSamples" auf dem Dienstcomputer. Stellen Sie sicher, dass Sie die Dateien in das Verzeichnis \bin einfügen können.  
  
    3.  Testen Sie, ob Sie mit einem Browser vom Clientcomputer auf den Dienst zugreifen können.  
  
     Wenn der Dienst selbst gehostet wird:  
  
    1.  Erstellen Sie auf dem Dienstcomputer ein Verzeichnis, das die Dienstdateien enthalten soll.  
  
    2.  Kopieren Sie die Dienstprogrammdateien aus dem Ordner "\service\bin\" (unterhalb des sprachspezifischen Ordners) auf den Dienstcomputer.  
  
    3.  Ändern Sie in der Dienstkonfigurationsdatei den Wert für die Adresse der Endpunktdefinition so, dass er mit der neuen Adresse Ihres Diensts übereinstimmt. Ersetzen Sie alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.  
  
    4.  Führen Sie an einer Eingabeaufforderung "Service.exe" aus.  
  
2. Kopieren Sie die Clientprogrammdateien aus dem Ordner "\client\bin\" (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.  
  
3. Richten Sie die Endpunktadresse ein.  
  
    1.  Wenn der Dienst nicht unter einem Domänenkonto ausgeführt wird, öffnen Sie die Konfigurationsdatei, und ändern Sie den Wert für die Adresse der Endpunktdefinition so, dass er mit der neuen Adresse Ihres Diensts übereinstimmt. Ersetzen Sie alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.  
  
    2.  Wenn der Dienst unter einem Domänenkonto ausgeführt wird, generieren Sie die Clientkonfiguration neu, indem Sie "Svcutil.exe" für den Dienst ausführen. Weitere Informationen zum Ausführen von Svcutil.exe finden Sie unter [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md). Verwenden Sie die generierte Datei statt der Konfigurationsdatei im Beispiel. Die generierte Konfigurationsdatei verfügt über zusätzliche Identitätsinformationen und enthält alle Einstellungen, die notwendig sind, um eine Verbindung zum Dienstendpunkt aufzubauen, auch wenn diese die Standardeinstellungen sind. Weitere Informationen zu Identitätsinformationen finden Sie unter [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md), und [ \<Identität >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md).  
  
4. Starten Sie auf dem Clientcomputer in einer Eingabeaufforderung die Datei "Client.exe".  
  
### <a name="to-debug-a-service"></a>So debuggen Sie einen Dienst  
  
1. Erstellen der Projektmappe (Client und Dienst) mit der **erstellen** Menü- oder STRG + UMSCHALT + B.  
  
2. Wenn der Dienst in IIS gehostet wird:  
  
    1.  Aktivieren Sie den Dienst über einen Browser unter Eingabe der Adresse `http://localhost/servicemodelsamples/service.svc`.  
  
    2.  Wählen Sie in der Projektmappe die **Debuggen** Menü und die **an den Prozess anhängen** Menüelement.  
  
    3.  Aktivieren Sie das Kontrollkästchen **Prozesse aller Benutzer anzeigen**.  
  
    4.  Wählen Sie zum Debuggen den Hostarbeitsprozess „W3wp.exe“ aus (unter Windows XP wählen Sie „ASPNet_wp.exe“ aus).  
  
3. Sie können jetzt Haltepunkte im Dienstcode festlegen und Haltepunkte für Ausnahmen aktivieren.  
  
4. Mit der rechten Maustaste in des clientprojektelement, und wählen Sie **Debuggen**, **neue Instanz starten**.  
  
### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
-   Wenn der Dienst in IIS gehostet wird, entfernen Sie aus Sicherheitsgründen die Definition des virtuellen Verzeichnisses und die in den Setupschritten gewährten Berechtigungen, wenn Sie die Beispiele abgeschlossen haben.  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md)
- [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))
