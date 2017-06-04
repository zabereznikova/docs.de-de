---
title: "Gewusst wie: Installieren und Konfigurieren von WCF-Aktivierungskomponenten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "HTTP-Aktivierung [WCF]"
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Gewusst wie: Installieren und Konfigurieren von WCF-Aktivierungskomponenten
In diesem Thema werden die Schritte vorgestellt, mit denen der Windows\-Prozessaktivierungsdienst \(auch WAS für Windows Process Activation Service genannt\) in [!INCLUDE[wv](../../../../includes/wv-md.md)] als Host für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienste, die nicht über HTTP\-Netzwerkprotokolle kommunizieren, konfiguriert wird.In den folgenden Abschnitten werden die für diese Konfiguration erforderlichen Schritte kurz beschrieben:  
  
-   Installieren Sie die \(oder bestätigen Sie die Installation der\) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Aktivierungskomponenten.  
  
-   Konfigurieren Sie WAS, sodass Nicht\-HTTP\-Protokolle unterstützt werden.Mit den folgenden Schritten wird [!INCLUDE[wv](../../../../includes/wv-md.md)] für die TCP\-Aktivierung konfiguriert.  
  
 Nachdem Sie WAS installiert und konfiguriert haben, finden Sie unter [Gewusst wie: Hosten eines WCF\-Diensts in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) Verfahren zum Erstellen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts, der einen mit WAS arbeitenden Nicht\-HTTP\-Endpunkt verfügbar macht.  
  
### So installieren Sie die WCF\-Aktivierungskomponenten für andere Protokolle als HTTP  
  
1.  Klicken Sie auf die Schaltfläche **Start** und anschließend auf **Systemsteuerung**.  
  
2.  Klicken Sie auf **Programme**, und klicken Sie dann auf **Programme und Funktionen**.  
  
3.  Klicken Sie im Menü **Aufgaben** auf **Windows\-Funktionen ein\- oder ausschalten**.  
  
4.  Suchen Sie den [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]\-Knoten, markieren Sie ihn, und erweitern Sie ihn dann.  
  
5.  Aktivieren Sie das Feld **Nicht\-HttpAktivierungskomponenten von WCF**, und speichern Sie die Einstellung.  
  
### So konfigurieren Sie den WAS, sodass die TCP\-Aktivierung unterstützt wird  
  
1.  Zur Unterstützung der net.tcp\-Aktivierung muss die Standardwebsite zuerst an einen net.tcp\-Anschluss gebunden werden.Sie können hierzu das Tool Appcmd.exe verwenden, das mit dem [!INCLUDE[iisver](../../../../includes/iisver-md.md)]\-Verwaltungstoolset installiert wird.Führen Sie in einem Eingabeaufforderungsfenster auf Administratorebene den folgenden Befehl aus.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Dieser Befehl ist eine einzelne Textzeile.Mit dem Befehl wird eine neue net.tcp\-Sitebindung der Standardwebsite hinzugefügt, die TCP\-Anschluss 808 mit jedem beliebigen Hostnamen belauscht.  
  
2.  Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.tcp\-Bindung, aber jede Anwendung kann die net.tcp\-Unterstützung unabhängig von den anderen Anwendungen aktivieren.Um net.tcp für die Anwendung zu aktivieren, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  Dieser Befehl ist eine einzelne Textzeile.Mit diesem Befehl wird die Anwendung \/\<*WCF Application*\> so konfiguriert, dass sowohl über http:\/\/localhost*\/\<WCF Application\>* als auch über net.tcp:\/\/localhost\/*\<WCF Application\>* darauf zugegriffen werden kann.  
  
     Entfernen Sie die net.tcp\-Sitebindung, die für dieses Beispiel hinzugefügt wurde.  
  
     Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveNetTcpSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.  
  
    1.  Entfernen Sie net.tcp aus der Liste aktivierter Protokolle, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Dieser Befehl ist eine einzelne Textzeile.  
  
    2.  Entfernen Sie die net.tcp\-Sitebindung, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  Dieser Befehl ist eine einzelne Textzeile.  
  
### So entfernen Sie net.tcp aus der Liste aktivierter Protokolle  
  
1.  Um net.tcp aus der Liste aktivierter Protokolle zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  Dieser Befehl ist eine einzelne Textzeile.  
  
### So entfernen Sie die net.tcp\-Bindung  
  
1.  Um die net.tcp\-Sitebindung zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Dieser Befehl ist eine einzelne Textzeile.  
  
## Siehe auch  
 [TCP\-Aktivierung](../../../../docs/framework/wcf/samples/tcp-activation.md)   
 [MSMQ\-Aktivierung](../../../../docs/framework/wcf/samples/msmq-activation.md)   
 [NamedPipe\-Aktivierung](../../../../docs/framework/wcf/samples/namedpipe-activation.md)   
 [Windows Server AppFabric\-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)