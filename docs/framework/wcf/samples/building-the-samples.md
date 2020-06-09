---
title: Erstellen der Windows Communication Foundation-Beispiele
ms.date: 03/30/2017
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
ms.openlocfilehash: 53599b3b1827651b48df9921bb59a679a36ee39c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592618"
---
# <a name="building-the-windows-communication-foundation-samples"></a>Erstellen der Windows Communication Foundation-Beispiele

Die Windows Communication Foundation (WCF)-Beispiele können mithilfe der Visual Studio-IDE oder mithilfe des **MSBuild** -Befehls von der Befehlszeile aus erstellt werden. In diesem Thema werden beide Vorgehensweisen beschrieben.

> [!NOTE]
> Stellen Sie vor dem Erstellen oder Ausführen eines der WCF-Beispiele sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

## <a name="to-build-the-sample-using-a-command-prompt"></a>So erstellen Sie das Beispiel mithilfe einer Eingabeaufforderung

1. Öffnen Sie Developer-Eingabeaufforderung für Visual Studio, und navigieren Sie zu dem sprachspezifischen Unterverzeichnis unter dem Verzeichnis, in dem Sie das Beispiel installiert haben.

2. Geben Sie `msbuild` in der Befehlszeile ein. Die Client Programmdateien werden in " *Client\Bin* " erstellt, und die Dienst Programmdateien werden in " *service\bin*" erstellt. Wenn der Dienst von Internetinformationsdienste (IIS) gehostet wird, werden die Dienst Programmdateien auch in das Verzeichnis " *Service Model Samples* " und das zugehörige Unterverzeichnis " *\bin* " kopiert.

> [!NOTE]
> Sie müssen die ACLs in *%systemdrive%\inetpub\wwwroot zuweisen* festlegen, um dem Konto, unter dem Sie ausführen, die Berechtigung "ändern" zu erteilen. Andernfalls führen einige Postbuildereignisse zu Fehlern. Sie können aber auch die ACLs unverändert lassen und die SDK-Eingabeaufforderung als Administrator ausführen.

## <a name="to-build-the-sample-using-visual-studio"></a>So erstellen Sie das Beispiel mithilfe von Visual Studio

1. Wählen Sie im Menü **Datei** in Visual Studio die **Open**Option  >  **Projekt/Projekt**Mappe öffnen aus. Navigieren Sie zu dem sprachspezifischen Unterverzeichnis unterhalb des Verzeichnisses, in dem Sie das Beispiel installiert haben, und doppelklicken Sie auf das Symbol für die SLN-Datei, um die Projekt Mappe in Visual Studio zu öffnen.

1. Wählen Sie im Menü **Erstellen** die Option Projekt Mappe **neu erstellen**aus.

   Die Clientprogrammdateien werden im Verzeichnis client\bin erstellt, und die Dienstprogrammdateien werden im Verzeichnis service\bin erstellt. Wenn der Dienst in IIS gehostet wird, werden die Dienst Programmdateien auch in das Verzeichnis " *Service Model Samples* " und das zugehörige Unterverzeichnis " *\bin* " kopiert.

> [!NOTE]
> Sie müssen die Zugriffssteuerungslisten (Access Control List, ACL) für %systemdrive%\inetpub\wwwroot festlegen, um dem Konto, unter dem das Programm ausgeführt wird, Berechtigungen zum Ändern zu erteilen. Andernfalls führen einige Postbuildereignisse zu Fehlern. Sie können die ACLs aber auch unverändert lassen und die SDK-Eingabeaufforderung oder Visual Studio als Administrator ausführen. Für einige Visual Studio-Aktionen (wie das Anfügen eines Debuggers an den ASP.NET-Arbeitsprozess) sind ebenfalls Administratorrechte erforderlich.

## <a name="setup-batch-files-and-scripts"></a>Setupbatchdateien und Skripts
 Die Batch Dateien und Skripts von "Setup. exe" und "Cleanup. exe" sollten über Developer-Eingabeaufforderung für Visual Studio ausgeführt werden. Einige Setup- und Cleanup-Dateien führen Aufgaben aus, für die Administratorrechte erforderlich sind. Sie müssen daher mit entsprechenden Rechten gestartet werden.

