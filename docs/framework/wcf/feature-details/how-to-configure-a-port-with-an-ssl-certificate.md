---
title: 'Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 30b24c4ff06cc7249d3ddb6d95549a574e313f52
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579617"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat

Beim Erstellen eines selbst gehosteten Windows Communication Foundation (WCF)-Diensts mit der- <xref:System.ServiceModel.WSHttpBinding> Klasse, die Transportsicherheit verwendet, müssen Sie auch einen Port mit einem X. 509-Zertifikat konfigurieren. Wenn Sie keinen selbst gehosteten Dienst erstellen, können Sie Ihren Dienst auch über Internetinformationsdienste (IIS) hosten. Weitere Informationen finden Sie unter [http-Transport Sicherheit](http-transport-security.md).  
  
 Welches Tool zum Konfigurieren eines Anschlusses verwendet wird, hängt vom Betriebssystem des Computers ab.  
  
 Wenn Sie Windows Server 2003 ausführen, verwenden Sie das Tool "Httpcfg. exe". Unter Windows Server 2003 ist dieses Tool installiert. Weitere Informationen finden Sie unter [Httpcfg Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)). In der [Dokumentation zur Windows-Support Tools](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) wird die Syntax für das Tool "Httpcfg. exe" erläutert.  
  
 Wenn Sie Windows Vista ausführen, verwenden Sie das Tool "Netsh. exe", das bereits installiert ist.
  
> [!NOTE]
> Zum Ändern der auf dem Computer gespeicherten Zertifikate sind Administratorrechte erforderlich.  
  
## <a name="determine-how-ports-are-configured"></a>Bestimmen, wie Ports konfiguriert werden  
  
1. Verwenden Sie unter Windows Server 2003 oder Windows XP das Tool Httpcfg. exe, um die aktuelle Port Konfiguration mithilfe der **Abfrage** -und **SSL** -Switches anzuzeigen, wie im folgenden Beispiel gezeigt.  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. Verwenden Sie in Windows Vista das Tool Netsh. exe, um die aktuelle Port Konfiguration anzuzeigen, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a>Fingerabdruck eines Zertifikats erhalten  
  
1. Verwenden Sie das Zertifikats-MMC-Snap-In, um nach einem X.509-Zertifikat zu suchen, das eine bestimmte Clientauthentifizierungsfunktion aufweist. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In](how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2. Greifen Sie auf den Fingerabdruck des Zertifikats zu. Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3. Kopieren Sie den Fingerabdruck des Zertifikats in einen Texteditor, beispielsweise den Windows-Editor.  
  
4. Entfernen Sie alle Leerstellen zwischen den Hexadezimalzeichen. Eine Möglichkeit besteht darin, die Suchen/Ersetzen-Funktion des Editors zu nutzen, um jede Leerstelle durch ein NULL-Zeichen zu ersetzen.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a>Binden eines SSL-Zertifikats an eine Portnummer  
  
1. Verwenden Sie in Windows Server 2003 oder Windows XP das Tool "Httpcfg. exe" im Modus "Set" im Secure Sockets Layer-Speicher (SSL), um das Zertifikat an eine Portnummer zu binden. Das Tool verwendet den Fingerabdruck, um das Zertifikat zu identifizieren, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - Der Schalter **-i** hat die Syntax von `IP` : `port` und weist das Tool an, das Zertifikat auf Port 8012 des Computers festzulegen. Optional können Sie die vier Nullen vor der Nummer auch durch die tatsächliche IP-Adresse des Computers ersetzen.  
  
    - Der Schalter **-h** gibt den Fingerabdruck des Zertifikats an.  
  
2. Verwenden Sie in Windows Vista das Tool Netsh. exe, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - Der **CertHash** -Parameter gibt den Fingerabdruck des Zertifikats an.  
  
    - Der **IPPort** -Parameter gibt die IP-Adresse und den Port sowie die Funktionen an, die genau wie der **-i-** Schalter des Tools "Httpcfg. exe" beschrieben werden.  
  
    - Der **AppID** -Parameter ist eine GUID, die zum Identifizieren der besitzenden Anwendung verwendet werden kann.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>Binden eines SSL-Zertifikats an eine Portnummer und unterstützen von Client Zertifikaten  
  
1. Wenn Sie in Windows Server 2003 oder Windows XP Clients verwenden möchten, die sich bei X. 509-Zertifikaten auf der Transportschicht authentifizieren, führen Sie das vorangehende Verfahren aus, übergeben Sie jedoch einen zusätzlichen Befehlszeilenparameter an HttpCfg. exe, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     Der Schalter **-f** hat die Syntax, `n` wobei n eine Zahl zwischen 1 und 7 ist.  Bei dem Wert "2" (wie im vorherigen Beispiel gezeigt) sind Clientzertifikate auf der Transportebene aktiviert. Der Wert&#160;"3" aktiviert Clientzertifikate und ordnet die Zertifikate einem Windows-Konto zu. Das Verhalten bei anderen Werten finden Sie in der Hilfe zu HttpCfg.exe.  
  
2. Zur Unterstützung von Clients, die sich bei X. 509-Zertifikaten auf der Transport Ebene authentifizieren, führen Sie in Windows Vista das vorherige Verfahren aus, aber mit einem zusätzlichen Parameter, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a>Löschen eines SSL-Zertifikats aus einer Portnummer  
  
1. Verwenden Sie das HttpCfg.exe- oder das Netsh.exe-Tool, um die Anschlüsse und Fingerabdrücke aller Bindungen auf dem Computer anzuzeigen. Um die Informationen auf dem Datenträger zu drucken, verwenden Sie das Umleitungs Zeichen ">", wie im folgenden Beispiel gezeigt.  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. Verwenden Sie in Windows Server 2003 oder Windows XP das Tool "Httpcfg. exe" mit den Schlüsselwörtern " **Delete** " und " **SSL** ". Verwenden Sie den Schalter **-i** , um den Wert " `IP` : Number" anzugeben `port` , und den Schalter **-h** , um den Fingerabdruck anzugeben.  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. Verwenden Sie in Windows Vista das Tool Netsh. exe, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>Beispiel  

 Der folgende Code zeigt, wie Sie einen selbst gehosteten Dienst erstellen, indem Sie die auf die Transportsicherheit festgelegte <xref:System.ServiceModel.WSHttpBinding>-Klasse verwenden. Geben Sie beim Erstellen einer Anwendung die Anschlussnummer in der Adresse an.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [HTTP-Transportsicherheit](http-transport-security.md)
