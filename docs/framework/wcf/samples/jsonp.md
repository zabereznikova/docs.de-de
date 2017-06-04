---
title: "JSONP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# JSONP
In diesem Beispiel wird erläutert, wie JSON mit Padding \(JSONP\) in WCF REST\-Diensten unterstützt wird.  JSONP ist eine Konvention, die zum Aufrufen domänenübergreifender Skripts durch das Generieren von Skripttags im aktuellen Dokument verwendet wird.  Das Ergebnis wird in einer festgelegten Rückruffunktion zurückgegeben.  JSONP basiert auf der Idee, dass Tags wie \<script src\=”http:\/\/...” \> Skripts aus jeder Domäne auswerten können und dass das durch solche Tags abgerufene Skript im Bereich ausgewertet wird, in dem andere Funktionen möglicherweise bereits definiert wurden.  
  
## Veranschaulicht  
 Domänenübergreifende Skripterstellung mit JSONP  
  
## Diskussion  
 Das Beispiel enthält eine Webseite, für die dynamisch ein Skriptblock hinzugefügt wird, nachdem die Seite im Browser gerendert wurde.  Dieser Skriptblock ruft einen WCF REST\-Dienst auf, der nur über den einen Vorgang `GetCustomer` verfügt.  Der WCF REST\-Dienst gibt den Namen und die Adresse eines Kunden durch Wrapping in einen Rückruffunktionsnamen zurück.  Wenn der WCF REST\-Dienst antwortet, wird die Rückruffunktion auf der Webseite mithilfe der Kundendaten aufgerufen, und die Rückruffunktion zeigt die Daten auf der Webseite an.  Die Einfügung des Skripttags und die Ausführung der Rückruffunktion werden automatisch vom ASP.NET AJAX ScriptManager\-Steuerelement behandelt.  Das Verwendungsmuster stimmt mit dem aller ASP.NET AJAX\-Proxys überein, allerdings mit einer zusätzlichen Zeile zur Aktivierung von JSONP. Dies wird im folgenden Code dargestellt:  
  
```csharp  
var proxy = new JsonpAjaxService.CustomerService();  
proxy.set_enableJsonp(true);  
proxy.GetCustomer(onSuccess, onFail, null);  
  
```  
  
 Die Webseite kann den WCF REST\-Dienst aufrufen, da der Dienst den <xref:System.ServiceModel.Description.WebScriptEndpoint> verwendet, wobei `crossDomainScriptAccessEnabled` auf `true` festgelegt wurde.  Beide Konfigurationen werden in der "Web.config"\-Datei unter dem \<system.serviceModel\>\-Element festgelegt.  
  
```  
<system.serviceModel>  
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 ScriptManager verwaltet die Interaktion mit dem Dienst und macht damit die Komplexität, die mit einer manuellen Implementierung des JSONP\-Zugriffs verbunden ist, überflüssig.  Wenn `crossDomainScriptAccessEnabled` auf `true` festgelegt ist und das Antwortformat eines Vorgangs JSON lautet, uberprüft die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Infrastruktur einen Zeichenfolgenparameter für eine Rückrufabfrage und führt ein Wrapping der JSON\-Antwort mit dem Wert des Zeichenfolgenparameters für die Rückrufabfrage aus.  Im Beispiel ruft die Webseite den WCF REST\-Dienst mit dem folgenden URI auf.  
  
```  
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0  
  
```  
  
 Da der Zeichenfolgenparameter der Rückrufabfrage über den Wert `JsonPCallback` verfügt, gibt der WCF\-Dienst die im folgenden Beispiel dargestellte JSONP\-Antwort zurück.  
  
```  
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});  
  
```  
  
 Diese JSONP\-Antwort enthält die als JSON formatierten Kundendaten, für die mit dem von der Webseite angeforderten Rückruffunktionsnamen ein Wrapping ausgeführt wurde.  ScriptManager führt diesen Rückruf mithilfe eines Skripttags aus, um die domänenübergreifende Anforderung zu ermöglichen und danach das Ergebnis an den onSuccess\-Handler zu übergeben, der an die GetCustomer\-Operation des ASP.NET AJAX\-Proxys übergeben wurde.  
  
 Das Beispiel besteht aus zwei ASP.NET\-Webanwendungen. Eine Anwendung enthält nur einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst, die andere enthält die ASPX\-Webseite, mit der der Dienst aufgerufen wird.  Während der Ausführung der Projektmappe hostet [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die zwei Websites auf unterschiedlichen Ports. Auf diese Weise wird eine Umgebung erstellt, in der der Dienst und der Client sich in zwei verschiedenen Domänen befinden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### So führen Sie das Beispiel aus  
  
1.  Öffnen Sie die Projektmappe für das JSONP\-Beispiel.  
  
2.  Drücken Sie F5, um http:\/\/localhost:26648\/JSONPClientPage .aspx im Browser zu starten.  
  
3.  Beachten Sie, dass nach dem Laden der Seite die Texteingaben für "Name" und "Adresse" mit Werten aufgefüllt werden.  Diese Werte wurden von einem Aufruf des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts angegeben, nachdem der Browser das Rendern der Seite beendet hat.