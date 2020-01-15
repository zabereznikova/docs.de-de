---
title: 'Gewusst wie: Installieren und Konfigurieren von WCF-Aktivierungskomponenten'
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: e71664b4361ba28a50b29499585b20a8adbaefd2
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964465"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a>Gewusst wie: Installieren und Konfigurieren von WCF-Aktivierungskomponenten

In diesem Thema werden die Schritte beschrieben, die zum Einrichten von Windows Process Activation Service (auch bekannt als was) unter Windows Vista erforderlich sind, um Windows Communication Foundation (WCF)-Dienste zu hosten, die nicht über HTTP-Netzwerkprotokolle kommunizieren. In den folgenden Abschnitten werden die für diese Konfiguration erforderlichen Schritte kurz beschrieben:

- Installieren (oder bestätigen Sie die Installation von) der WCF-Aktivierungs Komponenten.

- Konfigurieren Sie WAS, sodass Nicht-HTTP-Protokolle unterstützt werden. Mit dem folgenden Verfahren wird Windows Vista für die TCP-Aktivierung konfiguriert.

Nach der Installation und Konfiguration von was finden Sie unter Gewusst [wie: Hosten eines WCF-Diensts in was](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) die Verfahren zum Erstellen eines WCF-Diensts, der einen nicht-HTTP-Endpunkt bereitstellt, der was verwendet.

## <a name="to-install-the-wcf-non-http-activation-components"></a>So installieren Sie die WCF-Aktivierungskomponenten für andere Protokolle als HTTP

1. Klicken Sie auf die Schaltfläche **Start** und dann auf **Systemsteuerung**.

2. Klicken Sie auf **Programme** und dann auf **Programme und Funktionen**.

3. Klicken Sie im Menü **Aufgaben** auf **Windows-Funktionen ein-oder ausschalten**.

4. Suchen Sie den Knoten WinFX, wählen Sie ihn aus, und erweitern Sie ihn.

5. Aktivieren Sie das Kontrollkästchen **WCF-nicht-http-Aktivierungs Komponenten** , und speichern Sie die Einstellung.

## <a name="to-configure-the-was-to-support-tcp-activation"></a>So konfigurieren Sie den WAS, sodass die TCP-Aktivierung unterstützt wird

1. Zur Unterstützung der net.tcp-Aktivierung muss die Standardwebsite zuerst an einen net.tcp-Port gebunden werden. Hierfür können Sie Appcmd. exe verwenden, das mit dem IIS 7,0-Verwaltungs Toolset installiert wird. Führen Sie in einem Eingabeaufforderungsfenster auf Administratorebene den folgenden Befehl aus.

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > Dieser Befehl ist eine einzelne Textzeile. Mit dem Befehl wird eine neue net.tcp-Sitebindung der Standardwebsite hinzugefügt, die TCP-Anschluss 808 mit jedem beliebigen Hostnamen überwacht.

2. Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.tcp-Bindung, aber jede Anwendung kann die net.tcp-Unterstützung unabhängig von den anderen Anwendungen aktivieren. Um net.tcp für die Anwendung zu aktivieren, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp
    ```

    > [!NOTE]
    > Dieser Befehl ist eine einzelne Textzeile. Mit diesem Befehl wird der Zugriff auf die Anwendung "/\<*WCF-Anwendung*> mithilfe von `http://localhost/<WCF Application>` und `net.tcp://localhost/<WCF Application>`ermöglicht.

     Entfernen Sie die net.tcp-Sitebindung, die für dieses Beispiel hinzugefügt wurde.

     Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveNetTcpSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.

    1. Entfernen Sie net.tcp aus der Liste aktivierter Protokolle, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
        ```

        > [!NOTE]
        > Dieser Befehl ist eine einzelne Textzeile.

    2. Entfernen Sie die net.tcp-Sitebindung, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen:

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > Dieser Befehl ist eine einzelne Textzeile.

## <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a>So entfernen Sie net.tcp aus der Liste aktivierter Protokolle

1. Um net.tcp aus der Liste aktivierter Protokolle zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
    ```

    > [!NOTE]
    > Dieser Befehl ist eine einzelne Textzeile.

## <a name="to-remove-the-nettcp-site-binding"></a>So entfernen Sie die net.tcp-Bindung

1. Um die net.tcp-Sitebindung zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
    -bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > Dieser Befehl ist eine einzelne Textzeile.

## <a name="see-also"></a>Siehe auch

- [TCP-Aktivierung](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [MSMQ-Aktivierung](../../../../docs/framework/wcf/samples/msmq-activation.md)
- [NamedPipe-Aktivierung](../../../../docs/framework/wcf/samples/namedpipe-activation.md)
- [Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
