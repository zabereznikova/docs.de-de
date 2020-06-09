---
title: AJAX-Dienst ohne Konfiguration
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: ab3731ab6aeb80e0e46228b8bf702b0fe5c6e6e9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575900"
---
# <a name="ajax-service-without-configuration"></a>AJAX-Dienst ohne Konfiguration

In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) verwendet wird, um einen grundlegenden ASP.NET Asynchronous JavaScript and XML (Ajax)-Dienst (einen Dienst, auf den Sie mithilfe von JavaScript-Code von einem Webbrowser Client aus zugreifen können) ohne Konfigurationseinstellungen zu erstellen. Der Dienst verwendet eine besondere Syntax in der .svc-Datei zur automatischen Aktivierung eines AJAX-Endpunkts.

Die AJAX-Unterstützung in WCF ist für die Verwendung mit ASP.NET AJAX über das-Steuerelement optimiert `ScriptManager` . Ein Beispiel für die Verwendung von WCF mit ASP.NET AJAX finden Sie in den [AJAX-Beispielen](ajax.md).

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

 Dieses Beispiel basiert auf dem Beispiel "AJAX-Dienst mit HTTP POST". Wie im Beispiel für den [grundlegenden AJAX-Dienst](basic-ajax-service.md) beschrieben, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> wird zum Hosten des Diensts verwendet.

```text
<%ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"
%>
```

<xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> fügt dem Dienst automatisch einen <xref:System.ServiceModel.Description.WebScriptEndpoint> hinzu. Wenn keine Konfigurationsänderungen am Endpunkt vorgenommen werden müssen, kann der Abschnitt `<system.ServiceModel>` vollständig aus der Datei "Web.config" für den Dienst entfernt werden. Die Datei Web.config enthält einige ASP.NET-Einstellungen, die von ConfigFreeClientPage.aspx verwendet werden. Wenn dies nicht der Fall wäre, könnte die gesamte Datei Web.config entfernt werden.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie die Setup Anweisungen [für die Windows Communication Foundation Beispiele im einmaligen Setup Verfahren](one-time-setup-procedure-for-the-wcf-samples.md)ausführen.

2. Erstellen Sie die Projekt Mappe ConfigFreeAjaxService. sln, wie unter [Erstellen der Windows Communication Foundation Beispiele](building-the-samples.md)beschrieben.

3. Navigieren Sie zu `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (Öffnen Sie ConfigFreeClientPage. aspx nicht innerhalb des Projektverzeichnisses im Browser).

> [!NOTE]
> Stellen Sie bei der Ausführung dieses Beispiels sicher, dass für den Ordner ServiceModelSamples in IIS nicht gleichzeitig anonyme Authentifizierung und Windows-Authentifizierung aktiviert ist. Wenn das der Fall ist, deaktivieren Sie die Windows-Authentifizierung. Sobald Sie das Beispiel ausgeführt haben, aktivieren Sie die Windows-Authentifizierung und führen "iisreset" aus.

## <a name="see-also"></a>Weitere Informationen

- [Einfacher AJAX-Dienst](basic-ajax-service.md)
