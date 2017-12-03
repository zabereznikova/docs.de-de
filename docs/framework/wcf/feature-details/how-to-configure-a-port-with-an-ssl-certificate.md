---
title: 'Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc4d6e3bb20cbe005ad7ce21ed37fe57c5d3466b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat
Beim Erstellen eines selbst gehosteten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienstes mit der <xref:System.ServiceModel.WSHttpBinding>-Klasse, die die Transportsicherheit verwendet, müssen Sie auch einen Anschluss mit einem X.509-Zertifikat konfigurieren. Wenn Sie keinen selbst gehosteten Dienst erstellen, können Sie Ihren Dienst auch über Internetinformationsdienste (IIS) hosten. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][HTTP-Transportsicherheit](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Welches Tool zum Konfigurieren eines Anschlusses verwendet wird, hängt vom Betriebssystem des Computers ab.  
  
 Verwenden Sie unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)] das HttpCfg.exe-Tool. Unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] ist dieses Tool bereits installiert. Mit [!INCLUDE[wxp](../../../../includes/wxp-md.md)], Sie können das Tool herunterladen [Windows XP Service Pack 2-Supporttools](http://go.microsoft.com/fwlink/?LinkId=88606). [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Httpcfg-Übersicht](http://go.microsoft.com/fwlink/?LinkId=88605). Die [Dokumentation der Windows-Supporttools](http://go.microsoft.com/fwlink/?LinkId=94840) erklärt die Syntax der Tools "Httpcfg.exe".  
  
 Verwenden Sie unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das bereits installierte Tool Netsh.exe.  
  
 In diesem Thema wird die Ausführung einer Reihe von Prozeduren beschrieben:  
  
-   Bestimmen der aktuellen Anschlusskonfiguration eines Computers  
  
-   Abrufen des Fingerabdrucks eines Zertifikats (notwendig für die beiden anschließenden Prozeduren)  
  
-   Binden eines SSL-Zertifikats an eine Anschlusskonfiguration  
  
-   Binden eines SSL-Zertifikats an eine Anschlusskonfiguration und Unterstützen von Clientzertifikaten  
  
-   Löschen eines SSL-Zertifikats aus einer Anschlussnummer  
  
 Zum Ändern der auf dem Computer gespeicherten Zertifikate sind Administratorrechte erforderlich.  
  
### <a name="to-determine-how-ports-are-configured"></a>So ermitteln Sie, wie Anschlüsse konfiguriert sind  
  
1.  In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)], verwenden Sie die Tools "HttpCfg.exe" zum Anzeigen der aktuellen Portkonfiguration mithilfe der **Abfrage** und **Ssl** gewechselt wird, wie im folgenden Beispiel gezeigt.  
  
    ```  
    httpcfg query ssl  
    ```  
  
2.  Verwenden Sie zum Anzeigen der aktuellen Anschlusskonfiguration unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das Netsh.exe-Tool, wie im folgenden Beispiel gezeigt:  
  
    ```  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a>So rufen Sie den Fingerabdruck eines Zertifikats ab  
  
1.  Verwenden Sie das Zertifikats-MMC-Snap-In, um nach einem X.509-Zertifikat zu suchen, das eine bestimmte Clientauthentifizierungsfunktion aufweist. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2.  Greifen Sie auf den Fingerabdruck des Zertifikats zu. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Wie: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3.  Kopieren Sie den Fingerabdruck des Zertifikats in einen Texteditor, beispielsweise den Windows-Editor.  
  
4.  Entfernen Sie alle Leerstellen zwischen den Hexadezimalzeichen. Eine Möglichkeit besteht darin, die Suchen/Ersetzen-Funktion des Editors zu nutzen, um jede Leerstelle durch ein NULL-Zeichen zu ersetzen.  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a>So binden Sie ein SSL-Zertifikat an eine Anschlussnummer  
  
1.  Verwenden Sie unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] das Tool-HttpCfg.exe im Secure Sockets Layer (SSL)-Speicher im Modus "Set", um das Zertifikat an eine Anschlussnummer zu binden. Das Tool verwendet den Fingerabdruck, um das Zertifikat zu identifizieren, wie im folgenden Beispiel gezeigt.  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   Die **-i** Switch verfügt über die Syntax der `IP`:`port` und weist das Tool, um das Zertifikat auf den Anschluss 8012 des Computers festzulegen. Optional können Sie die vier Nullen vor der Nummer auch durch die tatsächliche IP-Adresse des Computers ersetzen.  
  
    -   Die **-h** Switch gibt den Fingerabdruck des Zertifikats.  
  
2.  Verwenden Sie unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das Netsh.exe-Tool, wie im folgenden Beispiel gezeigt:  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   Die **"CertHash"** Parameter gibt den Fingerabdruck des Zertifikats.  
  
    -   Die **IP-Port lautet** Parameter gibt die IP-Adresse und den Port an, und wie funktioniert die **-i** -Schalter des Tools "Httpcfg.exe" beschrieben.  
  
    -   Die **Appid** Parameter ist eine GUID, die mit die besitzende Anwendung identifiziert werden kann.  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>So binden Sie ein SSL-Zertifikat an eine Anschlussnummer und unterstützen Clientzertifikate  
  
1.  Führen Sie zum Unterstützen von Clients, die die Authentifizierung mithilfe von X.509-Zertifikaten auf der Transportebene durchführen, unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)] die obige Prozedur aus, übergeben Sie jedoch einen zusätzlichen Befehlszeilenparameter an HttpCfg.exe, wie im folgenden Beispiel gezeigt:  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     Die **-f** Switch verfügt über die Syntax der `n` wobei n eine Zahl zwischen 1 und 7 ist. Bei dem Wert "2" (wie im vorherigen Beispiel gezeigt) sind Clientzertifikate auf der Transportebene aktiviert. Der Wert&#160;"3" aktiviert Clientzertifikate und ordnet die Zertifikate einem Windows-Konto zu. Das Verhalten bei anderen Werten finden Sie in der Hilfe zu HttpCfg.exe.  
  
2.  Führen Sie zum Unterstützen von Clients, die die Authentifizierung mithilfe von X.509-Zertifikaten auf der Transportebene durchführen, unter [!INCLUDE[wv](../../../../includes/wv-md.md)] die obige Prozedur aus, verwenden Sie jedoch einen zusätzlichen Parameter, wie im folgenden Beispiel gezeigt:  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a>So löschen Sie ein SSL-Zertifikat aus einer Anschlussnummer  
  
1.  Verwenden Sie das HttpCfg.exe- oder das Netsh.exe-Tool, um die Anschlüsse und Fingerabdrücke aller Bindungen auf dem Computer anzuzeigen. Verwenden Sie das Umleitungszeichen ">", um die Informationen auf den Datenträger auszugeben, wie im folgenden Beispiel gezeigt:  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2.  In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)], verwenden Sie die Tools "HttpCfg.exe" mit der **löschen** und **Ssl** Schlüsselwörter. Verwenden der **-i** Switch an, die `IP`:`port` Anzahl, und die **-h** Switch den Fingerabdruck angegeben.  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3.  Verwenden Sie unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das Netsh.exe-Tool, wie im folgenden Beispiel gezeigt:  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie einen selbst gehosteten Dienst erstellen, indem Sie die auf die Transportsicherheit festgelegte <xref:System.ServiceModel.WSHttpBinding>-Klasse verwenden. Geben Sie beim Erstellen einer Anwendung die Anschlussnummer in der Adresse an.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [HTTP-Transportsicherheit](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
