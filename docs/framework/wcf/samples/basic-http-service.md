---
title: Einfacher HTTP-Dienst
ms.date: 03/30/2017
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
ms.openlocfilehash: 2e4aee93341404df5f06b096a9a7bf18a3c94f56
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48844708"
---
# <a name="basic-http-service"></a>Einfacher HTTP-Dienst
In diesem Beispiel wird veranschaulicht, wie ein HTTP-basierter, RPC-basierte Service – auch bezeichnet als "POX" (Plain Old XML)-Dienst mithilfe des Windows Communication Foundation (WCF)-REST-Programmiermodells implementiert wird. In diesem Beispiel besteht aus zwei Komponenten: einem selbst gehosteten WCF-HTTP-Dienst (Service.cs) und eine Konsolenanwendung (Program.cs), die der Dienst erstellt und Aufrufe durchführt.  
  
## <a name="sample-details"></a>Beispieldetails  
 Der WCF-Dienst macht 2 Vorgänge `EchoWithGet` und `EchoWithPost`, womit die Zeichenfolge, die als Eingabe übergeben wurde.  
  
 An den `EchoWithGet`-Vorgang wird das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut angehängt. Das bedeutet, dass der Vorgang HTTP-`GET`-Anforderungen verarbeitet. Da das <xref:System.ServiceModel.Web.WebGetAttribute> eine <xref:System.UriTemplate> nicht explizit angibt, erwartet der Vorgang, dass die Eingabezeichenfolge mit einem Abfragezeichenfolgenparameter namens `s` übergeben wird. Beachten Sie, dass das Format des vom Dienst erwarteten URIs mit der <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A>-Eigenschaft angepasst werden kann.  
  
 An den `EchoWithPost`-Vorgang wird das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut angehängt. Das bedeutet, dass es sich dabei nicht um einen `GET`-Vorgang handelt (er hat Nebenwirkungen). Da das <xref:System.ServiceModel.Web.WebInvokeAttribute> eine `Method` nicht explizit angibt, verarbeitet der Vorgang HTTP-`POST`-Anforderungen, bei denen die Zeichenfolge im Anforderungstext enthalten ist (z. B. im XML-Format). Beachten Sie, dass die HTTP-Methode und das Format des URIs für die Anforderung mit der <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>-Eigenschaft bzw. der <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate>-Eigenschaft angepasst werden können.  
  
 Die Datei App.config konfiguriert den WCF-Dienst mit einem Standard-<xref:System.ServiceModel.Description.WebHttpEndpoint>, für den die <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A>-Eigenschaft auf `true` festgelegt ist. Daher erstellt die WCF-Infrastruktur für eine automatische HTML-basierte Hilfeseite unter `http://localhost:8000/Customers/help` , Informationen zum HTTP-Anforderungen an den Dienst zu erstellen und nutzen Sie die HTTP-Antwort des Diensts bereitstellt.  
  
 "Program.cs" wird veranschaulicht, wie eine WCF-Kanalfactory Aufrufe an den Dienst und die Antworten verarbeiten verwendet werden kann. Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen WCF-Dienst darstellt. Es ist auch möglich, mit anderen .NET Framework-Klassen wie <xref:System.Net.HttpWebRequest> und <xref:System.Net.WebClient> auf den Dienst zuzugreifen.
  
 Das Beispiel umfasst einen selbst gehosteten Dienst und einen Client, die in einer Konsolenanwendung ausgeführt werden. Während die Konsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappe für das Beispiel eines grundlegenden HTTP-Diensts. Beim Starten von Visual Studio 2012, führen Sie als Administrator für das Beispiel erfolgreich ausgeführt. Zu diesem Zweck mit der rechten Maustaste in des Visual Studio 2012-Symbols, und wählen **als Administrator ausführen** aus dem Kontextmenü.  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen, und dann STRG+F5, um die Konsolenanwendung ohne Debuggen auszuführen. Im eingeblendeten Konsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt. Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben. Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.  
  
3.  Drücken Sie eine beliebige Taste, um das Beispiel zu beenden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`  
