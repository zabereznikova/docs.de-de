---
title: "Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SSL"
  - "WCF, Sicherheit"
  - "WCF, Sicherheitsmodus"
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat
Beim Erstellen eines selbst gehosteten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienstes mit der <xref:System.ServiceModel.WSHttpBinding>\-Klasse, die die Transportsicherheit verwendet, müssen Sie auch einen Anschluss mit einem X.509\-Zertifikat konfigurieren.  Wenn Sie keinen selbst gehosteten Dienst erstellen, können Sie Ihren Dienst auch über Internetinformationsdienste \(IIS\) hosten.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [HTTP\-Transportsicherheit](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Welches Tool zum Konfigurieren eines Anschlusses verwendet wird, hängt vom Betriebssystem des Computers ab.  
  
 Verwenden Sie unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)] das HttpCfg.exe\-Tool.  Unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] ist dieses Tool bereits installiert.  Mit [!INCLUDE[wxp](../../../../includes/wxp-md.md)] können Sie das Tool unter [Windows XP Service Pack 2\-Supporttools](http://go.microsoft.com/fwlink/?LinkId=88606) herunterladen.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Httpcfg\-Übersicht](http://go.microsoft.com/fwlink/?LinkId=88605).  Die Syntax des Tools "Httpcfg.exe" wird in der [Dokumentation der Windows\-Supporttools](http://go.microsoft.com/fwlink/?LinkId=94840) erläutert.  
  
 Verwenden Sie unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das bereits installierte Tool Netsh.exe.  
  
 In diesem Thema wird die Ausführung einer Reihe von Prozeduren beschrieben:  
  
-   Bestimmen der aktuellen Anschlusskonfiguration eines Computers  
  
-   Abrufen des Fingerabdrucks eines Zertifikats \(notwendig für die beiden anschließenden Prozeduren\)  
  
-   Binden eines SSL\-Zertifikats an eine Anschlusskonfiguration  
  
-   Binden eines SSL\-Zertifikats an eine Anschlusskonfiguration und Unterstützen von Clientzertifikaten  
  
-   Löschen eines SSL\-Zertifikats aus einer Anschlussnummer  
  
 Zum Ändern der auf dem Computer gespeicherten Zertifikate sind Administratorrechte erforderlich.  
  
### So ermitteln Sie, wie Anschlüsse konfiguriert sind  
  
1.  Verwenden Sie zum Anzeigen der aktuellen Anschlusskonfiguration unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)] das Tool **HttpCfg.exe** mit den Schaltern **query** und **ssl**, wie im folgenden Beispiel gezeigt:  
  
    ```  
    httpcfg query ssl  
    ```  
  
2.  Verwenden Sie zum Anzeigen der aktuellen Anschlusskonfiguration unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das Netsh.exe\-Tool, wie im folgenden Beispiel gezeigt:  
  
    ```  
    netsh http show sslcert  
    ```  
  
### So rufen Sie den Fingerabdruck eines Zertifikats ab  
  
1.  Verwenden Sie das Zertifikats\-MMC\-Snap\-In, um nach einem X.509\-Zertifikat zu suchen, das eine bestimmte Clientauthentifizierungsfunktion aufweist.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC\-Snap\-In](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2.  Greifen Sie auf den Fingerabdruck des Zertifikats zu.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3.  Kopieren Sie den Fingerabdruck des Zertifikats in einen Texteditor, beispielsweise den Windows\-Editor.  
  
4.  Entfernen Sie alle Leerstellen zwischen den Hexadezimalzeichen.  Eine Möglichkeit besteht darin, die Suchen\/Ersetzen\-Funktion des Editors zu nutzen, um jede Leerstelle durch ein NULL\-Zeichen zu ersetzen.  
  
### So binden Sie ein SSL\-Zertifikat an eine Anschlussnummer  
  
1.  Verwenden Sie unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] das Tool\-HttpCfg.exe im Secure Sockets Layer \(SSL\)\-Speicher im Modus "Set", um das Zertifikat an eine Anschlussnummer zu binden.  Das Tool verwendet den Fingerabdruck, um das Zertifikat zu identifizieren, wie im folgenden Beispiel gezeigt.  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   Der Schalter **\-i** verwendet die Syntax `IP`:`port` und weist das Tool an, das Zertifikat auf den Anschluss 8012 des Computers festzulegen.  Optional können Sie die vier Nullen vor der Nummer auch durch die tatsächliche IP\-Adresse des Computers ersetzen.  
  
    -   Der Schalter **\-h** gibt den Fingerabdruck des Zertifikats an.  
  