## <a name="important-security-information-about-metadata-endpoints"></a>Wichtige Sicherheitsinformationen über Metadatenendpunkte
 Um eine unbeabsichtigte Offenlegung von potenziell sensiblen Dienst Metadaten zu verhindern, wird die Metadatenveröffentlichung durch die Standardkonfiguration für Windows Communication Foundation (WCF)-Dienste deaktiviert. Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten (wie Svcutil.exe) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist. Um Ihnen das Experimentieren mit den Beispielen zu vereinfachen, wird in fast allen Beispielen ein ungesicherter Endpunkt zum Veröffentlichen von Metadaten verfügbar gemacht. Solche Endpunkte können für anonyme, nicht authentifizierte Benutzer möglicherweise verfügbar sein. Daher muss beim Bereitstellen solcher Endpunkte sorgfältig darauf geachtet werden, dass das Öffentlichmachen von Metadaten eines Diensts sachgerecht erfolgt. Weitere Informationen zum Veröffentlichen von Dienst Metadaten finden Sie im Beispiel [Metadatenveröffentlichungs-Verhalten](metadata-publishing-behavior.md) . Ein Beispiel zum Sichern eines Metadatenendpunkts finden Sie im Beispiel für einen [benutzerdefinierten sicheren Metadatenendpunkt](custom-secure-metadata-endpoint.md) .

## <a name="exception-handling"></a>Ausnahmebehandlung
 Im Allgemeinen enthalten diese Beispiele keine Ausnahmebehandlung, damit der Code auf das Thema des jeweiligen Beispiels beschränkt werden kann. Weitere Informationen zur Ausnahmebehandlung finden Sie im Beispiel [erwartete Ausnahmen](expected-exceptions.md) .

## <a name="regenerating-clients-and-configuration-with-svcutil"></a>Neugenerieren von Clients und Konfiguration mit "Svcutil"
 Sie können das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) verwenden, um den Client Code und die Konfiguration für die meisten Beispiele neu zu generieren. Bei einigen Beispielen ist es erforderlich, die Konfiguration manuell zu bearbeiten. Wenn Sie beispielsweise mit Svcutil.exe die Konfiguration für ein Beispiel neu generieren, in dem Clientzertifikat-Anmeldeinformationen verwendet werden, müssen Sie die vorher konfigurierten Anmeldeinformationen manuell angeben. Einige Beispiele beeinflussen den generierten Code mithilfe bestimmter Optionen für Svcutil.exe. Diese Optionen sind dann in den jeweiligen Beispielthemen angegeben.

### <a name="to-regenerate-the-client-and-configuration-files"></a>So generieren Sie den Client und die Konfigurationsdateien neu

1. Öffnen Sie eine SDK-Eingabeaufforderung, und navigieren Sie zu dem sprachspezifischen Unterverzeichnis unterhalb des Verzeichnisses, in dem Sie das Beispiel installiert haben.

2. Wenn der Dienst im Internet gehostet wird, verwenden Sie den folgenden Befehl.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Wenn der Dienst selbst gehostet ist, verwenden Sie den folgenden Befehl.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Ersetzen Sie `http://localhost:8000/ServiceModelSamples/service.svc/mex` durch die Adresse des MEX-Endpunkts des selbst gehosteten Dienstanbieter.

     Verwenden Sie zum Generieren des Clients in Visual Basic den folgenden Befehl.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

     Wenn der Dienst selbst gehostet ist, verwenden Sie den folgenden Befehl.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

    > [!NOTE]
    > Wenn Sie die Generierung der Client Konfiguration überspringen möchten, fügen Sie die Option **/noconfig** hinzu.

## <a name="see-also"></a>Weitere Informationen

- [Durchführen der Windows Communication Foundation-Beispiele](running-the-samples.md)
- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
