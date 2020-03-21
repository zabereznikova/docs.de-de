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
ms.openlocfilehash: 90d5424e12bb770dc3da85e1b2738206f4777c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185111"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat

Wenn Sie einen selbst gehosteten Windows Communication Foundation <xref:System.ServiceModel.WSHttpBinding> (WCF)-Dienst mit der Klasse erstellen, die Transportsicherheit verwendet, müssen Sie auch einen Port mit einem X.509-Zertifikat konfigurieren. Wenn Sie keinen selbst gehosteten Dienst erstellen, können Sie Ihren Dienst auch über Internetinformationsdienste (IIS) hosten. Weitere Informationen finden Sie unter [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Welches Tool zum Konfigurieren eines Anschlusses verwendet wird, hängt vom Betriebssystem des Computers ab.  
  
 Wenn Sie Windows Server 2003 ausführen, verwenden Sie das Tool HttpCfg.exe. Unter Windows Server 2003 wird dieses Tool installiert. Weitere Informationen finden Sie unter [Httpcfg-Übersicht](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)). In der Dokumentation zu [Windows Support Tools](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) wird die Syntax für das Tool Httpcfg.exe erläutert.  
  
 Wenn Sie Windows Vista ausführen, verwenden Sie das bereits installierte Tool Netsh.exe.
  
> [!NOTE]
> Das Ändern von auf dem Computer gespeicherten Zertifikaten erfordert Administratorrechte.  
  
## <a name="determine-how-ports-are-configured"></a>Bestimmen, wie Ports konfiguriert werden  
  
1. Verwenden Sie in Windows Server 2003 oder Windows XP das Tool HttpCfg.exe, um die aktuelle Portkonfiguration mithilfe der **Abfrage-** und **ssl-Switches** anzuzeigen, wie im folgenden Beispiel gezeigt.  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. Verwenden Sie in Windows Vista das Tool Netsh.exe, um die aktuelle Portkonfiguration anzuzeigen, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a>Abrufen des Fingerabdrucks eines Zertifikats  
  
1. Verwenden Sie das Zertifikats-MMC-Snap-In, um nach einem X.509-Zertifikat zu suchen, das eine bestimmte Clientauthentifizierungsfunktion aufweist. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2. Greifen Sie auf den Fingerabdruck des Zertifikats zu. Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3. Kopieren Sie den Fingerabdruck des Zertifikats in einen Texteditor, beispielsweise den Windows-Editor.  
  
4. Entfernen Sie alle Leerstellen zwischen den Hexadezimalzeichen. Eine Möglichkeit besteht darin, die Suchen/Ersetzen-Funktion des Editors zu nutzen, um jede Leerstelle durch ein NULL-Zeichen zu ersetzen.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a>Binden eines SSL-Zertifikats an eine Portnummer  
  
1. Verwenden Sie in Windows Server 2003 oder Windows XP das Tool HttpCfg.exe im Modus "Set" im SSL-Speicher (Secure Sockets Layer), um das Zertifikat an eine Portnummer zu binden. Das Tool verwendet den Fingerabdruck, um das Zertifikat zu identifizieren, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - Der **Schalter -i** hat `IP``port` die Syntax von : und weist das Tool an, das Zertifikat auf Port 8012 des Computers festzulegen. Optional können Sie die vier Nullen vor der Nummer auch durch die tatsächliche IP-Adresse des Computers ersetzen.  
  
    - Der Schalter **-h** gibt den Fingerabdruck des Zertifikats an.  
  
2. Verwenden Sie in Windows Vista das Tool Netsh.exe, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - Der **parameter certhash** gibt den Fingerabdruck des Zertifikats an.  
  
    - Der **ipport-Parameter** gibt die IP-Adresse und den Port an und funktioniert genau wie der beschriebene **-i-Switch** des Tools Httpcfg.exe.  
  
    - Der **parameter appid** ist eine GUID, die verwendet werden kann, um die besitzende Anwendung zu identifizieren.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>Binden eines SSL-Zertifikats an eine Portnummer und Unterstützung von Clientzertifikaten  
  
1. Führen Sie in Windows Server 2003 oder Windows XP Clients, die sich mit X.509-Zertifikaten auf der Transportebene authentifizieren, nach dem vorherigen Verfahren aus, übergeben Sie jedoch einen zusätzlichen Befehlszeilenparameter an HttpCfg.exe, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     Der **Schalter -f** hat `n` die Syntax, wobei n eine Zahl zwischen 1 und 7 ist.  Bei dem Wert "2" (wie im vorherigen Beispiel gezeigt) sind Clientzertifikate auf der Transportebene aktiviert. Der Wert&#160;"3" aktiviert Clientzertifikate und ordnet die Zertifikate einem Windows-Konto zu. Das Verhalten bei anderen Werten finden Sie in der Hilfe zu HttpCfg.exe.  
  
2. Führen Sie in Windows Vista, um Clients zu unterstützen, die sich mit X.509-Zertifikaten auf der Transportebene authentifizieren, dem vorherigen Verfahren, jedoch mit einem zusätzlichen Parameter, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a>Löschen eines SSL-Zertifikats aus einer Portnummer  
  
1. Verwenden Sie das HttpCfg.exe- oder das Netsh.exe-Tool, um die Anschlüsse und Fingerabdrücke aller Bindungen auf dem Computer anzuzeigen. Um die Informationen auf den Datenträger zu drucken, verwenden Sie das Umleitungszeichen ">", wie im folgenden Beispiel gezeigt.  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. Verwenden Sie in Windows Server 2003 oder Windows XP das Tool HttpCfg.exe mit den Schlüsselwörtern **delete** und **ssl.** Verwenden Sie den Schalter **-i,** um die `IP`:-Zahl`port` anzugeben, und den Schalter **-h,** um den Fingerabdruck anzugeben.  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. Verwenden Sie in Windows Vista das Tool Netsh.exe, wie im folgenden Beispiel gezeigt.  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>Beispiel  

 Der folgende Code zeigt, wie Sie einen selbst gehosteten Dienst erstellen, indem Sie die auf die Transportsicherheit festgelegte <xref:System.ServiceModel.WSHttpBinding>-Klasse verwenden. Geben Sie beim Erstellen einer Anwendung die Anschlussnummer in der Adresse an.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [HTTP-Transportsicherheit](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
