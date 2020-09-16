---
title: WCF-Diensthost (WcfSvcHost.exe)
description: Verwenden Sie den WCF-Dienst Host zum Hosten und Testen eines implementierten Diensts. Sie können den Dienst mit dem WCF-Test Client oder Ihrem eigenen Client testen.
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: 2ac1d6318d8a82a82c08f38305ee6f92ad3f52a2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544595"
---
# <a name="wcf-service-host-wcfsvchostexe"></a>WCF-Diensthost (WcfSvcHost.exe)

Mit Windows Communication Foundation (WCF)-Dienst Host (WcfSvcHost.exe) können Sie den Visual Studio-Debugger (F5) starten, um automatisch einen von Ihnen implementierten Dienst zu hosten und zu testen. Anschließend können Sie den Dienst mit dem WCF-Test Client (WcfTestClient.exe) oder Ihrem eigenen Client testen, um potenzielle Fehler zu finden und zu beheben.

## <a name="wcf-service-host"></a>WCF-Diensthost

Der WCF-Dienst Host listet die Dienste in einem WCF-Dienstprojekt auf, lädt die Konfiguration des Projekts und instanziiert einen Host für jeden gefundenen Dienst. Das Tool ist über die WCF-Dienst Vorlage in Visual Studio integriert und wird aufgerufen, wenn Sie mit dem Debuggen des Projekts beginnen.

Mithilfe des WCF-Dienst Hosts können Sie einen WCF-Dienst (in einem WCF-Dienst Bibliotheksprojekt) hosten, ohne zusätzlichen Code schreiben oder einen bestimmten Host während der Entwicklung ausführen zu müssen.

> [!NOTE]
> Der WCF-Dienst Host unterstützt keine teilweise Vertrauenswürdigkeit. Wenn Sie einen WCF-Dienst mit teilweiser Vertrauenswürdigkeit verwenden möchten, verwenden Sie nicht die WCF-Dienst Bibliothek-Projektvorlage in Visual Studio, um den Dienst zu erstellen. Erstellen Sie stattdessen eine neue Website in Visual Studio, indem Sie die Vorlage WCF-Dienst Website auswählen, die den Dienst auf einem Webserver hosten kann, auf dem eine teilweise vertrauenswürdige WCF-Funktion unterstützt wird.

## <a name="project-types-hosted-by-wcf-service-host"></a>Vom WCF-Diensthost gehostete Projekttypen

Der WCF-Dienst Host kann die folgenden WCF-Dienst Bibliotheksprojekt Typen hosten: WCF-Dienst Bibliothek, sequenzielle Workflow Dienst Bibliothek, Zustands Automat-Workflow Dienst Bibliothek und Syndizierungs Dienst Bibliothek. Der WCF-Dienst Host kann auch diese Dienste hosten, die einem Dienst Bibliotheksprojekt mithilfe der Funktion " **Element hinzufügen** " hinzugefügt werden können. Dies schließt den WCF-Dienst, den WF-zustandsautomatdienst, den sequenziellen WF-Dienst, den XAML-WF-zustandsautomatdienst und den sequenziellen

Beachten Sie jedoch, dass Sie mit dem Tool den Host nicht konfigurieren können. Zur Konfiguration müssen Sie die Datei App.config manuell bearbeiten. Mit dem Tool können Sie auch nicht benutzerdefinierte Konfigurationsdateien validieren.

> [!CAUTION]
> Der WCF-Dienst Host sollte nicht zum Hosten von Diensten in einer Produktionsumgebung verwendet werden, da er nicht zu diesem Zweck entwickelt wurde.  Der WCF-Dienst Host unterstützt nicht die Anforderungen an Zuverlässigkeit, Sicherheit und Verwaltbarkeit einer solchen Umgebung. Verwenden Sie stattdessen den IIS, da er über optimale Zuverlässigkeit und Überwachungsfunktionen verfügt und die bevorzugte Lösung für Hostdienste ist. Nachdem die Entwicklung der Dienste fertiggestellt wurde, sollten Sie die Dienste vom WCF-Dienst Host zu IIS migrieren.

## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Szenarien für die Verwendung des WCF-Diensthosts in Visual Studio

