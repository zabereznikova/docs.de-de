---
title: JSONP
ms.date: 03/30/2017
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
ms.openlocfilehash: 9e27d4e73f43f004ac1de078db6a73cd42b24bbc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237663"
---
# <a name="jsonp"></a>JSONP

In diesem Beispiel wird erläutert, wie JSON mit Padding (JSONP) in WCF REST-Diensten unterstützt wird. JSONP ist eine Konvention, die zum Aufrufen domänenübergreifender Skripts durch das Generieren von Skripttags im aktuellen Dokument verwendet wird. Das Ergebnis wird in einer festgelegten Rückruffunktion zurückgegeben. JSONP basiert auf der Idee, dass Tags wie z. b. `<script src="http://..." >` Skripts aus beliebigen Domänen auswerten können und dass das von diesen Tags abgerufene Skript innerhalb eines Bereichs ausgewertet wird, in dem andere Funktionen möglicherweise bereits definiert sind.

## <a name="demonstrates"></a>Zeigt

 Domänenübergreifende Skripterstellung mit JSONP

## <a name="discussion"></a>Diskussion

 Das Beispiel enthält eine Webseite, für die dynamisch ein Skriptblock hinzugefügt wird, nachdem die Seite im Browser gerendert wurde. Dieser Skriptblock ruft einen WCF REST-Dienst auf, der nur über den einen Vorgang `GetCustomer` verfügt. Der WCF REST-Dienst gibt den Namen und die Adresse eines Kunden durch Wrapping in einen Rückruffunktionsnamen zurück. Wenn der WCF REST-Dienst antwortet, wird die Rückruffunktion auf der Webseite mithilfe der Kundendaten aufgerufen, und die Rückruffunktion zeigt die Daten auf der Webseite an. Die Einfügung des Skripttags und die Ausführung der Rückruffunktion werden automatisch vom ASP.NET AJAX ScriptManager-Steuerelement behandelt. Das Verwendungsmuster stimmt mit dem aller ASP.NET AJAX-Proxys überein, allerdings mit einer zusätzlichen Zeile zur Aktivierung von JSONP. Dies wird im folgenden Code dargestellt:

```csharp
var proxy = new JsonpAjaxService.CustomerService();
proxy.set_enableJsonp(true);
proxy.GetCustomer(onSuccess, onFail, null);
```

 Die Webseite kann den WCF REST-Dienst aufrufen, da der Dienst den <xref:System.ServiceModel.Description.WebScriptEndpoint> verwendet, wobei `crossDomainScriptAccessEnabled` auf `true` festgelegt wurde. Beide Konfigurationen werden in der Web.config-Datei unter dem-Element durchgeführt \<system.serviceModel> .

```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

 ScriptManager verwaltet die Interaktion mit dem Dienst und macht damit die Komplexität, die mit einer manuellen Implementierung des JSONP-Zugriffs verbunden ist, überflüssig. Wenn `crossDomainScriptAccessEnabled` auf festgelegt ist `true` und das Antwortformat für einen Vorgang JSON ist, überprüft die WCF-Infrastruktur den URI der Anforderung nach einem Rückruf Abfrage-Zeichen folgen Parameter und umschließt die JSON-Antwort mit dem Wert des Parameters der Rückruf Abfrage Zeichenfolge. Im Beispiel ruft die Webseite den WCF REST-Dienst mit dem folgenden URI auf.

```http
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0
```

 Da der Zeichenfolgenparameter der Rückrufabfrage über den Wert `JsonPCallback` verfügt, gibt der WCF-Dienst die im folgenden Beispiel dargestellte JSONP-Antwort zurück.

```json
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});
```

 Diese JSONP-Antwort enthält die als JSON formatierten Kundendaten, für die mit dem von der Webseite angeforderten Rückruffunktionsnamen ein Wrapping ausgeführt wurde. ScriptManager führt diesen Rückruf mithilfe eines Skripttags aus, um die domänenübergreifende Anforderung zu ermöglichen und danach das Ergebnis an den onSuccess-Handler zu übergeben, der an die GetCustomer-Operation des ASP.NET AJAX-Proxys übergeben wurde.

 Das Beispiel besteht aus zwei ASP.NET-Webanwendungen: eine enthält nur einen WCF-Dienst, und eine andere enthält die ASPX-Webseite, die den Dienst aufruft. Wenn Sie die Lösung ausführen, hostet Visual Studio 2012 die beiden Websites auf verschiedenen Ports, wodurch eine Umgebung erstellt wird, in der sich der Dienst und der Client in verschiedenen Domänen befinden.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1. Öffnen Sie die Projektmappe für das JSONP-Beispiel.  
  
2. Drücken Sie F5, um `http://localhost:26648/JSONPClientPage.aspx` im Browser zu starten.  
  
3. Beachten Sie, dass nach dem Laden der Seite die Texteingaben für "Name" und "Address" mit Werten aufgefüllt werden.  Diese Werte wurden von einem-Befehl an den WCF-Dienst bereitgestellt, nachdem der Browser das Rendern der Seite abgeschlossen hat.
