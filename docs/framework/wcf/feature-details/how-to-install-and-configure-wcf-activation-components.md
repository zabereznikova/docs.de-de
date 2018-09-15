---
title: 'Gewusst wie: Installieren und Konfigurieren von WCF-Aktivierungskomponenten'
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 8b516bb4603f33828069b5356676d8b35dc961d2
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2018
ms.locfileid: "45646583"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a>Gewusst wie: Installieren und Konfigurieren von WCF-Aktivierungskomponenten
Dieses Thema beschreibt die erforderlichen Schritte zum Einrichten der Windows Process Activation Service (auch bekannt als "WAS") auf [!INCLUDE[wv](../../../../includes/wv-md.md)] zum Hosten von Windows Communication Foundation (WCF) Dienste, die nicht über HTTP kommunizieren die Netzwerkprotokolle. In den folgenden Abschnitten werden die für diese Konfiguration erforderlichen Schritte kurz beschrieben:  
  
-   Installieren (oder bestätigen Sie die Installation von) die WCF-aktivierungskomponenten.  
  
-   Konfigurieren Sie WAS, sodass Nicht-HTTP-Protokolle unterstützt werden. Mit den folgenden Schritten wird [!INCLUDE[wv](../../../../includes/wv-md.md)] für die TCP-Aktivierung konfiguriert.  
  
 Nach der Installation und Konfiguration von WAS finden Sie [Vorgehensweise: Hosten eines WCF-Diensts in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) für die Prozeduren zum Erstellen eines WCF-Diensts, die einen nicht-HTTP-Endpunkt verfügbar macht, der mit WAS arbeitet.  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a>So installieren Sie die WCF-Aktivierungskomponenten für andere Protokolle als HTTP  
  
1.  Klicken Sie auf die **starten** Schaltfläche, und klicken Sie dann auf **Systemsteuerung**.  
  
2.  Klicken Sie auf **Programme**, und klicken Sie dann auf **Programme und Funktionen**.  
  
3.  Auf der **Aufgaben** Menü klicken Sie auf **Aktivieren von Windows-Funktionen ein- oder ausschalten**.  
  
4.  Suchen Sie den [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]-Knoten, markieren Sie ihn, und erweitern Sie ihn dann.  
  
5.  Wählen Sie die **WCF-Aktivierungskomponenten für nicht-HTTP-** und speichern Sie die Einstellung.  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a>So konfigurieren Sie den WAS, sodass die TCP-Aktivierung unterstützt wird  
  
1.  Zur Unterstützung der net.tcp-Aktivierung muss die Standardwebsite zuerst an einen net.tcp-Port gebunden werden. Sie können hierzu das Tool Appcmd.exe verwenden, das mit dem [!INCLUDE[iisver](../../../../includes/iisver-md.md)]-Verwaltungstoolset installiert wird. Führen Sie in einem Eingabeaufforderungsfenster auf Administratorebene den folgenden Befehl aus.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Dieser Befehl ist eine einzelne Textzeile. Mit dem Befehl wird eine neue net.tcp-Sitebindung der Standardwebsite hinzugefügt, die TCP-Anschluss 808 mit jedem beliebigen Hostnamen überwacht.  
  
2.  Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.tcp-Bindung, aber jede Anwendung kann die net.tcp-Unterstützung unabhängig von den anderen Anwendungen aktivieren. Um net.tcp für die Anwendung zu aktivieren, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  Dieser Befehl ist eine einzelne Textzeile. Mit diesem Befehl wird die /\<*WCF-Anwendung*> Anwendung zugegriffen werden kann mit beiden `http://localhost/<WCF Application>` und `net.tcp://localhost/<WCF Application>`.
  
     Entfernen Sie die net.tcp-Sitebindung, die für dieses Beispiel hinzugefügt wurde.  
  
     Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveNetTcpSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.  
  
    1.  Entfernen Sie net.tcp aus der Liste aktivierter Protokolle, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Dieser Befehl ist eine einzelne Textzeile.  
  
    2.  Entfernen Sie die net.tcp-Sitebindung, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  Dieser Befehl ist eine einzelne Textzeile.  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a>So entfernen Sie net.tcp aus der Liste aktivierter Protokolle  
  
1.  Um net.tcp aus der Liste aktivierter Protokolle zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  Dieser Befehl ist eine einzelne Textzeile.  
  
### <a name="to-remove-the-nettcp-site-binding"></a>So entfernen Sie die net.tcp-Bindung  
  
1.  Um die net.tcp-Sitebindung zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Dieser Befehl ist eine einzelne Textzeile.  
  
## <a name="see-also"></a>Siehe auch  
 [TCP-Aktivierung](../../../../docs/framework/wcf/samples/tcp-activation.md)  
 [MSMQ-Aktivierung](../../../../docs/framework/wcf/samples/msmq-activation.md)  
 [NamedPipe-Aktivierung](../../../../docs/framework/wcf/samples/namedpipe-activation.md)  
 [Windows Server AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=201276)