In der folgenden Tabelle sind alle Parameter im Dialogfeld **Befehlszeilenargumente** aufgeführt. Sie finden diese, indem Sie im Projektmappen- **Explorer** in Visual Studio mit der rechten Maustaste auf das Projekt klicken, **Eigenschaften**auswählen und dann die Registerkarte **Debuggen** und dann auf **Projekt starten**klicken. Diese Parameter sind nützlich beim Konfigurieren des WCF-Dienst Hosts.

|Parameter|Bedeutung|
|---------------|-------------|
|`/client`|Ein optionaler Parameter, der den Pfad zu einer EXE-Datei bestimmt, die nach dem Hosten der Dienste ausgeführt werden soll. Dadurch wird der WCF-Test Client nach dem Hosting gestartet.|
|`/clientArg`|Legt eine Zeichenfolge als Argument fest, das an die benutzerdefinierte Clientanwendung geleitet wird.|
|`/?`|Zeigt die Hilfe an.|

#### <a name="using-wcf-test-client"></a>Verwenden des WCF-Testclients

Nachdem Sie ein neues WCF-Dienstprojekt erstellt und F5 drücken, um den Debugger zu starten, beginnt der WCF-Dienst Host mit dem Hosten aller Dienste, die im Projekt gefunden werden. Der WCF-Test Client wird automatisch geöffnet, und es wird eine Liste der in der Konfigurationsdatei definierten Dienst Endpunkte angezeigt. Vom Hauptfenster aus können Sie die Parameter testen und den Dienst aufrufen.

Um sicherzustellen, dass der WCF-Test Client verwendet wird, klicken Sie im Projektmappen- **Explorer** in Visual Studio mit der rechten Maustaste **auf das Projekt** , wählen Sie **Eigenschaften**aus, und wählen Sie dann Klicken Sie auf **Projekt starten** , und vergewissern Sie sich, dass im Dialogfeld **Befehlszeilenargumente** Folgendes angezeigt wird.

`/client:WcfTestClient.exe`

#### <a name="using-a-custom-client"></a>Verwenden eines benutzerdefinierten Clients

Klicken Sie im Projektmappen- **Explorer** in Visual Studio mit der rechten Maustaste auf das Projekt, wählen Sie **Eigenschaften**aus, und wählen Sie dann die Registerkarte **Debuggen** Klicken Sie auf **Projekt starten** , und bearbeiten Sie den `/client` Parameter im Dialogfeld **Befehlszeilenargumente** , um auf den benutzerdefinierten Client zu verweisen, wie im folgenden Beispiel gezeigt.

`/client:"path/CustomClient.exe"`

Wenn Sie F5 drücken, um den Dienst erneut zu starten, startet der WCF-Dienst Host automatisch den benutzerdefinierten Client, wenn Sie den Debugger starten.

Mit dem `/clientArg:`-Parameter können Sie auch eine Zeichenfolge als Argument festlegen, das an die benutzerdefinierte Clientanwendung geleitet wird, wie im folgenden Beispiel gezeigt.

`/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`

So können Sie beispielsweise bei Verwendung der Vorlage für die Syndication-Dienstbibliothek die folgenden Befehlszeilenargumente verwenden:

`/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`

#### <a name="specifying-no-client"></a>Keine Angabe des Clients

Klicken Sie im Projektmappen- **Explorer** in Visual Studio mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften**und dann die Registerkarte **Debuggen** aus, um anzugeben, dass nach dem WCF-Dienst Hosting kein Client Klicken Sie auf **Projekt starten** , und lassen Sie das Dialogfeld **Befehlszeilenargumente** leer.

#### <a name="using-a-custom-host"></a>Verwenden eines benutzerdefinierten Hosts

Wenn Sie einen benutzerdefinierten Host verwenden möchten, klicken Sie im Projektmappen- **Explorer** in Visual Studio mit der rechten Maustaste auf das Projekt, wählen Sie **Eigenschaften**und dann **die Registerkarte** Klicken Sie auf **externes Programm starten** , und geben Sie den vollständigen Pfad zum benutzerdefinierten Host ein. Sie können auch das Dialogfeld **Befehlszeilenargumente** verwenden, um Argumente anzugeben, die an den Host übermittelt werden sollen.

