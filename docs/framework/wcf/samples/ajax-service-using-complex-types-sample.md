---
title: Beispiel für AJAX-Dienst mit komplexen Typen
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: be8db36be7ed1639d839113174fdb95505466534
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716238"
---
# <a name="ajax-service-using-complex-types-sample"></a>Beispiel für AJAX-Dienst mit komplexen Typen

In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) verwendet wird, um einen ASP.NET Asynchronous JavaScript and XML (Ajax)-Dienst zu erstellen, der Instanzen komplexer Typen erstellt und diese zwischen Dienst und Client als JavaScript Object Notation (JSON) sendet. Sie können auf einen AJAX-Dienst zugreifen, indem Sie JavaScript-Code in einem Webbrowserclient verwenden. Dieses Beispiel baut auf dem [grundlegenden AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel auf.

Die AJAX-Unterstützung in WCF ist für die Verwendung mit ASP.NET AJAX über das <xref:System.Web.UI.ScriptManager>-Steuerelement optimiert. Ein Beispiel für die Verwendung von WCF mit ASP.NET AJAX finden Sie in den [AJAX-Beispielen](ajax.md).

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

Der Dienst im folgenden Beispiel ist ein WCF-Dienst ohne AJAX-spezifischen Code. Da kein <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut angewendet wird, wird das standardmäßige HTTP-Verb ("POST") verwendet. Der Dienst hat einen Vorgang, `DoMath`, der einen komplexen Typ namens `MathResult` zurückgibt. Der komplexe Typ ist ein Standarddatenvertragstyp, der ebenfalls keinen AJAX-spezifischen Code enthält.

```csharp
[DataContract]
public class MathResult
{
    [DataMember]
    public double sum;
    [DataMember]
    public double difference;
    [DataMember]
    public double product;
    [DataMember]
    public double quotient;
}
```

Erstellen Sie im Dienst mithilfe von <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> einen AJAX-Endpunkt wie im Beispiel "Einfacher AJAX-Dienst".

Die ComplexTypeClientPage. aspx-Client Webseite enthält ASP.net-und JavaScript-Code zum Aufrufen des Diensts, wenn der Benutzer auf der Seite auf die Schaltfläche **Berechnung ausführen** klickt. Der Code zum Aufrufen des Dienstanbieter erstellt einen JSON-Text und sendet ihn mithilfe von HTTP Post, ähnlich dem [AJAX-Dienst unter Verwendung von HTTP Post](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) Sample.

Wenn der Dienstaufruf erfolgreich war, können Sie im resultierenden JaveScript-Objekt auf die einzelnen Datenmember (`sum`, `difference`, `product` und `quotient`) zugreifen.

```javascript
function onSuccess(mathResult){
     document.getElementById("sum").value = mathResult.sum;
     document.getElementById("difference").value = mathResult.difference;
     document.getElementById("product").value = mathResult.product;
     document.getElementById("quotient").value = mathResult.quotient;
}
```

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Erstellen Sie die Projekt Mappe ComplexTypeAjaxService. sln, wie unter [Erstellen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md)beschrieben.

3. Navigieren Sie zu `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (Öffnen Sie ComplexTypeClientPage. aspx nicht im Browser aus dem Projektverzeichnis).

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`

## <a name="see-also"></a>Siehe auch

- [Einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
