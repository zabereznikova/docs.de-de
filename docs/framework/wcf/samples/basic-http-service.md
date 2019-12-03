---
title: Einfacher HTTP-Dienst
ms.date: 03/30/2017
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
ms.openlocfilehash: 8dfcd5a751bcef6aa24b5cb4a200c8820c43fe81
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716091"
---
# <a name="basic-http-service"></a>Einfacher HTTP-Dienst

In diesem Beispiel wird veranschaulicht, wie ein HTTP-basierter RPC-basierter Dienst, der als "POX" (Plain Old XML)-Dienst – bezeichnet wird, mit dem Rest-Programmiermodell Windows Communication Foundation (WCF) implementiert wird. Dieses Beispiel besteht aus zwei Komponenten: einem selbstgeh osteten WCF-HTTP-Dienst (Service.cs) und einer Konsolenanwendung (Program.cs), mit der der Dienst erstellt und aufgerufen wird.

## <a name="sample-details"></a>Beispieldetails

Der WCF-Dienst macht zwei Vorgänge verfügbar, `EchoWithGet` und `EchoWithPost`, die die Zeichenfolge zurückgeben, die als Eingabe übermittelt wurde.

An den `EchoWithGet`-Vorgang wird das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut angehängt. Das bedeutet, dass der Vorgang HTTP-`GET`-Anforderungen verarbeitet. Da das <xref:System.ServiceModel.Web.WebGetAttribute> eine <xref:System.UriTemplate> nicht explizit angibt, erwartet der Vorgang, dass die Eingabezeichenfolge mit einem Abfragezeichenfolgenparameter namens `s` übergeben wird. Beachten Sie, dass das Format des vom Dienst erwarteten URIs mit der <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A>-Eigenschaft angepasst werden kann.

Die `EchoWithPost`-Operation wird mit <xref:System.ServiceModel.Web.WebInvokeAttribute> versehen. Das bedeutet, dass es sich dabei nicht um einen `GET`-Vorgang handelt (er hat Nebenwirkungen). Da das <xref:System.ServiceModel.Web.WebInvokeAttribute> eine `Method` nicht explizit angibt, verarbeitet der Vorgang HTTP-`POST`-Anforderungen, bei denen die Zeichenfolge im Anforderungstext enthalten ist (z. B. im XML-Format). Beachten Sie, dass die HTTP-Methode und das Format des URIs für die Anforderung mit der <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>-Eigenschaft bzw. der <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate>-Eigenschaft angepasst werden können.

Die Datei App.config konfiguriert den WCF-Dienst mit einem Standard-<xref:System.ServiceModel.Description.WebHttpEndpoint>, für den die <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A>-Eigenschaft auf `true` festgelegt ist. Folglich erstellt die WCF-Infrastruktur eine automatische HTML-basierte Hilfeseite unter `http://localhost:8000/Customers/help`, die Informationen über das Erstellen von HTTP-Anforderungen an den Dienst und die Verwendung der HTTP-Antwort des Dienstanbieter bereitstellt.

Program.cs veranschaulicht, wie eine WCF-Kanalfactory verwendet werden kann, um Aufrufe an den Dienst vorzunehmen und Antworten zu verarbeiten. Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen WCF-Dienst darstellt. Es ist auch möglich, mit anderen .NET Framework-Klassen wie <xref:System.Net.HttpWebRequest> und <xref:System.Net.WebClient> auf den Dienst zuzugreifen.

Das Beispiel umfasst einen selbst gehosteten Dienst und einen Client, die in einer Konsolenanwendung ausgeführt werden. Während die Konsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie die Projektmappe für das Beispiel eines grundlegenden HTTP-Diensts. Beim Starten von Visual Studio 2012 müssen Sie als Administrator ausführen, damit das Beispiel erfolgreich ausgeführt werden kann. Klicken Sie dazu mit der rechten Maustaste auf das Visual Studio 2012-Symbol, und wählen Sie im Kontextmenü die Option **als Administrator ausführen** aus.

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen, und dann STRG+F5, um die Konsolenanwendung ohne Debuggen auszuführen. Im eingeblendeten Konsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt. Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben. Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.

3. Drücken Sie eine beliebige Taste, um das Beispiel zu beenden.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`
