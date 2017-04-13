---
title: "Einfacher HTTP-Dienst | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Einfacher HTTP-Dienst
In diesem Beispiel wird veranschaulicht, wie ein HTTP\-basierter, RPC\-basierter Dienst, der im Allgemeinen als "POX"\-Dienst \(Plain Old XML\) bezeichnet wird, mithilfe des [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST\-Programmiermodells implementiert wird.Dieses Beispiel besteht aus zwei Komponenten: einem selbst gehosteten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-HTTP\-Dienst \(Service.cs\) und einer Konsolenanwendung \(Program.cs\), die den Dienst erstellt und Aufrufe an den Dienst durchführt.  
  
## Beispieldetails  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst macht zwei Vorgänge, `EchoWithGet` und `EchoWithPost` verfügbar, wodurch die Zeichenfolge zurückgegeben wird, die als Eingabe übergeben wurde.  
  
 An den `EchoWithGet`\-Vorgang wird das <xref:System.ServiceModel.Web.WebGetAttribute>\-Attribut angehängt. Das bedeutet, dass der Vorgang HTTP\-`GET`\-Anforderungen verarbeitet.Da das <xref:System.ServiceModel.Web.WebGetAttribute> eine <xref:System.UriTemplate> nicht explizit angibt, erwartet der Vorgang, dass die Eingabezeichenfolge mit einem Abfragezeichenfolgenparameter namens `s` übergeben wird.Beachten Sie, dass das Format des vom Dienst erwarteten URIs mit der <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A>\-Eigenschaft angepasst werden kann.  
  
 An den `EchoWithPost`\-Vorgang wird das <xref:System.ServiceModel.Web.WebInvokeAttribute>\-Attribut angehängt. Das bedeutet, dass es sich dabei nicht um einen `GET`\-Vorgang handelt \(er hat Nebenwirkungen\).Da das <xref:System.ServiceModel.Web.WebInvokeAttribute> eine `Method` nicht explizit angibt, verarbeitet der Vorgang HTTP\-`POST`\-Anforderungen, bei denen die Zeichenfolge im Anforderungstext enthalten ist \(z. B. im XML\-Format\).Beachten Sie, dass die HTTP\-Methode und das Format des URIs für die Anforderung mit der <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>\-Eigenschaft bzw. der <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate>\-Eigenschaft angepasst werden können.  
  
 Die Datei App.config konfiguriert den WCF\-Dienst mit einem Standard\-<xref:System.ServiceModel.Description.WebHttpEndpoint>, für den die <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A>\-Eigenschaft auf `true` festgelegt ist.Daraufhin erstellt die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Infrastruktur eine automatische HTML\-basierte Hilfeseite unter `http://localhost:8000/Customers/help`, in der Informationen zum Erstellen von HTTP\-Anforderungen an den Dienst und zum Verwenden der HTTP\-Antwort des Diensts zu finden sind.  
  
 Die Datei Program.cs veranschaulicht, wie mit einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Kanalfactory Aufrufe des Diensts durchgeführt und die Antworten verarbeitet werden.Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst darstellt.Es ist auch möglich, mit anderen .NET Framework\-Klassen wie <xref:System.Net.HttpWebRequest> und <xref:System.Net.WebClient> auf den Dienst zuzugreifen.In anderen Beispielen im SDK \(z. B. [Automatische Formatauswahl](../../../../docs/framework/wcf/samples/automatic-format-selection.md) und [Einfacher Ressourcendienst](../../../../docs/framework/wcf/samples/basic-resource-service.md)\) wird gezeigt, wie diese Klassen verwendet werden, um mit einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst zu kommunizieren.  
  
 Das Beispiel umfasst einen selbst gehosteten Dienst und einen Client, die in einer Konsolenanwendung ausgeführt werden.Während die Konsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappe für das Beispiel eines grundlegenden HTTP\-Diensts.Sie müssen [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] als Administrator ausführen, damit das Beispiel erfolgreich ausgeführt werden kann.Klicken Sie dazu mit der rechten Maustaste auf das [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]\-Symbol, und wählen Sie im Kontextmenü die Option **Als Administrator ausführen** aus.  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen, und dann STRG\+F5, um die Konsolenanwendung ohne Debuggen auszuführen.Im eingeblendeten Konsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML\-Hilfeseite für den ausgeführten Dienst angezeigt.Sie können die HTML\-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.  
  
3.  Drücken Sie eine beliebige Taste, um das Beispiel zu beenden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`  
  
## Siehe auch  
 [Automatische Formatauswahl](../../../../docs/framework/wcf/samples/automatic-format-selection.md)   
 [Einfacher Ressourcendienst](../../../../docs/framework/wcf/samples/basic-resource-service.md)