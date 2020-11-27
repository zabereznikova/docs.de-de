---
title: Durchführen der Windows Communication Foundation-Beispiele
ms.date: 03/30/2017
ms.assetid: db8a83da-95c1-4a21-a9d2-48caeb6398ea
ms.openlocfilehash: 3a12128541739ba5c380be2efc291b9b419cab12
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262670"
---
# <a name="running-the-windows-communication-foundation-samples"></a>Durchführen der Windows Communication Foundation-Beispiele

Die Windows Communication Foundation (WCF)-Beispiele können in einer Konfiguration mit einem einzelnen Computer oder Computer übergreifend ausgeführt werden. Wie angegeben, können die Beispiele auf einem einzelnen Computer ausgeführt werden. In einer computerübergreifenden Konfiguration ist es notwendig, die Konfigurationsdateieinstellungen des Beispiels zu ändern. Die folgenden Prozeduren erklären, wie ein Beispiel in einer Konfiguration mit einem einzelnen Computer und computerübergreifend ausgeführt wird. Beachten Sie, dass es Abweichungen in den Schritten für Dienste, die in Internetinformationsdiensten (IIS) gehostet werden, und den selbst gehosteten Diensten gibt. Die meisten Beispiele werden in IIS gehostet. Der Infodatei eines Beispiels können Sie entnehmen, wie das Beispiel gehostet wird.  
  
 In Windows Vista erfordern Beispiele, die nicht in IIS gehostet werden, erhöhte Berechtigungen, um einen Listener bei Http.sys zu registrieren. Verwenden Sie Httpcfg.exe, um die Überwachungsadressen des Diensts mit dem Konto, unter dem der Dienst ausgeführt wird, zu registrieren, oder starten Sie den Dienst an einer Eingabeaufforderung, die mit Administratorrechten ausgeführt wird.  
  
> [!NOTE]
> Stellen Sie vor dem Erstellen oder Ausführen eines der WCF-Beispiele sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
### <a name="to-run-the-sample-on-the-same-machine"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1. Wenn der Dienst von IIS gehostet wird, stellen Sie sicher, dass Sie über einen Browser auf den Dienst zugreifen können, indem Sie die folgende Adresse eingeben: `http://localhost/servicemodelsamples/service.svc` . Als Antwort sollte eine Bestätigungsseite angezeigt werden. Wenn die Bestätigungsseite nicht angezeigt wird, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
2. Wenn der Dienst selbst gehostet ist, führen Sie "Service.exe" aus "\service\bin" im sprachspezifischen Ordner aus. Im Dienstkonsolenfenster wird die Dienstaktivität angezeigt.  
  
3. Führen Sie Client.exe aus dem Ordner "\client\bin" \\ unter dem sprachspezifischen Ordner aus. Im Clientkonsolenfenster wird die Clientaktivität angezeigt.  
  
4. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
### <a name="to-run-the-sample-across-machines"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1. Wenn der Dienst in IIS gehostet wird:  
  
    1. Erstellen Sie auf dem Dienstcomputer ein virtuelles Verzeichnis namens "ServiceModelSamples". Die Batchdatei Setupvroot.bat, die im [einmaligen Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md) enthalten ist, kann zum Erstellen des Datenträger Verzeichnisses und des virtuellen Verzeichnisses verwendet werden.  
  
    2. Kopieren Sie die Dienstprogrammdateien aus %SystemDrive%\Inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis "ServiceModelSamples" auf dem Dienstcomputer. Stellen Sie sicher, dass Sie die Dateien in das Verzeichnis \bin einfügen können.  
  
    3. Testen Sie, ob Sie mit einem Browser vom Clientcomputer auf den Dienst zugreifen können.  
  
     Wenn der Dienst selbst gehostet wird:  
  
    1. Erstellen Sie auf dem Dienstcomputer ein Verzeichnis, das die Dienstdateien enthalten soll.  
  
    2. Kopieren Sie die Dienstprogrammdateien aus dem Ordner "\service\bin\" (unterhalb des sprachspezifischen Ordners) auf den Dienstcomputer.  
  
    3. Ändern Sie in der Dienstkonfigurationsdatei den Wert für die Adresse der Endpunktdefinition so, dass er mit der neuen Adresse Ihres Diensts übereinstimmt. Ersetzen Sie alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.  
  
    4. Führen Sie an einer Eingabeaufforderung "Service.exe" aus.  
  
2. Kopieren Sie die Clientprogrammdateien aus dem Ordner "\client\bin\" (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.  
  
3. Richten Sie die Endpunktadresse ein.  
  
    1. Wenn der Dienst nicht unter einem Domänenkonto ausgeführt wird, öffnen Sie die Konfigurationsdatei, und ändern Sie den Wert für die Adresse der Endpunktdefinition so, dass er mit der neuen Adresse Ihres Diensts übereinstimmt. Ersetzen Sie alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.  
  
    2. Wenn der Dienst unter einem Domänenkonto ausgeführt wird, generieren Sie die Clientkonfiguration neu, indem Sie "Svcutil.exe" für den Dienst ausführen. Weitere Informationen zum Ausführen von Svcutil.exe finden Sie unter [Building the Windows Communication Foundation Samples](building-the-samples.md). Verwenden Sie die generierte Datei statt der Konfigurationsdatei im Beispiel. Die generierte Konfigurationsdatei verfügt über zusätzliche Identitätsinformationen und enthält alle Einstellungen, die notwendig sind, um eine Verbindung zum Dienstendpunkt aufzubauen, auch wenn diese die Standardeinstellungen sind. Weitere Informationen zu Identitätsinformationen finden Sie unter [Dienst Identität und-Authentifizierung](../feature-details/service-identity-and-authentication.md)und [\<identity>](../../configure-apps/file-schema/wcf/identity.md) .  
  
4. Starten Sie auf dem Clientcomputer in einer Eingabeaufforderung die Datei "Client.exe".  
  
### <a name="to-debug-a-service"></a>So debuggen Sie einen Dienst  
  
1. Erstellen Sie die Projekt Mappe (Client und Dienst) über das Menü **Build** oder STRG + UMSCHALT + B.  
  
2. Wenn der Dienst in IIS gehostet wird:  
  
    1. Aktivieren Sie den Dienst mithilfe eines Browsers, indem Sie die Adresse eingeben `http://localhost/servicemodelsamples/service.svc` .  
  
    2. Wählen Sie in der Projekt Mappe das Menü **Debuggen** und das Menü Element **an den Prozess anhängen** aus.  
  
    3. Aktivieren Sie das Kontrollkästchen **Prozesse aller Benutzer anzeigen**.  
  
    4. Wählen Sie zum Debuggen den Hostarbeitsprozess „W3wp.exe“ aus (unter Windows XP wählen Sie „ASPNet_wp.exe“ aus).  
  
3. Sie können jetzt Haltepunkte im Dienstcode festlegen und Haltepunkte für Ausnahmen aktivieren.  
  
4. Klicken Sie mit der rechten Maustaste auf das Client Projekt Element, und wählen Sie **Debuggen**, **neue Instanz starten**  
  
### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
- Wenn der Dienst in IIS gehostet wird, entfernen Sie aus Sicherheitsgründen die Definition des virtuellen Verzeichnisses und die in den Setupschritten gewährten Berechtigungen, wenn Sie die Beispiele abgeschlossen haben.  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen der Windows Communication Foundation-Beispiele](building-the-samples.md)
- [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))