2.  Verwenden Sie unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das Netsh.exe\-Tool, wie im folgenden Beispiel gezeigt:  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   Der **certhash**\-Parameter gibt den Fingerabdruck des Zertifikats an.  
  
    -   Der **ipport**\-Parameter gibt die IP\-Adresse und den Anschluss an und hat die gleiche Funktion wie der beschriebene Schalter **\-i** des Tools **Httpcfg.exe**.  
  
    -   Der **appid**\-Parameter ist eine GUID, mit der die besitzende Anwendung identifiziert werden kann.  
  
### So binden Sie ein SSL\-Zertifikat an eine Anschlussnummer und unterstützen Clientzertifikate  
  
1.  Führen Sie zum Unterstützen von Clients, die die Authentifizierung mithilfe von X.509\-Zertifikaten auf der Transportebene durchführen, unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)] die obige Prozedur aus, übergeben Sie jedoch einen zusätzlichen Befehlszeilenparameter an HttpCfg.exe, wie im folgenden Beispiel gezeigt:  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     Der Schalter **\-f** verwendet die Syntax `n`, wobei n eine Zahl zwischen 1 und 7 ist.   Bei dem Wert "2" \(wie im vorherigen Beispiel gezeigt\) sind Clientzertifikate auf der Transportebene aktiviert.  Der Wert&\#160;"3" aktiviert Clientzertifikate und ordnet die Zertifikate einem Windows\-Konto zu.  Das Verhalten bei anderen Werten finden Sie in der Hilfe zu HttpCfg.exe.  
  
2.  Führen Sie zum Unterstützen von Clients, die die Authentifizierung mithilfe von X.509\-Zertifikaten auf der Transportebene durchführen, unter [!INCLUDE[wv](../../../../includes/wv-md.md)] die obige Prozedur aus, verwenden Sie jedoch einen zusätzlichen Parameter, wie im folgenden Beispiel gezeigt:  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### So löschen Sie ein SSL\-Zertifikat aus einer Anschlussnummer  
  
1.  Verwenden Sie das HttpCfg.exe\- oder das Netsh.exe\-Tool, um die Anschlüsse und Fingerabdrücke aller Bindungen auf dem Computer anzuzeigen.  Verwenden Sie das Umleitungszeichen "\>", um die Informationen auf den Datenträger auszugeben, wie im folgenden Beispiel gezeigt:  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2.  Verwenden Sie unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)] das Tool **HttpCfg.exe** zusammen mit den Schlüsselwörtern **delete** und **ssl**.  Verwenden Sie den Schalter **\-i**, um die Nummer für `IP`:`port` anzugeben, und den Schalter **\-h**, um den Fingerabdruck anzugeben.  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3.  Verwenden Sie unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das Netsh.exe\-Tool, wie im folgenden Beispiel gezeigt:  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## Beispiel  
 Der folgende Code zeigt, wie Sie einen selbst gehosteten Dienst erstellen, indem Sie die auf die Transportsicherheit festgelegte <xref:System.ServiceModel.WSHttpBinding>\-Klasse verwenden.  Geben Sie beim Erstellen einer Anwendung die Anschlussnummer in der Adresse an.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## Siehe auch  
 [HTTP\-Transportsicherheit](../../../../docs/framework/wcf/feature-details/http-transport-security.md)