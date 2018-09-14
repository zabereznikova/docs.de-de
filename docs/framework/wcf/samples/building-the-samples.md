---
title: Erstellen der Windows Communication Foundation-Beispiele
ms.date: 03/30/2017
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
ms.openlocfilehash: 46f4015c00916a5cab932e8fd2539c7c86588a30
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45596909"
---
# <a name="building-the-windows-communication-foundation-samples"></a>Erstellen der Windows Communication Foundation-Beispiele

Die Beispiele für Windows Communication Foundation (WCF) erstellt werden können, mithilfe von Visual Studio-IDE oder mithilfe der **Msbuild** Befehl über die Befehlszeile. In diesem Thema werden beide Vorgehensweisen beschrieben.

> [!NOTE]
> Vor dem Erstellen, oder der WCF-Beispiele ausführen, stellen Sie sicher durchgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

## <a name="to-build-the-sample-using-a-command-prompt"></a>So erstellen Sie das Beispiel mithilfe einer Eingabeaufforderung

1.  Öffnen Sie die Developer-Eingabeaufforderung für Visual Studio, und navigieren Sie zu dem sprachspezifischen Unterverzeichnis unterhalb des Verzeichnisses, in dem Sie das Beispiel installiert.

2.  Typ `msbuild` an der Befehlszeile eingeben. Die Clientprogrammdateien werden erstellt, um *Client\bin* und die Dienstprogrammdateien werden erstellt, um *"\service\bin"*. Wenn der Dienst von IIS (Internetinformationsdienste) gehostet wird, werden die Dienstprogrammdateien auch in kopiert die *Servicemodelsamples* Verzeichnis und dessen *\bin* Unterverzeichnis.

> [!NOTE]
> Sie müssen die ACLs für festlegen *%systemdrive%\inetpub\wwwroot* gewähren Ändern von Berechtigungen für das Dienstkonto, unter dem Sie ausgeführt werden. Andernfalls führen einige Postbuildereignisse zu Fehlern. Sie können aber auch die ACLs unverändert lassen und die SDK-Eingabeaufforderung als Administrator ausführen.

## <a name="to-build-the-sample-using-visual-studio"></a>So erstellen Sie das Beispiel mithilfe von Visual Studio

1. Von der **Datei** in Visual Studio, wählen Sie im Menü **öffnen** > **Projekt/Projektmappe**. Navigieren Sie zum sprachspezifischen Unterverzeichnis unter dem Verzeichnis, in dem Sie das Beispiel installiert, und doppelklicken Sie auf das Symbol der SLN-Datei zum Öffnen der Projektmappe in Visual Studio.

1. Von der **erstellen** , wählen Sie im Menü **Projektmappe neu erstellen**.

   Die Clientprogrammdateien werden im Verzeichnis client\bin erstellt, und die Dienstprogrammdateien werden im Verzeichnis service\bin erstellt. Wenn der Dienst in IIS gehostet wird, werden die Dienstprogrammdateien auch in kopiert die *Servicemodelsamples* Verzeichnis und dessen *\bin* Unterverzeichnis.

> [!NOTE]
> Sie müssen die Zugriffssteuerungslisten (Access Control List, ACL) für %systemdrive%\inetpub\wwwroot festlegen, um dem Konto, unter dem das Programm ausgeführt wird, Berechtigungen zum Ändern zu erteilen. Andernfalls führen einige Postbuildereignisse zu Fehlern. Sie können die ACLs aber auch unverändert lassen und die SDK-Eingabeaufforderung oder Visual Studio als Administrator ausführen. Für einige Visual Studio-Aktionen (wie das Anfügen eines Debuggers an den ASP.NET-Arbeitsprozess) sind ebenfalls Administratorrechte erforderlich.

## <a name="setup-batch-files-and-scripts"></a>Setupbatchdateien und Skripts
 Setup.exe und Cleanup.exe-Batchdateien und Skripts sollte von der Developer-Eingabeaufforderung für Visual Studio ausgeführt werden. Einige Setup- und Cleanup-Dateien führen Aufgaben aus, für die Administratorrechte erforderlich sind. Sie müssen daher mit entsprechenden Rechten gestartet werden.

## <a name="important-security-information-about-metadata-endpoints"></a>Wichtige Sicherheitsinformationen über Metadatenendpunkte
 Um unbeabsichtigtes Offenlegen sicherheitsrelevanter Dienstmetadaten zu verhindern, die Standardkonfiguration für Windows Communication Foundation (WCF)-Dienste die Metadatenveröffentlichung deaktiviert. Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten (wie Svcutil.exe) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist. Um Ihnen das Experimentieren mit den Beispielen zu vereinfachen, wird in fast allen Beispielen ein ungesicherter Endpunkt zum Veröffentlichen von Metadaten verfügbar gemacht. Solche Endpunkte können für anonyme, nicht authentifizierte Benutzer möglicherweise verfügbar sein. Daher muss beim Bereitstellen solcher Endpunkte sorgfältig darauf geachtet werden, dass das Öffentlichmachen von Metadaten eines Diensts sachgerecht erfolgt. Weitere Informationen zum Veröffentlichen von Dienstmetadaten finden Sie unter den [Metadatenveröffentlichungsverhalten](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md) Beispiel. Finden Sie unter den [benutzerdefinierte sicherer Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) Beispiel ist ein Beispiel zum Absichern eines metadatenendpunkts.

## <a name="exception-handling"></a>Ausnahmebehandlung
 Im Allgemeinen enthalten diese Beispiele keine Ausnahmebehandlung, damit der Code auf das Thema des jeweiligen Beispiels beschränkt werden kann. Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter den [Ausnahmen erwartet](../../../../docs/framework/wcf/samples/expected-exceptions.md) Beispiel.

## <a name="regenerating-clients-and-configuration-with-svcutil"></a>Neugenerieren von Clients und Konfiguration mit "Svcutil"
 Sie können die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Clientcode und Konfiguration für die meisten Beispiele neu zu generieren. Bei einigen Beispielen ist es erforderlich, die Konfiguration manuell zu bearbeiten. Wenn Sie beispielsweise mit Svcutil.exe die Konfiguration für ein Beispiel neu generieren, in dem Clientzertifikat-Anmeldeinformationen verwendet werden, müssen Sie die vorher konfigurierten Anmeldeinformationen manuell angeben. Einige Beispiele beeinflussen den generierten Code mithilfe bestimmter Optionen für Svcutil.exe. Diese Optionen sind dann in den jeweiligen Beispielthemen angegeben.

### <a name="to-regenerate-the-client-and-configuration-files"></a>So generieren Sie den Client und die Konfigurationsdateien neu

1.  Öffnen Sie eine SDK-Eingabeaufforderung, und navigieren Sie zu dem sprachspezifischen Unterverzeichnis unterhalb des Verzeichnisses, in dem Sie das Beispiel installiert haben.

2.  Wenn der Dienst im Internet gehostet wird, verwenden Sie den folgenden Befehl.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Wenn der Dienst selbst gehostet ist, verwenden Sie den folgenden Befehl.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Ersetzen Sie dies http://localhost:8000/ServiceModelSamples/service.svc/mex mit der Adresse des Mex-Endpunkt für den selbst gehosteten Dienst.

     Verwenden Sie zum Generieren des Clients in Visual Basic den folgenden Befehl.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

     Wenn der Dienst selbst gehostet ist, verwenden Sie den folgenden Befehl.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

    > [!NOTE]
    > Hinzufügen der Generierung der Clientkonfiguration Überspringen der **/noconfig** Option.

## <a name="see-also"></a>Siehe auch

- [Durchführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md)
- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
