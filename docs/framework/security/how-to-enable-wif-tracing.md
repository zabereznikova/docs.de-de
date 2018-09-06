---
title: 'Gewusst wie: Aktivieren der WIF-Ablaufverfolgung'
ms.date: 03/30/2017
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 17650e06cb505dd778a9c0980c2a32fda8099cb4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856240"
---
# <a name="how-to-enable-wif-tracing"></a>Gewusst wie: Aktivieren der WIF-Ablaufverfolgung
## <a name="applies-to"></a>Gilt für  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   ASP.NET® Web Forms  
  
## <a name="summary"></a>Zusammenfassung  
 In dieser Vorgehensweise werden ausführliche schrittweise Prozeduren zum Aktivieren von WIF-Ablaufverfolgung in einer ASP.NET-Anwendung vorgestellt. Außerdem werden Anweisungen für den Test der Anwendung gegeben, mit dem geprüft wird, ob der Ablaufverfolgungslistener und das Protokoll ordnungsgemäß funktionieren. Diese Vorgehensweise enthält keine ausführlichen Anweisungen zum Erstellen eines Sicherheitstokendiensts (STS). Stattdessen wird der Entwicklungs-STS verwendet, der aus dem Identitäts- und Zugriffstool stammt. Der Entwicklungs-STS führt keine echte Authentifizierung durch und ist nur für Testzwecke vorgesehen. Sie müssen das Identitäts- und Zugriffs-Tool installieren, um diese Vorgehensweise nachzuvollziehen. Es kann auf der folgenden Seite heruntergeladen werden: [Identity and Access Tool (Identitäts- und Zugriffstool)](https://go.microsoft.com/fwlink/?LinkID=245849)  
  
> [!IMPORTANT]
>  Wenn die WIF-Ablaufverfolgung für passive Anwendungen, also Anwendungen, die das WS-Verbundprotokoll verwenden, aktiviert wird, kann die Anwendung DoS-Angriffen (DoS, Denial of Services) ausgesetzt sein oder Informationen könnten für nicht vertrauenswürdige Seiten mit böswilligen Absichten verfügbar werden. Dazu gehören auch passive vertrauende Seiten und passive STS. Aus diesem Grund wird empfohlen, keine WIF-Ablaufverfolgung für passive vertrauende Seiten oder STS in einer Produktionsumgebung zu aktivieren.  
  
## <a name="contents"></a>Inhalt  
  
-   Ziele  
  
-   Übersicht  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1 – Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Ablaufverfolgung  
  
-   Schritt 2 – Testen der Projektmappe  
  
## <a name="objectives"></a>Ziele  
  
-   Erstellen einer einfachen ASP.NET-Anwendung, die WIF und den Entwicklungs-STS aus dem Identitäts- und Zugriffs-Tool verwendet  
  
-   Aktivieren der Ablaufverfolgung und Überprüfen der Funktion  
  
## <a name="overview"></a>Übersicht  
 Mit Ablaufverfolgung können Sie viele Arten von Problemen mit WIF, einschließlich Token, Cookies, Ansprüche, Protokollmeldungen usw. debuggen und Fehler daran beheben. WIF-Ablaufverfolgung ähnelt der WCF-Ablaufverfolgung; Sie können beispielsweise den Ausführlichkeitsgrad von Ablaufverfolgungen auswählen, um Meldungen von kritischen Meldungen bis hin zu allen Meldungen anzuzeigen. WIF-Ablaufverfolgungen können in **XML**-Dateien oder in **SVCLOG**-Dateien generiert werden, die mit dem Service Trace Viewer-Tool angezeigt werden können. Dieses Tool befindet sich im Verzeichnis **bin** im Windows SDK-Installationspfad auf dem Computer, beispielsweise: **C:\Programme\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.  
  
## <a name="summary-of-steps"></a>Zusammenfassung von Schritten  
  
-   Schritt 1 – Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Ablaufverfolgung  
  
-   Schritt 2 – Testen der Projektmappe  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-tracing"></a>Schritt 1 – Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Ablaufverfolgung  
 In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung und ändern die Datei *Web.config*, um die Ablaufverfolgung zu aktivieren.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>So erstellen Sie eine einfache ASP.NET-Anwendung  
  
1.  Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu** und anschließend auf **Projekt**.  
  
2.  Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.  
  
3.  Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.  
  
4.  Klicken Sie mit der rechten Maustaste unter **Projektmappen-Explorer** auf das Projekt **TestApp**, und wählen Sie anschließend **Identität und Zugriff** aus.  
  
5.  Das Fenster **Identität und Zugriff** wird geöffnet. Klicken Sie unter **Anbieter** auf **Test your application with the Local Development STS** (Anwendung mit dem lokalen Entwicklungs-STS testen), und klicken Sie anschließend auf **Übernehmen**.  
  
6.  Erstellen Sie wie hier dargestellt im Stamm des Laufwerks **C:** einen neuen Ordner mit dem Namen **logs**: **C:\logs**.  
  
7.  Fügen Sie der Konfigurationsdatei *Web.config* direkt nach dem schließenden **\</configSections>**-Element das folgende **\<system.diagnostics>**-Element wie dargestellt hinzu:  
  
    ```xml  
    <configuration>  
        <configSections>  
        …  
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  Der Verzeichnisspeicherort, der im Attribut **initializeData** angegeben wird, muss vorhanden sein, bevor die Protokollierung beginnen kann. Wenn der Speicherort nicht vorhanden ist, werden keine Protokolle erstellt.  
  
     Mit den oben erwähnten Konfigurationseinstellungen werden die **ausführliche** Ablaufverfolgung für WIF aktiviert und das resultierende Protokoll in der Datei **C:\logs\WIF.xml** gespeichert.  
  
## <a name="step-2--test-your-solution"></a>Schritt 2 – Testen der Projektmappe  
 In diesem Schritt testen Sie die für WIF aktivierte ASP.NET-Anwendung, um zu überprüfen, ob Protokolle aufgezeichnet werden.  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-successful-tracing"></a>So testen Sie die für WIF aktivierte ASP.NET-Anwendung auf erfolgreiche Ablaufverfolgung  
  
1.  Starten Sie die Projektmappe durch Drücken der Taste **F5**. Die Standard-Homepage von ASP.NET wird angezeigt. Sie werden automatisch mit dem Benutzernamen *Terry* authentifiziert. Dies ist der Standardbenutzer, der vom Entwicklungs-STS zurückgegeben wird.  
  
2.  Schließen Sie das Browserfenster, und navigieren Sie dann zum Ordner **C:\logs**. Öffnen Sie die Datei **C:\logs\WIF.xml** in einem Text-Editor.  
  
3.  Überprüfen Sie, ob die Datei **WIF.xml** Einträge enthält, die mit **\<E2ETraceEvent>** beginnen. Diese Ablaufverfolgungen enthalten **\<TraceRecord>**-Elemente mit Beschreibungen für die aufgezeichnete Aktivität, z. B. **Sicherheitstoken wird überprüft**.
