---
title: AJAX-Dienst mit HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: 143585b40a493983b7265971a17224165de6f36d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575887"
---
# <a name="ajax-service-using-http-post"></a>AJAX-Dienst mit HTTP POST

In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) verwendet wird, um einen ASP.NET Asynchronous JavaScript and XML (Ajax)-Dienst zu erstellen, der HTTP Post verwendet. Bei einem AJAX-Dienst handelt es sich um einen Dienst, auf den Sie mit einfachem JavaScript-Code von einem Webbrowserclient aus zugreifen können. Dieses Beispiel baut auf dem Beispiel für den [grundlegenden AJAX-Dienst](basic-ajax-service.md) auf. der einzige Unterschied zwischen den beiden Beispielen besteht in der Verwendung von HTTP Post anstelle von HTTP Get.

Die AJAX-Unterstützung in Windows Communication Foundation (WCF) ist für die Verwendung mit ASP.NET AJAX über das-Steuerelement optimiert `ScriptManager` . Ein Beispiel für die Verwendung von WCF mit ASP.NET AJAX finden Sie in den [AJAX-Beispielen](ajax-service-using-http-post.md).

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

Der Dienst im folgenden Beispiel ist ein WCF-Dienst ohne AJAX-spezifischen Code.

Wenn das- <xref:System.ServiceModel.Web.WebInvokeAttribute> Attribut auf einen Vorgang angewendet wird oder das- <xref:System.ServiceModel.Web.WebGetAttribute> Attribut nicht angewendet wird, wird das HTTP-Standard Verb ("Post") verwendet. POST-Anforderungen sind schwieriger zu erstellen als GET-Anforderungen, sie werden jedoch nicht zwischengespeichert. Verwenden Sie POST-Anforderungen für alle Vorgänge, bei denen keine Zwischenspeicherung benötigt wird.

```csharp
[ServiceContract(Namespace = "PostAjaxService")]
public interface ICalculator
{
    [WebInvoke]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

Erstellen Sie im Dienst mithilfe von <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> einen AJAX-Endpunkt wie im Beispiel "Einfacher AJAX-Dienst".

Im Gegensatz zu GET-Anforderungen können Sie POST-Dienste nicht aus dem Browser aufrufen. Beispielsweise führt die Navigation zu zu `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` einem Fehler, da der Post-Dienst erwartet, dass der `n1` -Parameter und der- `n2` Parameter im Nachrichtentext im JSON-Format und nicht in der URL gesendet werden.

Die Clientwebseite "PostAjaxClientPage.aspx" enthält ASP.NET-Code zum Aufrufen des Diensts, wenn der Benutzer auf eine der Vorgangsschaltflächen auf der Seite klickt. Der Dienst antwortet auf die gleiche Weise wie im [grundlegenden AJAX-Dienst](basic-ajax-service.md) Beispiel mit der Get-Anforderung.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`

## <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie die Setup Anweisungen [zum einmaligen Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausführen.

2. Erstellen Sie die Projekt Mappe "PostAjaxService. sln", wie unter [Erstellen der Windows Communication Foundation Beispiele](building-the-samples.md)beschrieben.

3. Navigieren Sie zu `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (Öffnen Sie "PostAjaxClientPage. aspx" im Browser nicht aus dem Projektverzeichnis).
