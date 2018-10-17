---
title: 'Vorgehensweise: Zugänglichmachen von X.509-Zertifikaten für WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: 0917569b556c31413b715d75c83a96f3a4b015d7
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371952"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a>Vorgehensweise: Zugänglichmachen von X.509-Zertifikaten für WCF
Damit ein x. 509-Zertifikat für Windows Communication Foundation (WCF) zugreifen können, muss die Anwendungscode der Name des Zertifikatspeichers und Speicherort angeben. In bestimmten Fällen benötigt die Prozessidentität Zugriff auf die Datei, die den zugeordneten privaten Schlüssel für das X.509-Zertifikat enthält. Zum Abrufen des privaten Schlüssels mit einem x. 509-Zertifikat im Zertifikatspeicher verknüpft ist, muss WCF dazu berechtigt. Standardmäßig können nur der Besitzer und das Systemkonto auf den privaten Schlüssel eines Zertifikats zugreifen.  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a>So machen Sie X.509-Zertifikate für WCF zugänglich  
  
1.  Geben Sie das Konto, unter der WCF Lesezugriff auf die Datei ausgeführt wird, die die dem x. 509-Zertifikat zugeordneten privaten Schlüssel enthält.  
  
    1.  Bestimmen Sie, ob WCF Lesezugriff auf den privaten Schlüssel für das x. 509-Zertifikat erfordert.  
  
         Die folgende Tabelle beschreibt, ob ein privater Schlüssel bei der Verwendung eines X.509-Zertifikats verfügbar sein muss.  
  
        |Verwendung des X.509-Zertifikats|Privater Schlüssel|  
        |---------------------------|-----------------|  
        |Digitales Signieren einer ausgehenden SOAP-Nachricht.|Ja|  
        |Überprüfen der Signatur einer eingehenden SOAP-Nachricht.|Nein|  
        |Verschlüsseln einer ausgehenden SOAP-Nachricht.|Nein|  
        |Verschlüsseln einer eingehenden SOAP-Nachricht.|Ja|  
  
    2.  Ermitteln Sie den Ort und Namen des Zertifikatspeicherspeichers, in dem sich das Zertifikat befindet.  
  
         Der Zertifikatspeicher, in dem das Zertifikat gespeichert ist, wird entweder im Anwendungscode oder in einer Konfiguration angegeben. Im folgenden Beispiel wird angegeben, dass sich das Zertifikat im `CurrentUser`-Zertifikatsspeicher mit dem Namen `My` befindet.  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3.  Bestimmen, in dem der private Schlüssel für das Zertifikat auf dem Computer gefunden wurde die [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) Tool.  
  
         Die [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) Tool erfordert, den Namen des Zertifikatspeichers, den zertifikatspeicherort und etwas, das das Zertifikat eindeutig identifiziert. Als eindeutiger Bezeichner werden der Antragstellername oder der Fingerabdruck des Zertifikats von dem Tool akzeptiert. Weitere Informationen zum Ermitteln des Fingerabdrucks eines Zertifikats finden Sie unter [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
         Im folgenden Codebeispiel wird die [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) Tool, um zu bestimmen, den Speicherort des privaten Schlüssels eines Zertifikats in die `My` speichern in `CurrentUser` mit einem Fingerabdruck `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  Bestimmen Sie das Konto, dem WCF unter ausgeführt wird.  
  
         In der folgende Tabelle werden die Konten beschrieben unter der WCF für ein bestimmtes Szenario ausgeführt wird.  
  
        |Szenario|Prozessidentität|  
        |--------------|----------------------|  
        |Client (Konsole oder WinForms-Anwendung)|Aktuell angemeldeter Benutzer|  
        |Selbst gehosteter Dienst|Aktuell angemeldeter Benutzer|  
        |Dienst, der in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) oder IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]) gehostet wird.|NETZWERKDIENST|  
        |Dienst, der in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]) gehostet wird.|Wird durch das `<processModel>`-Element in der Datei Machine.config gesteuert. ASPNET ist das Standardkonto.|  
  
    5.  Gewähren von Lesezugriff auf die Datei, die den privaten Schlüssel für das Konto, die WCF enthält unter ausgeführt wird, mithilfe eines Tools wie icacls.exe.  
  
         Im folgenden Codebeispiel wird bearbeitet die besitzerverwaltete Zugriffssteuerungsliste (DACL) für die angegebene Datei das Lesen der NETZWERKDIENST-Konto zu gewähren (: R) Zugriff auf die Datei.  
  
        ```  
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a>Siehe auch  
- [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)  
- [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)  
- [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