## <a name="wcf-service-host-user-interface"></a>WCF-Diensthost-Benutzeroberfläche

Wenn Sie den WCF-Dienst Host anfänglich aufrufen (durch Drücken von F5 in Visual Studio), wird das Fenster **WCF-Dienst Host** automatisch geöffnet. Wenn der WCF-Dienst Host ausgeführt wird, wird das Programmsymbol im Benachrichtigungsbereich angezeigt. Doppelklicken Sie auf das Symbol, um das Fenster **WCF-Dienst Host** zu öffnen.

Wenn beim Hosten des Diensts Fehler auftreten, wird das Dialogfeld WCF-Dienst Host geöffnet, in dem relevante Informationen angezeigt werden.

Das Hauptfenster des **WCF-Dienst Hosts** enthält zwei Menüs:

- **File**: enthält die Befehle **Close** und **Exit** . Wenn Sie auf **Schließen**klicken, wird das Dialogfeld **WCF-Dienst Host** geschlossen, aber die Dienste werden weiterhin gehostet. Wenn Sie auf **Beenden**klicken, wird auch der WCF-Dienst Host heruntergefahren. Dadurch werden auch alle gehosteten Dienste gestoppt.

- **Help**: **enthält den Info** -Befehl, der Versionsinformationen enthält. Sie enthält auch den **Hilfe** Befehl, mit dem eine Hilfedatei geöffnet werden kann.

Das Hauptfenster des **WCF-Dienst Hosts** enthält zwei Bereiche:

- Der erste Bereich ist " **Service**". Er enthält eine Liste mit grundlegenden Informationen zu allen Diensten. Zu diesen Informationen zählen:

  - **Dienst**: Listet alle Dienste auf.

  - **Status**: Listet den Status des Dienstanbieter auf. Gültige Werte sind "Started", "beendet" und "Error".

  - **Metadatenadresse**: zeigt die Metadatenadresse der Dienste an.

- Der zweite Bereich stellt **zusätzliche Informationen**dar. Es wird eine ausführliche Erläuterung des Dienststatus angezeigt, wenn die jeweilige Dienst Zeile im **Dienst** Bereich ausgewählt ist. Wenn der Status auf Fehler gesetzt ist, können Sie am Bildschirm die vollständige Fehlermeldung anzeigen.

## <a name="stopping-wcf-service-host"></a>Beenden des WCF-Diensthostes

Der WCF-Dienst Host kann auf vier Arten heruntergefahren werden:

- Beendet die Debugsitzung in Visual Studio.

- Wählen Sie im Fenster für den WCF- **Dienst Host** aus dem Menü **Datei** die Option **Beenden** aus.

- Wählen Sie im Kontextmenü des WCF-Dienst Host-Task leisten Symbols im System Benachrichtigungsbereich die Option **Beenden** aus.

- Beenden Sie den WCF-Test Client, wenn er verwendet wird.

## <a name="using-service-host-without-administrator-privilege"></a>Verwenden des Diensthosts ohne Administratorberechtigung

Um Benutzern ohne Administratorrechte die Entwicklung von WCF-Diensten zu ermöglichen, wird http://+:8731/Design_Time_Addresses während der Installation von Visual Studio eine ACL (Access Control Liste) für den Namespace "" erstellt. Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden. Administratoren können dieser ACL Benutzer hinzufügen oder aus dieser ACL entfernen oder zusätzliche Ports öffnen. Diese ACL ermöglicht es Benutzern, den automatischen WCF-Dienst Host (wcfSvcHost.exe) zu verwenden, ohne Ihnen Administratorrechte zu erteilen.

Sie können den Zugriff mithilfe des netsh.exe Tools in Windows Vista unter dem Konto mit erhöhten Rechten ändern. Das folgende Beispiel veranschaulicht die Verwendung des Tools netsh.exe.

```console
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>
```

Weitere Informationen zu netsh.exe finden Sie unter "[Verwenden des Netsh.exe Tools und der Befehls Zeilenschalter](/previous-versions/tn-archive/bb490939(v=technet.10))".

## <a name="see-also"></a>Siehe auch

- [WCF-Testclient (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
